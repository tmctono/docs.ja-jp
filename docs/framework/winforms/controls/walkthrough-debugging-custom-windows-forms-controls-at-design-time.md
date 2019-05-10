---
title: 'チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: a8f228d334785cd880b06dbeda8f96550471599a
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211544"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="8aaac-102">チュートリアル: カスタム Windows フォーム コントロールのデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="8aaac-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="8aaac-103">カスタム コントロールを作成するときに多くの場合、表示されますが、デザイン時の動作をデバッグするために必要です。</span><span class="sxs-lookup"><span data-stu-id="8aaac-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="8aaac-104">これは、カスタム コントロールのカスタム デザイナーを作成する場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="8aaac-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="8aaac-105">詳細については、次を参照してください。[チュートリアル。Visual Studio のデザイン時機能を活用したコントロールをフォーム、Windows の作成](creating-a-wf-control-design-time-features.md)です。</span><span class="sxs-lookup"><span data-stu-id="8aaac-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="8aaac-106">その他の .NET Framework のクラスをデバッグする場合と同様に、Visual Studio を使用して、カスタム コントロールをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="8aaac-107">違いは、カスタム コントロールのコードを実行している Visual Studio の別のインスタンスをデバッグすることです。</span><span class="sxs-lookup"><span data-stu-id="8aaac-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>

<span data-ttu-id="8aaac-108">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="8aaac-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="8aaac-109">カスタム コントロールをホストする Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-109">Creating a Windows Forms project to host your custom control</span></span>

- <span data-ttu-id="8aaac-110">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-110">Creating a control library project</span></span>

- <span data-ttu-id="8aaac-111">カスタム コントロールにプロパティを追加</span><span class="sxs-lookup"><span data-stu-id="8aaac-111">Adding a property to your custom control</span></span>

- <span data-ttu-id="8aaac-112">ホストのフォームにカスタム コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-112">Adding your custom control to the host form</span></span>

- <span data-ttu-id="8aaac-113">デザイン時のデバッグ プロジェクトの設定</span><span class="sxs-lookup"><span data-stu-id="8aaac-113">Setting up the project for design-time debugging</span></span>

- <span data-ttu-id="8aaac-114">カスタム コントロールをデザイン時のデバッグ</span><span class="sxs-lookup"><span data-stu-id="8aaac-114">Debugging your custom control at design time</span></span>

<span data-ttu-id="8aaac-115">完了したら、カスタム コントロールのデザイン時の動作をデバッグするために必要な作業について理解があります。</span><span class="sxs-lookup"><span data-stu-id="8aaac-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="8aaac-116">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="8aaac-116">Create the project</span></span>

<span data-ttu-id="8aaac-117">最初の手順では、アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-117">The first step is to create the application project.</span></span> <span data-ttu-id="8aaac-118">このプロジェクトを使用すると、カスタム コントロールをホストするアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="8aaac-119">Visual Studio で、"DebuggingExample"と呼ばれる Windows アプリケーション プロジェクトを作成します (**ファイル** > **新規** > **プロジェクト** > **Visual C#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**).</span><span class="sxs-lookup"><span data-stu-id="8aaac-119">In Visual Studio, create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="8aaac-120">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-120">Create the control library project</span></span>

1. <span data-ttu-id="8aaac-121">追加、 **Windows コントロール ライブラリ**プロジェクトがソリューションにします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-121">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="8aaac-122">新しい追加**UserControl** DebugControlLibrary プロジェクトに項目。</span><span class="sxs-lookup"><span data-stu-id="8aaac-122">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="8aaac-123">詳細については、「[方法: 新しいプロジェクト項目の追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-123">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="8aaac-124">新しいソース ファイルに「タブ」の基本の名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-124">Give the new source file a base name of "DebugControl".</span></span>

