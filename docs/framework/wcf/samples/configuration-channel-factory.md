---
title: 構成チャネル ファクトリ
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 0f00ba5e217420fe416100071d380e413c3df118
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183949"
---
# <a name="configuration-channel-factory"></a><span data-ttu-id="3bfd6-102">構成チャネル ファクトリ</span><span class="sxs-lookup"><span data-stu-id="3bfd6-102">Configuration Channel Factory</span></span>
<span data-ttu-id="3bfd6-103">このサンプルでは、<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-103">This sample covers the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span> <span data-ttu-id="3bfd6-104">WCF<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>クライアント構成の一元管理を可能にします。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-104">The <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows central management of WCF client configuration.</span></span> <span data-ttu-id="3bfd6-105">これは、アプリケーション ドメインによる読み込みの後に構成が選択または変更される場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-105">This can also be useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3bfd6-106">対象</span><span class="sxs-lookup"><span data-stu-id="3bfd6-106">Demonstrates</span></span>
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a><span data-ttu-id="3bfd6-107">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="3bfd6-107">Discussion</span></span>
 <span data-ttu-id="3bfd6-108">このサンプルでは、既定のアプリケーション構成ファイルを使用することなく、<xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> を使用して、クライアント アプリケーションに特定の構成ファイルを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-108">This sample shows how to use <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> to add a particular configuration file to a client application, without having to use the default application configuration file.</span></span>

 <span data-ttu-id="3bfd6-109">このサンプルは、2 つのプロジェクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-109">The sample consists of two projects.</span></span> <span data-ttu-id="3bfd6-110">最初のプロジェクトは、クライアントから送信されるメッセージに応答するために実行される単純なサービスです。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-110">The first project is a simple service that runs to reply to messages coming from the clients.</span></span> <span data-ttu-id="3bfd6-111">2 番目のプロジェクトは、Test.config 構成ファイルの <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> を使用して、2 つの <xref:System.Configuration.ExeConfigurationFileMap> オブジェクトを作成し、サービスとの通信にそれらのオブジェクトを使用するクライアント アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-111">The second project is a client application that builds two <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> objects using a <xref:System.Configuration.ExeConfigurationFileMap> for the Test.config configuration file and uses them to communicate with the service.</span></span> <span data-ttu-id="3bfd6-112">どちらのクライアントも Test.config で指定された構成を使用してサービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-112">Both clients communicate with the service using the configuration specified in Test.config.</span></span>

 <span data-ttu-id="3bfd6-113">次のコードでは、カスタム構成ファイルをクライアント アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-113">The following code adds a custom configuration file to a client application.</span></span>

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3bfd6-114">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="3bfd6-114">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="3bfd6-115">管理者特権で Visual Studio 2012 を開きます。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-115">Open Visual Studio 2012 with administrator privileges.</span></span>

2. <span data-ttu-id="3bfd6-116">ConfigurationChannelFactory ソリューション (2 プロジェクト) を右クリックし、[**プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-116">Right-click the ConfigurationChannelFactory solution (2 projects) and then select **Properties**.</span></span>

3. <span data-ttu-id="3bfd6-117">[**共通のプロパティ]** で [**スタートアップ プロジェクト**] をクリックし、[**複数のスタートアップ プロジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-117">In **Common Properties**, select **Startup Project**, and then click **Multiple startup projects**.</span></span>

4. <span data-ttu-id="3bfd6-118">**サービス**プロジェクトを一覧の先頭に移動し **、"開始**" アクションを使用して **、サービス**プロジェクトの後に**クライアント**プロジェクトを**Action ‘Start’** 移動します。 **Client** **Service**</span><span class="sxs-lookup"><span data-stu-id="3bfd6-118">Move the **Service** project to the beginning of the list, with the **Action ‘Start’**, and then move the **Client** project after the **Service** project, also with the **Action ‘Start’**, so the **Client** project is executed after the **Service** project.</span></span>

5. <span data-ttu-id="3bfd6-119">**[OK]** をクリックし、F5 キー (または Ctrl + F5 キー) を押してサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-119">Click **OK**, and then press F5 (or CTRL+F5) to run the sample.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3bfd6-120">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3bfd6-121">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3bfd6-122">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3bfd6-123">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3bfd6-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
