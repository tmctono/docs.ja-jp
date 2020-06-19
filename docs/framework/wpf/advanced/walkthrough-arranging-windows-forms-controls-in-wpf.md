---
title: WPF で Windows フォーム コントロールを配置する
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 5cf48b347be2d0ca6a9b55f3e19affb8b471aa2b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095100"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="bfad0-102">チュートリアル: WPF での Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bfad0-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="bfad0-103">このチュートリアルでは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウト機能を使用して、ハイブリッド アプリケーションで Windows フォーム コントロールを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange Windows Forms controls in a hybrid application.</span></span>

<span data-ttu-id="bfad0-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="bfad0-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="bfad0-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="bfad0-105">Creating the project.</span></span>
- <span data-ttu-id="bfad0-106">既定のレイアウト設定の使用。</span><span class="sxs-lookup"><span data-stu-id="bfad0-106">Using default layout settings.</span></span>
- <span data-ttu-id="bfad0-107">コンテンツに合わせたサイズの変更。</span><span class="sxs-lookup"><span data-stu-id="bfad0-107">Sizing to content.</span></span>
- <span data-ttu-id="bfad0-108">絶対配置の使用。</span><span class="sxs-lookup"><span data-stu-id="bfad0-108">Using absolute positioning.</span></span>
- <span data-ttu-id="bfad0-109">サイズの明示的な指定。</span><span class="sxs-lookup"><span data-stu-id="bfad0-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="bfad0-110">レイアウト プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="bfad0-110">Setting layout properties.</span></span>
- <span data-ttu-id="bfad0-111">z オーダーの制限の理解。</span><span class="sxs-lookup"><span data-stu-id="bfad0-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="bfad0-112">ドッキング。</span><span class="sxs-lookup"><span data-stu-id="bfad0-112">Docking.</span></span>
- <span data-ttu-id="bfad0-113">可視性の設定。</span><span class="sxs-lookup"><span data-stu-id="bfad0-113">Setting visibility.</span></span>
- <span data-ttu-id="bfad0-114">伸縮しないコントロールのホスト。</span><span class="sxs-lookup"><span data-stu-id="bfad0-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="bfad0-115">スケーリング。</span><span class="sxs-lookup"><span data-stu-id="bfad0-115">Scaling.</span></span>
- <span data-ttu-id="bfad0-116">回転。</span><span class="sxs-lookup"><span data-stu-id="bfad0-116">Rotating.</span></span>
- <span data-ttu-id="bfad0-117">パディングとマージンの設定。</span><span class="sxs-lookup"><span data-stu-id="bfad0-117">Setting padding and margins.</span></span>
- <span data-ttu-id="bfad0-118">動的レイアウト コンテナーの使用。</span><span class="sxs-lookup"><span data-stu-id="bfad0-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="bfad0-119">このチュートリアルで示すタスクの完全なコード一覧については、[WPF での Windows フォーム コントロールの配置のサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfad0-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml).</span></span>

<span data-ttu-id="bfad0-120">完了すると、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ベースのアプリケーションでの Windows フォーム レイアウトの機能について理解できます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-120">When you are finished, you will have an understanding of Windows Forms layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bfad0-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfad0-121">Prerequisites</span></span>

<span data-ttu-id="bfad0-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="bfad0-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="bfad0-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="bfad0-123">Creating the Project</span></span>

<span data-ttu-id="bfad0-124">プロジェクトを作成して設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-125">`WpfLayoutHostingWf` という名前の WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="bfad0-126">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="bfad0-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="bfad0-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="bfad0-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="bfad0-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="bfad0-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="bfad0-129">System.Drawing</span></span>

3. <span data-ttu-id="bfad0-130">*MainWindow.xaml* をダブルクリックして、XAML ビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="bfad0-131"><xref:System.Windows.Window> 要素に、次の Windows フォーム名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-131">In the <xref:System.Windows.Window> element, add the following Windows Forms namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="bfad0-132"><xref:System.Windows.Controls.Grid> 要素で <xref:System.Windows.Controls.Grid.ShowGridLines%2A> プロパティを `true` に設定し、5 つの行と 3 つの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="bfad0-133">既定のレイアウト設定の使用</span><span class="sxs-lookup"><span data-stu-id="bfad0-133">Using Default Layout Settings</span></span>

<span data-ttu-id="bfad0-134">既定で、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素では、ホストされている Windows フォーム コントロールのレイアウトが処理されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted Windows Forms control.</span></span>

<span data-ttu-id="bfad0-135">既定のレイアウト設定を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-136">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="bfad0-137"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-138">Windows フォーム <xref:System.Windows.Forms.Button?displayProperty=nameWithType> コントロールが <xref:System.Windows.Controls.Canvas> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-138">The Windows Forms <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="bfad0-139">ホストされているコントロールは、そのコンテンツに基づいてサイズが変更され、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、ホストされているコントロールに合わせてサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="bfad0-140">コンテンツに合わせたサイズの変更</span><span class="sxs-lookup"><span data-stu-id="bfad0-140">Sizing to Content</span></span>

