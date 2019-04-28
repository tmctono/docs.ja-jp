---
title: 'チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: ed48db399ba47f0e6be96f7bca33d3892b19e433
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747685"
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="df219-102">チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成</span><span class="sxs-lookup"><span data-stu-id="df219-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>

<span data-ttu-id="df219-103">このトピックでは、Windows フォーム ベースのアプリケーションで使用する Windows Presentation Foundation (WPF) コントロールを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="df219-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="df219-104">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="df219-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="df219-105">プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="df219-105">Create the project.</span></span>

- <span data-ttu-id="df219-106">新しい WPF コントロールを作成する。</span><span class="sxs-lookup"><span data-stu-id="df219-106">Create a new WPF control.</span></span>

- <span data-ttu-id="df219-107">新しい WPF コントロールを Windows フォームに追加する。</span><span class="sxs-lookup"><span data-stu-id="df219-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="df219-108">WPF コントロールは <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="df219-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df219-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="df219-109">Prerequisites</span></span>

<span data-ttu-id="df219-110">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="df219-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="df219-111">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="df219-111">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="df219-112">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="df219-112">Creating the Project</span></span>

<span data-ttu-id="df219-113">まず、Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="df219-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="df219-114">Visual Studio を開き、新しい作成**Windows フォーム アプリ (.NET Framework)** Visual Basic または Visual c# のという名前でプロジェクト`HostingWpf`します。</span><span class="sxs-lookup"><span data-stu-id="df219-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="df219-115">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="df219-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="df219-116">新しい WPF コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="df219-116">Creating a New WPF Control</span></span>

<span data-ttu-id="df219-117">新しい WPF コントロールを作成し、プロジェクトに追加するのは、プロジェクトへの他の項目の追加と同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="df219-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="df219-118">Windows フォーム デザイナーがという名前のコントロールの特定の種類を連携*複合コントロール*、または*ユーザー コントロール*します。</span><span class="sxs-lookup"><span data-stu-id="df219-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="df219-119">WPF ユーザー コントロールの詳細については、「<xref:System.Windows.Controls.UserControl>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df219-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="df219-120">WPF の <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> の種類は、同じ <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> という名前を持つ、Windows フォームで提供されるユーザー コントロールの種類とは区別されます。</span><span class="sxs-lookup"><span data-stu-id="df219-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="df219-121">新しい WPF コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="df219-121">To create a new WPF control</span></span>

1. <span data-ttu-id="df219-122">**ソリューション エクスプ ローラー**、新しい追加**WPF ユーザー コントロール ライブラリ (.NET Framework)** プロジェクトがソリューションにします。</span><span class="sxs-lookup"><span data-stu-id="df219-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="df219-123">このコントロール ライブラリの既定の名前である `WpfControlLibrary1` を使用します。</span><span class="sxs-lookup"><span data-stu-id="df219-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="df219-124">既定のコントロールの名前は `UserControl1.xaml` です。</span><span class="sxs-lookup"><span data-stu-id="df219-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="df219-125">新しいコントロールを追加すると、次の効果があります。</span><span class="sxs-lookup"><span data-stu-id="df219-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="df219-126">ファイル UserControl1.xaml が追加されます。</span><span class="sxs-lookup"><span data-stu-id="df219-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="df219-127">ファイル UserControl1.xaml.cs または UserControl1.xaml.vb のいずれかが追加されます。</span><span class="sxs-lookup"><span data-stu-id="df219-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="df219-128">このファイルには、イベント ハンドラーとその他の実装のための分離コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df219-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="df219-129">WPF アセンブリへの参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="df219-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="df219-130">ファイル UserControl1.xaml が [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] で開きます。</span><span class="sxs-lookup"><span data-stu-id="df219-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="df219-131">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df219-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="df219-132">詳細については、「[方法 :選択し、デザイン サーフェイス上の要素の移動](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="df219-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="df219-133">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ**200**します。</span><span class="sxs-lookup"><span data-stu-id="df219-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="df219-134">**ツールボックス**、ドラッグ、<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>コントロールをデザイン画面。</span><span class="sxs-lookup"><span data-stu-id="df219-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="df219-135">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを**ホストするコンテンツの**します。</span><span class="sxs-lookup"><span data-stu-id="df219-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="df219-136">一般的には、もう少し高度な WPF コンテンツをホストしてください。</span><span class="sxs-lookup"><span data-stu-id="df219-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="df219-137">ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="df219-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="df219-138">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="df219-138">Build the project.</span></span>

## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="df219-139">WPF コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="df219-139">Adding a WPF Control to a Windows Form</span></span>

<span data-ttu-id="df219-140">新しい WPF コントロールは、フォームで使用可能な状態です。</span><span class="sxs-lookup"><span data-stu-id="df219-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="df219-141">Windows フォームを使用して、 <xref:System.Windows.Forms.Integration.ElementHost> WPF コンテンツをホストするコントロール。</span><span class="sxs-lookup"><span data-stu-id="df219-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="df219-142">WPF コントロールを Windows フォームに追加するには</span><span class="sxs-lookup"><span data-stu-id="df219-142">To add a WPF control to a Windows Form</span></span>

1. <span data-ttu-id="df219-143">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="df219-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="df219-144">**ツールボックス**、というラベルのタブを見つける**WPFUserControlLibrary WPF ユーザー コントロール**します。</span><span class="sxs-lookup"><span data-stu-id="df219-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="df219-145">`UserControl1` のインスタンスをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="df219-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="df219-146">WPF コントロールをホストするためのフォームの上に、<xref:System.Windows.Forms.Integration.ElementHost> コントロールが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="df219-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="df219-147"><xref:System.Windows.Forms.Integration.ElementHost>コントロールの名前は`elementHost1`し、**プロパティ**ウィンドウに、表示できるその<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>プロパティに設定されて**UserControl1**。</span><span class="sxs-lookup"><span data-stu-id="df219-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="df219-148">WPF アセンブリへの参照がプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="df219-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="df219-149">`elementHost1` コントロールに、使用可能なホスティング オプションを示すスマート タグ パネルがあります。</span><span class="sxs-lookup"><span data-stu-id="df219-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="df219-150">**ElementHost タスク**スマート タグ パネルで、**親コンテナーにドッキング**します。</span><span class="sxs-lookup"><span data-stu-id="df219-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="df219-151">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="df219-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df219-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="df219-152">Next Steps</span></span>

<span data-ttu-id="df219-153">Windows フォームと WPF は異なるテクノロジですが、密接に相互運用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="df219-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="df219-154">高度な外観とをアプリケーションでの動作を提供するには、次を試してください。</span><span class="sxs-lookup"><span data-stu-id="df219-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="df219-155">WPF ページで Windows フォーム コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="df219-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="df219-156">詳細については、「[チュートリアル:WPF でのフォーム コントロールのホストを Windows](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)します。</span><span class="sxs-lookup"><span data-stu-id="df219-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="df219-157">WPF コンテンツに Windows フォームの視覚スタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="df219-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="df219-158">詳細については、「[方法 :ハイブリッド アプリケーションで視覚スタイルを有効にする](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="df219-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="df219-159">WPF コンテンツのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="df219-159">Change the style of your WPF content.</span></span> <span data-ttu-id="df219-160">詳細については、「[チュートリアル:WPF コンテンツのスタイル設定](walkthrough-styling-wpf-content.md)します。</span><span class="sxs-lookup"><span data-stu-id="df219-160">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df219-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="df219-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="df219-162">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="df219-162">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="df219-163">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="df219-163">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="df219-164">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="df219-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
