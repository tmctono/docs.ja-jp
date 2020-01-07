---
title: メッセージ相関
ms.date: 03/30/2017
ms.assetid: 3f62babd-c991-421f-bcd8-391655c82a1f
ms.openlocfilehash: adabf02cb8ec232a887bd4720ea9552a7d870fe3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348332"
---
# <a name="message-correlation"></a><span data-ttu-id="709e3-102">メッセージ相関</span><span class="sxs-lookup"><span data-stu-id="709e3-102">Message Correlation</span></span>

<span data-ttu-id="709e3-103">このサンプルでは、メッセージキュー (MSMQ) アプリケーションが MSMQ メッセージを Windows Communication Foundation (WCF) サービスに送信する方法と、要求/応答シナリオでメッセージを送信側と受信側のアプリケーション間で相互に関連付ける方法を示します。</span><span class="sxs-lookup"><span data-stu-id="709e3-103">This sample demonstrates how a Message Queuing (MSMQ) application can send an MSMQ message to a Windows Communication Foundation (WCF) service and how messages can be correlated between sender and receiver applications in a request/response scenario.</span></span> <span data-ttu-id="709e3-104">このサンプルでは、msmqIntegrationBinding バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="709e3-104">This sample uses the msmqIntegrationBinding binding.</span></span> <span data-ttu-id="709e3-105">この場合、サービスは自己ホスト型コンソール アプリケーションで、サービスがキュー内のメッセージを受信したかどうかを監視できます。</span><span class="sxs-lookup"><span data-stu-id="709e3-105">The service in this case is a self-hosted console application to allow you to observe the service that receives queued messages.</span></span> <span data-ttu-id="709e3-106">k</span><span class="sxs-lookup"><span data-stu-id="709e3-106">k</span></span>

 <span data-ttu-id="709e3-107">サービスは、送信側からの受信メッセージを処理し、送信側に応答メッセージを返信します。</span><span class="sxs-lookup"><span data-stu-id="709e3-107">The service processes the message received from the sender and sends a response message back to the sender.</span></span> <span data-ttu-id="709e3-108">送信側は、受信した応答を、最初に送信した要求に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="709e3-108">The sender correlates the response it received to the request it sent originally.</span></span> <span data-ttu-id="709e3-109">メッセージの `MessageID` プロパティと `CorrelationID` プロパティを使用すると、要求メッセージと応答メッセージが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="709e3-109">The `MessageID` and `CorrelationID` properties of the message are used to correlate the request and response messages.</span></span>

 <span data-ttu-id="709e3-110">`IOrderProcessor` サービス コントラクトは、キューでの使用に適した一方向サービス操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="709e3-110">The `IOrderProcessor` service contract defines a one-way service operation that is suitable for use with queuing.</span></span> <span data-ttu-id="709e3-111">MSMQ メッセージには Action ヘッダーがないので、さまざまな MSMQ メッセージを操作コントラクトに自動的にマッピングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="709e3-111">An MSMQ message does not have an Action header, so it is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="709e3-112">したがってこの場合、存在する操作コントラクトは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="709e3-112">Therefore, there can be only one operation contract in this case.</span></span> <span data-ttu-id="709e3-113">サービス内に複数の操作コントラクトを定義する場合は、ディスパッチする操作コントラクトを決定するために使用できる、MSMQ メッセージ内のヘッダー (ラベルや correlationID など) に関する情報をアプリケーションで提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="709e3-113">If you want to define more operation contracts in the service, the application must provide information as to which header in the MSMQ message (for example, the label, or correlationID) can be used to decide which operation contract to dispatch.</span></span>

 <span data-ttu-id="709e3-114">さらに、MSMQ メッセージには、操作コントラクトの別のパラメータにマッピングされるヘッダーに関する情報は含まれません。</span><span class="sxs-lookup"><span data-stu-id="709e3-114">The MSMQ message also does not contain information as to which headers are mapped to the different parameters of the operation contract.</span></span> <span data-ttu-id="709e3-115">したがって、操作コントラクトに存在するパラメータは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="709e3-115">Therefore, there can be only one parameter in the operation contract.</span></span> <span data-ttu-id="709e3-116">パラメーターの型は <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>で、基になる MSMQ メッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="709e3-116">The parameter is of type <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, which contains the underlying MSMQ message.</span></span> <span data-ttu-id="709e3-117">`MsmqMessage<T>` クラスの型 "T" は、シリアル化されて MSMQ メッセージ本文に含まれているデータを表します。</span><span class="sxs-lookup"><span data-stu-id="709e3-117">The type "T" in the `MsmqMessage<T>` class represents the data that is serialized into the MSMQ message body.</span></span> <span data-ttu-id="709e3-118">このサンプルでは、`PurchaseOrder` 型がシリアル化されて MSMQ メッセージ本文になっています。</span><span class="sxs-lookup"><span data-stu-id="709e3-118">In this sample, the `PurchaseOrder` type is serialized into the MSMQ message body.</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 <span data-ttu-id="709e3-119">このサービス操作は発注書を処理し、サービス コンソール ウィンドウにその発注書の内容と状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="709e3-119">The service operation processes the purchase order and displays the contents of the purchase order and its status in the service console window.</span></span> <span data-ttu-id="709e3-120"><xref:System.ServiceModel.OperationBehaviorAttribute> はこの操作を構成してキューを伴うトランザクションに登録し、操作が返されたときにトランザクションに完了とマークします。</span><span class="sxs-lookup"><span data-stu-id="709e3-120">The <xref:System.ServiceModel.OperationBehaviorAttribute> configures the operation to enlist in a transaction with the queue and to mark the transaction complete when the operation returns.</span></span> <span data-ttu-id="709e3-121">`PurchaseOrder` には、サービスで処理する必要のある発注の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="709e3-121">The `PurchaseOrder` contains the order details that must be processed by the service.</span></span>

