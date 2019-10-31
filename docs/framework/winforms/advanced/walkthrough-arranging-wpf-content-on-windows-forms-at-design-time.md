---
title: 'チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの配置'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9062a3da9a6020762114702b6cce6b42414ab92d
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197450"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="d0080-102">チュートリアル: デザイン時の Windows フォームでの WPF コンテンツの配置</span><span class="sxs-lookup"><span data-stu-id="d0080-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="d0080-103">この記事では、アンカーやスナップ線などの Windows フォームのレイアウト機能を使用して Windows Presentation Foundation (WPF) コントロールを配置する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0080-103">This article shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d0080-104">必要条件</span><span class="sxs-lookup"><span data-stu-id="d0080-104">Prerequisites</span></span>

<span data-ttu-id="d0080-105">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0080-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d0080-106">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d0080-106">Create the project</span></span>

<span data-ttu-id="d0080-107">Visual Studio を開き、Visual Basic または `ArrangeElementHost`C#という名前の新しい Windows フォームアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0080-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="d0080-108">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d0080-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="d0080-109">WPF コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="d0080-109">Create the WPF control</span></span>

<span data-ttu-id="d0080-110">プロジェクトに WPF コントロール型を追加したら、フォーム状に配置できます。</span><span class="sxs-lookup"><span data-stu-id="d0080-110">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="d0080-111">新しい WPF <xref:System.Windows.Controls.UserControl> をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d0080-111">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="d0080-112">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0080-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="d0080-113">詳細については、「[チュートリアル: デザイン時の Windows フォームでの新しい WPF コンテンツの作成](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0080-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="d0080-114">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0080-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="d0080-115">**[プロパティ]** ウィンドウで、<xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> のプロパティの値を**200**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="d0080-116"><xref:System.Windows.Controls.Control.Background%2A> プロパティの値を**Blue**に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-116">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

5. <span data-ttu-id="d0080-117">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d0080-117">Build the project.</span></span>

## <a name="host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="d0080-118">レイアウトパネルで WPF コントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="d0080-118">Host WPF controls in a layout panel</span></span>

<span data-ttu-id="d0080-119">その他の Windows フォーム コントロールを使用するのと同じ方法で、レイアウト パネルで WPF コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0080-119">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

1. <span data-ttu-id="d0080-120">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="d0080-120">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="d0080-121">**[ツールボックス]** で、<xref:System.Windows.Forms.TableLayoutPanel> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d0080-121">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="d0080-122"><xref:System.Windows.Forms.TableLayoutPanel> コントロールのスマートタグパネルで、 **[最終行の削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0080-122">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="d0080-123">幅と高さが大きくなるよう <xref:System.Windows.Forms.TableLayoutPanel> コントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0080-123">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="d0080-124">**ツールボックス**で、[`UserControl1`] をダブルクリックして、<xref:System.Windows.Forms.TableLayoutPanel> コントロールの最初のセルに `UserControl1` のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0080-124">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="d0080-125">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="d0080-125">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="d0080-126">**ツールボックス**で、[`UserControl1`] をダブルクリックして、<xref:System.Windows.Forms.TableLayoutPanel> コントロールの2番目のセルに別のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d0080-126">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="d0080-127">**[ドキュメントアウトライン]** ウィンドウで、[`tableLayoutPanel1`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0080-127">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span>

8. <span data-ttu-id="d0080-128">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Control.Padding%2A>] プロパティの値を**10、** 10、10、10に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-128">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to **10, 10, 10, 10**.</span></span>

   <span data-ttu-id="d0080-129">両方の <xref:System.Windows.Forms.Integration.ElementHost> コントロールが、新しいレイアウトに収まるようにサイズ変更されました。</span><span class="sxs-lookup"><span data-stu-id="d0080-129">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="d0080-130">スナップ線を使用した WPF コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="d0080-130">Use snaplines to align WPF controls</span></span>

