---
title: WCF サービスと Event Tracing for Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 35d0202a3b9cf4060240dc521554644d419a5c23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723174"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="52da0-102">WCF サービスと Event Tracing for Windows</span><span class="sxs-lookup"><span data-stu-id="52da0-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="52da0-103">このサンプルでは、Event Tracing for Windows (ETW で) を出力する Windows Communication Foundation (WCF) での分析トレースを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="52da0-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="52da0-104">分析トレースは、運用環境で WCF サービスのトラブルシューティングできるように、WCF スタックのキー_ポイントで出力されるイベントです。</span><span class="sxs-lookup"><span data-stu-id="52da0-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="52da0-105">WCF サービスの分析トレースのトレースが可能に運用環境でのパフォーマンスに影響を最小限にします。</span><span class="sxs-lookup"><span data-stu-id="52da0-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="52da0-106">これらのトレースは、ETW セッションにイベントとして出力されます。</span><span class="sxs-lookup"><span data-stu-id="52da0-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="52da0-107">このサンプルでは、基本的な WCF サービスでイベントがサービスから生成された、イベント ビューアーを使用して表示できるイベント ログに含まれています。</span><span class="sxs-lookup"><span data-stu-id="52da0-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="52da0-108">WCF サービスからのイベントをリッスンする専用の ETW セッションを開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="52da0-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="52da0-109">サンプルには、バイナリ ファイルにイベントを格納する専用の ETW セッションを作成するためのスクリプトが含まれています。このバイナリ ファイルもイベント ビューアーを使用して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="52da0-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="52da0-110">このサンプルを使用するには</span><span class="sxs-lookup"><span data-stu-id="52da0-110">To use this sample</span></span>

1. <span data-ttu-id="52da0-111">Visual Studio 2012 を使用して、EtwAnalyticTraceSample.sln ソリューション ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="52da0-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="52da0-112">ソリューションをビルドするには、Ctrl キーと Shift キーを押しながら B キーを押します。</span><span class="sxs-lookup"><span data-stu-id="52da0-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="52da0-113">ソリューションを実行するには、Ctrl キーを押しながら F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="52da0-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="52da0-114">Web ブラウザーで次のようにクリックします。 **[calculator.svc]** します。</span><span class="sxs-lookup"><span data-stu-id="52da0-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="52da0-115">サービスの WSDL ドキュメントの URI がブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="52da0-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="52da0-116">その URI をコピーします。</span><span class="sxs-lookup"><span data-stu-id="52da0-116">Copy that URI.</span></span>

     <span data-ttu-id="52da0-117">既定では、サービスの開始ポート 1378 で要求のリッスン`http://localhost:1378/Calculator.svc`します。</span><span class="sxs-lookup"><span data-stu-id="52da0-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="52da0-118">WCF テスト クライアント (WcfTestClient.exe) を実行します。</span><span class="sxs-lookup"><span data-stu-id="52da0-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="52da0-119">WCF テスト クライアント (WcfTestClient.exe) は`\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`します。</span><span class="sxs-lookup"><span data-stu-id="52da0-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="52da0-120">既定の Visual Studio 2012 のインストール ディレクトリは`C:\Program Files\Microsoft Visual Studio 10.0`します。</span><span class="sxs-lookup"><span data-stu-id="52da0-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="52da0-121">選択して、サービスを追加、WCF テスト クライアント内で**ファイル**、し**サービスの追加**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="52da0-122">入力ボックスにエンドポイントのアドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="52da0-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="52da0-123">既定値は `http://localhost:1378/Calculator.svc` です。</span><span class="sxs-lookup"><span data-stu-id="52da0-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="52da0-124">イベント ビューアー アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="52da0-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="52da0-125">サービスを呼び出す前に、イベント ビューアーを起動し、WCF サービスから生成された追跡イベントのイベント ログがリッスンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="52da0-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="52da0-126">**開始**メニューの **管理ツール**、し**イベント ビューアー**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="52da0-127">有効にする、**分析**と**デバッグ**ログ。</span><span class="sxs-lookup"><span data-stu-id="52da0-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="52da0-128">イベント ビューアーのツリー ビューでに移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し、。**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="52da0-129">右クリックして**アプリケーション サーバー-アプリケーション**を選択します**ビュー**、し**分析およびデバッグ ログ**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="52da0-130">いることを確認、 **分析およびデバッグ ログ**オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="52da0-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="52da0-131">有効にする、**分析**ログ。</span><span class="sxs-lookup"><span data-stu-id="52da0-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="52da0-132">イベント ビューアーのツリー ビューでに移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し、。**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="52da0-133">右クリック**分析**選択**ログの有効化**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="52da0-134">サービスをテストするには</span><span class="sxs-lookup"><span data-stu-id="52da0-134">To test the service</span></span>

1. <span data-ttu-id="52da0-135">WCF テスト クライアントに戻ると、ダブルクリックして`Divide`分母を 0、既定値を保持しているとします。</span><span class="sxs-lookup"><span data-stu-id="52da0-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="52da0-136">分母が 0 の場合、サービスからエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="52da0-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="52da0-137">サービスから出力されたイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="52da0-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="52da0-138">イベント ビューアーに戻りに移動**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し、**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="52da0-139">右クリック**分析**選択**更新**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="52da0-140">WCF 分析トレースのイベントがイベント ビューアーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="52da0-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="52da0-141">サービスからエラーがスローされたため、イベント ビューアーにエラー トレース イベントが表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="52da0-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="52da0-142">手順 1. と 2. を繰り返します。ただし、今度は有効な入力値を指定します。</span><span class="sxs-lookup"><span data-stu-id="52da0-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="52da0-143">`N2` パラメーターの値は、0 以外であれば任意の数字でかまいません。</span><span class="sxs-lookup"><span data-stu-id="52da0-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="52da0-144">分析チャネルを更新して、WCF イベントにエラー イベントが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="52da0-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="52da0-145">このサンプルでは、WCF サービスから出力される分析トレース イベントを示します。</span><span class="sxs-lookup"><span data-stu-id="52da0-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="52da0-146">クリーンアップするには (省略可能)</span><span class="sxs-lookup"><span data-stu-id="52da0-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="52da0-147">イベント ビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="52da0-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="52da0-148">移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="52da0-149">右クリック**分析**選択**ログの無効化**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="52da0-150">移動します**イベント ビューアー**、 **Applications and Services Logs**、 **Microsoft**、 **Windows**、し**アプリケーション サーバー-アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="52da0-151">右クリック**分析**選択**ログの消去**します。</span><span class="sxs-lookup"><span data-stu-id="52da0-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="52da0-152">選択、**オフ**イベントを消去するオプション。</span><span class="sxs-lookup"><span data-stu-id="52da0-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="52da0-153">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="52da0-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="52da0-154">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="52da0-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="52da0-155">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="52da0-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="52da0-156">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="52da0-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="52da0-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="52da0-157">See also</span></span>

- [<span data-ttu-id="52da0-158">AppFabric の監視のサンプル</span><span class="sxs-lookup"><span data-stu-id="52da0-158">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
