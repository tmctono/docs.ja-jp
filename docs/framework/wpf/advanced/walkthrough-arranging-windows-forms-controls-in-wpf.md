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
ms.openlocfilehash: 88b360d8445a743e2be5f16919b0c5d637ca46d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620713"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="9c1fc-102">チュートリアル: WPF での Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="9c1fc-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="9c1fc-103">このチュートリアルは、使用する方法を示します[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]を配置するためのレイアウト機能[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]ハイブリッド アプリケーションでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="9c1fc-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-104">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="9c1fc-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-105">Creating the project.</span></span>  
  
- <span data-ttu-id="9c1fc-106">既定のレイアウト設定の使用。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-106">Using default layout settings.</span></span>  
  
- <span data-ttu-id="9c1fc-107">コンテンツに合わせたサイズの変更。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-107">Sizing to content.</span></span>  
  
- <span data-ttu-id="9c1fc-108">絶対配置の使用。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-108">Using absolute positioning.</span></span>  
  
- <span data-ttu-id="9c1fc-109">サイズの明示的な指定。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-109">Specifying size explicitly.</span></span>  
  
- <span data-ttu-id="9c1fc-110">レイアウト プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-110">Setting layout properties.</span></span>  
  
- <span data-ttu-id="9c1fc-111">z オーダーの制限の理解。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-111">Understanding z-order limitations.</span></span>  
  
- <span data-ttu-id="9c1fc-112">ドッキング。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-112">Docking.</span></span>  
  
- <span data-ttu-id="9c1fc-113">可視性の設定。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-113">Setting visibility.</span></span>  
  
- <span data-ttu-id="9c1fc-114">伸縮しないコントロールのホスト。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-114">Hosting a control that does not stretch.</span></span>  
  
- <span data-ttu-id="9c1fc-115">スケーリング。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-115">Scaling.</span></span>  
  
- <span data-ttu-id="9c1fc-116">回転。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-116">Rotating.</span></span>  
  
- <span data-ttu-id="9c1fc-117">パディングとマージンの設定。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-117">Setting padding and margins.</span></span>  
  