3. <span data-ttu-id="8aaac-125">使用して、**ソリューション エクスプ ローラー**の基本名を持つコード ファイルを削除することによって、プロジェクトの既定のコントロールを削除"`UserControl1`"。</span><span class="sxs-lookup"><span data-stu-id="8aaac-125">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="8aaac-126">詳細については、「[方法: 削除、削除、および項目を除外](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-126">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

4. <span data-ttu-id="8aaac-127">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-127">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="8aaac-128">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="8aaac-128">Checkpoint</span></span>

<span data-ttu-id="8aaac-129">この時点では、ことができますでカスタム コントロールを表示する、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-129">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="8aaac-130">進行状況を確認するという新しいタブを見つける**DebugControlLibrary コンポーネント** をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-130">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="8aaac-131">開くときに、コントロールが表示されます**タブ**の横にある既定のアイコン。</span><span class="sxs-lookup"><span data-stu-id="8aaac-131">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="8aaac-132">カスタム コントロールにプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-132">Add a property to your custom control</span></span>

<span data-ttu-id="8aaac-133">デザイン時にカスタム コントロールのコードが実行されていることを示すためは、プロパティを追加し、プロパティを実装するコードにブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-133">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="8aaac-134">開いている**タブ**で、**コード エディター**します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-134">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="8aaac-135">クラス定義には、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-135">Add the following code to the class definition:</span></span>

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. <span data-ttu-id="8aaac-136">ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-136">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="8aaac-137">ホストのフォームにカスタム コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-137">Add your custom control to the host form</span></span>

<span data-ttu-id="8aaac-138">カスタム コントロールのデザイン時の動作をデバッグするには、ホストのフォームにカスタム コントロール クラスのインスタンスを配置します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-138">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="8aaac-139">"DebuggingExample"プロジェクトで、Form1 を開き、 **Windows フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-139">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="8aaac-140">**ツールボックス**、オープン、 **DebugControlLibrary コンポーネント**タブし、ドラッグ、**タブ**フォーム上にインスタンス。</span><span class="sxs-lookup"><span data-stu-id="8aaac-140">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="8aaac-141">検索、`DemoString`にカスタム プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="8aaac-141">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="8aaac-142">他のプロパティと同様、その値を変更できますに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8aaac-142">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="8aaac-143">場合にも注意してください、`DemoString`プロパティが選択されている場合の下部にあるプロパティの説明文字列が表示されます、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="8aaac-143">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="8aaac-144">デザイン時のデバッグ プロジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-144">Set up the project for design-time debugging</span></span>

<span data-ttu-id="8aaac-145">カスタム コントロールのデザイン時の動作をデバッグするには、カスタム コントロールのコードを実行している Visual Studio の別のインスタンスをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-145">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="8aaac-146">右クリックし、 **DebugControlLibrary**プロジェクト、**ソリューション エクスプ ローラー**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-146">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="8aaac-147">**DebugControlLibrary**プロパティ シート、**デバッグ**タブ。</span><span class="sxs-lookup"><span data-stu-id="8aaac-147">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="8aaac-148">**開始動作**セクションで、**外部プログラムの開始**します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-148">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="8aaac-149">されますので、省略記号をクリックして、Visual Studio の別のインスタンスをデバッグ (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton"))、Visual Studio IDE を参照するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-149">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="8aaac-150">実行可能ファイルの名前は**devenv.exe**、され、パスは %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe で既定の場所にインストールした場合。</span><span class="sxs-lookup"><span data-stu-id="8aaac-150">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

3. <span data-ttu-id="8aaac-151">**[OK]** をクリックしてダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-151">Click **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="8aaac-152">右クリックし、 **DebugControlLibrary**順に選択して**スタートアップ プロジェクトとして設定**このデバッグ構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-152">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="8aaac-153">デザイン時に、カスタム コントロールをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-153">Debug your custom control at design time</span></span>

