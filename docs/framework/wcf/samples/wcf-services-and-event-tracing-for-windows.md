---
title: WCF サービスと Event Tracing for Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183209"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="cb621-102">WCF サービスと Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="cb621-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="cb621-103">このサンプルでは、Windows 通信基盤 (WCF) で分析トレースを使用して、Windows イベント トレース (ETW) でイベントを生成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cb621-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="cb621-104">分析トレースは、運用環境で WCF サービスのトラブルシューティングを可能にする WCF スタックのキー ポイントで生成されるイベントです。</span><span class="sxs-lookup"><span data-stu-id="cb621-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="cb621-105">WCF サービスの分析トレースは、パフォーマンスへの影響を最小限に抑えて運用環境で有効にできるトレースです。</span><span class="sxs-lookup"><span data-stu-id="cb621-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="cb621-106">これらのトレースは、ETW セッションにイベントとして出力されます。</span><span class="sxs-lookup"><span data-stu-id="cb621-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="cb621-107">このサンプルには、イベント ビューアーを使用して表示できるイベント ログに、サービスからイベントが出力される基本的な WCF サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb621-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="cb621-108">WCF サービスからのイベントをリッスンする専用の ETW セッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb621-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="cb621-109">サンプルには、バイナリ ファイルにイベントを格納する専用の ETW セッションを作成するためのスクリプトが含まれています。このバイナリ ファイルもイベント ビューアーを使用して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="cb621-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="cb621-110">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="cb621-110">To use this sample</span></span>

1. <span data-ttu-id="cb621-111">2012 年を使用して、EtwAnalyticTraceSample.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb621-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="cb621-112">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cb621-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="cb621-113">ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cb621-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="cb621-114">Web ブラウザで、[**電卓.svc]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb621-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="cb621-115">サービスの WSDL ドキュメントの URI がブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb621-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="cb621-116">その URI をコピーします。</span><span class="sxs-lookup"><span data-stu-id="cb621-116">Copy that URI.</span></span>

     <span data-ttu-id="cb621-117">デフォルトでは、サービスはポート 1378`http://localhost:1378/Calculator.svc`で要求のリッスンを開始します。</span><span class="sxs-lookup"><span data-stu-id="cb621-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="cb621-118">WCF テスト クライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="cb621-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="cb621-119">WCF テスト クライアント (WcfTestClient.exe)`\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`は に配置されています。</span><span class="sxs-lookup"><span data-stu-id="cb621-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="cb621-120">既定の Visual Studio 2012`C:\Program Files\Microsoft Visual Studio 10.0`インストール ディレクトリは です。</span><span class="sxs-lookup"><span data-stu-id="cb621-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="cb621-121">WCF テスト クライアント内で、[**ファイル**] を選択し、[**サービスの追加]** を選択してサービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb621-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="cb621-122">入力ボックスにエンドポイントのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="cb621-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="cb621-123">既定では、 `http://localhost:1378/Calculator.svc`です。</span><span class="sxs-lookup"><span data-stu-id="cb621-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="cb621-124">イベント ビューアー アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb621-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="cb621-125">サービスを呼び出す前に、イベント ビューアーを起動し、イベント ログが WCF サービスから生成された追跡イベントをリッスンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb621-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="cb621-126">[**スタート**] メニューの [**管理ツール**] をクリックし、[**イベント ビューア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb621-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="cb621-127">**分析**ログと**デバッグ**ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cb621-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="cb621-128">イベント ビューアのツリー ビューで、**イベント ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows、** および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb621-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="cb621-129">[アプリケーション**サーバー アプリケーション**] を右クリックし、[**表示**] をクリックして、[**分析ログとデバッグ ログの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb621-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="cb621-130">[**分析ログとデバッグ ログの表示]** オプションがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb621-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="cb621-131">分析ログを有効**に**します。</span><span class="sxs-lookup"><span data-stu-id="cb621-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="cb621-132">イベント ビューアのツリー ビューで、**イベント ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows、** および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb621-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="cb621-133">**[分析**] を右クリックし、[**ログの有効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb621-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="cb621-134">サービスをテストするには</span><span class="sxs-lookup"><span data-stu-id="cb621-134">To test the service</span></span>

1. <span data-ttu-id="cb621-135">WCF テスト クライアントに切り替えて`Divide`ダブルクリックし、0 の分母を指定する既定値を保持します。</span><span class="sxs-lookup"><span data-stu-id="cb621-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="cb621-136">分母が 0 の場合、サービスからエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="cb621-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="cb621-137">サービスから出力されたイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb621-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="cb621-138">イベント ビューアに戻り、**イベント ビューア**、**アプリケーションとサービス ログ\*\*\*\*、Microsoft** **、Windows、** および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb621-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="cb621-139">**[分析**] を右クリックし、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb621-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="cb621-140">WCF 分析トレースのイベントがイベント ビューアーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb621-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="cb621-141">サービスからエラーがスローされたため、イベント ビューアーにエラー トレース イベントが表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cb621-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="cb621-142">手順 1. と 2. を繰り返します。ただし、今度は有効な入力値を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb621-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="cb621-143">`N2` パラメーターの値は、0 以外であれば任意の数字でかまいません。</span><span class="sxs-lookup"><span data-stu-id="cb621-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="cb621-144">分析チャネルを更新して、WCF イベントにエラー イベントが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb621-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="cb621-145">このサンプルでは、WCF サービスから出力される分析トレース イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="cb621-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="cb621-146">クリーンアップするには (省略可能)</span><span class="sxs-lookup"><span data-stu-id="cb621-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="cb621-147">イベント ビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb621-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="cb621-148">イベント**ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows**、および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb621-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="cb621-149">**[分析**] を右クリックし、[**ログの無効化**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb621-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="cb621-150">イベント**ビューア**、**アプリケーションとサービス ログ** **、Microsoft** **、Windows**、および**アプリケーション サーバー アプリケーション**に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb621-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="cb621-151">**[分析**] を右クリックし、[**ログのクリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb621-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="cb621-152">イベントを**クリアするには、[クリア]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb621-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb621-153">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="cb621-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cb621-154">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb621-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="cb621-155">このディレクトリが存在しない場合は[、.NET Framework 4 の Windows コミュニケーション ファウンデーション (WCF) および Windows ワークフローファウンデーション (WF) サンプル](https://www.microsoft.com/download/details.aspx?id=21459)に移動して、すべての Windows 通信基盤 (WCF) とサンプルを[!INCLUDE[wf1](../../../../includes/wf1-md.md)]ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cb621-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cb621-156">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="cb621-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="cb621-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb621-157">See also</span></span>

- <span data-ttu-id="cb621-158">[AppFabric の監視のサンプル](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="cb621-158">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
