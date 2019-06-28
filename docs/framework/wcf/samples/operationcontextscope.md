---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 18dfcbbd84d04088026ca1016600fb0f6a4ce6c6
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424992"
---
# <a name="operationcontextscope"></a><span data-ttu-id="c469b-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="c469b-102">OperationContextScope</span></span>
<span data-ttu-id="c469b-103">OperationContextScope サンプルでは、ヘッダーを使用して Windows Communication Foundation (WCF) の呼び出しで追加の情報を送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c469b-103">The OperationContextScope sample demonstrates how to send extra information on a Windows Communication Foundation (WCF) call using headers.</span></span> <span data-ttu-id="c469b-104">このサンプルでは、サーバーとクライアントは両方ともコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c469b-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c469b-105">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c469b-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c469b-106">このサンプルでは、<xref:System.ServiceModel.Channels.MessageHeader> を使用して、クライアントが <xref:System.ServiceModel.OperationContextScope> として追加情報を送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c469b-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="c469b-107"><xref:System.ServiceModel.OperationContextScope> オブジェクトのスコープをチャネルに指定することにより、このオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c469b-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="c469b-108">リモート サービスに変換される必要があるヘッダーは、<xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> コレクションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c469b-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="c469b-109">このコレクションに追加されたヘッダーは、<xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> にアクセスすることによってサービス上で取得できます。</span><span class="sxs-lookup"><span data-stu-id="c469b-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="c469b-110">このヘッダー呼び出しは複数のチャネル上で行われ、クライアントに追加されたヘッダーは、<xref:System.ServiceModel.OperationContextScope> の作成に使用されたチャネルのみに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c469b-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="c469b-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="c469b-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="c469b-112">このサンプルは、クライアントからメッセージを受信し、<xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> コレクション内のヘッダーの検索を試行するサービスです。</span><span class="sxs-lookup"><span data-stu-id="c469b-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="c469b-113">クライアントは送信した GUID をヘッダー内に渡し、サービスはカスタム ヘッダーを取得します。カスタム ヘッダーがある場合は、引数としてクライアントによって渡された GUID と比較します。</span><span class="sxs-lookup"><span data-stu-id="c469b-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
```csharp
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a><span data-ttu-id="c469b-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="c469b-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="c469b-115">これは、クライアントの実装によって生成されたプロキシを使用して[ServiceModel メタデータ ユーティリティ ツール (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)リモート サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="c469b-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="c469b-116">`MessageHeaderReaderClient` の 2 つのプロキシ オブジェクトが最初に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c469b-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="c469b-117">次に、クライアントは OperationContextScope を作成し、スコープを `client1` に指定します。</span><span class="sxs-lookup"><span data-stu-id="c469b-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="c469b-118"><xref:System.ServiceModel.Channels.MessageHeader> が <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> に追加され、両方のクライアントで 1 つの呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="c469b-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="c469b-119">のみ、ヘッダーが送信されることになります`client1`できません`client2`からの戻り値をチェックして、`RetrieveHeader`呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c469b-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```csharp
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetrieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 <span data-ttu-id="c469b-120">このサンプルは自己ホスト型です。</span><span class="sxs-lookup"><span data-stu-id="c469b-120">This sample is self-hosted.</span></span> <span data-ttu-id="c469b-121">実行中のサンプルから、次のようなサンプル出力が提供されます。</span><span class="sxs-lookup"><span data-stu-id="c469b-121">The following sample output from running the sample is provided:</span></span>  
  
```console  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c469b-122">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="c469b-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c469b-123">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="c469b-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c469b-124">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c469b-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c469b-125">1 つまたは複数コンピュータ構成では、サンプルを実行する手順については、 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="c469b-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c469b-126">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c469b-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c469b-127">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c469b-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c469b-128">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="c469b-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c469b-129">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c469b-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
