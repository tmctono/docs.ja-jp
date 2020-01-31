---
title: WPF で Windows フォームコントロールを配置する
titleSuffix: ''
ms.date: 04/03/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
ms.openlocfilehash: eee26165e17b3327166a160e7c4ee3726215dcfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794250"
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="9cef6-102">チュートリアル: WPF での Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="9cef6-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>

<span data-ttu-id="9cef6-103">このチュートリアルでは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウト機能を使用して、ハイブリッドアプリケーションで Windows フォームコントロールを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange Windows Forms controls in a hybrid application.</span></span>

<span data-ttu-id="9cef6-104">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="9cef6-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="9cef6-105">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="9cef6-105">Creating the project.</span></span>
- <span data-ttu-id="9cef6-106">既定のレイアウト設定の使用。</span><span class="sxs-lookup"><span data-stu-id="9cef6-106">Using default layout settings.</span></span>
- <span data-ttu-id="9cef6-107">コンテンツに合わせたサイズの変更。</span><span class="sxs-lookup"><span data-stu-id="9cef6-107">Sizing to content.</span></span>
- <span data-ttu-id="9cef6-108">絶対配置の使用。</span><span class="sxs-lookup"><span data-stu-id="9cef6-108">Using absolute positioning.</span></span>
- <span data-ttu-id="9cef6-109">サイズの明示的な指定。</span><span class="sxs-lookup"><span data-stu-id="9cef6-109">Specifying size explicitly.</span></span>
- <span data-ttu-id="9cef6-110">レイアウト プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="9cef6-110">Setting layout properties.</span></span>
- <span data-ttu-id="9cef6-111">z オーダーの制限の理解。</span><span class="sxs-lookup"><span data-stu-id="9cef6-111">Understanding z-order limitations.</span></span>
- <span data-ttu-id="9cef6-112">ドッキング。</span><span class="sxs-lookup"><span data-stu-id="9cef6-112">Docking.</span></span>
- <span data-ttu-id="9cef6-113">可視性の設定。</span><span class="sxs-lookup"><span data-stu-id="9cef6-113">Setting visibility.</span></span>
- <span data-ttu-id="9cef6-114">伸縮しないコントロールのホスト。</span><span class="sxs-lookup"><span data-stu-id="9cef6-114">Hosting a control that does not stretch.</span></span>
- <span data-ttu-id="9cef6-115">Scaling。</span><span class="sxs-lookup"><span data-stu-id="9cef6-115">Scaling.</span></span>
- <span data-ttu-id="9cef6-116">回転。</span><span class="sxs-lookup"><span data-stu-id="9cef6-116">Rotating.</span></span>
- <span data-ttu-id="9cef6-117">パディングとマージンの設定。</span><span class="sxs-lookup"><span data-stu-id="9cef6-117">Setting padding and margins.</span></span>
- <span data-ttu-id="9cef6-118">動的レイアウト コンテナーの使用。</span><span class="sxs-lookup"><span data-stu-id="9cef6-118">Using dynamic layout containers.</span></span>

