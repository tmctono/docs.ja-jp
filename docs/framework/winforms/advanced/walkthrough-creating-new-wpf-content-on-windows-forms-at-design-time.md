---
title: 'チュートリアル: 設計時に Windows フォームで新しい WPF コンテンツを作成'
ms.date: 08/18/2018
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
ms.openlocfilehash: 889e81053d4e2264755468446a4e1681216ae22e
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040376"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="776b1-102">チュートリアル: デザイン時に Windows フォームに新しい WPF コンテンツを作成する</span><span class="sxs-lookup"><span data-stu-id="776b1-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="776b1-103">この記事では、Windows フォームベースのアプリケーションで使用するための Windows Presentation Foundation (WPF) コントロールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="776b1-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="776b1-104">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="776b1-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="776b1-105">プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="776b1-105">Create the project.</span></span>

- <span data-ttu-id="776b1-106">新しい WPF コントロールを作成する。</span><span class="sxs-lookup"><span data-stu-id="776b1-106">Create a new WPF control.</span></span>

- <span data-ttu-id="776b1-107">新しい WPF コントロールを Windows フォームに追加する。</span><span class="sxs-lookup"><span data-stu-id="776b1-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="776b1-108">WPF コントロールは <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="776b1-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="776b1-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="776b1-109">Prerequisites</span></span>

<span data-ttu-id="776b1-110">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="776b1-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="776b1-111">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="776b1-111">Visual Studio</span></span>

## <a name="create-the-project"></a><span data-ttu-id="776b1-112">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="776b1-112">Create the project</span></span>

<span data-ttu-id="776b1-113">まず、Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="776b1-113">The first step is to create the Windows Forms project.</span></span> <span data-ttu-id="776b1-114">Visual Studio を開き、`HostingWpf` という新しい **Windows フォーム アプリ (.NET Framework)** プロジェクトを Visual Basic または Visual C# で作成します。</span><span class="sxs-lookup"><span data-stu-id="776b1-114">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="776b1-115">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="776b1-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="776b1-116">新しい WPF コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="776b1-116">Create a new WPF control</span></span>

<span data-ttu-id="776b1-117">新しい WPF コントロールを作成し、プロジェクトに追加するのは、プロジェクトへの他の項目の追加と同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="776b1-117">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="776b1-118">Windows フォームデザイナーは、*複合コントロール*または*ユーザーコントロール*という名前の特定の種類のコントロールで動作します。</span><span class="sxs-lookup"><span data-stu-id="776b1-118">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="776b1-119">WPF ユーザー コントロールの詳細については、「<xref:System.Windows.Controls.UserControl>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="776b1-119">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="776b1-120">WPF の <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> の種類は、同じ <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> という名前を持つ、Windows フォームで提供されるユーザー コントロールの種類とは区別されます。</span><span class="sxs-lookup"><span data-stu-id="776b1-120">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="776b1-121">新しい WPF コントロールを作成するには:</span><span class="sxs-lookup"><span data-stu-id="776b1-121">To create a new WPF control:</span></span>

1. <span data-ttu-id="776b1-122">**ソリューションエクスプローラー**で、新しい**WPF ユーザーコントロールライブラリ (.NET Framework)** プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="776b1-122">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="776b1-123">このコントロール ライブラリの既定の名前である `WpfControlLibrary1` を使用します。</span><span class="sxs-lookup"><span data-stu-id="776b1-123">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="776b1-124">既定のコントロールの名前は `UserControl1.xaml` です。</span><span class="sxs-lookup"><span data-stu-id="776b1-124">The default control name is `UserControl1.xaml`.</span></span>

     <span data-ttu-id="776b1-125">新しいコントロールを追加すると、次のような効果があります。</span><span class="sxs-lookup"><span data-stu-id="776b1-125">Adding the new control has the following effects:</span></span>

    - <span data-ttu-id="776b1-126">ファイル UserControl1.xaml が追加されます。</span><span class="sxs-lookup"><span data-stu-id="776b1-126">File UserControl1.xaml is added.</span></span>

    - <span data-ttu-id="776b1-127">ファイル UserControl1.xaml.cs または UserControl1.xaml.vb のいずれかが追加されます。</span><span class="sxs-lookup"><span data-stu-id="776b1-127">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="776b1-128">このファイルには、イベント ハンドラーとその他の実装のための分離コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="776b1-128">This file contains the code-behind for event handlers and other implementation.</span></span>

    - <span data-ttu-id="776b1-129">WPF アセンブリへの参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="776b1-129">References to WPF assemblies are added.</span></span>

    - <span data-ttu-id="776b1-130">ファイル UserControl1.xaml が [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] で開きます。</span><span class="sxs-lookup"><span data-stu-id="776b1-130">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>

