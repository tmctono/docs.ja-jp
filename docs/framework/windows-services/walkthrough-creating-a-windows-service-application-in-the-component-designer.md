---
title: Visual Studio で Windows サービス アプリケーションを作成する
ms.date: 09/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: 52c2f64bbb71e07dcab1fd7cd42662f9ed2c8445
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665031"
---
# <a name="walkthrough-create-a-windows-service-app"></a><span data-ttu-id="1ed72-102">チュートリアル: Windows サービス アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="1ed72-102">Walkthrough: Create a Windows service app</span></span>

<span data-ttu-id="1ed72-103">この記事では、イベント ログにメッセージを書き込む単純な Windows サービス アプリを Visual Studio で作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-103">This article demonstrates how to create a simple Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="1ed72-104">サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="1ed72-104">Create a service</span></span>

<span data-ttu-id="1ed72-105">最初に、プロジェクトを作成し、サービスが正しく機能するために必要な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-105">To begin, create the project and set values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="1ed72-106">Visual Studio のメニュー バーで、**[ファイル]** > **[新規]** > **[プロジェクト]** を選択して (または **Ctrl**+**Shift**+**N** を押して)、**[新しいプロジェクト]** ダイアログを開きます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-106">In Visual Studio, on the menu bar, choose **File** > **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** dialog.</span></span>

