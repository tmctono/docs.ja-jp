---
title: CustomChannelTester
ms.date: 03/30/2017
ms.assetid: ee1fa307-98b1-4647-8860-2e9217ba6082
ms.openlocfilehash: c23bd3eddd49972b7083347fed88d4e70707ae58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183812"
---
# <a name="customchannelstester"></a><span data-ttu-id="5bdcd-102">CustomChannelTester</span><span class="sxs-lookup"><span data-stu-id="5bdcd-102">CustomChannelsTester</span></span>
<span data-ttu-id="5bdcd-103">`CustomChannelsTester` は、カスタム チャネルの実装を、定義済みのサービス コントラクト セットに対してテストする際に使用できるツールです。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-103">The `CustomChannelsTester` is a tool that you can use to test your custom channel implementations against a set of predefined service contracts.</span></span> <span data-ttu-id="5bdcd-104">サービス コントラクト セットを選択し、XML ファイルを使用してこのツールに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-104">You can select the set of service contracts and pass it to the tool using an XML file.</span></span> <span data-ttu-id="5bdcd-105">これを受け取ったツールは、メッセージ交換中にカスタム チャネル実装をテストするサービスとクライアントを生成します。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-105">The tool then generates the service and client that exercises your custom channel implementations during message exchange.</span></span>  
  
### <a name="to-build-the-tool"></a><span data-ttu-id="5bdcd-106">ツールをビルドするには</span><span class="sxs-lookup"><span data-stu-id="5bdcd-106">To build the tool</span></span>  
  
1. <span data-ttu-id="5bdcd-107">ソリューションをビルドするには、「 [Windows コミュニケーション ファウンデーション のサンプルの構築](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-107">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="5bdcd-108">ソリューションをビルドすると、CustomChannelsTester.exe、TestSpec.xml、および SampleRun.cmd の 3 つのファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-108">Building the solution generates three files: CustomChannelsTester.exe, TestSpec.xml and SampleRun.cmd.</span></span> <span data-ttu-id="5bdcd-109">SampleRun.cmd ファイルには、このツールを使用して[トランスポート: UDP](../../../../docs/framework/wcf/samples/transport-udp.md)サンプルをテストする方法を示すサンプル コマンド ラインがあります。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-109">The file SampleRun.cmd has a sample command line that shows how to use this tool to test the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span>  
  
### <a name="to-run-the-tool"></a><span data-ttu-id="5bdcd-110">ツールを実行するには</span><span class="sxs-lookup"><span data-stu-id="5bdcd-110">To run the tool</span></span>  
  
- <span data-ttu-id="5bdcd-111">コマンド プロンプトに次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-111">At the command prompt type the following command:</span></span>  
  
    ```console  
    CustomChannelsTester.exe /binding:YourCustomBindngName /dll:TheAssemblyWhereThisTypeisDefined /testspec:XmlFileNameWhichContainsTestOptions  
    ```  
  
     <span data-ttu-id="5bdcd-112">`/binding` オプションを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-112">Using the `/binding` option is required.</span></span>  
  
     <span data-ttu-id="5bdcd-113">`/dll`は、"バインディング" が Windows 通信基盤 (WCF) によって提供されるシステム提供のバインディングではない場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-113">`/dll` is required if "binding" is not a system-provided binding provided by Windows Communication Foundation (WCF).</span></span>  
  
     <span data-ttu-id="5bdcd-114">`/testspec` はオプションです。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-114">`/testspec` is optional.</span></span>  
  
     <span data-ttu-id="5bdcd-115">これにより、テストの仕様とバインディングに基づくサーバーとクライアントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-115">This creates server and clients based on the test specifications and the binding.</span></span>  
  
     <span data-ttu-id="5bdcd-116">クライアントとサーバーを実行し、結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-116">Executes the client and server and returns the results.</span></span>  
  
     <span data-ttu-id="5bdcd-117">テストの仕様を説明する XML のサンプルを次に示します (testspec.xml)。</span><span class="sxs-lookup"><span data-stu-id="5bdcd-117">The following is the sample XML for the description of the test specifications (testspec.xml):</span></span>  
  
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