<span data-ttu-id="bfad0-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を使用すると、ホストされているコントロールは、そのコンテンツが適切に表示されるように確実にサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="bfad0-142">コンテンツに合わせてサイズを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-143">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="bfad0-144"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-145">2 つの新しいボタン コントロールは、長いテキスト文字列と大きなフォント サイズが適切に表示されるようにサイズが変更され、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、ホストされるコントロールに合わせてサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="bfad0-146">絶対配置の使用</span><span class="sxs-lookup"><span data-stu-id="bfad0-146">Using Absolute Positioning</span></span>

<span data-ttu-id="bfad0-147">絶対配置を使用すると、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素をユーザー インターフェイス (UI) の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="bfad0-148">絶対配置を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-149">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="bfad0-150"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、グリッド セルの上端から 20 ピクセル、左端から 20 ピクセルの位置に配置されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="bfad0-152">サイズの明示的な指定</span><span class="sxs-lookup"><span data-stu-id="bfad0-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="bfad0-153"><xref:System.Windows.FrameworkElement.Width%2A> および <xref:System.Windows.FrameworkElement.Height%2A> プロパティを使用して、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のサイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="bfad0-154">サイズを明示的に指定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-155">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="bfad0-156"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は幅 50 ピクセル、高さ 70 ピクセルのサイズに設定されています。これは既定のレイアウト設定よりも小さいサイズです。</span><span class="sxs-lookup"><span data-stu-id="bfad0-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="bfad0-158">Windows フォーム コントロールのコンテンツは、それに応じて再配置されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-158">The content of the Windows Forms control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="bfad0-159">レイアウト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="bfad0-159">Setting Layout Properties</span></span>

<span data-ttu-id="bfad0-160">ホストされているコントロールには、常に、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のプロパティを使用してレイアウト関連のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="bfad0-161">ホストされているコントロールで直接レイアウト プロパティを設定すると、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="bfad0-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="bfad0-162">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] でホストされているコントロールにレイアウト関連プロパティを設定しても何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="bfad0-163">ホストされているコントロールでプロパティを設定した場合の結果を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-164">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="bfad0-165">**ソリューション エクスプローラー**で、*MainWindow.xaml.vb* または *MainWindow.xaml.cs* をダブルクリックして、コード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="bfad0-166">次のコードを `MainWindow` クラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="bfad0-167"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="bfad0-168">**[Click me]\(ここをクリック\)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-168">Click the **Click me** button.</span></span> <span data-ttu-id="bfad0-169">`button1_Click` イベント ハンドラーによって、ホストされているコントロールに <xref:System.Windows.Forms.Control.Top%2A> および <xref:System.Windows.Forms.Control.Left%2A> プロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="bfad0-170">これにより、ホストされているコントロールが <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素内に再配置されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="bfad0-171">ホストは同じ画面領域を維持しますが、ホストされているコントロールはクリップされます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="bfad0-172">そうではなく、ホストされているコントロールが常に <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素に合わせてサイズが変更されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfad0-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="bfad0-173">z オーダーの制限の理解</span><span class="sxs-lookup"><span data-stu-id="bfad0-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="bfad0-174">可視の <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は常に他の WPF 要素の上に描画され、z オーダーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="bfad0-175">この Z オーダーの動作を確認するために、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="bfad0-176">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="bfad0-177"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-178"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は label 要素の上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="bfad0-179">ドッキング</span><span class="sxs-lookup"><span data-stu-id="bfad0-179">Docking</span></span>

<span data-ttu-id="bfad0-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] のドッキングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="bfad0-181">ホストされているコントロールを <xref:System.Windows.Controls.DockPanel> 要素にドッキングするように <xref:System.Windows.Controls.DockPanel.Dock%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="bfad0-182">ホストされているコントロールをドッキングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-183">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="bfad0-184"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-185"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、<xref:System.Windows.Controls.DockPanel> 要素の右側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="bfad0-186">可視性の設定</span><span class="sxs-lookup"><span data-stu-id="bfad0-186">Setting Visibility</span></span>