<span data-ttu-id="8aaac-154">デザイン モードで実行するときに、カスタム コントロールをデバッグする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="8aaac-154">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="8aaac-155">デバッグ セッションを開始して、Visual Studio の新しいインスタンスを作成は"DebuggingExample"ソリューションの読み込みに使用します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-155">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="8aaac-156">Form1 を開くと、**フォーム デザイナー**、カスタム コントロールのインスタンスが作成され、実行が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-156">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="8aaac-157">開く、**タブ**内のソース ファイル、**コード エディター**にブレークポイントを配置し、`Set`のアクセサー、`DemoString`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="8aaac-157">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="8aaac-158">F5 キーを押して、デバッグ セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-158">Press F5 to start the debugging session.</span></span> <span data-ttu-id="8aaac-159">Visual Studio の新しいインスタンスが作成されたことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8aaac-159">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="8aaac-160">2 つの方法でインスタンスを区別することができます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-160">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="8aaac-161">デバッグ インスタンスが、word**を実行している**のタイトル バーに</span><span class="sxs-lookup"><span data-stu-id="8aaac-161">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="8aaac-162">デバッグ インスタンスが、**開始**のボタンではその**デバッグ**ツールバーを無効になっています</span><span class="sxs-lookup"><span data-stu-id="8aaac-162">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

     <span data-ttu-id="8aaac-163">デバッグ インスタンスで、ブレークポイントが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-163">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="8aaac-164">Visual Studio の新しいインスタンスでは、"DebuggingExample"ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-164">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="8aaac-165">選択して、ソリューションを簡単に見つけることができます**最近使ったプロジェクト**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="8aaac-165">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="8aaac-166">"DebuggingExample.sln"ソリューション ファイルは、最近使用したファイルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-166">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="8aaac-167">Form1 を開き、**フォーム デザイナー**を選択し、**タブ**コントロール。</span><span class="sxs-lookup"><span data-stu-id="8aaac-167">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="8aaac-168">`DemoString` プロパティの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-168">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="8aaac-169">変更をコミットするときに、Visual Studio のデバッグ インスタンスがフォーカスを取得し、実行がブレークポイントで停止に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8aaac-169">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="8aaac-170">プロパティ アクセサーを 1 ステップを実行できますと同様、その他のコードには。</span><span class="sxs-lookup"><span data-stu-id="8aaac-170">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="8aaac-171">Visual Studio のホスト インスタンスを閉じるか、クリックして終了する、デバッグ セッションがしたら、**デバッグの停止**デバッグ インスタンスでボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-171">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8aaac-172">次の手順</span><span class="sxs-lookup"><span data-stu-id="8aaac-172">Next steps</span></span>

<span data-ttu-id="8aaac-173">これで、カスタム コントロールをデバッグするにはデザイン時に、Visual Studio IDE とコントロールの相互作用を拡張するためのさまざまな操作があります。</span><span class="sxs-lookup"><span data-stu-id="8aaac-173">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="8aaac-174">使用することができます、<xref:System.ComponentModel.Component.DesignMode%2A>のプロパティ、<xref:System.ComponentModel.Component>クラスはデザイン時にのみ実行するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="8aaac-174">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="8aaac-175">詳細については、「<xref:System.ComponentModel.Component.DesignMode%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8aaac-175">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="8aaac-176">いくつかの属性があるデザイナーを使用したカスタム コントロールの相互作用を操作するコントロールのプロパティに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-176">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="8aaac-177">これらの属性を見つけることができます、<xref:System.ComponentModel?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="8aaac-177">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="8aaac-178">カスタム コントロールのカスタム デザイナーを記述できます。</span><span class="sxs-lookup"><span data-stu-id="8aaac-178">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="8aaac-179">これにより、Visual Studio によって公開される拡張可能なデザイナー インフラストラクチャを使用して、デザイン エクスペリエンスを完全に制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8aaac-179">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="8aaac-180">詳細については、次を参照してください。[チュートリアル。Visual Studio のデザイン時機能を活用したコントロールをフォーム、Windows の作成](creating-a-wf-control-design-time-features.md)です。</span><span class="sxs-lookup"><span data-stu-id="8aaac-180">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8aaac-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="8aaac-181">See also</span></span>

- [<span data-ttu-id="8aaac-182">チュートリアル: Visual Studio のデザイン時機能を活用した Windows フォーム コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="8aaac-182">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="8aaac-183">[方法: デザイン時サービスにアクセス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="8aaac-183">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="8aaac-184">[方法: Windows フォームでデザイン時サポートのアクセス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="8aaac-184">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
