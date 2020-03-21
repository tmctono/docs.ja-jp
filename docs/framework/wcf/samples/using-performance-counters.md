---
title: パフォーマンス カウンターの使用
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 7ffd9f5de5efb4be22968958246839e804daf23d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143578"
---
# <a name="using-performance-counters"></a><span data-ttu-id="7b0cc-102">パフォーマンス カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="7b0cc-102">Using Performance Counters</span></span>
<span data-ttu-id="7b0cc-103">このサンプルでは、Windows 通信基盤 (WCF) のパフォーマンス カウンターにアクセスする方法と、ユーザー定義のパフォーマンス カウンターを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="7b0cc-104">このサンプルは、[作業の開始に](../../../../docs/framework/wcf/samples/getting-started-sample.md)基づいています。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b0cc-105">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="7b0cc-106">このサンプルでは、クライアントが `ICalculator` サービスの 4 つのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="7b0cc-107">この処理は、ユーザーが中断するまで継続して行われます。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="7b0cc-108">サービスは変更されません。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="7b0cc-109">パフォーマンス カウンタは、サービスの Web.config ファイルの診断セクションで有効にします。次のサンプル構成を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="7b0cc-110">このタスクは、[構成エディター ツール (SvcConfigEditor.exe) を](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)使用して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="7b0cc-111">パフォーマンス カウンターが有効な場合、WCF パフォーマンス カウンターのスイート全体がサービスに対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="7b0cc-112">.NET Framework は、`ServiceModelService`、`ServiceModelEndpoint`、および `ServiceModelOperation` の 3 つのレベルで、パフォーマンス データを自動的に保持します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="7b0cc-113">これらの各レベルには、"呼び出し"、"1 秒あたりの呼び出し回数"、"承認されていないセキュリティ呼び出し" などのパフォーマンス カウンタがあります。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7b0cc-114">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="7b0cc-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7b0cc-115">[Windows コミュニケーションファウンデーション サンプルのワンタイム セットアップ手順を](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7b0cc-116">ソリューションの C# 版または Visual Basic .NET 版をビルドするには、「 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="7b0cc-117">単一または複数のコンピューターにまたがる構成でサンプルを実行するには、「 [Windows コミュニケーション ファウンデーション サンプルの実行](../../../../docs/framework/wcf/samples/running-the-samples.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="7b0cc-118">パフォーマンス データを表示するには</span><span class="sxs-lookup"><span data-stu-id="7b0cc-118">To view performance data</span></span>  
  
1. <span data-ttu-id="7b0cc-119">[**スタート**] ボタン、[**ファイル名を指定して実行]** をクリックしてパフォーマンス モニタ ツールを起動し、次のように入力`perfmon`**して [OK] を**クリックするか、またはコントロール パネルの [**管理ツール**] を選択して、[**パフォーマンス**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7b0cc-120">サンプル コードが実行されるまでは、カウンタを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-120">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="7b0cc-121">一覧表示されているパフォーマンス カウンタを削除するには、削除するパフォーマンス カウンタを選択して Del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="7b0cc-122">グラフ ペインを右クリックし、[カウンターの追加] を選択して、WCF**カウンターを追加**します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="7b0cc-123">[**カウンターの追加]** ダイアログ ボックスで、[パフォーマンス オブジェクト] ドロップダウン リスト ボックスの [**サービスモデルオペレーション 3.0.0.0]、[サービスモデルエンドポイント 3.0.0.0]、または [ServiceModelService 3.0.0.0]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="7b0cc-124">表示するカウンタを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7b0cc-125">コンピューターで実行されている WCF サービスがない場合は、サービスの WCF パフォーマンス カウンターはありません。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="7b0cc-126">構成エディターを使用してカウンターを有効にするには</span><span class="sxs-lookup"><span data-stu-id="7b0cc-126">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="7b0cc-127">SvcConfigEditor.exe のインスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="7b0cc-128">[ファイル] メニューの [**開く**] をクリックし、[**構成ファイル.**</span><span class="sxs-lookup"><span data-stu-id="7b0cc-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="7b0cc-129">サンプル アプリケーションの service フォルダーに移動し、Web.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="7b0cc-130">構成ツリーで **[診断**]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="7b0cc-131">**[診断]** ウィンドウの**パフォーマンス カウンター**を [すべて] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="7b0cc-132">構成ファイルを保存し、エディターを終了します。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7b0cc-133">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="7b0cc-134">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7b0cc-135">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7b0cc-136">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7b0cc-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="7b0cc-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b0cc-137">See also</span></span>

- <span data-ttu-id="7b0cc-138">[AppFabric の監視のサンプル](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="7b0cc-138">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