<span data-ttu-id="bfad0-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素に <xref:System.Windows.UIElement.Visibility%2A> プロパティを設定することで、Windows フォーム コントロールを非表示にしたり折りたたんだりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-187">You can make your Windows Forms control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="bfad0-188">コントロールを非表示にすると、そのコントロールは表示されませんが、レイアウト空間は使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="bfad0-189">コントロールを折りたたむと、そのコントロールは表示されず、レイアウト空間も使用されません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="bfad0-190">ホストされているコントロールの可視性を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-191">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="bfad0-192">*MainWindow.xaml.vb* または *MainWindow.xaml.cs* で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="bfad0-193"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="bfad0-194">**[Click to make invisible]\(クリックして非表示にする\)** ボタンをクリックして <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="bfad0-195">**[Click to collapse]\(クリックして折りたたむ\)** ボタンをクリックして、レイアウトから <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を完全に非表示にします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="bfad0-196">Windows フォーム コントロールが折りたたまれ、周りの要素が再配置されて、そのスペースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-196">When the Windows Forms control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="bfad0-197">伸縮しないコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="bfad0-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="bfad0-198">一部の Windows フォーム コントロールは、サイズが固定され、レイアウト内の使用可能なスペースに合わせて伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-198">Some Windows Forms controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="bfad0-199">たとえば、<xref:System.Windows.Forms.MonthCalendar> コントロールでは、固定されたスペースに月が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="bfad0-200">伸縮しないコントロールをホストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-201">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="bfad0-202"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-203"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素はグリッド行で中央揃えになりますが、使用可能なスペースに合わせて伸縮されることはありません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="bfad0-204">ウィンドウが十分に大きい場合は、ホストされている <xref:System.Windows.Forms.MonthCalendar> コントロールによって 2 か月以上の月が表示される場合もありますが、これらは行内で中央揃えになります。</span><span class="sxs-lookup"><span data-stu-id="bfad0-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="bfad0-205">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウト エンジンによって、使用可能なスペースに合わせてサイズを変更できない要素が中央揃えにされます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="bfad0-206">スケーリング</span><span class="sxs-lookup"><span data-stu-id="bfad0-206">Scaling</span></span>

<span data-ttu-id="bfad0-207">WPF 要素と異なり、ほとんどの Windows フォーム コントロールは継続的にスケーリングすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="bfad0-208">カスタムのスケーリングを提供するには、<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="bfad0-209">既定の動作を使用してホストされているコントロールをスケーリングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-210">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="bfad0-211"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-212">ホストされているコントロールとその周りの要素は、0.5 倍でスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="bfad0-213">ただし、ホストされているコントロールのフォントはスケーリングされません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="bfad0-214">回転</span><span class="sxs-lookup"><span data-stu-id="bfad0-214">Rotating</span></span>

<span data-ttu-id="bfad0-215">WPF 要素とは異なり、Windows フォーム コントロールは回転をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="bfad0-216">回転変換が適用されても、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は WPF の他の要素とともに回転しません。</span><span class="sxs-lookup"><span data-stu-id="bfad0-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="bfad0-217">回転値が 180 度の場合を除き、<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="bfad0-218">ハイブリッド アプリケーションでの回転の効果を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-219">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="bfad0-220"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-221">ホストされているコントロールは回転しませんが、その周りの要素は 180 度の角度で回転します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="bfad0-222">要素を表示するためにウィンドウのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfad0-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="bfad0-223">パディングとマージンの設定</span><span class="sxs-lookup"><span data-stu-id="bfad0-223">Setting Padding and Margins</span></span>

<span data-ttu-id="bfad0-224">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウトのパディングとマージンは、Windows フォーム のパディングとマージンと同様です。</span><span class="sxs-lookup"><span data-stu-id="bfad0-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in Windows Forms.</span></span> <span data-ttu-id="bfad0-225"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素に <xref:System.Windows.Controls.Control.Padding%2A> および <xref:System.Windows.FrameworkElement.Margin%2A> プロパティを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="bfad0-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="bfad0-226">ホストされているコントロールのパディングとマージンを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-227">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="bfad0-228"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-229">パディングとマージンの設定が、Windows フォーム で適用される場合と同じように、ホストされている Windows フォーム コントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-229">The padding and margin settings are applied to the hosted Windows Forms controls in the same way they would be applied in Windows Forms.</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="bfad0-230">動的レイアウト コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="bfad0-230">Using Dynamic Layout Containers</span></span>

<span data-ttu-id="bfad0-231">Windows フォームには、<xref:System.Windows.Forms.FlowLayoutPanel> と <xref:System.Windows.Forms.TableLayoutPanel> という 2 つの動的レイアウト コンテナーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bfad0-231">Windows Forms provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="bfad0-232">これらのコンテナーは、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウトで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="bfad0-233">動的レイアウト コンテナーを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="bfad0-234">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="bfad0-235">*MainWindow.xaml.vb* または *MainWindow.xaml.cs* で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfad0-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="bfad0-236">コンストラクター内の `InitializeFlowLayoutPanel` メソッドに呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="bfad0-237"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="bfad0-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="bfad0-238"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を使用すると、<xref:System.Windows.Controls.DockPanel> に合わせてサイズが変更され、<xref:System.Windows.Forms.FlowLayoutPanel> を使用すると、既定の <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> にその子コントロールが配置されます。</span><span class="sxs-lookup"><span data-stu-id="bfad0-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfad0-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfad0-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="bfad0-240">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="bfad0-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="bfad0-241">WindowsFormsHost 要素のレイアウトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="bfad0-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="bfad0-242">WPF での Windows フォーム コントロールの配置のサンプル</span><span class="sxs-lookup"><span data-stu-id="bfad0-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WpfLayoutHostingWfWithXaml)
- [<span data-ttu-id="bfad0-243">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="bfad0-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="bfad0-244">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="bfad0-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