<span data-ttu-id="d0080-131">スナップ線により、フォームのコントロールの配置を簡単に調整できます。</span><span class="sxs-lookup"><span data-stu-id="d0080-131">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="d0080-132">スナップ線を使用して、WPF コントロールも配置することができます。</span><span class="sxs-lookup"><span data-stu-id="d0080-132">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="d0080-133">詳細については、「[チュートリアル: スナップ線を使用した Windows フォームでのコントロールの配置](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0080-133">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

1. <span data-ttu-id="d0080-134">**ツールボックス**から `UserControl1` のインスタンスをフォームにドラッグし、<xref:System.Windows.Forms.TableLayoutPanel> コントロールの下の領域に配置します。</span><span class="sxs-lookup"><span data-stu-id="d0080-134">From the **Toolbox**, drag an instance of `UserControl1` onto the form, and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

   <span data-ttu-id="d0080-135">`UserControl1` のインスタンスは、`elementHost3` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="d0080-135">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="d0080-136">スナップ線を使用して、`elementHost3` の左端を <xref:System.Windows.Forms.TableLayoutPanel> コントロールの左端に揃えます。</span><span class="sxs-lookup"><span data-stu-id="d0080-136">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="d0080-137">スナップ線を使用して、`elementHost3` のサイズを <xref:System.Windows.Forms.TableLayoutPanel> コントロールと同じ幅にします。</span><span class="sxs-lookup"><span data-stu-id="d0080-137">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="d0080-138">コントロール間に中央揃えのスナップ線が表示されるまで`elementHost3` を <xref:System.Windows.Forms.TableLayoutPanel> コントロールの方へ移動します。</span><span class="sxs-lookup"><span data-stu-id="d0080-138">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="d0080-139">**[プロパティ]** ウィンドウで、Margin プロパティの値を20、20、20、20に設定**します。**</span><span class="sxs-lookup"><span data-stu-id="d0080-139">In the **Properties** window, set the value of the Margin property to **20, 20, 20, 20**.</span></span>

6. <span data-ttu-id="d0080-140">中央揃えのスナップ線がもう一度表示されるまで、`elementHost3` を <xref:System.Windows.Forms.TableLayoutPanel> コントロールから移動します。</span><span class="sxs-lookup"><span data-stu-id="d0080-140">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="d0080-141">中央揃えのスナップ線が、余白 20 を示すようになりました。</span><span class="sxs-lookup"><span data-stu-id="d0080-141">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="d0080-142">左端が `elementHost1`の左端に揃うまで `elementHost3` を右に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0080-142">Move `elementHost3` to the right until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="d0080-143">右端が `elementHost2` の右端に配置されるまで、`elementHost3` の幅を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0080-143">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchor-and-dock-wpf-controls"></a><span data-ttu-id="d0080-144">WPF コントロールのアンカーとドッキング</span><span class="sxs-lookup"><span data-stu-id="d0080-144">Anchor and dock WPF controls</span></span>

<span data-ttu-id="d0080-145">フォームでホストされている WPF コントロールは、他の Windows フォーム コントロールと同じ固定とドッキングの動作を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d0080-145">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

1. <span data-ttu-id="d0080-146">`elementHost1` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0080-146">Select `elementHost1`.</span></span>

2. <span data-ttu-id="d0080-147">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Control.Anchor%2A>] プロパティを [**上]、[下]、[左]、[右**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-147">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="d0080-148"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを大きなサイズに変更します。</span><span class="sxs-lookup"><span data-stu-id="d0080-148">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

   <span data-ttu-id="d0080-149">`elementHost1` コントロールがセルを満たすようサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0080-149">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="d0080-150">`elementHost2` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0080-150">Select `elementHost2`.</span></span>

5. <span data-ttu-id="d0080-151">**[プロパティ]** ウィンドウで、[<xref:System.Windows.Forms.Control.Dock%2A>] プロパティの値を <xref:System.Windows.Forms.DockStyle.Fill>に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-151">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="d0080-152">`elementHost2` コントロールがセルを満たすようサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0080-152">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="d0080-153"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0080-153">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="d0080-154"><xref:System.Windows.Forms.Control.Dock%2A> プロパティの値を <xref:System.Windows.Forms.DockStyle.Top> に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-154">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="d0080-155">`elementHost3` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0080-155">Select `elementHost3`.</span></span>

9. <span data-ttu-id="d0080-156"><xref:System.Windows.Forms.Control.Dock%2A> プロパティの値を <xref:System.Windows.Forms.DockStyle.Fill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="d0080-156">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

   <span data-ttu-id="d0080-157">`elementHost3` コントロールが、フォームの残りの領域を満たすようサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="d0080-157">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="d0080-158">フォームのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0080-158">Resize the form.</span></span>

    <span data-ttu-id="d0080-159">3 つすべての <xref:System.Windows.Forms.Integration.ElementHost> コントロールのサイズを適切に変更します。</span><span class="sxs-lookup"><span data-stu-id="d0080-159">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

    <span data-ttu-id="d0080-160">詳細については、「[方法: TableLayoutPanel コントロールで子コントロールを固定およびドッキング](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0080-160">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0080-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0080-161">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d0080-162">方法: TableLayoutPanel コントロールで子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="d0080-162">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d0080-163">方法: デザイン時にフォームの端に合わせてコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="d0080-163">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="d0080-164">チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="d0080-164">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="d0080-165">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="d0080-165">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="d0080-166">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="d0080-166">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="d0080-167">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="d0080-167">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