2. <span data-ttu-id="1ed72-107">**[Windows サービス]** プロジェクト テンプレートに移動して選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-107">Navigate to and select the **Windows Service** project template.</span></span> <span data-ttu-id="1ed72-108">**[インストール済み]** **[Visual C#** または **Visual Basic]** **[Windows Desktop]** の順に展開するか、右上の検索ボックスに「**Windows サービス**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-108">Expand **Installed** > [**Visual C#** or **Visual Basic**] > **Windows Desktop**, or type **Windows Service** in the search box on the upper right.</span></span>

   ![Visual Studio の [新しいプロジェクト] ダイアログの Windows サービス アプリ テンプレート](media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="1ed72-110">**[Windows サービス]** テンプレートが表示されない場合は、**.NET デスクトップ開発** ワークロードのインストールが必要である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-110">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload.</span></span> <span data-ttu-id="1ed72-111">**[新しいプロジェクト]** ダイアログで、左下にある **[Visual Studio インストーラーを開く]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ed72-111">In the **New Project** dialog, click the link that says **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="1ed72-112">**Visual Studio インストーラー**で、**[.NET デスクトップ開発]** ワークロードを選択し、**[変更]** ボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-112">In **Visual Studio Installer**, select the **.NET desktop development** workload and then choose **Modify**.</span></span>

3. <span data-ttu-id="1ed72-113">プロジェクトに **MyNewService** という名前を付け、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-113">Name the project **MyNewService**, and then choose **OK**.</span></span>

   <span data-ttu-id="1ed72-114">プロジェクト テンプレートには、<xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> から継承される `Service1` という名前のコンポーネント クラスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-114">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1ed72-115">それは、サービスを開始するコードなどの多数の基本的なサービス コードを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-115">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="1ed72-116">サービスの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="1ed72-116">Rename the service</span></span>

<span data-ttu-id="1ed72-117">サービスの名前を **Service1** から **MyNewService** に変更します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-117">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="1ed72-118">Service1.cs (または Service1.vb) の **[デザイン]** ビューで、**コード ビューに切り替える**ためのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ed72-118">In the **Design** view for Service1.cs (or Service1.vb), click the link to **switch to code view**.</span></span> <span data-ttu-id="1ed72-119">**[Service1]** を右クリックし、コンテキスト メニューから **[名前の変更]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-119">Right-click on **Service1** and select **Rename** from the context menu.</span></span> <span data-ttu-id="1ed72-120">「**MyNewService**」と入力し、**Enter** キーを押すか **[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ed72-120">Enter **MyNewService** and then press **Enter** or click **Apply**.</span></span>

2. <span data-ttu-id="1ed72-121">**Service1.cs の [デザイン]** または **Service1.vb の [デザイン]** の **[プロパティ]** ウィンドウで、**ServiceName** の値を **MyNewService** に変更します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-121">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, change the **ServiceName** value to **MyNewService**.</span></span>

3. <span data-ttu-id="1ed72-122">**ソリューション エクスプローラー**で、**Service1.cs** を **MyNewService.cs** に、または **Service1.vb** を **MyNewService.vb** に変更します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-122">In **Solution Explorer**, rename **Service1.cs** to **MyNewService.cs**, or rename **Service1.vb** to **MyNewService.vb**.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="1ed72-123">サービスに機能を追加する</span><span class="sxs-lookup"><span data-stu-id="1ed72-123">Add features to the service</span></span>

<span data-ttu-id="1ed72-124">このセクションでは、Windows サービスにカスタム イベント ログを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-124">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="1ed72-125">イベント ログは、Windows サービスとまったく関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="1ed72-125">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="1ed72-126">ここでは、Windows サービスに追加できるコンポーネントの種類の例として、<xref:System.Diagnostics.EventLog> コンポーネントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1ed72-126">The <xref:System.Diagnostics.EventLog> component is used here as an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="1ed72-127">サービスにカスタム イベント ログ機能を追加する</span><span class="sxs-lookup"><span data-stu-id="1ed72-127">Add custom event log functionality</span></span>

1. <span data-ttu-id="1ed72-128">**ソリューション エクスプローラー**で、 **MyNewService.cs** または **MyNewService.vb**のコンテキスト メニューを開き、 **[デザイナーの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-128">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="1ed72-129">**[ツールボックス]** の **[コンポーネント]** セクションから、 <xref:System.Diagnostics.EventLog> コンポーネントをデザイナーにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="1ed72-129">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>

3. <span data-ttu-id="1ed72-130">**ソリューション エクスプローラー**で、 **MyNewService.cs** または **MyNewService.vb**のコンテキスト メニューを開き、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-130">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>

4. <span data-ttu-id="1ed72-131">カスタム イベント ログを定義するコンストラクターを編集します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-131">Edit the constructor to define a custom event log:</span></span>

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new System.Diagnostics.EventLog();
        if (!System.Diagnostics.EventLog.SourceExists("MySource"))
        {
            System.Diagnostics.EventLog.CreateEventSource(
                "MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="1ed72-132">サービスの開始時の処理を定義する</span><span class="sxs-lookup"><span data-stu-id="1ed72-132">Define what occurs when the service starts</span></span>

<span data-ttu-id="1ed72-133">コード エディターで、プロジェクトの作成時に自動的にオーバーライドされた <xref:System.ServiceProcess.ServiceBase.OnStart%2A> を見つけます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-133">In the code editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project.</span></span> <span data-ttu-id="1ed72-134">サービスの開始時にイベント ログに対するエントリーを記述するコード行を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-134">Add a line of code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

<span data-ttu-id="1ed72-135">サービス アプリケーションは長期間実行するように設計されているため、通常は、システム内の何かをポーリングまたは監視しています。</span><span class="sxs-lookup"><span data-stu-id="1ed72-135">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="1ed72-136">この監視は、 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドで設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-136">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="1ed72-137">ただし、 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> は実際には監視を行いません。</span><span class="sxs-lookup"><span data-stu-id="1ed72-137">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="1ed72-138"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドは、サービスの操作が開始された後にオペレーティング システムに戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-138">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="1ed72-139">永久的に続くループやブロックは実行できません。</span><span class="sxs-lookup"><span data-stu-id="1ed72-139">It must not loop forever or block.</span></span> <span data-ttu-id="1ed72-140">簡単なポーリング メカニズムをセットアップするには、次のように <xref:System.Timers.Timer?displayProperty=nameWithType> コンポーネントを使用できます。<xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドで、コンポーネントにパラメーターを設定してから、<xref:System.Timers.Timer.Enabled%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-140">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="1ed72-141">このタイマーによって、コード内で定期的にイベントが発生します。サービスは、イベントが発生するごとに監視を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-141">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="1ed72-142">このためには、次のコードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-142">You can use the following code to do this:</span></span>

```csharp
// Set up a timer that triggers every minute.
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 60000; // 60 seconds
timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);
timer.Start();
```

```vb
' Set up a timer that triggers every minute.
Dim timer As System.Timers.Timer = New System.Timers.Timer()
timer.Interval = 60000 ' 60 seconds
AddHandler timer.Elapsed, AddressOf Me.OnTimer
timer.Start()
```

<span data-ttu-id="1ed72-143">メンバー変数をクラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-143">Add a member variable to the class.</span></span> <span data-ttu-id="1ed72-144">それには、イベント ログに書き込まれる次のイベントの識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-144">It contains the identifier of the next event to write into the event log.</span></span>

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

<span data-ttu-id="1ed72-145">タイマー イベントを処理する新しいコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-145">Add a new method to handle the timer event:</span></span>

```csharp
public void OnTimer(object sender, System.Timers.ElapsedEventArgs args)
{
    // TODO: Insert monitoring activities here.
    eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);
}
```

```vb
Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)
    ' TODO: Insert monitoring activities here.
    eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)
    eventId = eventId + 1
End Sub
```

<span data-ttu-id="1ed72-146">メイン スレッドですべての作業を実行するのではなく、バックグラウンド ワーカー スレッドを使用してタスクを実行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-146">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="1ed72-147">詳細については、「<xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-147">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="1ed72-148">サービスの停止時の処理を定義する</span><span class="sxs-lookup"><span data-stu-id="1ed72-148">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="1ed72-149">サービスの停止時にイベント ログに対するエントリーを追加するコード行を <xref:System.ServiceProcess.ServiceBase.OnStop%2A> に追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-149">Add a line of code to the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="1ed72-150">サービスに対して他の処理を定義する</span><span class="sxs-lookup"><span data-stu-id="1ed72-150">Define other actions for the service</span></span>

<span data-ttu-id="1ed72-151"><xref:System.ServiceProcess.ServiceBase.OnPause%2A>、<xref:System.ServiceProcess.ServiceBase.OnContinue%2A>、および <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> の各メソッドをオーバーライドして、コンポーネントの処理をさらに定義できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-151">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span> <span data-ttu-id="1ed72-152">次のコード例は、 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> メソッドをオーバーライドする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1ed72-152">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

<span data-ttu-id="1ed72-153">いくつかのカスタム動作は、Windows サービスが <xref:System.Configuration.Install.Installer> クラスによりインストールされるときに発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-153">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="1ed72-154">Visual Studio は、これらのインストーラーを Windows サービス専用に作成し、プロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-154">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>

## <a name="set-service-status"></a><span data-ttu-id="1ed72-155">サービスの状態を設定する</span><span class="sxs-lookup"><span data-stu-id="1ed72-155">Set service status</span></span>

<span data-ttu-id="1ed72-156">サービスは、その状態をサービス コントロール マネージャーに報告します。これによりユーザーは、サービスが正常に機能しているかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-156">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="1ed72-157">既定では、 <xref:System.ServiceProcess.ServiceBase> を継承するサービスは、[停止]、[一時停止]、[実行中] など、限られた状態設定のセットを報告します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-157">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="1ed72-158">サービスの開始に若干時間がかかるときは、[保留の開始] 状態を報告すると役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-158">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="1ed72-159">[保留の開始] と [保留の停止] の状態設定は、Windows の [SetServiceStatus 関数](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)を呼び出すコードを追加することによって実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-159">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus).</span></span>

<span data-ttu-id="1ed72-160">サービス保留の状態を実装するには:</span><span class="sxs-lookup"><span data-stu-id="1ed72-160">To implement service pending status:</span></span>

1. <span data-ttu-id="1ed72-161"><xref:System.Runtime.InteropServices?displayProperty=nameWithType> 名前空間に対する `using` ステートメントまたは `Imports` 宣言を MyNewService.cs ファイルまたは MyNewService.vb ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-161">Add a `using` statement or `Imports` declaration for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="1ed72-162">MyNewService.cs に次のコードを追加して、 `ServiceState` の値を宣言し、プラットフォーム呼び出しで使用する状態の構造を追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-162">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

    ```csharp
    public enum ServiceState
    {
        SERVICE_STOPPED = 0x00000001,
        SERVICE_START_PENDING = 0x00000002,
        SERVICE_STOP_PENDING = 0x00000003,
        SERVICE_RUNNING = 0x00000004,
        SERVICE_CONTINUE_PENDING = 0x00000005,
        SERVICE_PAUSE_PENDING = 0x00000006,
        SERVICE_PAUSED = 0x00000007,
    }

    [StructLayout(LayoutKind.Sequential)]
    public struct ServiceStatus
    {
        public int dwServiceType;
        public ServiceState dwCurrentState;
        public int dwControlsAccepted;
        public int dwWin32ExitCode;
        public int dwServiceSpecificExitCode;
        public int dwCheckPoint;
        public int dwWaitHint;
    };
    ```

    ```vb
    Public Enum ServiceState
        SERVICE_STOPPED = 1
        SERVICE_START_PENDING = 2
        SERVICE_STOP_PENDING = 3
        SERVICE_RUNNING = 4
        SERVICE_CONTINUE_PENDING = 5
        SERVICE_PAUSE_PENDING = 6
        SERVICE_PAUSED = 7
    End Enum

    <StructLayout(LayoutKind.Sequential)>
    Public Structure ServiceStatus
        Public dwServiceType As Long
        Public dwCurrentState As ServiceState
        Public dwControlsAccepted As Long
        Public dwWin32ExitCode As Long
        Public dwServiceSpecificExitCode As Long
        Public dwCheckPoint As Long
        Public dwWaitHint As Long
    End Structure
    ```

3. <span data-ttu-id="1ed72-163">次に、`MyNewService` クラスで、[プラットフォーム呼び出し](../interop/consuming-unmanaged-dll-functions.md)を使用して、[SetServiceStatus 関数](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)を宣言します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-163">Now, in the `MyNewService` class, declare the [SetServiceStatus function](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="1ed72-164">[保留の開始] 状態を実装するには、 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドの先頭に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-164">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

    ```csharp
    // Update the service state to Start Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Start Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

5. <span data-ttu-id="1ed72-165"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドの末尾に、状態を [実行中] に設定するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-165">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>

    ```csharp
    // Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Running.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING
    SetServiceStatus(Me.ServiceHandle, serviceStatus)
    ```

6. <span data-ttu-id="1ed72-166">(省略可能) <xref:System.ServiceProcess.ServiceBase.OnStop%2A> メソッドに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-166">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed72-167">[サービス コントロール マネージャー](/windows/desktop/Services/service-control-manager)は、[SERVICE_STATUS 構造体](/windows/desktop/api/winsvc/ns-winsvc-_service_status)の `dwWaitHint` メンバーと `dwCheckpoint` メンバーを使って、Windows サービスの開始やシャットダウンまでの待機時間を判断します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-167">The [Service Control Manager](/windows/desktop/Services/service-control-manager) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/desktop/api/winsvc/ns-winsvc-_service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="1ed72-168"><xref:System.ServiceProcess.ServiceBase.OnStart%2A> メソッドと <xref:System.ServiceProcess.ServiceBase.OnStop%2A> メソッドが長時間実行している場合、サービスは、インクリメントした `dwCheckPoint` 値で [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) をもう一度呼び出すことによって、追加の時間を要求できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-168">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) again with an incremented `dwCheckPoint` value.</span></span>

## <a name="add-installers-to-the-service"></a><span data-ttu-id="1ed72-169">サービスにインストーラーを追加する</span><span class="sxs-lookup"><span data-stu-id="1ed72-169">Add installers to the service</span></span>

<span data-ttu-id="1ed72-170">Windows サービスを実行するには、まず、サービスをインストールする必要があります。これにより、サービスがサービス コントロール マネージャーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-170">Before you can run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="1ed72-171">登録の詳細を処理するインストーラーをプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-171">You can add installers to your project that handle the registration details.</span></span>

1. <span data-ttu-id="1ed72-172">**ソリューション エクスプローラー**で、 **MyNewService.cs** または **MyNewService.vb**のコンテキスト メニューを開き、 **[デザイナーの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-172">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>

2. <span data-ttu-id="1ed72-173">デザイナーの背景をクリックして、サービスの内容ではなくサービス自体を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-173">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>

3. <span data-ttu-id="1ed72-174">デザイナー ウィンドウのコンテキスト メニューを開き (ポインティング デバイスを使用している場合は、ウィンドウ内を右クリック)、 **[インストーラーの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-174">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>

   <span data-ttu-id="1ed72-175">既定では、2 つのインストーラーを含むコンポーネント クラスがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-175">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="1ed72-176">このコンポーネントは **ProjectInstaller**という名前で、サービス用のインストーラーと、サービスの関連プロセス用のインストーラーを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-176">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>

4. <span data-ttu-id="1ed72-177">**[ProjectInstaller]** の **[デザイン]** ビューで、 **[serviceInstaller1]** (Visual C# プロジェクトの場合) または **[ServiceInstaller1]** (Visual Basic プロジェクトの場合) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-177">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>

5. <span data-ttu-id="1ed72-178">**[プロパティ]** ウィンドウで、 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> プロパティが **MyNewService**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-178">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

6. <span data-ttu-id="1ed72-179">**[説明]** プロパティに、「A sample service」などのテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-179">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="1ed72-180">このテキストは [サービス] ウィンドウに表示されます。これによりユーザーは、サービスを識別したり、その用途を理解したりできます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-180">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>

7. <span data-ttu-id="1ed72-181"><xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> プロパティに、[サービス] ウィンドウの **[名前]** 列に表示するテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-181">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="1ed72-182">たとえば、「MyNewService Display Name」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-182">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="1ed72-183">この名前は、システムによって使用される (たとえば、 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> コマンドを使用してサービスを開始する場合) 名前である `net start` プロパティとは異なる名前にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-183">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>

8. <span data-ttu-id="1ed72-184"><xref:System.ServiceProcess.ServiceInstaller.StartType%2A> プロパティを <xref:System.ServiceProcess.ServiceStartMode.Automatic>に設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-184">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>

     <span data-ttu-id="1ed72-185">![Windows サービスのインストーラー プロパティ](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span><span class="sxs-lookup"><span data-stu-id="1ed72-185">![Installer Properties for a Windows service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>

9. <span data-ttu-id="1ed72-186">デザイナーで、 **[serviceProcessInstaller1]** (Visual C# プロジェクトの場合) または **[ServiceProcessInstaller1]** (Visual Basic プロジェクトの場合) を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-186">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="1ed72-187"><xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> プロパティを <xref:System.ServiceProcess.ServiceAccount.LocalSystem>に設定します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-187">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="1ed72-188">これにより、サービスがインストールされ、ローカル システム アカウントを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-188">This causes the service to be installed and to run using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1ed72-189"><xref:System.ServiceProcess.ServiceAccount.LocalSystem> アカウントには、イベント ログへの書き込みを含む、幅広いアクセス許可が設定されています。</span><span class="sxs-lookup"><span data-stu-id="1ed72-189">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="1ed72-190">このアカウントは悪意のあるソフトウェアから攻撃されるリスクが高いため、使用する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ed72-190">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="1ed72-191">その他のタスクについては、ローカル コンピューターで非特権ユーザーとして機能し、リモート サーバーには匿名の資格情報を渡す <xref:System.ServiceProcess.ServiceAccount.LocalService> アカウントの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-191">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="1ed72-192">この例は、 <xref:System.ServiceProcess.ServiceAccount.LocalService> アカウントを使用しようとすると失敗します。これは、イベント ログに書き込むアクセス許可が必要になるためです。</span><span class="sxs-lookup"><span data-stu-id="1ed72-192">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="1ed72-193">インストーラーについて詳しくは、「[方法: サービス アプリケーションにインストーラーを追加する](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-193">For more information about installers, see [How to: Add Installers to Your service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="1ed72-194">(省略可能) スタートアップ パラメーターを設定する</span><span class="sxs-lookup"><span data-stu-id="1ed72-194">(Optional) Set startup parameters</span></span>

<span data-ttu-id="1ed72-195">Windows サービスは、他の実行可能ファイルと同じように、コマンド ライン引数 (スタートアップ パラメーター) を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-195">A Windows service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="1ed72-196">スタートアップ パラメーターを処理するコードを追加すると、ユーザーは、Windows のコントロール パネルの [サービス] ウィンドウを使用して、カスタムのスタートアップ パラメーターによりサービスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-196">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="1ed72-197">ただし、これらのスタートアップ パラメーターは、次回のサービスの開始時には保持されません。</span><span class="sxs-lookup"><span data-stu-id="1ed72-197">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="1ed72-198">スタートアップ パラメーターを永続的に設定するために、次の手順で示すようにレジストリに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-198">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed72-199">スタートアップ パラメーターを追加するよう決定する前に、これがサービスに情報を渡す最適な方法であるかどうかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-199">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="1ed72-200">スタートアップ パラメーターの使用や解析は簡単であり、ユーザーが簡単にオーバーライドできますが、ドキュメントなしでは検索や使用が困難である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-200">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="1ed72-201">一般的に、サービスに必要なスタートアップ パラメーターが複数ある場合は、代わりにレジストリまたは構成ファイルの使用を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-201">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="1ed72-202">すべての Windows サービスのレジストリのエントリは、**HKLM\System\CurrentControlSet\services** にあります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-202">Every Windows service has an entry in the registry under **HKLM\System\CurrentControlSet\services**.</span></span> <span data-ttu-id="1ed72-203">サービスのキーで、 **Parameters** サブキーを使用して、サービスがアクセスできる情報を格納することができます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-203">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="1ed72-204">その他の種類のプログラムの場合と同じ方法で、Windows サービスに対してアプリケーション構成ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-204">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="1ed72-205">コード例については、「 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-205">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>

<span data-ttu-id="1ed72-206">スタートアップ パラメーターを追加するには:</span><span class="sxs-lookup"><span data-stu-id="1ed72-206">To add startup parameters:</span></span>

1. <span data-ttu-id="1ed72-207">Program.cs または MyNewService.Designer.vb の `Main` メソッドに、サービスのコンス トラクターに渡す入力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-207">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an input parameter to pass to the service constructor:</span></span>

   ```csharp
   static void Main(string[] args)
   {
       ServiceBase[] ServicesToRun;
       ServicesToRun = new ServiceBase[]
       {
           new MyNewService(args)
       };
       ServiceBase.Run(ServicesToRun);
   }
   ```

   ```vb
   Shared Sub Main(ByVal cmdArgs() As String)
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. <span data-ttu-id="1ed72-208">`MyNewService` コンストラクターを次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-208">Change the `MyNewService` constructor as follows:</span></span>

   ```csharp
   public MyNewService(string[] args)
   {
       InitializeComponent();

        string eventSourceName = "MySource";
        string logName = "MyNewLog";

        if (args.Length > 0)
        {
            eventSourceName = args[0];
        }

        if (args.Length > 1)
        {
            logName = args[1];
        }

        eventLog1 = new System.Diagnostics.EventLog();

        if (!System.Diagnostics.EventLog.SourceExists(eventSourceName))
        {
            System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName);
        }

        eventLog1.Source = eventSourceName;
        eventLog1.Log = logName;
   }
   ```

   ```vb
   Public Sub New(ByVal cmdArgs() As String)
       InitializeComponent()
       Dim eventSourceName As String = "MySource"
       Dim logName As String = "MyNewLog"
       If (cmdArgs.Count() > 0) Then
           eventSourceName = cmdArgs(0)
       End If
       If (cmdArgs.Count() > 1) Then
           logName = cmdArgs(1)
       End If
       eventLog1 = New System.Diagnostics.EventLog()
       If (Not System.Diagnostics.EventLog.SourceExists(eventSourceName)) Then
           System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="1ed72-209">このコードでは、指定したスタートアップ パラメーターに従ってイベント ソースとログ名が設定されるか、引数を指定しなかった場合は既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-209">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>

3. <span data-ttu-id="1ed72-210">コマンド ライン引数を指定するには、ProjectInstaller.cs または ProjectInstaller.vb の `ProjectInstaller` クラスに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-210">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>

   ```csharp
   protected override void OnBeforeInstall(IDictionary savedState)
   {
       string parameter = "MySource1\" \"MyLogFile1";
       Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
       base.OnBeforeInstall(savedState);
   }
   ```

   ```vb
   Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
       Dim parameter As String = "MySource1"" ""MyLogFile1"
       Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
       MyBase.OnBeforeInstall(savedState)
   End Sub
   ```

   <span data-ttu-id="1ed72-211">このコードでは、既定のパラメーター値を追加することによって、一般的に Windows サービスの実行可能ファイルへの完全パスが含まれる **ImagePath** レジストリ キーが変更されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-211">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows service, by adding the default parameter values.</span></span> <span data-ttu-id="1ed72-212">サービスが正しく開始されるためには、パス (およびそれぞれ個々のパラメーター) を囲む引用符が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ed72-212">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="1ed72-213">この Windows サービスのスタートアップ パラメーターを変更するために、ユーザーは、**ImagePath** レジストリ キーで指定されたパラメーターを変更できます。ただし、パラメーターをプログラムによって変更し、ユーザーに対してはわかりやすい方法 (たとえば、管理ユーティリティや構成ユーティリティ) で機能を示すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1ed72-213">To change the startup parameters for this Windows service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>

## <a name="build-the-service"></a><span data-ttu-id="1ed72-214">サービスをビルドする</span><span class="sxs-lookup"><span data-stu-id="1ed72-214">Build the service</span></span>

1. <span data-ttu-id="1ed72-215">**ソリューション エクスプローラー**で、プロジェクトのコンテキスト メニューを開き、 **[プロパティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-215">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span>

   <span data-ttu-id="1ed72-216">プロジェクトのプロパティ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-216">The property pages for your project appear.</span></span>

2. <span data-ttu-id="1ed72-217">**[アプリケーション]** タブで、**[スタートアップ オブジェクト]** ボックスの一覧の **[MyNewService.Program]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-217">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>

3. <span data-ttu-id="1ed72-218">**ソリューション エクスプローラー**で、プロジェクトのコンテキスト メニューを開き、**[ビルド]** を選択してプロジェクトをビルドします (または **Ctrl**+**Shift**+**B**を押します)。</span><span class="sxs-lookup"><span data-stu-id="1ed72-218">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="1ed72-219">サービスをインストールする</span><span class="sxs-lookup"><span data-stu-id="1ed72-219">Install the service</span></span>

<span data-ttu-id="1ed72-220">Windows サービスを構築済みであるため、サービスをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-220">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="1ed72-221">Windows サービスをインストールするには、インストール先のコンピューターの管理者資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ed72-221">To install a Windows service, you must have administrator credentials on the computer on which you're installing it.</span></span>

1. <span data-ttu-id="1ed72-222">管理者資格情報を使用して、**Visual Studio 用開発者コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-222">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span> <span data-ttu-id="1ed72-223">マウスを使用している場合は、Windows の [スタート] メニューから **[Developer Command Prompt for VS 2017]/(VS 2017 用開発者コマンド プロンプト/)** を右クリックし、**[その他]** > **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-223">If you’re using a mouse, right-click on **Developer Command Prompt for VS 2017** in the Windows Start menu, and then choose **More** > **Run as Administrator**.</span></span>

2. <span data-ttu-id="1ed72-224">**[開発者コマンド プロンプト]** ウィンドウで、プロジェクトの出力を含むフォルダーに移動します (既定では、プロジェクトの *\bin\Debug* サブディレクトリです)。</span><span class="sxs-lookup"><span data-stu-id="1ed72-224">In the **Developer Command Prompt** window, navigate to the folder that contains your project's output (by default, it's the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="1ed72-225">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-225">Enter the following command:</span></span>

    ```shell
    installutil.exe MyNewService.exe
    ```

    <span data-ttu-id="1ed72-226">サービスが正常にインストールされると、正常に実行されたことが **installutil.exe** によって報告されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-226">If the service installs successfully, **installutil.exe** reports success.</span></span> <span data-ttu-id="1ed72-227">システムが **InstallUtil.exe** が見付けることができなかった場合は、コンピューター上に存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-227">If the system could not find **InstallUtil.exe**, make sure that it exists on your computer.</span></span> <span data-ttu-id="1ed72-228">このツールは、.NET Framework と共に *%windir%\Microsoft.NET\Framework[64]\\[framework version]* フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-228">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\[framework version]*.</span></span> <span data-ttu-id="1ed72-229">たとえば、32 ビット バージョンでの既定のパスは *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe* です。</span><span class="sxs-lookup"><span data-stu-id="1ed72-229">For example, the default path for the 32-bit version is *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="1ed72-230">**installutil.exe** プロセスでエラーが報告された場合は、インストール ログを調べて理由を確認します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-230">If the **installutil.exe** process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="1ed72-231">既定で、ログはサービスの実行可能ファイルと同じフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-231">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="1ed72-232"><xref:System.ComponentModel.RunInstallerAttribute> クラスが `ProjectInstaller` クラスにない場合、属性が **true** に設定されていない場合、または `ProjectInstaller` クラスが **public** とマークされていない場合は、インストールが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ed72-232">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, if the attribute is not set to **true**, or if the `ProjectInstaller` class is not marked **public**.</span></span>

<span data-ttu-id="1ed72-233">詳細については、「[方法 :サービスをインストールおよびアンインストールする](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-233">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="1ed72-234">サービスを開始して実行する</span><span class="sxs-lookup"><span data-stu-id="1ed72-234">Start and run the service</span></span>

1. <span data-ttu-id="1ed72-235">Windows で、**[サービス]** デスクトップ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-235">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="1ed72-236">**Windows**+**R** を押して **[ファイル名を指定して実行]** ボックスを開き、「**services.msc**」と入力して、**Enter** を押すか **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ed72-236">Press **Windows**+**R** to open the **Run** box, and then enter **services.msc** and press **Enter** or click **OK**.</span></span>

     <span data-ttu-id="1ed72-237">**[サービス]** 内にサービスが一覧表示されます。サービスは、サービスに対して設定した表示名でアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-237">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![[サービス] ウィンドウの MyNewService。](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="1ed72-239">**[サービス]** で、サービスのショートカット メニューを開き、**[開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-239">In **Services**, open the shortcut menu for your service, and then choose **Start**.</span></span>

3. <span data-ttu-id="1ed72-240">サービスを停止するには、サービスのショートカット メニューを開き、**[停止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-240">To stop the service, open the shortcut menu for the service, and then choose **Stop**.</span></span>

4. <span data-ttu-id="1ed72-241">(省略可能) コマンド ラインから `net start ServiceName` コマンドと `net stop ServiceName` コマンドを使用することで、サービスの開始と停止を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-241">(Optional) From the command line, you can use the commands `net start ServiceName` and `net stop ServiceName` to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="1ed72-242">サービスのイベント ログ出力を確認する</span><span class="sxs-lookup"><span data-stu-id="1ed72-242">Verify the event log output of your service</span></span>

1. <span data-ttu-id="1ed72-243">Windows タスクバーの検索ボックスに**イベント ビューア―** というテキストの入力を開始し、検索結果から **[イベント ビューア―]** を選択することで、**イベント ビューアー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-243">Open **Event Viewer** by starting to type **Event Viewer** in the search box on the Windows task bar, and then selecting **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="1ed72-244">Visual Studio でイベント ログにアクセスするには、**サーバー エクスプローラー**を開き (キーボード: **Ctrl** + **Alt** + **S**)、ローカル コンピューターの **[イベント ログ]** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-244">In Visual Studio, you can access event logs by opening **Server Explorer** (Keyboard: **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="1ed72-245">**[イベント ビューアー]** で、**[アプリケーションとサービス ログ]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-245">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="1ed72-246">**MyNewLog** (または、省略可能な手順に従ってコマンド ライン引数を追加した場合は **MyLogFile1**) の一覧を見つけて展開します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-246">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you followed the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="1ed72-247">サービスが実行した 2 つの操作 (開始および停止) のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-247">You should see entries for the two actions (start and stop) that your service performed.</span></span>

     ![イベント ビューアーを使用してイベント ログの項目を表示する](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a><span data-ttu-id="1ed72-249">サービスをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="1ed72-249">Uninstall the service</span></span>

1. <span data-ttu-id="1ed72-250">管理者資格情報を使用して、**Visual Studio 用開発者コマンド プロンプト**を開きます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-250">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="1ed72-251">コマンド プロンプト ウィンドウで、プロジェクトの出力が格納されているフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-251">In the command prompt window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="1ed72-252">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1ed72-252">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="1ed72-253">サービスが正常にアンインストールされると、サービスが正常に削除されたことが **installutil.exe** によって報告されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-253">If the service uninstalls successfully, **installutil.exe** reports that your service was successfully removed.</span></span> <span data-ttu-id="1ed72-254">詳細については、「[方法 :サービスをインストールおよびアンインストールする](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-254">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1ed72-255">次の手順</span><span class="sxs-lookup"><span data-stu-id="1ed72-255">Next steps</span></span>

<span data-ttu-id="1ed72-256">これでサービスの作成は終わりましたが、作成した Windows サービスを他のユーザーがインストールするために使用できるスタンドアロン セットアップ プログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-256">Now that you've created the service, you might want to create a standalone setup program that others can use to install your Windows service.</span></span> <span data-ttu-id="1ed72-257">ClickOnce ではWindows サービスはサポートされませんが、[WiX Toolset](http://wixtoolset.org/) を使用して Windows サービス用のインストーラーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-257">ClickOnce doesn't support Windows services, but you can use the [WiX Toolset](http://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="1ed72-258">その他のアイデアについては、[インストーラー パッケージの作成](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-258">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

<span data-ttu-id="1ed72-259">インストールしたサービスにコマンドを送信できる <xref:System.ServiceProcess.ServiceController> コンポーネントの使用法を調べることもできます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-259">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

<span data-ttu-id="1ed72-260">インストーラーを使用すると、アプリケーションの実行時にイベント ログを作成する代わりに、アプリケーションのインストール時にイベント ログを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-260">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="1ed72-261">さらに、イベント ログは、アプリケーションがアンインストールされたときにインストーラーによって削除されます。</span><span class="sxs-lookup"><span data-stu-id="1ed72-261">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="1ed72-262">詳細については、 <xref:System.Diagnostics.EventLogInstaller> のリファレンス ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ed72-262">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ed72-263">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ed72-263">See also</span></span>

- [<span data-ttu-id="1ed72-264">Windows サービス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1ed72-264">Windows service applications</span></span>](../../../docs/framework/windows-services/index.md)
- [<span data-ttu-id="1ed72-265">Windows サービス アプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="1ed72-265">Introduction to Windows service applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="1ed72-266">方法: Windows サービス アプリケーションをデバッグする</span><span class="sxs-lookup"><span data-stu-id="1ed72-266">How to: Debug Windows service applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="1ed72-267">サービス (Windows)</span><span class="sxs-lookup"><span data-stu-id="1ed72-267">Services (Windows)</span></span>](/windows/desktop/Services/services)
