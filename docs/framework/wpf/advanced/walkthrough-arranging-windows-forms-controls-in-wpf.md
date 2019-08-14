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
ms.openlocfilehash: fa0181e95a03324c4cfa9395ae57439c260d1c23
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972307"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="6eda8-102">チュートリアル: WPF での Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="6eda8-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="6eda8-103">このチュートリアルでは、レイアウト機能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を使用して[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 、ハイブリッドアプリケーションでコントロールを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>

<span data-ttu-id="6eda8-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="6eda8-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="6eda8-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="6eda8-105">Creating the project.</span></span>

- <span data-ttu-id="6eda8-106">既定のレイアウト設定の使用。</span><span class="sxs-lookup"><span data-stu-id="6eda8-106">Using default layout settings.</span></span>

- <span data-ttu-id="6eda8-107">コンテンツに合わせたサイズの変更。</span><span class="sxs-lookup"><span data-stu-id="6eda8-107">Sizing to content.</span></span>

- <span data-ttu-id="6eda8-108">絶対配置の使用。</span><span class="sxs-lookup"><span data-stu-id="6eda8-108">Using absolute positioning.</span></span>

- <span data-ttu-id="6eda8-109">サイズの明示的な指定。</span><span class="sxs-lookup"><span data-stu-id="6eda8-109">Specifying size explicitly.</span></span>

- <span data-ttu-id="6eda8-110">レイアウト プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="6eda8-110">Setting layout properties.</span></span>

- <span data-ttu-id="6eda8-111">z オーダーの制限の理解。</span><span class="sxs-lookup"><span data-stu-id="6eda8-111">Understanding z-order limitations.</span></span>

- <span data-ttu-id="6eda8-112">ドッキング。</span><span class="sxs-lookup"><span data-stu-id="6eda8-112">Docking.</span></span>

- <span data-ttu-id="6eda8-113">可視性の設定。</span><span class="sxs-lookup"><span data-stu-id="6eda8-113">Setting visibility.</span></span>

- <span data-ttu-id="6eda8-114">伸縮しないコントロールのホスト。</span><span class="sxs-lookup"><span data-stu-id="6eda8-114">Hosting a control that does not stretch.</span></span>

- <span data-ttu-id="6eda8-115">スケーリング。</span><span class="sxs-lookup"><span data-stu-id="6eda8-115">Scaling.</span></span>

- <span data-ttu-id="6eda8-116">回転。</span><span class="sxs-lookup"><span data-stu-id="6eda8-116">Rotating.</span></span>

- <span data-ttu-id="6eda8-117">パディングとマージンの設定。</span><span class="sxs-lookup"><span data-stu-id="6eda8-117">Setting padding and margins.</span></span>

- <span data-ttu-id="6eda8-118">動的レイアウト コンテナーの使用。</span><span class="sxs-lookup"><span data-stu-id="6eda8-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="6eda8-119">このチュートリアルで示すタスクの完全なコード一覧については、「 [WPF の Windows フォームコントロールの配置](https://go.microsoft.com/fwlink/?LinkID=159971)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eda8-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="6eda8-120">完了すると、ベースのアプリケーションの[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]レイアウト[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]機能について理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6eda8-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6eda8-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6eda8-121">Prerequisites</span></span>

<span data-ttu-id="6eda8-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="6eda8-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="6eda8-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="6eda8-123">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="6eda8-124">プロジェクトを作成し、設定するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-124">To create and set up the project</span></span>

1. <span data-ttu-id="6eda8-125">という名前`WpfLayoutHostingWf`の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="6eda8-126">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-126">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="6eda8-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6eda8-127">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="6eda8-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="6eda8-128">System.Windows.Forms</span></span>

    - <span data-ttu-id="6eda8-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="6eda8-129">System.Drawing</span></span>

3. <span data-ttu-id="6eda8-130">MainWindow.xaml をダブルクリックして、XAML ビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>

4. <span data-ttu-id="6eda8-131">要素に、次[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]の名前空間マッピングを追加します。 <xref:System.Windows.Window></span><span class="sxs-lookup"><span data-stu-id="6eda8-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="6eda8-132">要素で、 <xref:System.Windows.Controls.Grid.ShowGridLines%2A>プロパティをに`true`設定し、5つの行と3つの列を定義します。 <xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="6eda8-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="6eda8-133">既定のレイアウト設定の使用</span><span class="sxs-lookup"><span data-stu-id="6eda8-133">Using Default Layout Settings</span></span>

<span data-ttu-id="6eda8-134">既定では、 <xref:System.Windows.Forms.Integration.WindowsFormsHost>要素はホスト[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]されるコントロールのレイアウトを処理します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-use-default-layout-settings"></a><span data-ttu-id="6eda8-135">既定のレイアウト設定を使用するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-135">To use default layout settings</span></span>

1. <span data-ttu-id="6eda8-136">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="6eda8-137">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-138">コントロールがに<xref:System.Windows.Controls.Canvas>表示されます。 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="6eda8-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6eda8-139">ホストされるコントロールは、そのコンテンツに基づいてサイズ<xref:System.Windows.Forms.Integration.WindowsFormsHost>が設定され、ホストされるコントロールに合わせて要素のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="6eda8-140">コンテンツに合わせたサイズの変更</span><span class="sxs-lookup"><span data-stu-id="6eda8-140">Sizing to Content</span></span>

<span data-ttu-id="6eda8-141">要素<xref:System.Windows.Forms.Integration.WindowsFormsHost>によって、ホストされるコントロールのサイズが、コンテンツを適切に表示するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

### <a name="to-size-to-content"></a><span data-ttu-id="6eda8-142">コンテンツに合わせてサイズ変更するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-142">To size to content</span></span>

1. <span data-ttu-id="6eda8-143">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="6eda8-144">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-145">2つの新しいボタンコントロールは、長いテキスト文字列と大きいフォントサイズを適切に表示するよう<xref:System.Windows.Forms.Integration.WindowsFormsHost>にサイズが設定され、ホストされているコントロールに合わせて要素のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="6eda8-146">絶対配置の使用</span><span class="sxs-lookup"><span data-stu-id="6eda8-146">Using Absolute Positioning</span></span>

<span data-ttu-id="6eda8-147">絶対配置を使用して、 <xref:System.Windows.Forms.Integration.WindowsFormsHost>要素をユーザーインターフェイス (UI) 内の任意の場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

### <a name="to-use-absolute-positioning"></a><span data-ttu-id="6eda8-148">絶対配置を使用するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-148">To use absolute positioning</span></span>

1. <span data-ttu-id="6eda8-149">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="6eda8-150">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は、グリッドセルの上端から20ピクセル、左から20ピクセルが配置されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="6eda8-152">サイズの明示的な指定</span><span class="sxs-lookup"><span data-stu-id="6eda8-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="6eda8-153"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素のサイズは、プロパティ<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

### <a name="to-specify-size-explicitly"></a><span data-ttu-id="6eda8-154">サイズを明示的に指定するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-154">To specify size explicitly</span></span>

1. <span data-ttu-id="6eda8-155">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="6eda8-156">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は、幅50ピクセル、高さ70ピクセル、既定のレイアウト設定より小さいサイズに設定されています。</span><span class="sxs-lookup"><span data-stu-id="6eda8-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="6eda8-158">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールの内容は、それに応じて再配置されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="6eda8-159">レイアウト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="6eda8-159">Setting Layout Properties</span></span>

<span data-ttu-id="6eda8-160">常に、 <xref:System.Windows.Forms.Integration.WindowsFormsHost>要素のプロパティを使用して、ホストされるコントロールのレイアウト関連のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6eda8-161">ホストされているコントロールで直接レイアウト プロパティを設定すると、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="6eda8-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="6eda8-162">で[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]ホストされるコントロールのレイアウト関連のプロパティを設定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="6eda8-163">ホストされているコントロールでプロパティを設定した場合の結果を確認するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-163">To see the effects of setting properties on the hosted control</span></span>

1. <span data-ttu-id="6eda8-164">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="6eda8-165">ソリューションエクスプローラーで、Mainwindow.xaml をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="6eda8-166">vb または MainWindow.xaml.cs をコードエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>

3. <span data-ttu-id="6eda8-167">次のコードを`MainWindow`クラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-167">Copy the following code into the `MainWindow` class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="6eda8-168">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="6eda8-169">**[クリック**してください] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-169">Click the **Click me** button.</span></span> <span data-ttu-id="6eda8-170">イベント`button1_Click`ハンドラーは、ホスト<xref:System.Windows.Forms.Control.Top%2A>さ<xref:System.Windows.Forms.Control.Left%2A>れるコントロールのプロパティとプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="6eda8-171">これにより、ホストされるコントロールが<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素内で位置が移動します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6eda8-172">ホストは同じ画面領域を維持しますが、ホストされているコントロールはクリップされます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="6eda8-173">代わりに、ホストされるコントロールは常に<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素を埋める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eda8-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="6eda8-174">z オーダーの制限の理解</span><span class="sxs-lookup"><span data-stu-id="6eda8-174">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="6eda8-175">可視<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は、常に他の WPF 要素の上に描画され、z オーダーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="6eda8-176">この z オーダーの動作を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="6eda8-177">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="6eda8-178">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は label 要素上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="6eda8-180">ドッキング</span><span class="sxs-lookup"><span data-stu-id="6eda8-180">Docking</span></span>

<span data-ttu-id="6eda8-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ドッキングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6eda8-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="6eda8-182">添付プロパティを設定して、ホストされて<xref:System.Windows.Controls.DockPanel>いるコントロールを要素にドッキングします。 <xref:System.Windows.Controls.DockPanel.Dock%2A></span><span class="sxs-lookup"><span data-stu-id="6eda8-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="6eda8-183">ホストされているコントロールをドッキングするには</span><span class="sxs-lookup"><span data-stu-id="6eda8-183">To dock a hosted control</span></span>

1. <span data-ttu-id="6eda8-184">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="6eda8-185">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-186">要素は<xref:System.Windows.Controls.DockPanel>要素の右側にドッキングされます。 <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="6eda8-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="6eda8-187">可視性の設定</span><span class="sxs-lookup"><span data-stu-id="6eda8-187">Setting Visibility</span></span>

<span data-ttu-id="6eda8-188">要素のプロパティ[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.UIElement.Visibility%2A>を設定することによって、コントロールを非表示にしたり折りたたんだりできます。 <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="6eda8-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="6eda8-189">コントロールを非表示にすると、そのコントロールは表示されませんが、レイアウト空間は使用されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="6eda8-190">コントロールを折りたたむと、そのコントロールは表示されず、レイアウト空間も使用されません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="6eda8-191">ホストされているコントロールの可視性を設定するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="6eda8-192">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="6eda8-193">MainWindow.xaml.vb または MainWindow.xaml.cs で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="6eda8-194">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="6eda8-195">[クリックして**非表示に**する] ボタン<xref:System.Windows.Forms.Integration.WindowsFormsHost>をクリックすると、要素が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="6eda8-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="6eda8-196">レイアウトの<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素を完全に非表示にするには、 **[クリック**して閉じる] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="6eda8-197">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールを折りたたむと、周囲の要素が再配置され、そのスペースが占有されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="6eda8-198">伸縮しないコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6eda8-198">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="6eda8-199">一部[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]のコントロールは固定サイズであり、レイアウト内の使用可能な領域を塗りつぶすために伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="6eda8-200">たとえば、コントロールは<xref:System.Windows.Forms.MonthCalendar> 、固定されたスペースで月を表示します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="6eda8-201">伸縮しないコントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="6eda8-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="6eda8-202">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="6eda8-203">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素はグリッド行の中央に配置されますが、使用可能な領域に合わせて拡大されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="6eda8-205">ウィンドウのサイズが十分な場合は、ホスト<xref:System.Windows.Forms.MonthCalendar>されているコントロールによって複数の月が表示されることがありますが、これらは行の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="6eda8-206">レイアウト[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]エンジンは、使用可能な領域に合わせてサイズを変更できない要素を中央揃えにします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="6eda8-207">スケーリング</span><span class="sxs-lookup"><span data-stu-id="6eda8-207">Scaling</span></span>

<span data-ttu-id="6eda8-208">WPF 要素とは異なり、ほとんどの Windows フォームコントロールは継続的に拡張できません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="6eda8-209">カスタムスケーリングを提供するには<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> 、メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="6eda8-210">既定の動作を使用してホストされているコントロールをスケーリングするには</span><span class="sxs-lookup"><span data-stu-id="6eda8-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="6eda8-211">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="6eda8-212">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-213">ホストされているコントロールとその周りの要素は、0.5 倍でスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="6eda8-214">ただし、ホストされているコントロールのフォントはスケーリングされません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="6eda8-215">回転</span><span class="sxs-lookup"><span data-stu-id="6eda8-215">Rotating</span></span>

<span data-ttu-id="6eda8-216">WPF 要素とは異なり、Windows フォームコントロールは回転をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="6eda8-217">回転<xref:System.Windows.Forms.Integration.WindowsFormsHost>変換が適用されている場合、要素は他の WPF 要素とは回転しません。</span><span class="sxs-lookup"><span data-stu-id="6eda8-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="6eda8-218">180°以外の回転値を指定する<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>と、イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="6eda8-219">ハイブリッド アプリケーションでの回転の効果を確認するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="6eda8-220">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="6eda8-221">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-222">ホストされているコントロールは回転しませんが、その周りの要素は 180 度の角度で回転します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="6eda8-223">要素を表示するためにウィンドウのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6eda8-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="6eda8-224">パディングとマージンの設定</span><span class="sxs-lookup"><span data-stu-id="6eda8-224">Setting Padding and Margins</span></span>

<span data-ttu-id="6eda8-225">レイアウトの[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]埋め込みと余白は、の[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]埋め込みと余白に似ています。</span><span class="sxs-lookup"><span data-stu-id="6eda8-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="6eda8-226">要素のプロパティ<xref:System.Windows.Controls.Control.Padding%2A>と<xref:System.Windows.FrameworkElement.Margin%2A>プロパティを設定するだけです。 <xref:System.Windows.Forms.Integration.WindowsFormsHost></span><span class="sxs-lookup"><span data-stu-id="6eda8-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="6eda8-227">ホストされているコントロールのパディングとマージンを設定するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="6eda8-228">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="6eda8-229">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-230">埋め込みと余白の設定は、で[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]適用されるのと同じ方法で、ホストされるコントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="6eda8-231">動的レイアウト コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="6eda8-231">Using Dynamic Layout Containers</span></span>

[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="6eda8-232">には、とという<xref:System.Windows.Forms.FlowLayoutPanel> 2 <xref:System.Windows.Forms.TableLayoutPanel>つの動的レイアウトコンテナーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6eda8-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="6eda8-233">これらのコンテナーはレイアウトで[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]も使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eda8-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="6eda8-234">動的レイアウト コンテナーを使用するには</span><span class="sxs-lookup"><span data-stu-id="6eda8-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="6eda8-235">次の XAML を<xref:System.Windows.Controls.Grid>要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="6eda8-236">MainWindow.xaml.vb または MainWindow.xaml.cs で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6eda8-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="6eda8-237">コンストラクター内の `InitializeFlowLayoutPanel` メソッドに呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="6eda8-238">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="6eda8-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="6eda8-239">要素<xref:System.Windows.Forms.Integration.WindowsFormsHost> は、<xref:System.Windows.Forms.FlowLayoutPanel> <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>を設定し、既定ので子コントロールを配置します。 <xref:System.Windows.Controls.DockPanel></span><span class="sxs-lookup"><span data-stu-id="6eda8-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="6eda8-240">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eda8-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6eda8-241">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="6eda8-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6eda8-242">WindowsFormsHost 要素のレイアウトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6eda8-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="6eda8-243">WPF サンプルでの Windows フォームコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="6eda8-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="6eda8-244">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6eda8-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="6eda8-245">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="6eda8-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