- <span data-ttu-id="9c1fc-118">動的レイアウト コンテナーの使用。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="9c1fc-119">このチュートリアルで示すタスクの完全なコード一覧については、次を参照してください。 [WPF のサンプルを使用した Windows フォーム コントロールを配置する](https://go.microsoft.com/fwlink/?LinkID=159971)します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="9c1fc-120">理解する必要が完了したら、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]レイアウト機能[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-ベースのアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c1fc-121">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9c1fc-121">Prerequisites</span></span>  

<span data-ttu-id="9c1fc-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="creating-the-project"></a><span data-ttu-id="9c1fc-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="9c1fc-123">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="9c1fc-124">プロジェクトを作成し、設定するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-124">To create and set up the project</span></span>  
  
1. <span data-ttu-id="9c1fc-125">という名前の WPF アプリケーション プロジェクトを作成する`WpfLayoutHostingWf`します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2. <span data-ttu-id="9c1fc-126">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-126">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="9c1fc-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="9c1fc-127">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="9c1fc-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="9c1fc-128">System.Windows.Forms</span></span>  
  
    - <span data-ttu-id="9c1fc-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="9c1fc-129">System.Drawing</span></span>  
  
3. <span data-ttu-id="9c1fc-130">MainWindow.xaml をダブルクリックして、XAML ビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-130">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4. <span data-ttu-id="9c1fc-131"><xref:System.Windows.Window>要素では、次の追加[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]名前空間のマッピング。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-131">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="9c1fc-132"><xref:System.Windows.Controls.Grid>要素が設定されて、<xref:System.Windows.Controls.Grid.ShowGridLines%2A>プロパティを`true`し、5 つの行と 3 つの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="9c1fc-133">既定のレイアウト設定の使用</span><span class="sxs-lookup"><span data-stu-id="9c1fc-133">Using Default Layout Settings</span></span>  
 <span data-ttu-id="9c1fc-134">既定で、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素が、ホストされるレイアウトを処理[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロール。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="9c1fc-135">既定のレイアウト設定を使用するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-135">To use default layout settings</span></span>  
  
1. <span data-ttu-id="9c1fc-136">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2. <span data-ttu-id="9c1fc-137">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-137">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-138">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType>コントロールに表示され、<xref:System.Windows.Controls.Canvas>します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-138">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="9c1fc-139">ホストされるコントロールのサイズは、その内容に基づいて、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素のサイズは、ホストされるコントロールに対応します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="9c1fc-140">コンテンツに合わせたサイズの変更</span><span class="sxs-lookup"><span data-stu-id="9c1fc-140">Sizing to Content</span></span>  
 <span data-ttu-id="9c1fc-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素によりホストされるコントロールがそのコンテンツを正しく表示するサイズを調整するようになります。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="9c1fc-142">コンテンツに合わせてサイズ変更するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-142">To size to content</span></span>  
  
1. <span data-ttu-id="9c1fc-143">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2. <span data-ttu-id="9c1fc-144">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-144">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-145">2 つの新しいボタン コントロールより長いテキスト文字列と大きくなったフォント サイズが正しく表示にサイズ設定と<xref:System.Windows.Forms.Integration.WindowsFormsHost>にホストされるコントロールを対応する要素のサイズします。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="9c1fc-146">絶対配置の使用</span><span class="sxs-lookup"><span data-stu-id="9c1fc-146">Using Absolute Positioning</span></span>  
 <span data-ttu-id="9c1fc-147">絶対配置を使用する配置、<xref:System.Windows.Forms.Integration.WindowsFormsHost>ユーザー インターフェイス (UI) の任意の場所内の要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="9c1fc-148">絶対配置を使用するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-148">To use absolute positioning</span></span>  
  
1. <span data-ttu-id="9c1fc-149">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2. <span data-ttu-id="9c1fc-150">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-150">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は、グリッド セルの上辺から 20 ピクセル、左端から 20 ピクセルに配置されます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="9c1fc-152">サイズの明示的な指定</span><span class="sxs-lookup"><span data-stu-id="9c1fc-152">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="9c1fc-153">サイズを指定することができます、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素を使用して、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="9c1fc-154">サイズを明示的に指定するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-154">To specify size explicitly</span></span>  
  
1. <span data-ttu-id="9c1fc-155">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2. <span data-ttu-id="9c1fc-156">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-156">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は既定のレイアウト設定よりも小さいは 50 ピクセル、高さ 70 ピクセルのサイズに設定します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="9c1fc-158">コンテンツ、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールがそれに応じて再配置します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-158">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="9c1fc-159">レイアウト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="9c1fc-159">Setting Layout Properties</span></span>  
 <span data-ttu-id="9c1fc-160">常のプロパティを使用してホストされるコントロールにレイアウト関連のプロパティを設定、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="9c1fc-161">ホストされているコントロールで直接レイアウト プロパティを設定すると、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="9c1fc-162">ホストされるコントロールにレイアウト関連プロパティを設定[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]も何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="9c1fc-163">ホストされているコントロールでプロパティを設定した場合の結果を確認するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-163">To see the effects of setting properties on the hosted control</span></span>  
  
1. <span data-ttu-id="9c1fc-164">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2. <span data-ttu-id="9c1fc-165">ソリューション エクスプ ローラーで MainWindow.xaml をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-165">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="9c1fc-166">vb または MainWindow.xaml.cs をコード エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-166">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3. <span data-ttu-id="9c1fc-167">次のコードをコピー、`MainWindow`クラスの定義。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-167">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="9c1fc-168">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-168">Press F5 to build and run the application.</span></span>

5. <span data-ttu-id="9c1fc-169">をクリックして、 **Click me**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-169">Click the **Click me** button.</span></span> <span data-ttu-id="9c1fc-170">`button1_Click`イベント ハンドラーの設定、<xref:System.Windows.Forms.Control.Top%2A>と<xref:System.Windows.Forms.Control.Left%2A>ホストされるコントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-170">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="9c1fc-171">これにより、ホストされるコントロール内の位置を変更する、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-171">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="9c1fc-172">ホストは同じ画面領域を維持しますが、ホストされているコントロールはクリップされます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-172">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="9c1fc-173">ホストされるコントロールの代わりに、常に塗りつぶし、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-173">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="9c1fc-174">z オーダーの制限の理解</span><span class="sxs-lookup"><span data-stu-id="9c1fc-174">Understanding Z-Order Limitations</span></span>
 <span data-ttu-id="9c1fc-175">表示される<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素は常に、他の WPF 要素の上に描画し、それらは z オーダーによる影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-175">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="9c1fc-176">この z オーダーの動作を確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-176">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="9c1fc-177">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-177">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="9c1fc-178">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-178">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-179"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素がラベル要素上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-179">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="9c1fc-180">ドッキング</span><span class="sxs-lookup"><span data-stu-id="9c1fc-180">Docking</span></span>
 <span data-ttu-id="9c1fc-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素をサポートして[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ドッキングします。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="9c1fc-182">設定、<xref:System.Windows.Controls.DockPanel.Dock%2A>添付プロパティでホストされるコントロールをドッキングするのには、<xref:System.Windows.Controls.DockPanel>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-182">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="9c1fc-183">ホストされているコントロールをドッキングするには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-183">To dock a hosted control</span></span>

1. <span data-ttu-id="9c1fc-184">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-184">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="9c1fc-185">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-185">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-186"><xref:System.Windows.Forms.Integration.WindowsFormsHost>の右側にある要素がドッキングされた、<xref:System.Windows.Controls.DockPanel>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-186">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="9c1fc-187">可視性の設定</span><span class="sxs-lookup"><span data-stu-id="9c1fc-187">Setting Visibility</span></span>
 <span data-ttu-id="9c1fc-188">行うことができます、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールを非表示にしたり、折りたたんだりするには、<xref:System.Windows.UIElement.Visibility%2A>プロパティを<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-188">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="9c1fc-189">コントロールを非表示にすると、そのコントロールは表示されませんが、レイアウト空間は使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-189">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="9c1fc-190">コントロールを折りたたむと、そのコントロールは表示されず、レイアウト空間も使用されません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-190">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="9c1fc-191">ホストされているコントロールの可視性を設定するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-191">To set the visibility of a hosted control</span></span>

1. <span data-ttu-id="9c1fc-192">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-192">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="9c1fc-193">MainWindow.xaml.vb または MainWindow.xaml.cs で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-193">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="9c1fc-194">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-194">Press F5 to build and run the application.</span></span>

4. <span data-ttu-id="9c1fc-195">をクリックして、**を非表示 をクリックします**を作成するボタン、<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素を非表示します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-195">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="9c1fc-196">をクリックして、**折りたたむにはクリック**ボタンを非表示に、<xref:System.Windows.Forms.Integration.WindowsFormsHost>レイアウトからの要素全体。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-196">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="9c1fc-197">ときに、[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールが折りたたまれ、周囲の要素がその領域を占有するように再配置します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-197">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="9c1fc-198">伸縮しないコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="9c1fc-198">Hosting a Control That Does Not Stretch</span></span>
 <span data-ttu-id="9c1fc-199">いくつか[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールは固定サイズし、レイアウトで使用可能なスペースに合わせて伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-199">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="9c1fc-200">たとえば、<xref:System.Windows.Forms.MonthCalendar>コントロールは、固定された間隔で 1 か月を表示します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-200">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="9c1fc-201">伸縮しないコントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-201">To host a control that does not stretch</span></span>

1. <span data-ttu-id="9c1fc-202">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-202">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="9c1fc-203">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-203">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-204"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素がグリッドの行の中央に配置が、空き領域の塗りつぶしに拡張されていません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-204">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="9c1fc-205">によってホストされている 2 つ以上の月が生じる、ウィンドウが十分に大きい場合<xref:System.Windows.Forms.MonthCalendar>コントロールが、これらが、行の中央に配置します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-205">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="9c1fc-206">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]レイアウト エンジンの中心要素を使用可能なスペースに合わせてサイズを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-206">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="9c1fc-207">スケーリング</span><span class="sxs-lookup"><span data-stu-id="9c1fc-207">Scaling</span></span>
 <span data-ttu-id="9c1fc-208">WPF の要素とは異なりは、ほとんどの Windows フォーム コントロールは継続的にスケーリングではありません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-208">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="9c1fc-209">オーバーライドするカスタム スケーリングを提供する、<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-209">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="9c1fc-210">既定の動作を使用してホストされているコントロールをスケーリングするには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-210">To scale a hosted control by using the default behavior</span></span>

1. <span data-ttu-id="9c1fc-211">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-211">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="9c1fc-212">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-212">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-213">ホストされているコントロールとその周りの要素は、0.5 倍でスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-213">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="9c1fc-214">ただし、ホストされているコントロールのフォントはスケーリングされません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-214">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="9c1fc-215">回転</span><span class="sxs-lookup"><span data-stu-id="9c1fc-215">Rotating</span></span>
 <span data-ttu-id="9c1fc-216">WPF の要素とは異なり、Windows フォーム コントロールが回転にサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-216">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="9c1fc-217"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素では、回転変換を適用すると、その他の WPF 要素とともに回転しません。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-217">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="9c1fc-218">回転値が 180 度発生させ、<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>イベント。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-218">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="9c1fc-219">ハイブリッド アプリケーションでの回転の効果を確認するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-219">To see the effect of rotation in a hybrid application</span></span>

1. <span data-ttu-id="9c1fc-220">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-220">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="9c1fc-221">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-221">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-222">ホストされているコントロールは回転しませんが、その周りの要素は 180 度の角度で回転します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-222">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="9c1fc-223">要素を表示するためにウィンドウのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-223">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="9c1fc-224">パディングとマージンの設定</span><span class="sxs-lookup"><span data-stu-id="9c1fc-224">Setting Padding and Margins</span></span>
 <span data-ttu-id="9c1fc-225">パディングとマージンは[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]レイアウトのパディングとマージンのような[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-225">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="9c1fc-226">設定するだけです、<xref:System.Windows.Controls.Control.Padding%2A>と<xref:System.Windows.FrameworkElement.Margin%2A>プロパティを<xref:System.Windows.Forms.Integration.WindowsFormsHost>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-226">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="9c1fc-227">ホストされているコントロールのパディングとマージンを設定するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-227">To set padding and margins for a hosted control</span></span>

1. <span data-ttu-id="9c1fc-228">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-228">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="9c1fc-229">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-229">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-230">パディングとマージンの設定が適用されるホストに[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]コントロールに適用される場合と同じ方法で[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-230">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="9c1fc-231">動的レイアウト コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="9c1fc-231">Using Dynamic Layout Containers</span></span>
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <span data-ttu-id="9c1fc-232">2 つの動的レイアウト コンテナーを提供します<xref:System.Windows.Forms.FlowLayoutPanel>と<xref:System.Windows.Forms.TableLayoutPanel>します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-232">provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="9c1fc-233">これらのコンテナーを使用することもできます。[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]レイアウト。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-233">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="9c1fc-234">動的レイアウト コンテナーを使用するには</span><span class="sxs-lookup"><span data-stu-id="9c1fc-234">To use a dynamic layout container</span></span>

1. <span data-ttu-id="9c1fc-235">次の XAML をコピー、<xref:System.Windows.Controls.Grid>要素。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-235">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="9c1fc-236">MainWindow.xaml.vb または MainWindow.xaml.cs で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-236">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="9c1fc-237">コンストラクター内の `InitializeFlowLayoutPanel` メソッドに呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-237">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4. <span data-ttu-id="9c1fc-238">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="9c1fc-239"><xref:System.Windows.Forms.Integration.WindowsFormsHost>要素の設定、 <xref:System.Windows.Controls.DockPanel>、および<xref:System.Windows.Forms.FlowLayoutPanel>、既定では、その子コントロール<xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>します。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-239">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c1fc-240">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c1fc-240">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9c1fc-241">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="9c1fc-241">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="9c1fc-242">WindowsFormsHost 要素のレイアウトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9c1fc-242">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="9c1fc-243">WPF のサンプルでのフォーム コントロールの Windows の配置</span><span class="sxs-lookup"><span data-stu-id="9c1fc-243">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="9c1fc-244">チュートリアル: WPF で Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="9c1fc-244">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="9c1fc-245">チュートリアル: Windows フォームでの WPF 複合コントロールをホストしています。</span><span class="sxs-lookup"><span data-stu-id="9c1fc-245">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