<span data-ttu-id="9cef6-119">このチュートリアルで示すタスクの完全なコード一覧については、「 [WPF の Windows フォームコントロールの配置](https://go.microsoft.com/fwlink/?LinkID=159971)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9cef6-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159971).</span></span>

<span data-ttu-id="9cef6-120">完了すると、[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ベースのアプリケーションの Windows フォームレイアウト機能について理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9cef6-120">When you are finished, you will have an understanding of Windows Forms layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9cef6-121">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="9cef6-121">Prerequisites</span></span>

<span data-ttu-id="9cef6-122">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="9cef6-122">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="9cef6-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="9cef6-123">Creating the Project</span></span>

<span data-ttu-id="9cef6-124">プロジェクトを作成して設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-124">To create and set up the project, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-125">`WpfLayoutHostingWf`という名前の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-125">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>

2. <span data-ttu-id="9cef6-126">ソリューションエクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-126">In Solution Explorer, add references to the following assemblies:</span></span>

    - <span data-ttu-id="9cef6-127">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="9cef6-127">WindowsFormsIntegration</span></span>
    - <span data-ttu-id="9cef6-128">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="9cef6-128">System.Windows.Forms</span></span>
    - <span data-ttu-id="9cef6-129">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="9cef6-129">System.Drawing</span></span>

3. <span data-ttu-id="9cef6-130">*Mainwindow.xaml*をダブルクリックして、xaml ビューで開きます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-130">Double-click *MainWindow.xaml* to open it in XAML view.</span></span>

4. <span data-ttu-id="9cef6-131"><xref:System.Windows.Window> 要素に、次の Windows フォーム名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-131">In the <xref:System.Windows.Window> element, add the following Windows Forms namespace mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="9cef6-132"><xref:System.Windows.Controls.Grid> 要素で、<xref:System.Windows.Controls.Grid.ShowGridLines%2A> プロパティを `true` に設定し、5つの行と3つの列を定義します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-132">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]

## <a name="using-default-layout-settings"></a><span data-ttu-id="9cef6-133">既定のレイアウト設定の使用</span><span class="sxs-lookup"><span data-stu-id="9cef6-133">Using Default Layout Settings</span></span>

<span data-ttu-id="9cef6-134">既定では、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、ホストされている Windows フォームコントロールのレイアウトを処理します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-134">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted Windows Forms control.</span></span>

<span data-ttu-id="9cef6-135">既定のレイアウト設定を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-135">To use default layout settings, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-136">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-136">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]

2. <span data-ttu-id="9cef6-137"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-137">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-138"><xref:System.Windows.Controls.Canvas>に Windows フォーム <xref:System.Windows.Forms.Button?displayProperty=nameWithType> コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-138">The Windows Forms <xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="9cef6-139">ホストされるコントロールは、そのコンテンツに基づいてサイズが変更され、ホストされるコントロールに合わせて <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-139">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>

## <a name="sizing-to-content"></a><span data-ttu-id="9cef6-140">コンテンツに合わせたサイズの変更</span><span class="sxs-lookup"><span data-stu-id="9cef6-140">Sizing to Content</span></span>

<span data-ttu-id="9cef6-141"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素によって、ホストされるコントロールのサイズが、コンテンツを適切に表示するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-141">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>

<span data-ttu-id="9cef6-142">コンテンツのサイズを変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-142">To size to content, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-143">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-143">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]

2. <span data-ttu-id="9cef6-144"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-144">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-145">2つの新しいボタンコントロールは、長いテキスト文字列と大きいフォントサイズを適切に表示するようにサイズが設定され、ホストされているコントロールに合わせて <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-145">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>

## <a name="using-absolute-positioning"></a><span data-ttu-id="9cef6-146">絶対配置の使用</span><span class="sxs-lookup"><span data-stu-id="9cef6-146">Using Absolute Positioning</span></span>

<span data-ttu-id="9cef6-147">絶対配置を使用して、ユーザーインターフェイス (UI) の任意の場所に <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を配置できます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-147">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>

<span data-ttu-id="9cef6-148">絶対配置を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-148">To use absolute positioning, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-149">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-149">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]

2. <span data-ttu-id="9cef6-150"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-150">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、グリッドセルの上端から20ピクセル、左側から20ピクセルが配置されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-151">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>

## <a name="specifying-size-explicitly"></a><span data-ttu-id="9cef6-152">サイズの明示的な指定</span><span class="sxs-lookup"><span data-stu-id="9cef6-152">Specifying Size Explicitly</span></span>

<span data-ttu-id="9cef6-153"><xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> プロパティを使用して、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のサイズを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-153">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>

<span data-ttu-id="9cef6-154">サイズを明示的に指定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-154">To specify size explicitly, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-155">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-155">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]

2. <span data-ttu-id="9cef6-156"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-156">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-157"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、既定のレイアウト設定よりも小さい50ピクセルのサイズ (高さ70ピクセル) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-157">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="9cef6-158">Windows フォームコントロールの内容は、それに応じて再配置されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-158">The content of the Windows Forms control is rearranged accordingly.</span></span>

## <a name="setting-layout-properties"></a><span data-ttu-id="9cef6-159">レイアウト プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="9cef6-159">Setting Layout Properties</span></span>

<span data-ttu-id="9cef6-160"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素のプロパティを使用して、ホストされるコントロールのレイアウト関連のプロパティを常に設定します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-160">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="9cef6-161">ホストされているコントロールで直接レイアウト プロパティを設定すると、予期しない結果になります。</span><span class="sxs-lookup"><span data-stu-id="9cef6-161">Setting layout properties directly on the hosted control will yield unintended results.</span></span>

 <span data-ttu-id="9cef6-162">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] のホストされるコントロールにレイアウト関連のプロパティを設定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-162">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>

