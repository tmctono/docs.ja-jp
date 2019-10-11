---
title: 'チュートリアル: WPF での Windows フォーム コントロールの配置'
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: 3a94ef65be99b01a9511f37872cbcacd6ec12264
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179434"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="27b40-102">チュートリアル: WPF での Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="27b40-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="27b40-103">このチュートリアルでは @no__t 0 のレイアウト機能を使用して、ハイブリッドアプリケーションで @no__t 1 コントロールを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27b40-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="27b40-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="27b40-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="27b40-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="27b40-105">Creating the project.</span></span>
- <span data-ttu-id="27b40-106">既定のレイアウト設定の使用。</span><span class="sxs-lookup"><span data-stu-id="27b40-106">Using default layout settings.</span></span>
- <span data-ttu-id="27b40-107">コンテンツに合わせたサイズの変更。</span><span class="sxs-lookup"><span data-stu-id="27b40-107">Sizing to content.</span></span>
- <span data-ttu-id="27b40-108">絶対配置の使用。</span><span class="sxs-lookup"><span data-stu-id="27b40-108">Using absolute positioning.</span></span>
- <span data-ttu-id="27b40-109">サイズの明示的な指定。</span><span class="sxs-lookup"><span data-stu-id="27b40-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="27b40-110">レイアウト プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="27b40-110">Setting layout properties.</span></span>
- <span data-ttu-id="27b40-111">z オーダーの制限の理解。</span><span class="sxs-lookup"><span data-stu-id="27b40-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="27b40-112">ドッキング。</span><span class="sxs-lookup"><span data-stu-id="27b40-112">Docking.</span></span>
- <span data-ttu-id="27b40-113">可視性の設定。</span><span class="sxs-lookup"><span data-stu-id="27b40-113">Setting visibility.</span></span>
- <span data-ttu-id="27b40-114">伸縮しないコントロールのホスト。</span><span class="sxs-lookup"><span data-stu-id="27b40-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="27b40-115">スケーリング。</span><span class="sxs-lookup"><span data-stu-id="27b40-115">Scaling.</span></span>
- <span data-ttu-id="27b40-116">回転。</span><span class="sxs-lookup"><span data-stu-id="27b40-116">Rotating.</span></span>
- <span data-ttu-id="27b40-117">パディングとマージンの設定。</span><span class="sxs-lookup"><span data-stu-id="27b40-117">Setting padding and margins.</span></span>
- <span data-ttu-id="27b40-118">動的レイアウト コンテナーの使用。</span><span class="sxs-lookup"><span data-stu-id="27b40-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="27b40-119">このチュートリアルで示すタスクの完全なコード一覧については、「 [WPF の Windows フォームコントロールの配置](https://go.microsoft.com/fwlink/?LinkID=159971)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27b40-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="27b40-120">完了すると、@no__t の-1 ベースのアプリケーションの @no__t 0 のレイアウト機能について理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="27b40-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27b40-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="27b40-121">Prerequisites</span></span>

<span data-ttu-id="27b40-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="27b40-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="27b40-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="27b40-123">Creating the Project</span></span>

<span data-ttu-id="27b40-124">プロジェクトを作成して設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="27b40-125">@No__t-0 という名前の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="27b40-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="27b40-126">ソリューションエクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="27b40-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="27b40-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="27b40-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="27b40-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="27b40-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="27b40-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="27b40-129">System.Drawing</span></span>

3. <span data-ttu-id="27b40-130">*Mainwindow.xaml*をダブルクリックして、xaml ビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="27b40-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="27b40-131">@No__t-0 要素に、次の [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="27b40-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="27b40-132">@No__t-0 要素で、<xref:System.Windows.Controls.Grid.ShowGridLines%2A> プロパティを `true` に設定し、5つの行と3つの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="27b40-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="27b40-133">既定のレイアウト設定の使用</span><span class="sxs-lookup"><span data-stu-id="27b40-133">Using Default Layout Settings</span></span>

<span data-ttu-id="27b40-134">既定では、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、ホストされている @no__t 1 コントロールのレイアウトを処理します。</span><span class="sxs-lookup"><span data-stu-id="27b40-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="27b40-135">既定のレイアウト設定を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="27b40-136">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="27b40-137"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-138">@No__t-0 <xref:System.Windows.Forms.Button?displayProperty=nameWithType> コントロールが <xref:System.Windows.Controls.Canvas> に表示されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="27b40-139">ホストされるコントロールは、そのコンテンツに基づいてサイズが変更され、ホストされるコントロールに合わせて @no__t 0 要素のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="27b40-140">コンテンツに合わせたサイズの変更</span><span class="sxs-lookup"><span data-stu-id="27b40-140">Sizing to Content</span></span>

<span data-ttu-id="27b40-141">@No__t-0 要素を指定すると、ホストされているコントロールのサイズが、コンテンツを適切に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="27b40-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="27b40-142">コンテンツのサイズを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="27b40-143">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="27b40-144"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-145">2つの新しいボタンコントロールは、長いテキスト文字列と大きいフォントサイズを適切に表示するようにサイズが設定され、ホストされているコントロールに合わせて @no__t 0 要素のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="27b40-146">絶対配置の使用</span><span class="sxs-lookup"><span data-stu-id="27b40-146">Using Absolute Positioning</span></span>

