---
title: WCF 分析トレース
ms.date: 03/30/2017
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
ms.openlocfilehash: ef636a672d9384e8e3d658f0488cfaadb8d293e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183217"
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="3ffba-102">WCF 分析トレース</span><span class="sxs-lookup"><span data-stu-id="3ffba-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="3ffba-103">このサンプルでは、Windows 通信財団 (WCF) が ETW に書き込む分析トレースのストリームに独自の[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]トレース イベントを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that Windows Communication Foundation (WCF) writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="3ffba-104">分析トレースは、パフォーマンスを低下させずに簡単にサービスを確認できるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="3ffba-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="3ffba-105">このサンプルでは<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>、API を使用して、WCF サービスと統合するイベントを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with WCF services.</span></span>  
  
 <span data-ttu-id="3ffba-106">API の<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>詳細については、を参照してください<xref:System.Diagnostics.Eventing?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="3ffba-106">For more information about the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3ffba-107">Windows でのイベント トレースの詳細については[、「ETW を使用したデバッグとパフォーマンスのチューニングの向上](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ffba-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="3ffba-108">EventProvider の破棄</span><span class="sxs-lookup"><span data-stu-id="3ffba-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="3ffba-109">このサンプルでは、<xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> を実装した <xref:System.IDisposable?displayProperty=nameWithType> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3ffba-110">WCF サービスのトレースを実装する場合、サービスの有効期間に対して<xref:System.Diagnostics.Eventing.EventProvider>リソースを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ffba-110">When implementing tracing for a WCF service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="3ffba-111">そのため、読みやすくするためにも、このサンプルでは、ラップされた <xref:System.Diagnostics.Eventing.EventProvider> を破棄しません。</span><span class="sxs-lookup"><span data-stu-id="3ffba-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="3ffba-112">何かの理由で、サービスに対して別のトレースの要件を設定し、このリソースを破棄しなければならない場合は、アンマネージ リソースの破棄に関するベスト プラクティスに従ってこのサンプルを変更してください。</span><span class="sxs-lookup"><span data-stu-id="3ffba-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> <span data-ttu-id="3ffba-113">アンマネージ リソースの破棄の詳細については、「 [Dispose メソッドの実装](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ffba-113">For more information about disposing unmanaged resources, see [Implementing a Dispose Method](https://docs.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="3ffba-114">自己ホスト型と Web ホスト型</span><span class="sxs-lookup"><span data-stu-id="3ffba-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="3ffba-115">Web ホスト サービスの場合、WCF の分析トレースは、トレースを生成するサービスを識別するために使用される "HostReference" と呼ばれるフィールドを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="3ffba-116">拡張可能なユーザー トレースをこのモデルに加えることができます。このサンプルで、そのためのベスト プラクティスを示します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="3ffba-117">パイプの 「&#124;' 文字が実際に結果の文字列に現れる場合の Web ホスト参照の形式は、次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="3ffba-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
- <span data-ttu-id="3ffba-118">アプリケーションがルート以外にある場合</span><span class="sxs-lookup"><span data-stu-id="3ffba-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="3ffba-119">\<サービス名> \<>>&#124;アプリケーション\<仮想パス>&#124;\<サイト名</span><span class="sxs-lookup"><span data-stu-id="3ffba-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
- <span data-ttu-id="3ffba-120">アプリケーションがルートにある場合</span><span class="sxs-lookup"><span data-stu-id="3ffba-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="3ffba-121">\<サービス名>&#124;\<サービス名パス>&#124;\<サービス名></span><span class="sxs-lookup"><span data-stu-id="3ffba-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="3ffba-122">自己ホスト型サービスの場合、WCF の分析トレースは"HostReference" フィールドに値を設定しません。</span><span class="sxs-lookup"><span data-stu-id="3ffba-122">For self-hosted services, WCF’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="3ffba-123">このサンプルの `WCFUserEventProvider` クラスは、自己ホスト型サービスで使用した場合も同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="3ffba-124">カスタム イベントの詳細</span><span class="sxs-lookup"><span data-stu-id="3ffba-124">Custom Event Details</span></span>  
 <span data-ttu-id="3ffba-125">WCF の ETW イベント プロバイダー マニフェストは、サービス コード内から WCF サービスの作成者によって生成されるように設計されている 3 つのイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-125">WCF’s ETW Event Provider manifest defines three events that are designed to be emitted by WCF service authors from within service code.</span></span> <span data-ttu-id="3ffba-126">次の表に、その 3 つのイベントの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="3ffba-127">Event</span><span class="sxs-lookup"><span data-stu-id="3ffba-127">Event</span></span>|<span data-ttu-id="3ffba-128">説明</span><span class="sxs-lookup"><span data-stu-id="3ffba-128">Description</span></span>|<span data-ttu-id="3ffba-129">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3ffba-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="3ffba-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="3ffba-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="3ffba-131">このイベントは、問題以外の通知すべき処理がサービスで発生した場合に生成します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="3ffba-132">たとえば、データベースの呼び出しに成功した後にイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="3ffba-133">301</span><span class="sxs-lookup"><span data-stu-id="3ffba-133">301</span></span>|  
|<span data-ttu-id="3ffba-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="3ffba-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="3ffba-135">このイベントは、後続の処理でエラーになる可能性がある問題が発生した場合に生成します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="3ffba-136">たとえば、データベースの呼び出しが失敗したものの、冗長なデータ ストアを使用して回復できた場合に警告イベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="3ffba-137">302</span><span class="sxs-lookup"><span data-stu-id="3ffba-137">302</span></span>|  
|<span data-ttu-id="3ffba-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="3ffba-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="3ffba-139">このイベントは、サービスが想定どおりに動作しなかった場合に生成します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="3ffba-140">たとえば、データベースの呼び出しが失敗し、別の場所からもデータを取得できなかった場合にイベントを生成します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="3ffba-141">303</span><span class="sxs-lookup"><span data-stu-id="3ffba-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3ffba-142">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="3ffba-142">To use this sample</span></span>  
  
1. <span data-ttu-id="3ffba-143">Visual Studio 2012 を使用して、WCFAnalyticTracingEx 拡張性.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-143">Using Visual Studio 2012, open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2. <span data-ttu-id="3ffba-144">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="3ffba-145">ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="3ffba-146">Web ブラウザで、[**電卓.svc]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="3ffba-147">サービスの WSDL ドキュメントの URI がブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="3ffba-148">その URI をコピーします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-148">Copy that URI.</span></span>  
  
4. <span data-ttu-id="3ffba-149">WCF テスト クライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-149">Run the WCF test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="3ffba-150">WCF テスト クライアント (WcfTestClient.exe)`\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`は に配置されています。</span><span class="sxs-lookup"><span data-stu-id="3ffba-150">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span> <span data-ttu-id="3ffba-151">既定の Visual Studio 2012`C:\Program Files\Microsoft Visual Studio 10.0`インストール ディレクトリは です。</span><span class="sxs-lookup"><span data-stu-id="3ffba-151">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>  
  
5. <span data-ttu-id="3ffba-152">WCF テスト クライアント内で、[**ファイル**] を選択し、[**サービスの追加]** を選択してサービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-152">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="3ffba-153">入力ボックスにエンドポイントのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-153">Add the endpoint address in the input box.</span></span>  
  
6. <span data-ttu-id="3ffba-154">[**OK**] をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-154">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="3ffba-155">ICalculator サービスは、左側のペインの **[マイ サービス プロジェクト**] の下に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-155">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7. <span data-ttu-id="3ffba-156">イベント ビューアー アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-156">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="3ffba-157">サービスを呼び出す前に、イベント ビューアーを起動し、イベント ログが WCF サービスから生成された追跡イベントをリッスンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-157">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>  
  
8. <span data-ttu-id="3ffba-158">[**スタート**] メニューの [**管理ツール**] をクリックし、[**イベント ビューア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-158">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="3ffba-159">**分析**ログと**デバッグ**ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-159">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="3ffba-160">イベント ビューアのツリー ビューで、**イベント ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows、** および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-160">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="3ffba-161">[アプリケーション**サーバー アプリケーション**] を右クリックし、[**表示**] をクリックして、[**分析ログとデバッグ ログの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-161">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="3ffba-162">[**分析ログとデバッグ ログの表示]** オプションがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-162">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="3ffba-163">分析ログを有効**に**します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-163">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="3ffba-164">イベント ビューアのツリー ビューで、**イベント ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows**、**アプリケーション サーバー アプリケーション**、および**分析**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-164">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="3ffba-165">**[分析**] を右クリックし、[**ログの有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-165">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="3ffba-166">WCF テスト クライアントを使用してサービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-166">Test the service using the WCF Test Client.</span></span>  
  
    1. <span data-ttu-id="3ffba-167">WCF テスト クライアントで、ICalculator サービス ノードの下で**Add()** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-167">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="3ffba-168">**Add()** メソッドは、2 つのパラメータを持つ右側のペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-168">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2. <span data-ttu-id="3ffba-169">最初のパラメーターに「2」と入力し、2 番目のパラメーターに「3」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-169">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3. <span data-ttu-id="3ffba-170">[**呼び出し**] をクリックしてメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-170">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="3ffba-171">既に開いている**イベント ビューア**ウィンドウに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-171">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="3ffba-172">イベント**ビューア**、**アプリケーションとサービス ログ**、 **Microsoft**、 **Windows**、 アプリケーション サーバー**アプリケーション に**移動します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-172">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="3ffba-173">**[分析**] ノードを右クリックし、[**最新の情報に更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-173">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="3ffba-174">右ペインにイベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-174">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="3ffba-175">ID が 303 のイベントを探してダブルクリックして開き、内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-175">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="3ffba-176">このイベントは、ICalculator`Add()`サービスのメソッドによって生成され、ペイロードが "2+3=5" に等しい。</span><span class="sxs-lookup"><span data-stu-id="3ffba-176">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="3ffba-177">クリーンアップするには (省略可能)</span><span class="sxs-lookup"><span data-stu-id="3ffba-177">To clean up (Optional)</span></span>  
  
1. <span data-ttu-id="3ffba-178">**イベント ビューアー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-178">Open **Event Viewer**.</span></span>  
  
2. <span data-ttu-id="3ffba-179">イベント**ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows**、および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-179">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="3ffba-180">**[分析**] を右クリックし、[**ログの無効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-180">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3. <span data-ttu-id="3ffba-181">イベント**ビューア**、**アプリケーションとサービス ログ**、 **Microsoft**、 **Windows**、 アプリケーション**サーバー アプリケーション**、および**分析**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-181">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="3ffba-182">**[分析**] を右クリックし、[**ログのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-182">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4. <span data-ttu-id="3ffba-183">イベントを**クリアするには、[クリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-183">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="3ffba-184">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3ffba-184">Known Issue</span></span>  
 <span data-ttu-id="3ffba-185">**イベント ビューア**に既知の問題があり、ETW イベントのデコードに失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ffba-185">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="3ffba-186">"ソースの Microsoft-Windows アプリケーション サーバー アプリケーションから>\<イベント ID の説明が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="3ffba-186">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="3ffba-187">このイベントを発生させるコンポーネントがローカル コンピューターにインストールされていないか、インストールが壊れています。</span><span class="sxs-lookup"><span data-stu-id="3ffba-187">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="3ffba-188">コンポーネントは、ローカル コンピュータにインストールまたは修復できます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-188">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="3ffba-189">このエラーが発生した場合は、[**アクション]** メニューの **[最新の情報に更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ffba-189">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="3ffba-190">これにより、イベントが正常にデコードされます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-190">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ffba-191">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ffba-191">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3ffba-192">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ffba-192">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3ffba-193">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3ffba-193">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3ffba-194">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3ffba-194">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="3ffba-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ffba-195">See also</span></span>

- <span data-ttu-id="3ffba-196">[AppFabric の監視のサンプル](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3ffba-196">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