<span data-ttu-id="9cef6-163">ホストされるコントロールでプロパティを設定した場合の影響を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-163">To see the effects of setting properties on the hosted control, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-164">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-164">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]

2. <span data-ttu-id="9cef6-165">**ソリューションエクスプローラー**で、 *mainwindow.xaml*または*MainWindow.xaml.cs*をダブルクリックしてコードエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-165">In **Solution Explorer**, double-click *MainWindow.xaml.vb* or *MainWindow.xaml.cs* to open it in the Code Editor.</span></span>

3. <span data-ttu-id="9cef6-166">`MainWindow` クラス定義に次のコードをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-166">Copy the following code into the `MainWindow` class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]

4. <span data-ttu-id="9cef6-167"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-167">Press <kbd>F5</kbd> to build and run the application.</span></span>

5. <span data-ttu-id="9cef6-168">**[クリック**してください] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-168">Click the **Click me** button.</span></span> <span data-ttu-id="9cef6-169">`button1_Click` イベントハンドラーは、ホストされるコントロールの <xref:System.Windows.Forms.Control.Top%2A> および <xref:System.Windows.Forms.Control.Left%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-169">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="9cef6-170">これにより、ホストされているコントロールが <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素内で位置が移動します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-170">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="9cef6-171">ホストは同じ画面領域を維持しますが、ホストされているコントロールはクリップされます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-171">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="9cef6-172">代わりに、ホストされるコントロールは常に <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cef6-172">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

## <a name="understanding-z-order-limitations"></a><span data-ttu-id="9cef6-173">z オーダーの制限の理解</span><span class="sxs-lookup"><span data-stu-id="9cef6-173">Understanding Z-Order Limitations</span></span>

<span data-ttu-id="9cef6-174">可視の <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、常に他の WPF 要素の上に描画され、z オーダーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-174">Visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other WPF elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="9cef6-175">この z オーダーの動作を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-175">To see this z-order behavior, do the following:</span></span>

1. <span data-ttu-id="9cef6-176">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-176">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]

2. <span data-ttu-id="9cef6-177"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-177">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-178"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、label 要素上に描画されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-178">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>

## <a name="docking"></a><span data-ttu-id="9cef6-179">Docking</span><span class="sxs-lookup"><span data-stu-id="9cef6-179">Docking</span></span>

<span data-ttu-id="9cef6-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ドッキングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-180"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="9cef6-181"><xref:System.Windows.Controls.DockPanel> 要素にホストされるコントロールをドッキングするには、<xref:System.Windows.Controls.DockPanel.Dock%2A> 添付プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-181">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>

<span data-ttu-id="9cef6-182">ホストされたコントロールをドッキングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-182">To dock a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-183">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-183">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#9](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]

2. <span data-ttu-id="9cef6-184"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-184">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-185"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は、<xref:System.Windows.Controls.DockPanel> 要素の右側にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-185">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>

## <a name="setting-visibility"></a><span data-ttu-id="9cef6-186">可視性の設定</span><span class="sxs-lookup"><span data-stu-id="9cef6-186">Setting Visibility</span></span>

