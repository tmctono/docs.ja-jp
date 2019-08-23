---
title: カスタム バインドのトランスポートとエンコード
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 83b6f98ca889d4f80841b629d7a958401bac1e87
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953752"
---
# <a name="custom-binding-transport-and-encoding"></a><span data-ttu-id="7478a-102">カスタム バインドのトランスポートとエンコード</span><span class="sxs-lookup"><span data-stu-id="7478a-102">Custom Binding Transport and Encoding</span></span>
<span data-ttu-id="7478a-103">カスタム バインドは、個々のバインド要素の順序付きリストとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="7478a-103">A custom binding is defined by an ordered list of discrete binding elements.</span></span> <span data-ttu-id="7478a-104">このサンプルでは、さまざまなトランスポートとメッセージ エンコーディング要素を使用してカスタム バインディングを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7478a-104">This sample demonstrates how to configure a custom binding with various transport and message encoding elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7478a-105">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7478a-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="7478a-106">このサンプルは[自己ホスト](../../../../docs/framework/wcf/samples/self-host.md)に基づいており、カスタムバインドを使用した HTTP、TCP、および namedpipe トランスポートをサポートする3つのエンドポイントを構成するために変更されています。</span><span class="sxs-lookup"><span data-stu-id="7478a-106">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md), and has been modified to configure three endpoints to support HTTP, TCP, and NamedPipe transports with custom bindings.</span></span> <span data-ttu-id="7478a-107">クライアント構成も同様に変更され、クライアント コードは 3 つのエンドポイントそれぞれと通信するように変更されています。</span><span class="sxs-lookup"><span data-stu-id="7478a-107">The client configuration was similarly modified, and the client code changed to communicate with each of the three endpoints.</span></span>  
  
 <span data-ttu-id="7478a-108">このサンプルでは、特定のトランスポートとメッセージ エンコーディング要素をサポートするカスタム バインディングを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7478a-108">The sample demonstrates a how to configure a custom binding that supports a particular transport and message encoding.</span></span> <span data-ttu-id="7478a-109">これを行うには、`binding` 要素のトランスポートとメッセージ エンコーディングを構成します。</span><span class="sxs-lookup"><span data-stu-id="7478a-109">This is accomplished by configuring a transport and a message encoding for the `binding` element.</span></span> <span data-ttu-id="7478a-110">バインディング要素の順序は、カスタムバインディングを定義する際に重要です。これは、それぞれがチャネルスタック内のレイヤーを表しているためです (「[カスタムバインド](../../../../docs/framework/wcf/extending/custom-bindings.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7478a-110">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="7478a-111">このサンプルでは、テキスト エンコーディングによる HTTP トランスポート、テキスト エンコーディングによる TCP トランスポート、およびバイナリ エンコーディングによる NamedPipe トランスポートの 3 つのカスタム バインドを構成します。</span><span class="sxs-lookup"><span data-stu-id="7478a-111">This sample configures three custom bindings: an HTTP transport with text encoding, a TCP transport with text encoding, and a NamedPipe transport with a binary encoding.</span></span>  
  
 <span data-ttu-id="7478a-112">サービス構成では、次のようにカスタム バインドが定義されます。</span><span class="sxs-lookup"><span data-stu-id="7478a-112">The service configuration defines the custom bindings as follows:</span></span>  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding   
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="7478a-113">このサンプルを実行すると、操作要求と応答がサービスとクライアントの両方のコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7478a-113">When you run the sample, the operation requests and responses are displayed in both the service and client console window.</span></span> <span data-ttu-id="7478a-114">クライアントは、3 つのエンドポイントのそれぞれと通信します。最初に HTTP、次に TCP、最後に NamedPipe にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="7478a-114">The client communicates with each of the three endpoints, accessing first HTTP, then TCP, and finally NamedPipe.</span></span> <span data-ttu-id="7478a-115">どちらかのコンソールで Enter キーを押すと、サービスとクライアントがどちらもシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="7478a-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="7478a-116">`namedPipeTransport` バインディングは、複数のコンピュータ間の操作をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="7478a-116">The `namedPipeTransport` binding does not support machine-to-machine operations.</span></span> <span data-ttu-id="7478a-117">同じコンピュータの通信だけに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7478a-117">It is used only for communication on the same machine.</span></span> <span data-ttu-id="7478a-118">したがって、このサンプルを複数コンピュータのシナリオで実行する場合は、クライアント コード ファイル内の次の行をコメント化してください。</span><span class="sxs-lookup"><span data-stu-id="7478a-118">Therefore, when running the sample in a cross-machine scenario, comment out the following lines in the client code file:</span></span>  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> <span data-ttu-id="7478a-119">Svcutil.exe を使用してこのサンプルの構成を再生成した場合は、クライアント コードに一致するように、クライアント構成内のエンドポイント名を変更してください。</span><span class="sxs-lookup"><span data-stu-id="7478a-119">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7478a-120">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="7478a-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7478a-121">[Windows Communication Foundation サンプルの1回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)を実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7478a-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7478a-122">ソリューションの .net C#エディションC++、、または Visual Basic ビルドするには、「 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7478a-122">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="7478a-123">サンプルを単一コンピューター構成または複数コンピューター構成で実行するには、「 [Windows Communication Foundation サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7478a-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7478a-124">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7478a-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7478a-125">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7478a-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7478a-126">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="7478a-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7478a-127">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7478a-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
