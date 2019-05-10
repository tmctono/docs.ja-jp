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
ms.openlocfilehash: a8f690438136450cb12dbcf5e17ddfcca617457e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211443"
---
# <a name="walkthrough-arrange-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="d587c-102">チュートリアル: デザイン時に Windows フォームでの WPF コンテンツを配置します。</span><span class="sxs-lookup"><span data-stu-id="d587c-102">Walkthrough: Arrange WPF content on Windows Forms at design time</span></span>

<span data-ttu-id="d587c-103">このチュートリアルでは、固定やスナップ線などの Windows フォームのレイアウト機能を使用して、Windows Presentation Foundation (WPF) コントロールを配置する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d587c-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>

<span data-ttu-id="d587c-104">このチュートリアルでは次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="d587c-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="d587c-105">プロジェクトを作成する。</span><span class="sxs-lookup"><span data-stu-id="d587c-105">Create the project.</span></span>

- <span data-ttu-id="d587c-106">WPF コントロールを作成する。</span><span class="sxs-lookup"><span data-stu-id="d587c-106">Create the WPF control.</span></span>

- <span data-ttu-id="d587c-107">レイアウト パネルで WPF コントロールをホストする。</span><span class="sxs-lookup"><span data-stu-id="d587c-107">Host WPF controls in a layout panel.</span></span>

- <span data-ttu-id="d587c-108">WPF コントロールを配置するスナップ線を使用する。</span><span class="sxs-lookup"><span data-stu-id="d587c-108">Use snaplines to align WPF controls.</span></span>

- <span data-ttu-id="d587c-109">WPF コントロールを固定してドッキングする。</span><span class="sxs-lookup"><span data-stu-id="d587c-109">Anchor and dock WPF controls.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d587c-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d587c-110">Prerequisites</span></span>

<span data-ttu-id="d587c-111">このチュートリアルを完了するには Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="d587c-111">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d587c-112">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="d587c-112">Create the project</span></span>

<span data-ttu-id="d587c-113">Visual Studio を開き、Visual Basic または Visual で新しい Windows フォーム アプリケーション プロジェクトを作成C#という`ArrangeElementHost`します。</span><span class="sxs-lookup"><span data-stu-id="d587c-113">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>

> [!NOTE]
> <span data-ttu-id="d587c-114">WPF コンテンツをホストする場合は、C# プロジェクトと Visual Basic プロジェクトのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d587c-114">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control"></a><span data-ttu-id="d587c-115">WPF コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d587c-115">Create the WPF control</span></span>

<span data-ttu-id="d587c-116">プロジェクトに WPF コントロール型を追加したら、フォーム状に配置できます。</span><span class="sxs-lookup"><span data-stu-id="d587c-116">After you add a WPF control to the project, you can arrange it on the form.</span></span>

