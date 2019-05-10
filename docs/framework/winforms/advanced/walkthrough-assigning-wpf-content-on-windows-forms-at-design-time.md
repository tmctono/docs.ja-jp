---
title: 'チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの割り当て'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
ms.openlocfilehash: 09427bfc836f40ca9c7aa76f4904bfe7083bf8dc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211237"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="3bd79-102">チュートリアル: デザイン時に Windows フォームでの WPF コンテンツを割り当てる</span><span class="sxs-lookup"><span data-stu-id="3bd79-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="3bd79-103">このチュートリアルでは、フォームに表示する Windows Presentation Foundation (WPF) コントロール型を選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-103">This walkthrough show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="3bd79-104">プロジェクトに含まれている WPF コントロール型であれば、どれでも選択できます。</span><span class="sxs-lookup"><span data-stu-id="3bd79-104">You can select any WPF control types which are included in your project.</span></span>

<span data-ttu-id="3bd79-105">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-105">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="3bd79-106">プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="3bd79-106">Create the project.</span></span>

- <span data-ttu-id="3bd79-107">WPF コントロール型を作成する。</span><span class="sxs-lookup"><span data-stu-id="3bd79-107">Create the WPF control types.</span></span>

- <span data-ttu-id="3bd79-108">WPF コントロールを選択する。</span><span class="sxs-lookup"><span data-stu-id="3bd79-108">Select WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3bd79-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3bd79-109">Prerequisites</span></span>

<span data-ttu-id="3bd79-110">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="3bd79-110">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="3bd79-111">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="3bd79-111">Create the project</span></span>

<span data-ttu-id="3bd79-112">Visual Studio を開き、Visual Basic または Visual で新しい Windows フォーム アプリケーション プロジェクトを作成C#という`SelectingWpfContent`します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-112">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="3bd79-113">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3bd79-113">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="3bd79-114">WPF コントロール型を作成します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-114">Create the WPF control types</span></span>

<span data-ttu-id="3bd79-115">プロジェクトに追加した WPF コントロール型は、さまざまな <xref:System.Windows.Forms.Integration.ElementHost> コントロール内でホストできます。</span><span class="sxs-lookup"><span data-stu-id="3bd79-115">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

## <a name="create-wpf-control-types"></a><span data-ttu-id="3bd79-116">WPF コントロール型を作成します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-116">Create WPF control types</span></span>

1. <span data-ttu-id="3bd79-117">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-117">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="3bd79-118">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="3bd79-119">詳細については、「[チュートリアル:デザイン時に Windows フォームで新しい WPF コンテンツを作成する](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="3bd79-120">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="3bd79-121">詳細については、「[方法 :選択し、デザイン サーフェイス上の要素の移動](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="3bd79-122">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="3bd79-123">追加、<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>への制御、<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを**ホストするコンテンツの**します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-123">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="3bd79-124">WPF <xref:System.Windows.Controls.UserControl> をプロジェクトにもう 1 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-124">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="3bd79-125">コントロール型の既定の名前である `UserControl2.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-125">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="3bd79-126">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-126">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

7. <span data-ttu-id="3bd79-127">追加、<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType>への制御、<xref:System.Windows.Controls.UserControl>の値を設定し、<xref:System.Windows.Controls.TextBox.Text%2A>プロパティを**Hosted Content 2**します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-127">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

 <span data-ttu-id="3bd79-128">**注**一般より高度な WPF コンテンツをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bd79-128">**Note** In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="3bd79-129">ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="3bd79-129">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

1. <span data-ttu-id="3bd79-130">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="3bd79-130">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="3bd79-131">WPF コントロールを選択</span><span class="sxs-lookup"><span data-stu-id="3bd79-131">Select WPF controls</span></span>

<span data-ttu-id="3bd79-132">既にコンテンツをホストしている <xref:System.Windows.Forms.Integration.ElementHost> コントロールに異なる WPF コンテンツを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3bd79-132">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="3bd79-133">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="3bd79-133">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="3bd79-134">**ツールボックス**、 をダブルクリックします`UserControl1`のインスタンスを作成する`UserControl1`形式にします。</span><span class="sxs-lookup"><span data-stu-id="3bd79-134">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="3bd79-135">
  `UserControl1\` のインスタンスは、`elementHost1\` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="3bd79-135">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="3bd79-136">スマート タグ パネルで`elementHost1`、オープン、**ホストされているコンテンツの選択**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="3bd79-136">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="3bd79-137">選択 **[usercontrol2]** ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="3bd79-137">Select **UserControl2** from the drop-down list box.</span></span>

     <span data-ttu-id="3bd79-138">これで、`elementHost1` コントロールが `UserControl2` 型のインスタンスをホストするようになりました。</span><span class="sxs-lookup"><span data-stu-id="3bd79-138">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="3bd79-139">**プロパティ**ウィンドウで、いることを確認、<xref:System.Windows.Forms.Integration.ElementHost.Child%2A>プロパティに設定されて **[usercontrol2]** します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-139">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="3bd79-140">**ツールボックス**の**WPF 相互運用性**グループで、ドラッグ、<xref:System.Windows.Forms.Integration.ElementHost>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="3bd79-140">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

     <span data-ttu-id="3bd79-141">新しい名前として、このコントロールの既定である `elementHost2` を使用します。</span><span class="sxs-lookup"><span data-stu-id="3bd79-141">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="3bd79-142">スマート タグ パネルで`elementHost2`、オープン、**ホストされているコンテンツの選択**ドロップダウン リスト。</span><span class="sxs-lookup"><span data-stu-id="3bd79-142">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="3bd79-143">選択**UserControl1**ドロップダウン リストから。</span><span class="sxs-lookup"><span data-stu-id="3bd79-143">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="3bd79-144">これで、`elementHost2` コントロールが `UserControl1` 型のインスタンスをホストするようになりました。</span><span class="sxs-lookup"><span data-stu-id="3bd79-144">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bd79-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="3bd79-145">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="3bd79-146">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="3bd79-146">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="3bd79-147">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="3bd79-147">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="3bd79-148">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="3bd79-148">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
