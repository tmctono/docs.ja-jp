---
title: CustomChannelTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: 0d77af319e18868ce7d600269cd9afaa0c4ce2c6
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928644"
---
# <a name="customchannelstester"></a><span data-ttu-id="e2f95-102">CustomChannelTester</span><span class="sxs-lookup"><span data-stu-id="e2f95-102">CustomChannelsTester</span></span>
<span data-ttu-id="e2f95-103">`CustomChannelsTester` は、カスタム チャネルの実装を、定義済みのサービス コントラクト セットに対してテストする際に使用できるツールです。</span><span class="sxs-lookup"><span data-stu-id="e2f95-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="e2f95-104">サービス コントラクト セットを選択し、XML ファイルを使用してこのツールに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="e2f95-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="e2f95-105">これを受け取ったツールは、メッセージ交換中にカスタム チャネル実装をテストするサービスとクライアントを生成します。</span><span class="sxs-lookup"><span data-stu-id="e2f95-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="e2f95-106">ツールをビルドするには</span><span class="sxs-lookup"><span data-stu-id="e2f95-106">To build the tool</span></span>  
  
1. <span data-ttu-id="e2f95-107">ソリューションをビルドするには、「 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e2f95-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="e2f95-108">ソリューションをビルドすると、次の3つのファイルが生成されます。CustomChannelsTester TestSpec .xml、および Samplerun.cmd。</span><span class="sxs-lookup"><span data-stu-id="e2f95-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="e2f95-109">Samplerun.cmd ファイルには、このツールを使用して[トランスポートをテストする方法を示すサンプルコマンドラインがあります。UDP](../../../../docs/framework/wcf/samples/transport-udp.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="e2f95-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="e2f95-110">ツールを実行するには</span><span class="sxs-lookup"><span data-stu-id="e2f95-110">To run the tool</span></span>  
  
- <span data-ttu-id="e2f95-111">コマンド プロンプトに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2f95-111">At the command prompt type the following command:</span></span>  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="e2f95-112">`/binding` オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f95-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="e2f95-113">`/dll`"binding" が Windows Communication Foundation (WCF) によって提供されるシステム指定のバインディングでない場合は、が必要です。</span><span class="sxs-lookup"><span data-stu-id="e2f95-113">`/dll` is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     <span data-ttu-id="e2f95-114">`/testspec` は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="e2f95-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="e2f95-115">これにより、テストの仕様とバインディングに基づくサーバーとクライアントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2f95-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="e2f95-116">クライアントとサーバーを実行し、結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="e2f95-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="e2f95-117">テストの仕様を説明する XML のサンプルを次に示します (testspec.xml)。</span><span class="sxs-lookup"><span data-stu-id="e2f95-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
    ```xml  
    <TestSpec xmlns="http://WCF/TestSpec" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" >  
    <ServiceContract>  
    <!-- Test a contract which has oneway / twoway operations. If you set ExpandAll = true, both types of contracts are tested -->    <IsOneWay ExpandAll="true">true</IsOneWay>  
    <!-- Test a contract with Asynchronous / Synchronous Operations-->  
        <IsAsync>false</IsAsync>   
    <!-- Test a sessionful / sessionless contract-->      
        <IsSession ExpandAll="true">true</IsSession>  
    <!-- If the Service Contract includes a CallBack Contract-->      
        <IsCallBack ExpandAll="true">true</IsCallBack>  
    </ServiceContract>  
    <TestDetails>  
    <!-- Name of the machine that runs the server - required if you want to run the test crossmachine-->  
        <ServerName>ReplaceThisWithTheServerMachineName</ServerName>  
    <!-- Port Number - Optional-->  
        <Port>8000</Port>  
    <!--URI for the callBack address for the client. The client will receive the messages from the server on this address in case of a CallBack Contract-->  
        <ClientCallBackAddress/>      
    <!-- Duration (in sec) after the server has started, it times out - optional(default = 300sec) -->  
        <ServerTimeout>300</ServerTimeout>  
    <!-- Duration (in sec) before the Client initializes -optional(default = 60sec) -->  
        <ClientTimeout>60</ClientTimeout>  
    <!-- Number of clients for each service - optional(default = 1) -->  
        <NumberOfClients>1</NumberOfClients>  
    <!-- Number of messages each client sends to the service - optional(default = 1) -->  
        <MessagesPerClient>1</MessagesPerClient>  
    </TestDetails>  
    </TestSpec>  
    ```  