1. <span data-ttu-id="d587c-117">新しい WPF <xref:System.Windows.Controls.UserControl> をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="d587c-117">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="d587c-118">コントロール型の既定の名前である `UserControl1.xaml` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d587c-118">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="d587c-119">詳細については、「[チュートリアル:デザイン時に Windows フォームで新しい WPF コンテンツを作成する](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)します。</span><span class="sxs-lookup"><span data-stu-id="d587c-119">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="d587c-120">デザイン ビューで `UserControl1` が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d587c-120">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="d587c-121">詳細については、「[方法 :選択し、デザイン サーフェイス上の要素の移動](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="d587c-121">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="d587c-122">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.FrameworkElement.Width%2A>と<xref:System.Windows.FrameworkElement.Height%2A>プロパティ`200`します。</span><span class="sxs-lookup"><span data-stu-id="d587c-122">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="d587c-123"><xref:System.Windows.Controls.Control.Background%2A> プロパティの値を `Blue` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d587c-123">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

5. <span data-ttu-id="d587c-124">プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d587c-124">Build the project.</span></span>

## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="d587c-125">レイアウト パネルで WPF コントロールをホストする</span><span class="sxs-lookup"><span data-stu-id="d587c-125">Hosting WPF Controls in a Layout Panel</span></span>
 <span data-ttu-id="d587c-126">その他の Windows フォーム コントロールを使用するのと同じ方法で、レイアウト パネルで WPF コントロールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d587c-126">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>

#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="d587c-127">レイアウト パネルで WPF コントロールをホストするには</span><span class="sxs-lookup"><span data-stu-id="d587c-127">To host WPF controls in a layout panel</span></span>

1. <span data-ttu-id="d587c-128">Windows フォーム デザイナーで `Form1` を開きます。</span><span class="sxs-lookup"><span data-stu-id="d587c-128">Open `Form1` in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="d587c-129">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.TableLayoutPanel>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="d587c-129">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>

3. <span data-ttu-id="d587c-130"><xref:System.Windows.Forms.TableLayoutPanel>コントロールのスマート タグ パネルで、**最後の行を削除**します。</span><span class="sxs-lookup"><span data-stu-id="d587c-130">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>

4. <span data-ttu-id="d587c-131">幅と高さが大きくなるよう <xref:System.Windows.Forms.TableLayoutPanel> コントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="d587c-131">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>

5. <span data-ttu-id="d587c-132">**ツールボックス**、ダブルクリックして`UserControl1`のインスタンスを作成する`UserControl1`の最初のセルで、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d587c-132">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="d587c-133">`UserControl1` のインスタンスは、`elementHost1` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="d587c-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

6. <span data-ttu-id="d587c-134">**ツールボックス**、ダブルクリックして`UserControl1`の 2 番目のセルで別のインスタンスを作成する、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d587c-134">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="d587c-135">**ドキュメント アウトライン**ウィンドウで、`tableLayoutPanel1`します。</span><span class="sxs-lookup"><span data-stu-id="d587c-135">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="d587c-136">詳細については、次を参照してください。[ドキュメント アウトライン ウィンドウ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf)します。</span><span class="sxs-lookup"><span data-stu-id="d587c-136">For more information, see [Document Outline Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/46xf4h0w(v=vs.100)#using-the-document-outline-window-for-silverlight-and-wpf).</span></span>

8. <span data-ttu-id="d587c-137">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Forms.Control.Padding%2A>プロパティを`10, 10, 10, 10`します。</span><span class="sxs-lookup"><span data-stu-id="d587c-137">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>

     <span data-ttu-id="d587c-138">両方の <xref:System.Windows.Forms.Integration.ElementHost> コントロールが、新しいレイアウトに収まるようにサイズ変更されました。</span><span class="sxs-lookup"><span data-stu-id="d587c-138">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>

## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="d587c-139">WPF コントロールを配置するスナップ線を使用する</span><span class="sxs-lookup"><span data-stu-id="d587c-139">Using Snaplines to Align WPF Controls</span></span>
 <span data-ttu-id="d587c-140">スナップ線により、フォームのコントロールの配置を簡単に調整できます。</span><span class="sxs-lookup"><span data-stu-id="d587c-140">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="d587c-141">スナップ線を使用して、WPF コントロールも配置することができます。</span><span class="sxs-lookup"><span data-stu-id="d587c-141">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="d587c-142">詳細については、「[チュートリアル:フォームのスナップ線を使用して Windows 上のコントロール](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)します。</span><span class="sxs-lookup"><span data-stu-id="d587c-142">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="d587c-143">WPF コントロールを配置するスナップ線を使用するには</span><span class="sxs-lookup"><span data-stu-id="d587c-143">To use snaplines to align WPF controls</span></span>

1. <span data-ttu-id="d587c-144">**ツールボックス**のインスタンスをドラッグ`UserControl1`をフォームに下の領域に配置し、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d587c-144">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

     <span data-ttu-id="d587c-145">`UserControl1` のインスタンスは、`elementHost3` という名前の新しい <xref:System.Windows.Forms.Integration.ElementHost> コントロールでホストされます。</span><span class="sxs-lookup"><span data-stu-id="d587c-145">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>

2. <span data-ttu-id="d587c-146">スナップ線を使用して、`elementHost3` の左端を <xref:System.Windows.Forms.TableLayoutPanel> コントロールの左端に揃えます。</span><span class="sxs-lookup"><span data-stu-id="d587c-146">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="d587c-147">スナップ線を使用して、`elementHost3` のサイズを <xref:System.Windows.Forms.TableLayoutPanel> コントロールと同じ幅にします。</span><span class="sxs-lookup"><span data-stu-id="d587c-147">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="d587c-148">コントロール間に中央揃えのスナップ線が表示されるまで`elementHost3` を <xref:System.Windows.Forms.TableLayoutPanel> コントロールの方へ移動します。</span><span class="sxs-lookup"><span data-stu-id="d587c-148">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>

5. <span data-ttu-id="d587c-149">**プロパティ**ウィンドウで、余白プロパティの値を設定する`20, 20, 20, 20`します。</span><span class="sxs-lookup"><span data-stu-id="d587c-149">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>

6. <span data-ttu-id="d587c-150">中央揃えのスナップ線がもう一度表示されるまで、`elementHost3` を <xref:System.Windows.Forms.TableLayoutPanel> コントロールから移動します。</span><span class="sxs-lookup"><span data-stu-id="d587c-150">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="d587c-151">中央揃えのスナップ線が、余白 20 を示すようになりました。</span><span class="sxs-lookup"><span data-stu-id="d587c-151">The center snapline now indicates a margin of 20.</span></span>

7. <span data-ttu-id="d587c-152">左端が `elementHost1` の左端に配置されるまで、`elementHost3` を右に移動します。</span><span class="sxs-lookup"><span data-stu-id="d587c-152">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>

8. <span data-ttu-id="d587c-153">右端が `elementHost2` の右端に配置されるまで、`elementHost3` の幅を変更します。</span><span class="sxs-lookup"><span data-stu-id="d587c-153">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>

## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="d587c-154">WPF コントロールの固定およびドッキング</span><span class="sxs-lookup"><span data-stu-id="d587c-154">Anchoring and Docking WPF Controls</span></span>
 <span data-ttu-id="d587c-155">フォームでホストされている WPF コントロールは、他の Windows フォーム コントロールと同じ固定とドッキングの動作を持ちます。</span><span class="sxs-lookup"><span data-stu-id="d587c-155">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>

#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="d587c-156">WPF コントロールを固定してドッキングするには</span><span class="sxs-lookup"><span data-stu-id="d587c-156">To anchor and dock WPF controls</span></span>

1. <span data-ttu-id="d587c-157">`elementHost1` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d587c-157">Select `elementHost1`.</span></span>

2. <span data-ttu-id="d587c-158">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを**Top、Bottom、Left、Right**します。</span><span class="sxs-lookup"><span data-stu-id="d587c-158">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>

3. <span data-ttu-id="d587c-159"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを大きなサイズに変更します。</span><span class="sxs-lookup"><span data-stu-id="d587c-159">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>

     <span data-ttu-id="d587c-160">`elementHost1` コントロールがセルを満たすようサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="d587c-160">The `elementHost1` control resizes to fill the cell.</span></span>

4. <span data-ttu-id="d587c-161">`elementHost2` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d587c-161">Select `elementHost2`.</span></span>

5. <span data-ttu-id="d587c-162">**プロパティ**ウィンドウで、設定の値、<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Fill>します。</span><span class="sxs-lookup"><span data-stu-id="d587c-162">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="d587c-163">`elementHost2` コントロールがセルを満たすようサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="d587c-163">The `elementHost2` control resizes to fill the cell.</span></span>

6. <span data-ttu-id="d587c-164"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d587c-164">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

7. <span data-ttu-id="d587c-165"><xref:System.Windows.Forms.Control.Dock%2A> プロパティの値を <xref:System.Windows.Forms.DockStyle.Top> に設定します。</span><span class="sxs-lookup"><span data-stu-id="d587c-165">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>

8. <span data-ttu-id="d587c-166">`elementHost3` を選択します。</span><span class="sxs-lookup"><span data-stu-id="d587c-166">Select `elementHost3`.</span></span>

9. <span data-ttu-id="d587c-167"><xref:System.Windows.Forms.Control.Dock%2A> プロパティの値を <xref:System.Windows.Forms.DockStyle.Fill> に設定します。</span><span class="sxs-lookup"><span data-stu-id="d587c-167">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

     <span data-ttu-id="d587c-168">`elementHost3` コントロールが、フォームの残りの領域を満たすようサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="d587c-168">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>

10. <span data-ttu-id="d587c-169">フォームのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="d587c-169">Resize the form.</span></span>

     <span data-ttu-id="d587c-170">3 つすべての <xref:System.Windows.Forms.Integration.ElementHost> コントロールのサイズを適切に変更します。</span><span class="sxs-lookup"><span data-stu-id="d587c-170">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>

     <span data-ttu-id="d587c-171">詳細については、「[方法 :固定およびドッキング TableLayoutPanel コントロールで子コントロール](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="d587c-171">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d587c-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="d587c-172">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d587c-173">方法: 固定およびドッキング TableLayoutPanel コントロールで子コントロール</span><span class="sxs-lookup"><span data-stu-id="d587c-173">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d587c-174">方法: デザイン時にコントロールをフォームの端を揃える</span><span class="sxs-lookup"><span data-stu-id="d587c-174">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)
- [<span data-ttu-id="d587c-175">チュートリアル: スナップ線を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="d587c-175">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="d587c-176">移行と相互運用性</span><span class="sxs-lookup"><span data-stu-id="d587c-176">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="d587c-177">WPF コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="d587c-177">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="d587c-178">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="d587c-178">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
