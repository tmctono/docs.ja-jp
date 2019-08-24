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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e5112aa0b025648ce68a93f0f3da026ec99fe89
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987144"
---
# <a name="walkthrough-create-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="b746e-102">チュートリアル: デザイン時に Windows フォームに新しい WPF コンテンツを作成する</span><span class="sxs-lookup"><span data-stu-id="b746e-102">Walkthrough: Create new WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="b746e-103">この記事では、Windows フォームベースのアプリケーションで使用するための Windows Presentation Foundation (WPF) コントロールを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b746e-103">This article shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b746e-104">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b746e-104">Prerequisites</span></span>

<span data-ttu-id="b746e-105">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="b746e-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="b746e-106">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="b746e-106">Create the project</span></span>

<span data-ttu-id="b746e-107">Visual Studio を開き、`HostingWpf` という新しい **Windows フォーム アプリ (.NET Framework)** プロジェクトを Visual Basic または Visual C# で作成します。</span><span class="sxs-lookup"><span data-stu-id="b746e-107">Open Visual Studio and create a new **Windows Forms App (.NET Framework)** project in Visual Basic or Visual C# named `HostingWpf`.</span></span>

> [!NOTE]
> <span data-ttu-id="b746e-108">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="b746e-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-a-new-wpf-control"></a><span data-ttu-id="b746e-109">新しい WPF コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="b746e-109">Create a new WPF control</span></span>

<span data-ttu-id="b746e-110">新しい WPF コントロールを作成し、プロジェクトに追加するのは、プロジェクトへの他の項目の追加と同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="b746e-110">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="b746e-111">Windows フォームデザイナーは、*複合コントロール*または*ユーザーコントロール*という名前の特定の種類のコントロールで動作します。</span><span class="sxs-lookup"><span data-stu-id="b746e-111">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="b746e-112">WPF ユーザー コントロールの詳細については、「<xref:System.Windows.Controls.UserControl>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b746e-112">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>

> [!NOTE]
> <span data-ttu-id="b746e-113">WPF の <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> の種類は、同じ <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType> という名前を持つ、Windows フォームで提供されるユーザー コントロールの種類とは区別されます。</span><span class="sxs-lookup"><span data-stu-id="b746e-113">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b746e-114">新しい WPF コントロールを作成するには:</span><span class="sxs-lookup"><span data-stu-id="b746e-114">To create a new WPF control:</span></span>

1. <span data-ttu-id="b746e-115">**ソリューションエクスプローラー**で、新しい**WPF ユーザーコントロールライブラリ (.NET Framework)** プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b746e-115">In **Solution Explorer**, add a new **WPF User Control Library (.NET Framework)** project to the solution.</span></span> <span data-ttu-id="b746e-116">このコントロール ライブラリの既定の名前である `WpfControlLibrary1` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b746e-116">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="b746e-117">既定のコントロールの名前は `UserControl1.xaml` です。</span><span class="sxs-lookup"><span data-stu-id="b746e-117">The default control name is `UserControl1.xaml`.</span></span>

   <span data-ttu-id="b746e-118">新しいコントロールを追加すると、次のような効果があります。</span><span class="sxs-lookup"><span data-stu-id="b746e-118">Adding the new control has the following effects:</span></span>

   - <span data-ttu-id="b746e-119">ファイル UserControl1.xaml が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b746e-119">File UserControl1.xaml is added.</span></span>

   - <span data-ttu-id="b746e-120">UserControl1.xaml.cs ファイル (または UserControl1) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b746e-120">File UserControl1.xaml.cs (or UserControl1.xaml.vb) is added.</span></span> <span data-ttu-id="b746e-121">このファイルには、イベント ハンドラーとその他の実装のための分離コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b746e-121">This file contains the code-behind for event handlers and other implementation.</span></span>

   - <span data-ttu-id="b746e-122">WPF アセンブリへの参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="b746e-122">References to WPF assemblies are added.</span></span>

   - <span data-ttu-id="b746e-123">UserControl1 ファイルは、Visual Studio の WPF デザイナーで開きます。</span><span class="sxs-lookup"><span data-stu-id="b746e-123">File UserControl1.xaml opens in the WPF Designer for Visual Studio.</span></span>

2. <span data-ttu-id="b746e-124">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b746e-124">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="b746e-125">**[プロパティ]** ウィンドウで、プロパティ<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="b746e-125">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="b746e-126">**[ツールボックス]** からコントロール<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>をデザイン画面にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b746e-126">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>

