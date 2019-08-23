---
title: '方法: WCF サービス操作を非同期に呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2d075bfebf7b5cbd2b2ce031a1c3855a925405a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964026"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="90837-102">方法: WCF サービス操作を非同期に呼び出す</span><span class="sxs-lookup"><span data-stu-id="90837-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="90837-103">ここでは、クライアントからサービス操作に非同期にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90837-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="90837-104">このトピックのサービスは、`ICalculator` インターフェイスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="90837-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="90837-105">クライアントは、イベント ドリブンの非同期呼び出しモデルを使用して、このインターフェイスで操作を非同期に呼び出すことができます</span><span class="sxs-lookup"><span data-stu-id="90837-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="90837-106">(イベントベースの非同期呼び出しモデルの詳細については、「[イベントベースの非同期パターンを使用したマルチスレッドプログラミング](https://go.microsoft.com/fwlink/?LinkId=248184)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="90837-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="90837-107">サービスで操作を非同期に実装する方法を示す例については[、「方法:非同期サービス操作](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)を実装します。</span><span class="sxs-lookup"><span data-stu-id="90837-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="90837-108">同期操作と非同期操作の詳細については、「[同期操作と非同期操作](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90837-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90837-109"><xref:System.ServiceModel.ChannelFactory%601> を使用している場合、イベント ドリブンの非同期呼び出しモデルはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="90837-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="90837-110">を使用した<xref:System.ServiceModel.ChannelFactory%601>非同期呼び出しの作成の詳細については、「 [方法:チャネルファクトリ](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)を使用して操作を非同期に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="90837-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="90837-111">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="90837-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="90837-112">WCF サービス操作を非同期に呼び出すには</span><span class="sxs-lookup"><span data-stu-id="90837-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="90837-113">次のコマンドに示すように、 `/async`との`/tcv:Version35`両方のコマンドオプションを一緒に使用して、 [ServiceModel メタデータユーティリティツール (svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="90837-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="90837-114">これにより、同期および標準のデリゲートベースの非同期操作に加えて、次のものを含む WCF クライアントクラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="90837-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="90837-115">イベントベース`operationName`の非同期呼び出し方法で使用する2つの <> `Async`操作。</span><span class="sxs-lookup"><span data-stu-id="90837-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="90837-116">例:</span><span class="sxs-lookup"><span data-stu-id="90837-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="90837-117">イベントベースの非同期呼び出し方法で`operationName`使用するために <> `Completed`フォームの操作完了イベント。</span><span class="sxs-lookup"><span data-stu-id="90837-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="90837-118">例:</span><span class="sxs-lookup"><span data-stu-id="90837-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="90837-119"><xref:System.EventArgs?displayProperty=nameWithType>イベントベースの非同期呼び出し方法で使用する`operationName`各操作 (フォーム <>`CompletedEventArgs`) の型。</span><span class="sxs-lookup"><span data-stu-id="90837-119"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="90837-120">例:</span><span class="sxs-lookup"><span data-stu-id="90837-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="90837-121">次のサンプル コードに示すように、呼び出し元アプリケーションで、非同期操作の完了時に呼び出されるコールバック メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="90837-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="90837-122">操作を呼び出す<xref:System.EventHandler%601?displayProperty=nameWithType>前に、<`operationName` > `EventArgs`型の新しいジェネリックを使用して、(前の手順で作成した) ハンドラーメソッドを`operationName` <> `Completed`イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="90837-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="90837-123">次に、<`operationName` > `Async`メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="90837-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="90837-124">例:</span><span class="sxs-lookup"><span data-stu-id="90837-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="90837-125">例</span><span class="sxs-lookup"><span data-stu-id="90837-125">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90837-126">イベント ベースの非同期モデルのデザイン ガイドラインには、複数の値を返す場合に、1 つの値を `Result` プロパティとして返し、残りの値を <xref:System.EventArgs> オブジェクトのプロパティとして返すことが記載されています。</span><span class="sxs-lookup"><span data-stu-id="90837-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="90837-127">この 1 つの結果として、クライアントがイベント ベースの非同期コマンド オプションを使用してメタデータをインポートし、操作から複数の値が返される場合、既定の <xref:System.EventArgs> オブジェクトが 1 つの値を `Result` プロパティとして返し、残りの値は <xref:System.EventArgs> オブジェクトのプロパティになります。メッセージ オブジェクトを `Result` プロパティとして受け取り、返された値をそのオブジェクトのプロパティとして取得する場合は、`/messageContract` コマンド オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="90837-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="90837-128">これにより、`Result` オブジェクトの <xref:System.EventArgs> プロパティとして応答メッセージを返すシグネチャが生成されます。</span><span class="sxs-lookup"><span data-stu-id="90837-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="90837-129">すべての内部戻り値は、応答メッセージ オブジェクトのプロパティになります。</span><span class="sxs-lookup"><span data-stu-id="90837-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="90837-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="90837-130">See also</span></span>

- [<span data-ttu-id="90837-131">方法: 非同期サービス操作を実装する</span><span class="sxs-lookup"><span data-stu-id="90837-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
