---
title: カスタム メッセージ フィルター
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 34e6d851bd0aa3515c5c43521be6213451b7ed12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003068"
---
# <a name="custom-message-filter"></a><span data-ttu-id="994d2-102">カスタム メッセージ フィルター</span><span class="sxs-lookup"><span data-stu-id="994d2-102">Custom Message Filter</span></span>
<span data-ttu-id="994d2-103">このサンプルでは、Windows Communication Foundation (WCF) を使用してエンドポイントにメッセージをディスパッチするメッセージ フィルターを交換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="994d2-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="994d2-104">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="994d2-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="994d2-105">チャネルでの最初のメッセージがサーバーに到着すると、サーバーは、URI に関連付けられているエンドポイントがある場合に、どのエンドポイントがメッセージを受信する必要があるかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="994d2-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="994d2-106">この処理は、<xref:System.ServiceModel.Dispatcher.MessageFilter> に関連付けられている <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> オブジェクトで制御されます。</span><span class="sxs-lookup"><span data-stu-id="994d2-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="994d2-107">サービスの各エンドポイントには、単一の <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> があります。</span><span class="sxs-lookup"><span data-stu-id="994d2-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="994d2-108"><xref:System.ServiceModel.Dispatcher.EndpointDispatcher> には、<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> と <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> の両方があります。</span><span class="sxs-lookup"><span data-stu-id="994d2-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="994d2-109">これら 2 つのフィルタを結合したものが、このエンドポイントに使用されるメッセージ フィルタです。</span><span class="sxs-lookup"><span data-stu-id="994d2-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="994d2-110">エンドポイントの <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> の既定では、アドレス指定されているメッセージと、サービス エンドポイントの <xref:System.ServiceModel.EndpointAddress> に一致するアドレスを照合します。</span><span class="sxs-lookup"><span data-stu-id="994d2-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="994d2-111">既定で、<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>のエンドポイントが受信メッセージのアクションを検査し、サービス エンドポイントのコントラクトの操作のアクションのいずれかに対応するアクション メッセージと一致する (だけ`IsInitiating` = `true`アクションと見なされます)。</span><span class="sxs-lookup"><span data-stu-id="994d2-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="994d2-112">その結果、エンドポイントのフィルタの既定で一致と見なされるのは、メッセージの To ヘッダーがエンドポイントの <xref:System.ServiceModel.EndpointAddress> に一致し、メッセージのアクションがエンドポイントの操作のいずれかのアクションと一致するという、2 つの条件がどちらも満たされる場合だけです。</span><span class="sxs-lookup"><span data-stu-id="994d2-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="994d2-113">これらのフィルタは、動作を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="994d2-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="994d2-114">サンプルのサービスは、次のように <xref:System.ServiceModel.Description.IEndpointBehavior> を作成して、<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> の <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> と <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="994d2-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```  
class FilteringEndpointBehavior : IEndpointBehavior …  
```  
  
 <span data-ttu-id="994d2-115">2 つのアドレス フィルタは、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="994d2-115">Two address filters are defined:</span></span>  
  
```  
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter …  
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter  
```  
  
 <span data-ttu-id="994d2-116">`FilteringEndpointBehavior` は構成可能になり、2 つの異なるバリエーションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="994d2-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```  
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement  
```  
  
 <span data-ttu-id="994d2-117">バリエーション 1 では 'e' が含まれる (ただし任意のアクションを含む) アドレスのみを照合します。これに対して、バリエーション 2 では 'e' が含まれないアドレスのみを照合します。</span><span class="sxs-lookup"><span data-stu-id="994d2-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```  
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="994d2-118">構成ファイルでは、サービスは次のように新しい動作を登録します。</span><span class="sxs-lookup"><span data-stu-id="994d2-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>      
```  
  
 <span data-ttu-id="994d2-119">次に、各バリエーションの `endpointBehavior` 構成を次のように作成します。</span><span class="sxs-lookup"><span data-stu-id="994d2-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 <span data-ttu-id="994d2-120">最後に、サービスのエンドポイントは、`behaviorConfigurations` の 1 つを次のように参照します。</span><span class="sxs-lookup"><span data-stu-id="994d2-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""   
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"   
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="994d2-121">クライアント アプリケーションの実装は単純で、URI の値を 2 番目の (`via`) パラメータとして <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> に渡すことによって、2 つのチャネルをサービスの URI に作成し、各チャネルに 1 つのメッセージを送信します。ただし、チャネルごとに異なるエンドポイント アドレスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="994d2-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="994d2-122">この結果、次のクライアントの出力に示すように、クライアントからの送信メッセージにはそれぞれ異なる宛先が指定され、サーバーはこれに応じて応答します。</span><span class="sxs-lookup"><span data-stu-id="994d2-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="994d2-123">サーバーの構成ファイルのバリエーションを切り替えると、フィルターが入れ替わり、クライアントには逆の動作が表示されます (`urn:e` へのメッセージは正常に送信されますが、`urn:a` へのメッセージはエラーになります)。</span><span class="sxs-lookup"><span data-stu-id="994d2-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""   
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"   
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="994d2-124">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="994d2-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="994d2-125">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="994d2-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="994d2-126">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="994d2-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="994d2-127">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="994d2-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="994d2-128">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="994d2-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="994d2-129">ソリューションをビルドする手順については、 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="994d2-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="994d2-130">単一コンピューター構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="994d2-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="994d2-131">複数コンピューター構成でサンプルを実行する」の手順に従います[Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)Client.cs の次の行を変更します。</span><span class="sxs-lookup"><span data-stu-id="994d2-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```  
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="994d2-132">つまり、localhost をサーバー名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="994d2-132">Replace localhost with the name of server.</span></span>  
  
    ```  
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