<span data-ttu-id="27b40-147">絶対配置を使用して、ユーザーインターフェイス (UI) の任意の場所に @no__t 0 要素を配置できます。</span><span class="sxs-lookup"><span data-stu-id="27b40-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="27b40-148">絶対配置を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="27b40-149">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="27b40-150"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-151">@No__t-0 要素は、グリッドセルの上端から20ピクセル、左側から20ピクセルが配置されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="27b40-152">サイズの明示的な指定</span><span class="sxs-lookup"><span data-stu-id="27b40-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="27b40-153">@No__t-1 と <xref:System.Windows.FrameworkElement.Height%2A> のプロパティを使用して <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のサイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="27b40-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="27b40-154">サイズを明示的に指定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="27b40-155">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="27b40-156"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-157">@No__t-0 要素は、既定のレイアウト設定よりも小さい50ピクセルのサイズ (高さ70ピクセル) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="27b40-158">@No__t-0 コントロールの内容は、それに応じて再配置されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="27b40-159">レイアウト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="27b40-159">Setting Layout Properties</span></span>

<span data-ttu-id="27b40-160">@No__t-0 要素のプロパティを使用して、ホストされるコントロールのレイアウト関連のプロパティを常に設定します。</span><span class="sxs-lookup"><span data-stu-id="27b40-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="27b40-161">ホストされているコントロールで直接レイアウト プロパティを設定すると、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="27b40-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="27b40-162">@No__t-0 でホストされるコントロールのレイアウト関連のプロパティを設定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="27b40-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="27b40-163">ホストされるコントロールでプロパティを設定した場合の影響を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="27b40-164">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="27b40-165">**ソリューションエクスプローラー**で、 *mainwindow.xaml*または*MainWindow.xaml.cs*をダブルクリックしてコードエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="27b40-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="27b40-166">@No__t-0 クラス定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="27b40-167"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="27b40-168">**[クリック**してください] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="27b40-168">Click the **Click me** button.</span></span> <span data-ttu-id="27b40-169">@No__t-0 イベントハンドラーは、ホストされているコントロールの <xref:System.Windows.Forms.Control.Top%2A> および <xref:System.Windows.Forms.Control.Left%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="27b40-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="27b40-170">これにより、ホストされているコントロールが <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素内に位置が移動します。</span><span class="sxs-lookup"><span data-stu-id="27b40-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="27b40-171">ホストは同じ画面領域を維持しますが、ホストされているコントロールはクリップされます。</span><span class="sxs-lookup"><span data-stu-id="27b40-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="27b40-172">代わりに、ホストされるコントロールは常に <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を埋める必要があります。</span><span class="sxs-lookup"><span data-stu-id="27b40-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="27b40-173">z オーダーの制限の理解</span><span class="sxs-lookup"><span data-stu-id="27b40-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="27b40-174">可視 <xref:System.Windows.Forms.Integration.WindowsFormsHost> の要素は、常に他の WPF 要素の上に描画され、z オーダーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="27b40-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="27b40-175">この z オーダーの動作を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="27b40-176">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="27b40-177"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-178">@No__t-0 要素が label 要素の上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="27b40-179">ドッキング</span><span class="sxs-lookup"><span data-stu-id="27b40-179">Docking</span></span>

<span data-ttu-id="27b40-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ドッキングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="27b40-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="27b40-181">ホストされるコントロールを <xref:System.Windows.Controls.DockPanel> 要素にドッキングするには、<xref:System.Windows.Controls.DockPanel.Dock%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="27b40-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="27b40-182">ホストされたコントロールをドッキングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="27b40-183">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="27b40-184"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-185">@No__t-0 要素は、<xref:System.Windows.Controls.DockPanel> 要素の右側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="27b40-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="27b40-186">可視性の設定</span><span class="sxs-lookup"><span data-stu-id="27b40-186">Setting Visibility</span></span>