<span data-ttu-id="9cef6-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.UIElement.Visibility%2A> プロパティを設定することによって、Windows フォームコントロールを非表示にしたり折りたたんだりできます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-187">You can make your Windows Forms control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="9cef6-188">コントロールを非表示にすると、そのコントロールは表示されませんが、レイアウト空間は使用されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-188">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="9cef6-189">コントロールを折りたたむと、そのコントロールは表示されず、レイアウト空間も使用されません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-189">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>

<span data-ttu-id="9cef6-190">ホストされるコントロールの表示を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-190">To set the visibility of a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-191">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-191">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]

2. <span data-ttu-id="9cef6-192">*Mainwindow.xaml*または*MainWindow.xaml.cs*で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-192">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]

3. <span data-ttu-id="9cef6-193"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-193">Press <kbd>F5</kbd> to build and run the application.</span></span>

4. <span data-ttu-id="9cef6-194">[クリックして**非表示に**する] ボタンをクリックすると、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素が非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9cef6-194">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>

5. <span data-ttu-id="9cef6-195">レイアウトの <xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素を完全に非表示にするには、 **[クリック**して閉じる] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-195">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="9cef6-196">Windows フォームコントロールを折りたたむと、周囲の要素が再配置され、そのスペースが占有されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-196">When the Windows Forms control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>

## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="9cef6-197">伸縮しないコントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="9cef6-197">Hosting a Control That Does Not Stretch</span></span>

<span data-ttu-id="9cef6-198">一部の Windows フォームコントロールのサイズは固定されており、レイアウト内の使用可能な領域を塗りつぶすために伸縮しません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-198">Some Windows Forms controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="9cef6-199">たとえば、<xref:System.Windows.Forms.MonthCalendar> コントロールでは、固定領域に月が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-199">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>

<span data-ttu-id="9cef6-200">ストレッチされないコントロールをホストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-200">To host a control that does not stretch, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-201">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-201">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]

2. <span data-ttu-id="9cef6-202"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-202">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-203"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素はグリッド行の中央に配置されますが、使用可能な領域に合わせて拡大されることはありません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-203">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="9cef6-204">ウィンドウのサイズが十分な場合は、ホストされている <xref:System.Windows.Forms.MonthCalendar> コントロールによって複数の月が表示されることがありますが、これらは行の中央に配置されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-204">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="9cef6-205">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウトエンジンは、使用可能な領域に合わせてサイズを変更できない要素を中央揃えにします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-205">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>

## <a name="scaling"></a><span data-ttu-id="9cef6-206">スケーリング</span><span class="sxs-lookup"><span data-stu-id="9cef6-206">Scaling</span></span>

<span data-ttu-id="9cef6-207">WPF 要素とは異なり、ほとんどの Windows フォームコントロールは継続的に拡張できません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-207">Unlike WPF elements, most Windows Forms controls are not continuously scalable.</span></span> <span data-ttu-id="9cef6-208">カスタムスケーリングを提供するには、<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-208">To provide custom scaling, you override the <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9cef6-209">既定の動作を使用してホストされているコントロールをスケーリングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-209">To scale a hosted control by using the default behavior, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-210">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-210">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]

2. <span data-ttu-id="9cef6-211"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-211">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-212">ホストされているコントロールとその周りの要素は、0.5 倍でスケーリングされます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-212">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="9cef6-213">ただし、ホストされているコントロールのフォントはスケーリングされません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-213">However, the hosted control's font is not scaled.</span></span>

<!-- This could use an example of custom scaling. -->

## <a name="rotating"></a><span data-ttu-id="9cef6-214">回転</span><span class="sxs-lookup"><span data-stu-id="9cef6-214">Rotating</span></span>

<span data-ttu-id="9cef6-215">WPF 要素とは異なり、Windows フォームコントロールは回転をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-215">Unlike WPF elements, Windows Forms controls do not support rotation.</span></span> <span data-ttu-id="9cef6-216">回転変換が適用されている場合、<xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は他の WPF 要素とは回転しません。</span><span class="sxs-lookup"><span data-stu-id="9cef6-216">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other WPF elements when a rotation transformation is applied.</span></span> <span data-ttu-id="9cef6-217">180°以外の回転値を指定すると、<xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-217">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>