```csharp
// Service class that implements the service contract.
public class OrderProcessorService : IOrderProcessor
{
   [OperationBehavior(TransactionScopeRequired = true,
          TransactionAutoComplete = true)]
   public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> ordermsg)
   {
       PurchaseOrder po = (PurchaseOrder)ordermsg.Body;
       Random statusIndexer = new Random();
       po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];
       Console.WriteLine("Processing {0} ", po);
       //Send a response to the client that the order has been received
         and is pending fullfillment.
       SendResponse(ordermsg);
    }

    private void SendResponse(MsmqMessage<PurchaseOrder> ordermsg)
    {
        OrderResponseClient client = new OrderResponseClient("OrderResponseEndpoint");

        //Set the correlation ID such that the client can correlate the response to the order.
        MsmqMessage<PurchaseOrder> orderResponsemsg = new MsmqMessage<PurchaseOrder>(ordermsg.Body);
        orderResponsemsg.CorrelationId = ordermsg.Id;
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.SendOrderResponse(orderResponsemsg);
            scope.Complete();
        }

        client.Close();
    }
}
```

 <span data-ttu-id="709e3-122">サービスは、MSMQ メッセージをキューに送信するためにカスタム クライアント `OrderResponseClient` を使用します。</span><span class="sxs-lookup"><span data-stu-id="709e3-122">The service uses a custom client `OrderResponseClient` to send the MSMQ message to the queue.</span></span> <span data-ttu-id="709e3-123">メッセージを受信して処理するアプリケーションは MSMQ アプリケーションであり、WCF アプリケーションではないため、2つのアプリケーション間に暗黙のサービスコントラクトはありません。</span><span class="sxs-lookup"><span data-stu-id="709e3-123">Because the application that receives and processes the message is an MSMQ application and not a WCF application, there is no implicit service contract between the two applications.</span></span> <span data-ttu-id="709e3-124">したがって、このシナリオでは Svcutil.exe ツールを使用してプロキシを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="709e3-124">So we cannot create a proxy using the Svcutil.exe tool in this scenario.</span></span>

 <span data-ttu-id="709e3-125">カスタムプロキシは、`msmqIntegrationBinding` バインディングを使用してメッセージを送信するすべての WCF アプリケーションで基本的に同じです。</span><span class="sxs-lookup"><span data-stu-id="709e3-125">The custom proxy is essentially the same for all WCF applications that use the `msmqIntegrationBinding` binding to send messages.</span></span> <span data-ttu-id="709e3-126">他のプロキシと異なり、サービス操作の範囲は含まれません。</span><span class="sxs-lookup"><span data-stu-id="709e3-126">Unlike other proxies, it does not include a range of service operations.</span></span> <span data-ttu-id="709e3-127">メッセージ送信操作のみです。</span><span class="sxs-lookup"><span data-stu-id="709e3-127">It is a submit message operation only.</span></span>

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IOrderResponse
{

    [System.ServiceModel.OperationContractAttribute(IsOneWay = true, Action = "*")]
    void SendOrderResponse(MsmqMessage<PurchaseOrder> msg);
}

public partial class OrderResponseClient : System.ServiceModel.ClientBase<IOrderResponse>, IOrderResponse
{

    public OrderResponseClient()
    { }

