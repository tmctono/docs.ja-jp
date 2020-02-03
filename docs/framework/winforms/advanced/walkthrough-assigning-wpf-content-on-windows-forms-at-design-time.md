---
title: Windows フォームの WPF コントロールを選択する
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 19f1dfec282b025f5a1fa367ec5fa9a52472c691
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746802"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="77a7a-102">チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの割り当て</span><span class="sxs-lookup"><span data-stu-id="77a7a-102">Walkthrough: Assign WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="77a7a-103">この記事では、フォームに表示する Windows Presentation Foundation (WPF) コントロールの種類を選択する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-103">This article show you how to select the Windows Presentation Foundation (WPF) control types you want to display on your form.</span></span> <span data-ttu-id="77a7a-104">プロジェクトに含まれている WPF コントロールの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-104">You can select any WPF control types that are included in your project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="77a7a-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="77a7a-105">Prerequisites</span></span>

<span data-ttu-id="77a7a-106">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="77a7a-106">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="77a7a-107">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="77a7a-107">Create the project</span></span>

<span data-ttu-id="77a7a-108">Visual Studio を開き、Visual Basic または `SelectingWpfContent`C#という名前の新しい Windows フォームアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-108">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `SelectingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="77a7a-109">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-109">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="77a7a-110">WPF コントロール型を作成する</span><span class="sxs-lookup"><span data-stu-id="77a7a-110">Create the WPF control types</span></span>

<span data-ttu-id="77a7a-111">プロジェクトに追加した WPF コントロール型は、さまざまな <xref:System.Windows.Forms.Integration.ElementHost> コントロール内でホストできます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-111">After you add WPF control types to the project, you can host them in different <xref:System.Windows.Forms.Integration.ElementHost> controls.</span></span>

1. <span data-ttu-id="77a7a-112">新しい WPF <xref:System.Windows.Controls.UserControl> プロジェクトをソリューションに追加します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-112">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="77a7a-113">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-113">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="77a7a-114">詳細については、「[チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77a7a-114">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="77a7a-115">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-115">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="77a7a-116">**[プロパティ]** ウィンドウで、<xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> のプロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-116">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="77a7a-117"><xref:System.Windows.Controls.UserControl> に <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを追加し、<xref:System.Windows.Controls.TextBox.Text%2A> プロパティの値を**Hosted Content**に設定します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-117">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>

5. <span data-ttu-id="77a7a-118">WPF <xref:System.Windows.Controls.UserControl> をプロジェクトにもう 1 つ追加します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-118">Add a second WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="77a7a-119">コントロール型の既定の名前である `UserControl2.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-119">Use the default name for the control type, `UserControl2.xaml`.</span></span>

6. <span data-ttu-id="77a7a-120">**[プロパティ]** ウィンドウで、<xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> のプロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

7. <span data-ttu-id="77a7a-121"><xref:System.Windows.Controls.UserControl> に <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを追加し、<xref:System.Windows.Controls.TextBox.Text%2A> プロパティの値を**Hosted Content 2**に設定します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-121">Add a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content 2**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="77a7a-122">一般的には、もう少し高度な WPF コンテンツをホストしてください。</span><span class="sxs-lookup"><span data-stu-id="77a7a-122">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="77a7a-123">ここでは、説明する目的でのみ <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> コントロールを使用しています。</span><span class="sxs-lookup"><span data-stu-id="77a7a-123">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>

8. <span data-ttu-id="77a7a-124">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="77a7a-124">Build the project.</span></span>

## <a name="select-wpf-controls"></a><span data-ttu-id="77a7a-125">WPF コントロールの選択</span><span class="sxs-lookup"><span data-stu-id="77a7a-125">Select WPF controls</span></span>

<span data-ttu-id="77a7a-126">既にコンテンツをホストしている <xref:System.Windows.Forms.Integration.ElementHost> コントロールに異なる WPF コンテンツを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-126">You can assign different WPF content to an <xref:System.Windows.Forms.Integration.ElementHost> control, which is already hosting content.</span></span>

1. <span data-ttu-id="77a7a-127">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-127">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="77a7a-128">**ツールボックス**の [`UserControl1`] をダブルクリックして、フォームに `UserControl1` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-128">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="77a7a-129">`UserControl1` のインスタンスは、<xref:System.Windows.Forms.Integration.ElementHost> という名前の新しい `elementHost1` コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-129">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

3. <span data-ttu-id="77a7a-130">`elementHost1`のスマートタグパネルで、 **[ホスト**されているコンテンツの選択] ドロップダウンリストを開きます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-130">In the smart tag panel for `elementHost1`, open the **Select Hosted Content** drop-down list.</span></span>

4. <span data-ttu-id="77a7a-131">ドロップダウンリストボックスから  **usercontrol2**  を選択します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-131">Select **UserControl2** from the drop-down list box.</span></span>

   <span data-ttu-id="77a7a-132">これで、`elementHost1` コントロールが `UserControl2` 型のインスタンスをホストするようになりました。</span><span class="sxs-lookup"><span data-stu-id="77a7a-132">The `elementHost1` control now hosts an instance of the `UserControl2` type.</span></span>

5. <span data-ttu-id="77a7a-133">**プロパティ** ウィンドウで、<xref:System.Windows.Forms.Integration.ElementHost.Child%2A> プロパティが  **usercontrol2** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-133">In the **Properties** window, confirm that the <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl2**.</span></span>

6. <span data-ttu-id="77a7a-134">**[ツールボックス]** の **[WPF 相互運用性]** グループで、[<xref:System.Windows.Forms.Integration.ElementHost>] コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="77a7a-134">From the **Toolbox**, in the **WPF Interoperability** group, drag an <xref:System.Windows.Forms.Integration.ElementHost> control onto the form.</span></span>

   <span data-ttu-id="77a7a-135">新しい名前として、このコントロールの既定である `elementHost2` を使用します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-135">The default name for the new control is `elementHost2`.</span></span>

7. <span data-ttu-id="77a7a-136">`elementHost2`のスマートタグパネルで、 **[ホスト**されているコンテンツの選択] ドロップダウンリストを開きます。</span><span class="sxs-lookup"><span data-stu-id="77a7a-136">In the smart tag panel for `elementHost2`, open the **Select Hosted Content** drop-down list.</span></span>

8. <span data-ttu-id="77a7a-137">ドロップダウンリストから **[UserControl1]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="77a7a-137">Select **UserControl1** from the drop-down list.</span></span>

9. <span data-ttu-id="77a7a-138">これで、`elementHost2` コントロールが `UserControl1` 型のインスタンスをホストするようになりました。</span><span class="sxs-lookup"><span data-stu-id="77a7a-138">The `elementHost2` control now hosts an instance of the `UserControl1` type.</span></span>

## <a name="see-also"></a><span data-ttu-id="77a7a-139">参照</span><span class="sxs-lookup"><span data-stu-id="77a7a-139">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="77a7a-140">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="77a7a-140">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="77a7a-141">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="77a7a-141">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="77a7a-142">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="77a7a-142">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
