---
title: '方法: WCF エンドポイントを使用してキューに置かれたメッセージを交換する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
ms.openlocfilehash: dd59e7689fbca68d3e7b0b0008973e471d092fe0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778340"
---
# <a name="how-to-exchange-queued-messages-with-wcf-endpoints"></a><span data-ttu-id="c5a7f-102">方法: WCF エンドポイントを使用してキューに置かれたメッセージを交換する</span><span class="sxs-lookup"><span data-stu-id="c5a7f-102">How to: Exchange Queued Messages with WCF Endpoints</span></span>
<span data-ttu-id="c5a7f-103">キューは、通信時に、サービスをご利用いただけません場合でも、信頼性の高いメッセージングがクライアントと、Windows Communication Foundation (WCF) サービスの間で発生することことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-103">Queues ensure that reliable messaging can occur between a client and a Windows Communication Foundation (WCF) service, even if the service is not available at the time of communication.</span></span> <span data-ttu-id="c5a7f-104">次の手順では、WCF サービスを実装する場合、クライアントと、標準を使用してサービスの間の永続的な通信がバインディング キューに登録することを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-104">The following procedures show how to ensure durable communication between a client and a service by using the standard queued binding when implementing the WCF service.</span></span>  
  
 <span data-ttu-id="c5a7f-105">このセクションを使用する方法を説明します<xref:System.ServiceModel.NetMsmqBinding>の WCF クライアントと WCF サービスの間のキューに置かれた通信します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-105">This section explains how to use <xref:System.ServiceModel.NetMsmqBinding> for queued communication between a WCF client and a WCF service.</span></span>  
  
### <a name="to-use-queuing-in-a-wcf-service"></a><span data-ttu-id="c5a7f-106">WCF サービスでキューを使用するには</span><span class="sxs-lookup"><span data-stu-id="c5a7f-106">To use queuing in a WCF service</span></span>  
  
1. <span data-ttu-id="c5a7f-107"><xref:System.ServiceModel.ServiceContractAttribute> でマークされたインターフェイスを使用して、サービス コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-107">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="c5a7f-108">サービス コントラクトの一部であるインターフェイスの動作を <xref:System.ServiceModel.OperationContractAttribute> でマークし、メソッドに対して応答が返されないため、一方向と指定します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-108">Mark the operations in the interface that are part of the service contract with the <xref:System.ServiceModel.OperationContractAttribute> and specify them as one-way because no response to the method is returned.</span></span> <span data-ttu-id="c5a7f-109">サービス コントラクトおよびその操作の定義の例を次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-109">The following code provides an example service contract and its operation definition.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2. <span data-ttu-id="c5a7f-110">サービス コントラクトがユーザー定義型を渡す場合は、その型のデータ コントラクトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-110">When the service contract passes user-defined types, you must define data contracts for those types.</span></span> <span data-ttu-id="c5a7f-111">次のコードは、2 つのデータ コントラクト (`PurchaseOrder` および `PurchaseOrderLineItem`) を示します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-111">The following code shows two data contracts, `PurchaseOrder` and `PurchaseOrderLineItem`.</span></span> <span data-ttu-id="c5a7f-112">これらの 2 つの型は、サービスに送信されるデータを定義します </span><span class="sxs-lookup"><span data-stu-id="c5a7f-112">These two types define data that is sent to the service.</span></span> <span data-ttu-id="c5a7f-113">(このデータ コントラクトを定義するクラスによって多数のメソッドが定義されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-113">(Note that the classes that define this data contract also define a number of methods.</span></span> <span data-ttu-id="c5a7f-114">これらのメソッドは、データ コントラクトの一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-114">These methods are not considered part of the data contract.</span></span> <span data-ttu-id="c5a7f-115"><xref:System.Runtime.Serialization.DataMemberAttribute> 属性で宣言されているメンバーだけがデータ コントラクトに含まれます。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-115">Only those members that are declared with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute are part of the data contract.)</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3. <span data-ttu-id="c5a7f-116">インターフェイスで定義したサービス コントラクトのメソッドをクラスに実装します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-116">Implement the methods of the service contract defined in the interface in a class.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     <span data-ttu-id="c5a7f-117"><xref:System.ServiceModel.OperationBehaviorAttribute> メソッド上の `SubmitPurchaseOrder` に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-117">Notice the <xref:System.ServiceModel.OperationBehaviorAttribute> placed on the `SubmitPurchaseOrder` method.</span></span> <span data-ttu-id="c5a7f-118">これは、トランザクション内でこの操作を呼び出す必要があること、およびメソッドが完了したときにトランザクションが自動的に完了することを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-118">This specifies that this operation must be called within a transaction and that the transaction automatically completes when the method completes.</span></span>  
  