    public OrderResponseClient(string configurationName)
        : base(configurationName)
    { }

    public OrderResponseClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)
        : base(binding, address)
    { }

    public void SendOrderResponse(MsmqMessage<PurchaseOrder> msg)
    {
        base.Channel.SendOrderResponse(msg);
    }
}
```

 <span data-ttu-id="709e3-128">サービスは自己ホスト型です。</span><span class="sxs-lookup"><span data-stu-id="709e3-128">The service is self hosted.</span></span> <span data-ttu-id="709e3-129">MSMQ 統合トランスポートを使用する場合、使用するキューをあらかじめ作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="709e3-129">When using the MSMQ integration transport, the queue used must be created in advance.</span></span> <span data-ttu-id="709e3-130">手動で作成することもコードで作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="709e3-130">This can be done manually or through code.</span></span> <span data-ttu-id="709e3-131">このサンプルでは、キューの存在を確認して、必要な場合は作成するための <xref:System.Messaging> コードがサービスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="709e3-131">In this sample, the service contains <xref:System.Messaging> code to check for the existence of the queue and create it if necessary.</span></span> <span data-ttu-id="709e3-132">キュー名は構成ファイルから読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="709e3-132">The queue name is read from the configuration file.</span></span>

```csharp
public static void Main()
{
       // Get the MSMQ queue name from application settings in configuration.
      string queueName =
                ConfigurationManager.AppSettings["orderQueueName"];
      // Create the transacted MSMQ queue if necessary.
      if (!MessageQueue.Exists(queueName))
                MessageQueue.Create(queueName, true);
     // Create a ServiceHost for the OrderProcessorService type.
     using (ServiceHost serviceHost = new
                   ServiceHost(typeof(OrderProcessorService)))
     {
            serviceHost.Open();
            // The service can now be accessed.
            Console.WriteLine("The service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.ReadLine();
            // Close the ServiceHost to shutdown the service.
            serviceHost.Close();
      }
}
```

 <span data-ttu-id="709e3-133">発注要求が送信される MSMQ キューは、構成ファイルの appSettings セクションで指定されます。</span><span class="sxs-lookup"><span data-stu-id="709e3-133">The MSMQ queue to which the order requests are sent is specified in the appSettings section of the configuration file.</span></span> <span data-ttu-id="709e3-134">クライアントおよびサービスのエンドポイントは、構成ファイルの system.serviceModel セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="709e3-134">The client and service endpoints are defined in the system.serviceModel section of the configuration file.</span></span> <span data-ttu-id="709e3-135">どちらも `msmqIntegrationbinding` バインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="709e3-135">Both specify the `msmqIntegrationbinding` binding.</span></span>

```xml
<appSettings>
  <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>

<system.serviceModel>
  <client>
    <endpoint    name="OrderResponseEndpoint"
              address="msmq.formatname:DIRECT=OS:.\private$\OrderResponse"
              binding="msmqIntegrationBinding"
              bindingConfiguration="OrderProcessorBinding"
              contract="Microsoft.ServiceModel.Samples.IOrderResponse">
    </endpoint>
  </client>

  <services>
    <service
      name="Microsoft.ServiceModel.Samples.OrderProcessorService">
      <endpoint address="msmq.formatname:DIRECT=OS:.\private$\Orders"
                            binding="msmqIntegrationBinding"
                bindingConfiguration="OrderProcessorBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor">
      </endpoint>
    </service>
  </services>

  <bindings>
    <msmqIntegrationBinding>
      <binding name="OrderProcessorBinding" >
        <security mode="None" />
      </binding>
    </msmqIntegrationBinding>
  </bindings>

</system.serviceModel>
```

 <span data-ttu-id="709e3-136">クライアント アプリケーションは <xref:System.Messaging> を使用して、非揮発性メッセージとトランザクション メッセージをキューに送信します。</span><span class="sxs-lookup"><span data-stu-id="709e3-136">The client application uses <xref:System.Messaging> to send a durable and transactional message to the queue.</span></span> <span data-ttu-id="709e3-137">メッセージの本文には発注書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="709e3-137">The message's body contains the purchase order.</span></span>

```csharp
static void PlaceOrder()
{
    //Connect to the queue
    MessageQueue orderQueue =
            new MessageQueue(
                    ConfigurationManager.AppSettings["orderQueueName"])
    // Create the purchase order.
    PurchaseOrder po = new PurchaseOrder();
    po.CustomerId = "somecustomer.com";
    po.PONumber = Guid.NewGuid().ToString();
    PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
    lineItem1.ProductId = "Blue Widget";
    lineItem1.Quantity = 54;
    lineItem1.UnitCost = 29.99F;

    PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
    lineItem2.ProductId = "Red Widget";
    lineItem2.Quantity = 890;
    lineItem2.UnitCost = 45.89F;

    po.orderLineItems = new PurchaseOrderLineItem[2];
    po.orderLineItems[0] = lineItem1;
    po.orderLineItems[1] = lineItem2;

    Message msg = new Message();
    msg.UseDeadLetterQueue = true;
    msg.Body = po;

    //Create a transaction scope.
    using (TransactionScope scope = new
     TransactionScope(TransactionScopeOption.Required))
    {
        // Submit the purchase order.
        orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
        // Complete the transaction.
        scope.Complete();
    }
    //Save the messageID for order response correlation.
    orderMessageID = msg.Id;
    Console.WriteLine("Placed the order, waiting for response...");
}
```

 <span data-ttu-id="709e3-138">発注の応答を受信する MSMQ キューは、構成ファイルの appSettings セクションで指定されます。次のサンプル構成を参照してください。</span><span class="sxs-lookup"><span data-stu-id="709e3-138">The MSMQ queue from which the order responses are received is specified in an appSettings section of the configuration file, as shown in the following sample configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="709e3-139">キュー名では、ドット (.) を使用してローカル コンピューターを表し、バックスラッシュを使用してパスを区切ります。</span><span class="sxs-lookup"><span data-stu-id="709e3-139">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="709e3-140">WCF エンドポイントアドレスでは、formatname スキーマを指定し、ローカルコンピューターに "localhost" を使用します。</span><span class="sxs-lookup"><span data-stu-id="709e3-140">The WCF endpoint address specifies a msmq.formatname scheme, and uses "localhost" for the local computer.</span></span> <span data-ttu-id="709e3-141">URI の msmq.formatname の後には、MSMQ ガイドラインに沿って正しく書式設定された形式名が続きます。</span><span class="sxs-lookup"><span data-stu-id="709e3-141">A properly formed format name follows msmq.formatname in the URI according to MSMQ guidelines.</span></span>

```xml
<appSettings>
    <add key=" orderResponseQueueName" value=".\private$\Orders" />
</appSettings>
```

 <span data-ttu-id="709e3-142">クライアント アプリケーションは、サービスに送信する発注要求メッセージの `messageID` を保存し、サービスからの応答を待機します。</span><span class="sxs-lookup"><span data-stu-id="709e3-142">The client application saves the `messageID` of the order request message that it sends to the service and waits for a response from the service.</span></span> <span data-ttu-id="709e3-143">応答がキューに到着すると、クライアントは発注メッセージの `correlationID` プロパティを使用して、送信した発注メッセージと応答を関連付けます。このプロパティには、クライアントが最初にサービスに送信した発注メッセージの `messageID` が含まれています。</span><span class="sxs-lookup"><span data-stu-id="709e3-143">Once a response arrives in the queue the client correlates it with the order message it sent using the `correlationID` property of the message, which contains the `messageID` of the order message that the client sent to the service originally.</span></span>

```csharp
static void DisplayOrderStatus()
{
    MessageQueue orderResponseQueue = new
     MessageQueue(ConfigurationManager.AppSettings
                  ["orderResponseQueueName"]);
    //Create a transaction scope.
    bool responseReceived = false;
    orderResponseQueue.MessageReadPropertyFilter.CorrelationId = true;
    while (!responseReceived)
    {
       Message responseMsg;
       using (TransactionScope scope2 = new
         TransactionScope(TransactionScopeOption.Required))
       {
          //Receive the Order Response message.
          responseMsg =
              orderResponseQueue.Receive
                   (MessageQueueTransactionType.Automatic);
          scope2.Complete();
     }
     responseMsg.Formatter = new
     System.Messaging.XmlMessageFormatter(new Type[] {
         typeof(PurchaseOrder) });
     PurchaseOrder responsepo = (PurchaseOrder)responseMsg.Body;
    //Check if the response is for the order placed.
    if (orderMessageID == responseMsg.CorrelationId)
    {
       responseReceived = true;
       Console.WriteLine("Status of current Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
    else
    {
       Console.WriteLine("Status of previous Order: OrderID-{0},Order
            Status-{1}", responsepo.PONumber, responsepo.Status);
    }
  }
}
```

 <span data-ttu-id="709e3-144">サンプルを実行すると、クライアントとサービスのアクティビティがサービスとクライアントの両方のコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="709e3-144">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="709e3-145">サービスがクライアントからメッセージを受信し、クライアントに応答を返信するアクティビティを参照できます。</span><span class="sxs-lookup"><span data-stu-id="709e3-145">You can see the service receive messages from the client and sends a response back to the client.</span></span> <span data-ttu-id="709e3-146">クライアントでは、サービスから受信した応答が表示されます。</span><span class="sxs-lookup"><span data-stu-id="709e3-146">The client displays the response received from the service.</span></span> <span data-ttu-id="709e3-147">どちらかのコンソールで Enter キーを押すと、サービスとクライアントがどちらもシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="709e3-147">Press ENTER in each console window to shut down the service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="709e3-148">このサンプルを実行するには、メッセージ キュー (MSMQ) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="709e3-148">This sample requires the installation of Message Queuing (MSMQ).</span></span> <span data-ttu-id="709e3-149">インストールの手順については、「参照」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="709e3-149">See the MSMQ installation instructions in the See Also section.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="709e3-150">サンプルをセットアップ、ビルド、および実行する</span><span class="sxs-lookup"><span data-stu-id="709e3-150">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="709e3-151">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="709e3-151">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="709e3-152">サービスを最初に実行すると、サービスはキューが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="709e3-152">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="709e3-153">キューが存在しない場合、サービスによってキューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="709e3-153">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="709e3-154">最初にサービスを実行してキューを作成することも、MSMQ キュー マネージャーでキューを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="709e3-154">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="709e3-155">Windows 2008 でキューを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="709e3-155">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="709e3-156">Visual Studio 2012 でサーバーマネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="709e3-156">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="709e3-157">**[機能]** タブを展開します。</span><span class="sxs-lookup"><span data-stu-id="709e3-157">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="709e3-158">**[プライベートメッセージキュー]** を右クリックし、 **[新規]** 、 **[プライベートキュー]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="709e3-158">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="709e3-159">**[トランザクション]** ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="709e3-159">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="709e3-160">新しいキューの名前として `ServiceModelSamplesTransacted` を入力します。</span><span class="sxs-lookup"><span data-stu-id="709e3-160">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="709e3-161">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="709e3-161">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="709e3-162">1台のコンピューター構成でサンプルを実行するには、「 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="709e3-162">To run the sample in a single-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

## <a name="run-the-sample-across-computers"></a><span data-ttu-id="709e3-163">コンピューター間でサンプルを実行する</span><span class="sxs-lookup"><span data-stu-id="709e3-163">Run the sample across computers</span></span>

1. <span data-ttu-id="709e3-164">サービスのプログラム ファイルを、言語固有のフォルダーにある \service\bin\ フォルダーからサービス コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="709e3-164">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>

2. <span data-ttu-id="709e3-165">クライアント プログラム ファイルを、言語固有のフォルダーにある \client\bin\ フォルダーからクライアント コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="709e3-165">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>

3. <span data-ttu-id="709e3-166">Client.exe.config ファイルを開き、orderQueueName を変更して "." の代わりにサービス コンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="709e3-166">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>

4. <span data-ttu-id="709e3-167">Service.exe.config ファイルで、クライアント エンドポイントのアドレスを変更して "." の代わりにクライアント コンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="709e3-167">In the Service.exe.config file, change the client endpoint address to specify the client computer name instead of ".".</span></span>

5. <span data-ttu-id="709e3-168">サービス コンピューターで、コマンド プロンプトから Service.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="709e3-168">On the service computer, launch Service.exe from a command prompt.</span></span>

6. <span data-ttu-id="709e3-169">クライアント コンピューターで、コマンド プロンプトから Client.exe を起動します。</span><span class="sxs-lookup"><span data-stu-id="709e3-169">On the client computer, launch Client.exe from a command prompt.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="709e3-170">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="709e3-170">The samples may already be installed on your computer.</span></span> <span data-ttu-id="709e3-171">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="709e3-171">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="709e3-172">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459)にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) と [!INCLUDE[wf1](../../../../includes/wf1-md.md)] サンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="709e3-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="709e3-173">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="709e3-173">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MessageCorrelation`

## <a name="see-also"></a><span data-ttu-id="709e3-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="709e3-174">See also</span></span>

- [<span data-ttu-id="709e3-175">WCF でのキュー</span><span class="sxs-lookup"><span data-stu-id="709e3-175">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [<span data-ttu-id="709e3-176">メッセージキュー</span><span class="sxs-lookup"><span data-stu-id="709e3-176">Message Queuing</span></span>](https://go.microsoft.com/fwlink/?LinkId=94968)