5. <span data-ttu-id="b746e-127">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Controls.TextBox.Text%2A>プロパティの値を ホストされた **[コンテンツ]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="b746e-127">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b746e-128">一般的には、もう少し高度な WPF コンテンツをホストしてください。</span><span class="sxs-lookup"><span data-stu-id="b746e-128">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="b746e-129">ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b746e-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

6. <span data-ttu-id="b746e-130">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b746e-130">Build the project.</span></span>

## <a name="add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="b746e-131">WPF コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="b746e-131">Add a WPF control to a Windows Form</span></span>

<span data-ttu-id="b746e-132">新しい WPF コントロールは、フォームで使用可能な状態です。</span><span class="sxs-lookup"><span data-stu-id="b746e-132">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="b746e-133">Windows フォームは、 <xref:System.Windows.Forms.Integration.ElementHost>コントロールを使用して WPF コンテンツをホストします。</span><span class="sxs-lookup"><span data-stu-id="b746e-133">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content.</span></span>

<span data-ttu-id="b746e-134">WPF コントロールを Windows フォームに追加するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b746e-134">To add a WPF control to a Windows Form:</span></span>

1. <span data-ttu-id="b746e-135">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="b746e-135">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="b746e-136">**ツールボックス**で、 **[WPFUserControlLibrary WPF User Controls]** というラベルのタブを探します。</span><span class="sxs-lookup"><span data-stu-id="b746e-136">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>

3. <span data-ttu-id="b746e-137">`UserControl1` のインスタンスをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b746e-137">Drag an instance of `UserControl1` onto the form.</span></span>

    - <span data-ttu-id="b746e-138">WPF コントロールをホストするためのフォームの上に、<xref:System.Windows.Forms.Integration.ElementHost> コントロールが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b746e-138">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>

    - <span data-ttu-id="b746e-139"><xref:System.Windows.Forms.Integration.ElementHost.Child%2A> `elementHost1`このコントロールにはという名前が付けられ、[プロパティ] ウィンドウで、プロパティが UserControl1 に設定されていることを確認できます。 <xref:System.Windows.Forms.Integration.ElementHost></span><span class="sxs-lookup"><span data-stu-id="b746e-139">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>

    - <span data-ttu-id="b746e-140">WPF アセンブリへの参照がプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="b746e-140">References to WPF assemblies are added to the project.</span></span>

    - <span data-ttu-id="b746e-141">`elementHost1` コントロールに、使用可能なホスティング オプションを示すスマート タグ パネルがあります。</span><span class="sxs-lookup"><span data-stu-id="b746e-141">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>

4. <span data-ttu-id="b746e-142">**[エンティティタスク]** スマートタグパネルで、 **[親コンテナーにドッキング]** する を選択します。</span><span class="sxs-lookup"><span data-stu-id="b746e-142">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>

5. <span data-ttu-id="b746e-143">**F5** キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="b746e-143">Press **F5** to build and run the application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b746e-144">次の手順</span><span class="sxs-lookup"><span data-stu-id="b746e-144">Next steps</span></span>

<span data-ttu-id="b746e-145">Windows フォームと WPF は異なるテクノロジですが、密接に相互運用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="b746e-145">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="b746e-146">アプリケーションの外観と動作を充実させるには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b746e-146">To provide richer appearance and behavior in your applications, try the following:</span></span>

- <span data-ttu-id="b746e-147">WPF ページで Windows フォーム コントロールをホストします。</span><span class="sxs-lookup"><span data-stu-id="b746e-147">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="b746e-148">詳細については、「[チュートリアル:WPF での Windows フォーム コントロールのホスト](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b746e-148">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>

- <span data-ttu-id="b746e-149">WPF コンテンツに Windows フォームの視覚スタイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="b746e-149">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="b746e-150">詳細については、「[方法 :ハイブリッドアプリケーション](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)で視覚スタイルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b746e-150">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>

- <span data-ttu-id="b746e-151">WPF コンテンツのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="b746e-151">Change the style of your WPF content.</span></span> <span data-ttu-id="b746e-152">詳細については、「[チュートリアル:WPF コンテンツ](walkthrough-styling-wpf-content.md)のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="b746e-152">For more information, see [Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b746e-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="b746e-153">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="b746e-154">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="b746e-154">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="b746e-155">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="b746e-155">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="b746e-156">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="b746e-156">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