4. <span data-ttu-id="c5a7f-119"><xref:System.Messaging> を使用してトランザクション キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-119">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="c5a7f-120">代わりに、MSMQ (Microsoft Message Queuing) Microsoft 管理コンソール (MMC: Microsoft Management Console) を使用してキューを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-120">You can choose to create the queue using Microsoft Message Queuing (MSMQ) Microsoft Management Console (MMC) instead.</span></span> <span data-ttu-id="c5a7f-121">その場合は、トランザクション キューを作成してください。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-121">If so, make sure you create a transactional queue.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5. <span data-ttu-id="c5a7f-122">サービス アドレスを指定し、標準の <xref:System.ServiceModel.Description.ServiceEndpoint> バインディングを使用する <xref:System.ServiceModel.NetMsmqBinding> を構成で定義します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-122">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the service address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding.</span></span> <span data-ttu-id="c5a7f-123">詳細については、WCF 構成を使用して、次を参照してください。[を構成する WCF サービス](../configuring-services.md)します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-123">For more information about using WCF configuration, see [Configuring WCF services](../configuring-services.md).</span></span>  

6. <span data-ttu-id="c5a7f-124">`OrderProcessing` を使用して、キューからメッセージを読み取って処理する <xref:System.ServiceModel.ServiceHost> サービスのホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-124">Create a host for the `OrderProcessing` service using <xref:System.ServiceModel.ServiceHost> that reads messages from the queue and processes them.</span></span> <span data-ttu-id="c5a7f-125">サービス ホストを開いてサービスを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-125">Open the service host to make the service available.</span></span> <span data-ttu-id="c5a7f-126">任意のキーを押してサービスを終了するようユーザーに伝えるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-126">Display a message that tells the user to press any key to terminate the service.</span></span> <span data-ttu-id="c5a7f-127">`ReadLine` を呼び出して、キーが押されるまで待機してサービスを終了します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-127">Call `ReadLine` to wait for the key to be pressed and then close the service.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a><span data-ttu-id="c5a7f-128">キューに置かれたサービスのクライアントを作成するには</span><span class="sxs-lookup"><span data-stu-id="c5a7f-128">To create a client for the queued service</span></span>  
  
1. <span data-ttu-id="c5a7f-129">次の例では、ホスティング アプリケーションを実行し、Svcutil.exe ツールを使用して WCF クライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-129">The following example shows how to run the hosting application and use the Svcutil.exe tool to create the WCF client.</span></span>  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2. <span data-ttu-id="c5a7f-130">次の例に示すように、アドレスを指定し、標準の <xref:System.ServiceModel.Description.ServiceEndpoint> バインディングを使用する <xref:System.ServiceModel.NetMsmqBinding> を構成で定義します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-130">Define a <xref:System.ServiceModel.Description.ServiceEndpoint> in configuration that specifies the address and uses the standard <xref:System.ServiceModel.NetMsmqBinding> binding, as shown in the following example.</span></span>  

3. <span data-ttu-id="c5a7f-131">呼び出し、トランザクション キューに書き込むトランザクション スコープを作成、`SubmitPurchaseOrder`操作と閉じる、WCF クライアントは、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-131">Create a transaction scope to write to the transactional queue, call the `SubmitPurchaseOrder` operation and close the WCF client, as shown in the following example.</span></span>  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="c5a7f-132">例</span><span class="sxs-lookup"><span data-stu-id="c5a7f-132">Example</span></span>  
 <span data-ttu-id="c5a7f-133">次の例は、この例に含まれるサービス コード、ホスト アプリケーション、App.config ファイル、およびクライアント コードを示します。</span><span class="sxs-lookup"><span data-stu-id="c5a7f-133">The following examples show the service code, hosting application, App.config file, and client code included for this example.</span></span>  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  

 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  

## <a name="see-also"></a><span data-ttu-id="c5a7f-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5a7f-134">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- [<span data-ttu-id="c5a7f-135">トランザクション MSMQ バインディング</span><span class="sxs-lookup"><span data-stu-id="c5a7f-135">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)
- [<span data-ttu-id="c5a7f-136">WCF でのキュー</span><span class="sxs-lookup"><span data-stu-id="c5a7f-136">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
- [<span data-ttu-id="c5a7f-137">方法: WCF エンドポイントとメッセージ キュー アプリケーションでメッセージを交換</span><span class="sxs-lookup"><span data-stu-id="c5a7f-137">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [<span data-ttu-id="c5a7f-138">Windows Communication Foundation でのメッセージ キュー</span><span class="sxs-lookup"><span data-stu-id="c5a7f-138">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)
- [<span data-ttu-id="c5a7f-139">メッセージ キュー (MSMQ) のインストール</span><span class="sxs-lookup"><span data-stu-id="c5a7f-139">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)
- [<span data-ttu-id="c5a7f-140">Windows Communication Foundation へのメッセージ キュー</span><span class="sxs-lookup"><span data-stu-id="c5a7f-140">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)
- [<span data-ttu-id="c5a7f-141">メッセージ キューを介したメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="c5a7f-141">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