<span data-ttu-id="27b40-187">@No__t-2 要素の <xref:System.Windows.UIElement.Visibility%2A> プロパティを設定することによって、@no__t 0 コントロールを非表示にしたり折りたたんだりできます。</span><span class="sxs-lookup"><span data-stu-id="27b40-187">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="27b40-188">コントロールを非表示にすると、そのコントロールは表示されませんが、レイアウト空間は使用されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="27b40-189">コントロールを折りたたむと、そのコントロールは表示されず、レイアウト空間も使用されません。</span><span class="sxs-lookup"><span data-stu-id="27b40-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="27b40-190">ホストされるコントロールの表示を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="27b40-191">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="27b40-192">*Mainwindow.xaml*または*MainWindow.xaml.cs*で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="27b40-193"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="27b40-194">@No__t-1 要素を非表示にするには、 **[クリック**して非表示にする] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="27b40-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="27b40-195">レイアウトの <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を完全に非表示にするには、 **[クリック**して閉じる] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="27b40-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="27b40-196">@No__t 0 コントロールを折りたたむと、周囲の要素が再配置され、そのスペースが占有されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-196">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="27b40-197">伸縮しないコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="27b40-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="27b40-198">一部の [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] コントロールは固定サイズであり、レイアウト内の使用可能な領域を塗りつぶすために伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="27b40-198">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="27b40-199">たとえば、@no__t 0 のコントロールでは、固定領域に月が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="27b40-200">ストレッチされないコントロールをホストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="27b40-201">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="27b40-202"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-203">@No__t-0 要素はグリッド行の中央に配置されますが、使用可能な領域に合わせて拡大されることはありません。</span><span class="sxs-lookup"><span data-stu-id="27b40-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="27b40-204">ウィンドウのサイズが十分な場合は、ホストされている @no__t 0 コントロールによって複数の月が表示されることがありますが、これらは行の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="27b40-205">@No__t 0 のレイアウトエンジンは、使用可能な領域に合わせてサイズを変更できない要素を中央揃えにします。</span><span class="sxs-lookup"><span data-stu-id="27b40-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="27b40-206">スケーリング</span><span class="sxs-lookup"><span data-stu-id="27b40-206">Scaling</span></span>

<span data-ttu-id="27b40-207">WPF 要素とは異なり、ほとんどの Windows フォームコントロールは継続的に拡張できません。</span><span class="sxs-lookup"><span data-stu-id="27b40-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="27b40-208">カスタムスケーリングを提供するには、<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="27b40-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="27b40-209">既定の動作を使用してホストされているコントロールをスケーリングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="27b40-210">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="27b40-211"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-212">ホストされているコントロールとその周りの要素は、0.5 倍でスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="27b40-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="27b40-213">ただし、ホストされているコントロールのフォントはスケーリングされません。</span><span class="sxs-lookup"><span data-stu-id="27b40-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="27b40-214">回転</span><span class="sxs-lookup"><span data-stu-id="27b40-214">Rotating</span></span>

<span data-ttu-id="27b40-215">WPF 要素とは異なり、Windows フォームコントロールは回転をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="27b40-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="27b40-216">回転変換が適用されている場合、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は他の WPF 要素とは回転しません。</span><span class="sxs-lookup"><span data-stu-id="27b40-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="27b40-217">180°以外の回転値を指定すると、@no__t 0 のイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="27b40-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="27b40-218">ハイブリッドアプリケーションでのローテーションの効果を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="27b40-219">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="27b40-220"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-221">ホストされているコントロールは回転しませんが、その周りの要素は 180 度の角度で回転します。</span><span class="sxs-lookup"><span data-stu-id="27b40-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="27b40-222">要素を表示するためにウィンドウのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="27b40-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="27b40-223">パディングとマージンの設定</span><span class="sxs-lookup"><span data-stu-id="27b40-223">Setting Padding and Margins</span></span>

<span data-ttu-id="27b40-224">@No__t 0 レイアウトの埋め込みと余白は、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] の埋め込みと余白に似ています。</span><span class="sxs-lookup"><span data-stu-id="27b40-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="27b40-225">@No__t-2 要素の <xref:System.Windows.Controls.Control.Padding%2A> および <xref:System.Windows.FrameworkElement.Margin%2A> プロパティを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="27b40-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="27b40-226">ホストされるコントロールの埋め込みと余白を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="27b40-227">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="27b40-228"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-229">埋め込みと余白の設定は、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] で適用するのと同じように、ホストされている [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] コントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="27b40-229">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="27b40-230">動的レイアウト コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="27b40-230">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="27b40-231">は、2つの動的レイアウトコンテナー (<xref:System.Windows.Forms.FlowLayoutPanel> と <xref:System.Windows.Forms.TableLayoutPanel>) を提供します。</span><span class="sxs-lookup"><span data-stu-id="27b40-231">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="27b40-232">これらのコンテナーは @no__t 0 のレイアウトで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="27b40-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="27b40-233">動的レイアウトコンテナーを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="27b40-234">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="27b40-235">*Mainwindow.xaml*または*MainWindow.xaml.cs*で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="27b40-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="27b40-236">コンストラクターに `InitializeFlowLayoutPanel` メソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="27b40-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="27b40-237"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="27b40-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="27b40-238">@No__t-0 要素は <xref:System.Windows.Controls.DockPanel> を入力し、<xref:System.Windows.Forms.FlowLayoutPanel> は既定の <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> で子コントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="27b40-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="27b40-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="27b40-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="27b40-240">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="27b40-240">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="27b40-241">WindowsFormsHost 要素のレイアウトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="27b40-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="27b40-242">WPF サンプルでの Windows フォームコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="27b40-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- <span data-ttu-id="27b40-243">[チュートリアル: WPF での Windows フォーム複合コントロールのホスト @ no__t</span><span class="sxs-lookup"><span data-stu-id="27b40-243">[Walkthrough: Hosting a Windows Forms Composite Control in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)</span></span>
- <span data-ttu-id="27b40-244">[チュートリアル: Windows フォーム @ no__t での WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="27b40-244">[Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)</span></span>