2. <span data-ttu-id="776b1-131">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="776b1-131">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="776b1-132">詳細については、「[方法 :デザインサーフェイス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))上の要素を選択して移動します。</span><span class="sxs-lookup"><span data-stu-id="776b1-132">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="776b1-133">[**プロパティ**] ウィンドウで、プロパティ<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="776b1-133">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="776b1-134">[**ツールボックス**] からコントロール<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>をデザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="776b1-134">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="776b1-135">[**プロパティ**] ウィンドウで、 <xref:System.Windows.Controls.TextBox.Text%2A>プロパティの値を [ホストされた**コンテンツ**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="776b1-135">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="776b1-136">一般的には、もう少し高度な WPF コンテンツをホストしてください。</span><span class="sxs-lookup"><span data-stu-id="776b1-136">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="776b1-137">ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="776b1-137">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="776b1-138">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="776b1-138">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="776b1-139">WPF コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="776b1-139">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="776b1-140">新しい WPF コントロールは、フォームで使用可能な状態です。</span><span class="sxs-lookup"><span data-stu-id="776b1-140">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="776b1-141">Windows フォームは、 <xref:System.Windows.Forms.Integration.ElementHost>コントロールを使用して WPF コンテンツをホストします。</span><span class="sxs-lookup"><span data-stu-id="776b1-141">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="776b1-142">WPF コントロールを Windows フォームに追加するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="776b1-142">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="776b1-143">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="776b1-143">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="776b1-144">**ツールボックス**で、[ **WPFUserControlLibrary WPF User Controls**] というラベルのタブを探します。</span><span class="sxs-lookup"><span data-stu-id="776b1-144">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="776b1-145">`UserControl1` のインスタンスをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="776b1-145">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="776b1-146">WPF コントロールをホストするためのフォームの上に、<xref:System.Windows.Forms.Integration.ElementHost> コントロールが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="776b1-146">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="776b1-147"><xref:System.Windows.Forms.Integration.ElementHost.Child%2A> `elementHost1`このコントロールにはという名前が付けられ、[プロパティ] ウィンドウで、プロパティが UserControl1 に設定されていることを確認できます。 <xref:System.Windows.Forms.Integration.ElementHost></span><span class="sxs-lookup"><span data-stu-id="776b1-147">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="776b1-148">WPF アセンブリへの参照がプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="776b1-148">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="776b1-149">`elementHost1` コントロールに、使用可能なホスティング オプションを示すスマート タグ パネルがあります。</span><span class="sxs-lookup"><span data-stu-id="776b1-149">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="776b1-150">[**エンティティタスク**] スマートタグパネルで、[**親コンテナーにドッキング**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="776b1-150">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="776b1-151">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="776b1-151">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="776b1-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="776b1-152">Next steps</span></span>

<span data-ttu-id="776b1-153">Windows フォームと WPF は異なるテクノロジですが、密接に相互運用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="776b1-153">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="776b1-154">アプリケーションの外観と動作を充実させるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="776b1-154">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="776b1-155">WPF ページで Windows フォーム コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="776b1-155">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="776b1-156">詳細については、「[チュートリアル:WPF での Windows フォーム コントロールのホスト](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="776b1-156">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="776b1-157">WPF コンテンツに Windows フォームの視覚スタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="776b1-157">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="776b1-158">詳細については、「[方法 :ハイブリッドアプリケーション](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)で視覚スタイルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="776b1-158">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="776b1-159">WPF コンテンツのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="776b1-159">Change the style of your WPF content.</span></span> <span data-ttu-id="776b1-160">詳細については、「[チュートリアル:WPF コンテンツ](walkthrough-styling-wpf-content.md)のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="776b1-160">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="776b1-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="776b1-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="776b1-162">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="776b1-162">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="776b1-163">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="776b1-163">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="776b1-164">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="776b1-164">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