<span data-ttu-id="9cef6-218">ハイブリッドアプリケーションでのローテーションの効果を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-218">To see the effect of rotation in a hybrid application, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-219">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-219">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]

2. <span data-ttu-id="9cef6-220"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-220">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-221">ホストされているコントロールは回転しませんが、その周りの要素は 180 度の角度で回転します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-221">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="9cef6-222">要素を表示するためにウィンドウのサイズを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9cef6-222">You may have to resize the window to see the elements.</span></span>

## <a name="setting-padding-and-margins"></a><span data-ttu-id="9cef6-223">パディングとマージンの設定</span><span class="sxs-lookup"><span data-stu-id="9cef6-223">Setting Padding and Margins</span></span>

<span data-ttu-id="9cef6-224">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウトの埋め込みと余白は Windows フォームの埋め込みと余白に似ています。</span><span class="sxs-lookup"><span data-stu-id="9cef6-224">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in Windows Forms.</span></span> <span data-ttu-id="9cef6-225"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素の <xref:System.Windows.Controls.Control.Padding%2A> と <xref:System.Windows.FrameworkElement.Margin%2A> のプロパティを設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="9cef6-225">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>

<span data-ttu-id="9cef6-226">ホストされるコントロールの埋め込みと余白を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-226">To set padding and margins for a hosted control, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-227">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-227">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]

2. <span data-ttu-id="9cef6-228"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-228">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-229">埋め込みと余白の設定は、Windows フォームで適用されるのと同じ方法で、ホストされる Windows フォームコントロールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-229">The padding and margin settings are applied to the hosted Windows Forms controls in the same way they would be applied in Windows Forms.</span></span>

## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="9cef6-230">動的レイアウト コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="9cef6-230">Using Dynamic Layout Containers</span></span>

<span data-ttu-id="9cef6-231">Windows フォームには、<xref:System.Windows.Forms.FlowLayoutPanel> と <xref:System.Windows.Forms.TableLayoutPanel>の2つの動的レイアウトコンテナーが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9cef6-231">Windows Forms provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="9cef6-232">これらのコンテナーは [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] レイアウトでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9cef6-232">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>

<span data-ttu-id="9cef6-233">動的レイアウトコンテナーを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-233">To use a dynamic layout container, follow these steps:</span></span>

1. <span data-ttu-id="9cef6-234">次の XAML を <xref:System.Windows.Controls.Grid> 要素にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-234">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element:</span></span>

     [!code-xaml[WpfLayoutHostingWfWithXaml#16](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]

2. <span data-ttu-id="9cef6-235">*Mainwindow.xaml*または*MainWindow.xaml.cs*で、次のコードをクラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9cef6-235">In *MainWindow.xaml.vb* or *MainWindow.xaml.cs*, copy the following code into the class definition:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]

3. <span data-ttu-id="9cef6-236">コンストラクターで `InitializeFlowLayoutPanel` メソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-236">Add a call to the `InitializeFlowLayoutPanel` method in the constructor:</span></span>

     [!code-csharp[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]

4. <span data-ttu-id="9cef6-237"><kbd>F5</kbd> キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-237">Press <kbd>F5</kbd> to build and run the application.</span></span> <span data-ttu-id="9cef6-238"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 要素は <xref:System.Windows.Controls.DockPanel>に入力し、<xref:System.Windows.Forms.FlowLayoutPanel> 子コントロールを既定の <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>に配置します。</span><span class="sxs-lookup"><span data-stu-id="9cef6-238">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cef6-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="9cef6-239">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="9cef6-240">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="9cef6-240">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="9cef6-241">WindowsFormsHost 要素のレイアウトに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="9cef6-241">Layout Considerations for the WindowsFormsHost Element</span></span>](layout-considerations-for-the-windowsformshost-element.md)
- [<span data-ttu-id="9cef6-242">WPF サンプルでの Windows フォームコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="9cef6-242">Arranging Windows Forms Controls in WPF Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159971)
- [<span data-ttu-id="9cef6-243">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="9cef6-243">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="9cef6-244">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="9cef6-244">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
