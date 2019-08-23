---
title: 'チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], arranging with snaplines
- snaplines [Windows Forms], arranging Windows Forms controls
- SnapLine class [Windows Forms], walkthroughs
- Windows Forms controls, arranging
ms.assetid: d5c9edc7-cf30-4a97-8ebe-201d569340f8
ms.openlocfilehash: 8ac1ba6b8121aabea3c992ca5b943f231fc19ce2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950072"
---
# <a name="walkthrough-arranging-controls-on-windows-forms-using-snaplines"></a><span data-ttu-id="ac1b0-102">チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-102">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>
<span data-ttu-id="ac1b0-103">フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="ac1b0-104">Windows フォームデザイナーには、これを実現するための多数のレイアウトツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-104">The Windows Forms Designer gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="ac1b0-105">最も重要なものの1つ<xref:System.Windows.Forms.Design.Behavior.SnapLine>は、機能です。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-105">One of the most important is the <xref:System.Windows.Forms.Design.Behavior.SnapLine> feature.</span></span>

 <span data-ttu-id="ac1b0-106">スナップ線を使用すると、他のコントロールとコントロールを整列する場所を正確に確認できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-106">Snaplines show you precisely where to line up controls with other controls.</span></span> <span data-ttu-id="ac1b0-107">また、Windows ユーザーインターフェイスのガイドラインに従って、コントロール間の余白の推奨される距離も示しています。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-107">They also show you the recommended distances for margins between controls, as specified by the Windows User Interface Guidelines.</span></span> <span data-ttu-id="ac1b0-108">詳細については、「[ユーザーインターフェイスのデザインと開発](https://go.microsoft.com/FWLink/?LinkId=83878)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-108">For details, see [User Interface Design and Development](https://go.microsoft.com/FWLink/?LinkId=83878).</span></span>

 <span data-ttu-id="ac1b0-109">スナップ線を使用すると、コントロールの配置が簡単になり、プロフェッショナルな外観と動作 (ルックアンドフィール) がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-109">Snaplines make it easy to align your controls, for crisp, professional appearance and behavior (look and feel).</span></span>

 <span data-ttu-id="ac1b0-110">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ac1b0-111">Windows フォーム プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ac1b0-111">Creating a Windows Forms project</span></span>

- <span data-ttu-id="ac1b0-112">スナップ線を使用したコントロールの間隔と配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-112">Spacing and Aligning Controls Using Snaplines</span></span>

- <span data-ttu-id="ac1b0-113">配置 (フォームとコンテナーの余白に)</span><span class="sxs-lookup"><span data-stu-id="ac1b0-113">Aligning to Form and Container Margins</span></span>

- <span data-ttu-id="ac1b0-114">配置 (グループ化コントロールに)</span><span class="sxs-lookup"><span data-stu-id="ac1b0-114">Aligning to Grouped Controls</span></span>

- <span data-ttu-id="ac1b0-115">スナップ線を使用したサイズのアウトライン化によるコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-115">Using Snaplines to Place a Control by Outlining Its Size</span></span>

- <span data-ttu-id="ac1b0-116">ツールボックスからコントロールをドラッグするときにスナップ線を使用する</span><span class="sxs-lookup"><span data-stu-id="ac1b0-116">Using Snaplines When Dragging a Control from the Toolbox</span></span>

- <span data-ttu-id="ac1b0-117">スナップ線を使用したコントロールのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="ac1b0-117">Resizing Controls Using Snaplines</span></span>

- <span data-ttu-id="ac1b0-118">コントロールのテキストへのラベルの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-118">Aligning a Label to a Control's Text</span></span>

- <span data-ttu-id="ac1b0-119">キーボードナビゲーションでのスナップ線の使用</span><span class="sxs-lookup"><span data-stu-id="ac1b0-119">Using Snaplines with Keyboard Navigation</span></span>

- <span data-ttu-id="ac1b0-120">スナップ線とレイアウトパネル</span><span class="sxs-lookup"><span data-stu-id="ac1b0-120">Snaplines and Layout Panels</span></span>

- <span data-ttu-id="ac1b0-121">スナップガイドラインの無効化</span><span class="sxs-lookup"><span data-stu-id="ac1b0-121">Disabling Snaplines</span></span>

 <span data-ttu-id="ac1b0-122">終了すると、スナップ線機能によって再生されるレイアウトロールについて理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-122">When you are finished, you will have an understanding of the layout role played by the snaplines feature.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="ac1b0-123">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ac1b0-123">Creating the Project</span></span>
 <span data-ttu-id="ac1b0-124">最初にプロジェクトを作成し、フォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-124">The first step is to create the project and set up the form.</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="ac1b0-125">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-125">To create the project</span></span>

1. <span data-ttu-id="ac1b0-126">"SnaplineExample" という名前の Windows ベースのアプリケーションプロジェクトを作成します (**ファイル** >  **新しい** > **プロジェクト** >   **C# Visual** または クラシック**Visual Basic** > )。デスクトップ > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-126">Create a Windows-based application project called "SnaplineExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="ac1b0-127">フォームデザイナーでフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-127">Select the form in the Forms Designer.</span></span>

## <a name="spacing-and-aligning-controls-using-snaplines"></a><span data-ttu-id="ac1b0-128">スナップ線を使用したコントロールの間隔と配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-128">Spacing and Aligning Controls Using Snaplines</span></span>
 <span data-ttu-id="ac1b0-129">スナップ線を使用すると、フォーム上にコントロールを配置するための正確で直感的な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-129">Snaplines give you an accurate and intuitive way to align controls on your form.</span></span> <span data-ttu-id="ac1b0-130">これは、選択したコントロールを、別のコントロールまたはコントロールのセットと一致する位置の近くに移動するときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-130">They appear when you are moving a selected control or controls near a position that would align with another control or set of controls.</span></span> <span data-ttu-id="ac1b0-131">他のコントロールを移動すると、選択した位置が提案された位置に "スナップ" されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-131">Your selection will "snap" to the suggested position as you move it past the other controls.</span></span>

### <a name="to-arrange-controls-using-snaplines"></a><span data-ttu-id="ac1b0-132">スナップ線を使用してコントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-132">To arrange controls using snaplines</span></span>

1. <span data-ttu-id="ac1b0-133"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-133">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="ac1b0-134">コントロールを<xref:System.Windows.Forms.Button>フォームの右下隅に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-134">Move the <xref:System.Windows.Forms.Button> control to the lower-right corner of the form.</span></span> <span data-ttu-id="ac1b0-135"><xref:System.Windows.Forms.Button>コントロールとして表示されるスナップ線は、フォームの下と右の境界線に近づいています。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-135">Note the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the form.</span></span> <span data-ttu-id="ac1b0-136">これらのスナップ線には、コントロールの境界線とフォームとの間の推奨される距離が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-136">These snaplines display the recommended distance between the borders of the control and the form.</span></span>

3. <span data-ttu-id="ac1b0-137">フォームの<xref:System.Windows.Forms.Button>境界線を囲むようにコントロールを移動し、スナップ線が表示される場所をメモします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-137">Move the <xref:System.Windows.Forms.Button> control around the borders of the form and note where the snaplines appear.</span></span> <span data-ttu-id="ac1b0-138"><xref:System.Windows.Forms.Button>操作が完了したら、フォームの中央付近にコントロールを移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-138">When you are finished, move the <xref:System.Windows.Forms.Button> control near the center of the form.</span></span>

4. <span data-ttu-id="ac1b0-139"><xref:System.Windows.Forms.Button> **ツールボックス**から別のコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-139">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="ac1b0-140">2番目<xref:System.Windows.Forms.Button>のコントロールを、最初のコントロールとほぼ同じになるまで移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-140">Move the second <xref:System.Windows.Forms.Button> control until it is nearly level with the first.</span></span> <span data-ttu-id="ac1b0-141">両方のボタンのテキストベースラインに表示されるスナップ線に注目してください。移動しようとしているコントロールは、他のコントロールと正確に同じ位置にスナップします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-141">Note the snapline that appears at the text baseline of both buttons, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

6. <span data-ttu-id="ac1b0-142">最初のコントロール<xref:System.Windows.Forms.Button>のすぐ上に配置されるまで、2番目のコントロールを移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-142">Move the second <xref:System.Windows.Forms.Button> control until it is positioned directly above the first.</span></span> <span data-ttu-id="ac1b0-143">両方のボタンの左端と右端に表示されるスナップ線に注目してください。移動するコントロールは、他のコントロールと正確に一致する位置にスナップされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-143">Note the snaplines that appear along the left and right edges of both buttons, and note that the control you are moving snaps to a position that is exactly aligned with the other control.</span></span>

7. <span data-ttu-id="ac1b0-144"><xref:System.Windows.Forms.Button>コントロールの1つを選択し、ほぼタッチするまで、そのコントロールの近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-144">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span> <span data-ttu-id="ac1b0-145">これらの間に表示されるスナップ線に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-145">Note the snapline that appears between them.</span></span> <span data-ttu-id="ac1b0-146">この距離は、コントロールの境界線の間の推奨される距離です。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-146">This distance is the recommended distance between the borders of the controls.</span></span> <span data-ttu-id="ac1b0-147">また、移動しようとしているコントロールがこの位置にスナップされることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-147">Also note that the control you are moving snaps to this position.</span></span>

8. <span data-ttu-id="ac1b0-148"><xref:System.Windows.Forms.Panel> **ツールボックス**からフォームに2つのコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-148">Drag two <xref:System.Windows.Forms.Panel> controls from the **Toolbox** onto your form.</span></span>

9. <span data-ttu-id="ac1b0-149"><xref:System.Windows.Forms.Panel>コントロールの1つを、最初のコントロールの最上位レベルまで移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-149">Move one of the <xref:System.Windows.Forms.Panel> controls until it is nearly level with the first.</span></span> <span data-ttu-id="ac1b0-150">両方のコントロールの上端と下端に表示されるスナップ線に注目します。また、移動しようとしているコントロールは、他のコントロールと正確に同じ位置にスナップします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-150">Note the snaplines that appear along the top and bottom edges of both controls, and note that the control you are moving snaps to a position that is exactly level with the other control.</span></span>

## <a name="aligning-to-form-and-container-margins"></a><span data-ttu-id="ac1b0-151">配置 (フォームとコンテナーの余白に)</span><span class="sxs-lookup"><span data-stu-id="ac1b0-151">Aligning to Form and Container Margins</span></span>
 <span data-ttu-id="ac1b0-152">スナップ線を使用すると、一貫した方法でコントロールを配置し、コンテナーの余白を整えることができます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-152">Snaplines help you to align your controls to form and container margins in a consistent manner.</span></span>

### <a name="to-align-controls-to-form-and-container-margins"></a><span data-ttu-id="ac1b0-153">コントロールをフォームとコンテナーの余白に合わせるには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-153">To align controls to form and container margins</span></span>

1. <span data-ttu-id="ac1b0-154"><xref:System.Windows.Forms.Button>コントロールの1つを選択し、スナップ線が表示されるまで、フォームの右の境界線の近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-154">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="ac1b0-155">右の境界線からのスナップ線の距離は、コントロールの<xref:System.Windows.Forms.Control.Margin%2A>プロパティとフォームの<xref:System.Windows.Forms.Control.Padding%2A>プロパティ値の合計です。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-155">The snapline's distance from the right border is the sum of the control's <xref:System.Windows.Forms.Control.Margin%2A> property and the form's <xref:System.Windows.Forms.Control.Padding%2A> property values.</span></span>

> [!NOTE]
> <span data-ttu-id="ac1b0-156">フォームの<xref:System.Windows.Forms.Control.Padding%2A>プロパティが0、0、0、0に設定されている場合、Windows フォームデザイナーによって<xref:System.Windows.Forms.Control.Padding%2A> 、フォームには9、9、9、9の影付きの値が与えられます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-156">If the form's <xref:System.Windows.Forms.Control.Padding%2A> property is set to 0,0,0,0, the Windows Forms Designer gives the form a shadowed <xref:System.Windows.Forms.Control.Padding%2A> value of 9,9,9,9.</span></span> <span data-ttu-id="ac1b0-157">この動作をオーバーライドするには、0、0、0、0以外の値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-157">To override this behavior, assign a value other than 0,0,0,0.</span></span>

1. <span data-ttu-id="ac1b0-158">[プロパティ] ウィンドウで<xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Margin%2A>エントリを展開し、 プロパティを0に設定して、コントロールのプロパティの値を変更します。<xref:System.Windows.Forms.Padding.All%2A></span><span class="sxs-lookup"><span data-stu-id="ac1b0-158">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 0.</span></span> <span data-ttu-id="ac1b0-159">詳細について[は、「チュートリアル:埋め込み、余白、AutoSize プロパティ](windows-forms-controls-padding-autosize.md)を使用して Windows フォームコントロールをレイアウトします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-159">For details, see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](windows-forms-controls-padding-autosize.md).</span></span>

2. <span data-ttu-id="ac1b0-160">スナップ線<xref:System.Windows.Forms.Button>が表示されるまで、フォームの右境界線の近くにコントロールを移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-160">Move the <xref:System.Windows.Forms.Button> control close to the right border of the form until a snapline appears.</span></span> <span data-ttu-id="ac1b0-161">この距離は、フォームの<xref:System.Windows.Forms.Control.Padding%2A>プロパティの値によって指定されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-161">This distance is now given by the value of the form's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

3. <span data-ttu-id="ac1b0-162"><xref:System.Windows.Forms.GroupBox> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-162">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="ac1b0-163">[プロパティ] ウィンドウで<xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Padding%2A>エントリを展開し、 プロパティを10に設定して、コントロールのプロパティの値を変更します。<xref:System.Windows.Forms.Padding.All%2A></span><span class="sxs-lookup"><span data-stu-id="ac1b0-163">Change the value of the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 10.</span></span>

5. <span data-ttu-id="ac1b0-164">コントロールを<xref:System.Windows.Forms.Button> **[ツールボックス]** からコントロールにドラッグします。<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="ac1b0-164">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

6. <span data-ttu-id="ac1b0-165">スナップ線が表示されるまで、コントロール<xref:System.Windows.Forms.GroupBox>の右の境界線の近くにコントロールを移動します。<xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="ac1b0-165">Move the <xref:System.Windows.Forms.Button> control close to the right border of the <xref:System.Windows.Forms.GroupBox> control until a snapline appears.</span></span> <span data-ttu-id="ac1b0-166"><xref:System.Windows.Forms.Button>コントロール内のコントロールを移動し、スナップ線が表示されている場所<xref:System.Windows.Forms.GroupBox>を確認します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-166">Move the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and note where the snaplines appear.</span></span>

## <a name="aligning-to-grouped-controls"></a><span data-ttu-id="ac1b0-167">配置 (グループ化コントロールに)</span><span class="sxs-lookup"><span data-stu-id="ac1b0-167">Aligning to Grouped Controls</span></span>
 <span data-ttu-id="ac1b0-168">スナップ線を使用すると、グループ化されたコントロールだけ<xref:System.Windows.Forms.GroupBox>でなく、コントロール内のコントロールも配置できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-168">You can use snaplines to align grouped controls as well as controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span>

### <a name="to-align-to-grouped-controls"></a><span data-ttu-id="ac1b0-169">グループ化されたコントロールに合わせるには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-169">To align to grouped controls</span></span>

1. <span data-ttu-id="ac1b0-170">フォーム上の2つのコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-170">Select two of the controls on your form.</span></span> <span data-ttu-id="ac1b0-171">選択範囲を移動し、選択範囲と他のコントロールの間に表示されるスナップ線をメモします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-171">Move the selection around and note the snaplines that appear between your selection and the other controls.</span></span>

2. <span data-ttu-id="ac1b0-172"><xref:System.Windows.Forms.GroupBox> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-172">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="ac1b0-173">コントロールを<xref:System.Windows.Forms.Button> **[ツールボックス]** からコントロールにドラッグします。<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="ac1b0-173">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span>

4. <span data-ttu-id="ac1b0-174"><xref:System.Windows.Forms.Button>コントロールの1つを選択し、 <xref:System.Windows.Forms.GroupBox>コントロールの周囲に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-174">Select one of the <xref:System.Windows.Forms.Button> controls and move it around the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ac1b0-175"><xref:System.Windows.Forms.GroupBox>コントロールの端に表示されるスナップ線に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-175">Note the snaplines that appear at the edges of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ac1b0-176">また、 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox>コントロールに含まれるコントロールの端に表示されるスナップ線もメモします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-176">Also note the snaplines that appear at the edges of the <xref:System.Windows.Forms.Button> control that is contained by the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ac1b0-177">コンテナーコントロールの子であるコントロールは、スナップ線もサポートします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-177">Controls that are children of a container control also support snaplines.</span></span>

## <a name="using-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="ac1b0-178">スナップ線を使用したサイズのアウトライン化によるコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-178">Using Snaplines to Place a Control by Outlining Its Size</span></span>
 <span data-ttu-id="ac1b0-179">スナップ線を使用すると、フォーム上にコントロールを配置するときに、コントロールを整列できます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-179">Snaplines help you align controls when you first place them on a form.</span></span>

### <a name="to-use-snaplines-to-place-a-control-by-outlining-its-size"></a><span data-ttu-id="ac1b0-180">スナップ線を使用して、そのサイズをアウトラインしてコントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-180">To use snaplines to place a control by outlining its size</span></span>

1. <span data-ttu-id="ac1b0-181">**ツールボックス**で <xref:System.Windows.Forms.Button> コントロール アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-181">In the **Toolbox**, click the <xref:System.Windows.Forms.Button> control icon.</span></span> <span data-ttu-id="ac1b0-182">フォームにドラッグしないでください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-182">Do not drag it onto the form.</span></span>

2. <span data-ttu-id="ac1b0-183">フォームのデザイン画面上にマウスポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-183">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="ac1b0-184">ポインターが <xref:System.Windows.Forms.Button> コントロール アイコンが付いた十字カーソルに変わることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-184">Note that the pointer changes to a crosshair with the <xref:System.Windows.Forms.Button> control icon attached.</span></span> <span data-ttu-id="ac1b0-185">また、 <xref:System.Windows.Forms.Button>コントロールに対して配置された位置を示すために表示されるスナップ線もメモします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-185">Also note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span>

3. <span data-ttu-id="ac1b0-186">マウス ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-186">Click and hold the mouse button.</span></span>

4. <span data-ttu-id="ac1b0-187">フォームの周りにマウスポインターをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-187">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="ac1b0-188">コントロールの位置とサイズを示すアウトラインが描画されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-188">Note that an outline is drawn, indicating the position and the size of the control.</span></span>

5. <span data-ttu-id="ac1b0-189">フォーム上の別のコントロールに合わせて、ポインターをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-189">Drag the pointer until it aligns with another control on the form.</span></span> <span data-ttu-id="ac1b0-190">スナップ線が配置を示すように見えることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-190">Note that a snapline appears to indicate alignment.</span></span>

6. <span data-ttu-id="ac1b0-191">マウスのボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-191">Release the mouse button.</span></span> <span data-ttu-id="ac1b0-192">コントロールは、アウトラインによって示される位置とサイズで作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-192">The control is created at the position and size indicated by the outline.</span></span>

## <a name="using-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="ac1b0-193">ツールボックスからコントロールをドラッグするときにスナップ線を使用する</span><span class="sxs-lookup"><span data-stu-id="ac1b0-193">Using Snaplines When Dragging a Control from the Toolbox</span></span>
 <span data-ttu-id="ac1b0-194">スナップ線を使用すると、コントロールを**ツールボックス**からフォームにドラッグしたときに、コントロールを整列させることができます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-194">Snaplines help you align controls when you drag them from the **Toolbox** onto your form.</span></span>

### <a name="to-use-snaplines-when-dragging-a-control-from-the-toolbox"></a><span data-ttu-id="ac1b0-195">ツールボックスからコントロールをドラッグするときにスナップ線を使用するには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-195">To use snaplines when dragging a control from the Toolbox</span></span>

1. <span data-ttu-id="ac1b0-196">コントロールを<xref:System.Windows.Forms.Button> **ツールボックス**からフォームにドラッグしますが、マウスボタンを離しません。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-196">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form, but do not release the mouse button.</span></span>

2. <span data-ttu-id="ac1b0-197">フォームのデザイン画面上にマウスポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-197">Move the mouse pointer over the form's design surface.</span></span> <span data-ttu-id="ac1b0-198">ポインターは、新しい<xref:System.Windows.Forms.Button>コントロールが作成される位置を示すように変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-198">Note that the pointer changes to indicate the position at which the new <xref:System.Windows.Forms.Button> control will be created.</span></span>

3. <span data-ttu-id="ac1b0-199">フォームの周りにマウスポインターをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-199">Drag the mouse pointer around the form.</span></span> <span data-ttu-id="ac1b0-200"><xref:System.Windows.Forms.Button>コントロールに対して配置された位置を提案するために表示されるスナップ線に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-200">Note the snaplines that appear to suggest aligned positions for the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="ac1b0-201">他のコントロールに合わせて配置された位置を検索します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-201">Find a position that is aligned with other controls.</span></span>

4. <span data-ttu-id="ac1b0-202">マウスのボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-202">Release the mouse button.</span></span> <span data-ttu-id="ac1b0-203">コントロールは、スナップ線によって示される位置に作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-203">The control is created at the position indicated by the snaplines.</span></span>

## <a name="resizing-controls-using-snaplines"></a><span data-ttu-id="ac1b0-204">スナップ線を使用したコントロールのサイズ変更</span><span class="sxs-lookup"><span data-stu-id="ac1b0-204">Resizing Controls Using Snaplines</span></span>
 <span data-ttu-id="ac1b0-205">スナップ線を使用すると、コントロールのサイズを変更するときにコントロールを揃えることができます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-205">Snaplines help you align controls as you resize them.</span></span>

### <a name="to-resize-a-control-using-snaplines"></a><span data-ttu-id="ac1b0-206">スナップ線を使用してコントロールのサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-206">To resize a control using snaplines</span></span>

1. <span data-ttu-id="ac1b0-207"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-207">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="ac1b0-208">角の<xref:System.Windows.Forms.Button>サイズ変更ハンドルとドラッグを取得して、コントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-208">Resize the <xref:System.Windows.Forms.Button> control by grabbing one of the corner sizing handles and dragging.</span></span> <span data-ttu-id="ac1b0-209">詳細については、「[方法: Windows フォーム](how-to-resize-controls-on-windows-forms.md)のコントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-209">For details, see [How to: Resize Controls on Windows Forms](how-to-resize-controls-on-windows-forms.md).</span></span>

3. <span data-ttu-id="ac1b0-210">サイズ変更ハンドルをドラッグして、 <xref:System.Windows.Forms.Button>コントロールのいずれかの境界線が別のコントロールに揃うようにします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-210">Drag the sizing handle until one of the <xref:System.Windows.Forms.Button> control's borders is aligned with another control.</span></span> <span data-ttu-id="ac1b0-211">スナップ線が表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-211">Note that a snapline appears.</span></span> <span data-ttu-id="ac1b0-212">また、サイズ変更ハンドルはスナップ線によって示される位置にスナップされることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-212">Also note that the sizing handle snaps to the position indicated by the snapline.</span></span>

4. <span data-ttu-id="ac1b0-213">異なる方向<xref:System.Windows.Forms.Button>にコントロールのサイズを変更し、サイズ変更ハンドルを別のコントロールに揃えます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-213">Resize the <xref:System.Windows.Forms.Button> control in different directions and align the sizing handle to different controls.</span></span> <span data-ttu-id="ac1b0-214">整列を示すために、さまざまな向きでスナップ線がどのように表示されるかに注目してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-214">Note how the snaplines appear in various orientations to indicate alignment.</span></span>

## <a name="aligning-a-label-to-a-controls-text"></a><span data-ttu-id="ac1b0-215">コントロールのテキストへのラベルの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-215">Aligning a Label to a Control's Text</span></span>
 <span data-ttu-id="ac1b0-216">コントロールによっては、他のコントロールを表示テキストに揃えるためのスナップ線が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-216">Some controls offer a snapline for aligning other controls to displayed text.</span></span>

### <a name="to-align-a-label-to-a-controls-text"></a><span data-ttu-id="ac1b0-217">ラベルをコントロールのテキストに揃えるには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-217">To align a label to a control's text</span></span>

1. <span data-ttu-id="ac1b0-218"><xref:System.Windows.Forms.TextBox> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-218">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="ac1b0-219">フォームに<xref:System.Windows.Forms.TextBox>コントロールをドロップするときに、スマートタググリフをクリックし、 **[テキストを textBox1 に設定]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-219">When you drop the <xref:System.Windows.Forms.TextBox> control onto the form, click the smart-tag glyph and select the **Set text to textBox1** option.</span></span> <span data-ttu-id="ac1b0-220">詳細について[は、「チュートリアル:Windows フォームコントロール](performing-common-tasks-using-smart-tags-on-wf-controls.md)でスマートタグを使用して一般的なタスクを実行する。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-220">For details, see [Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md).</span></span>

2. <span data-ttu-id="ac1b0-221"><xref:System.Windows.Forms.Label> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-221">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto your form.</span></span>

3. <span data-ttu-id="ac1b0-222"><xref:System.Windows.Forms.Label> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を `true`に変更します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-222">Change the value of the <xref:System.Windows.Forms.Label> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="ac1b0-223">コントロールの境界線は、表示テキストに合わせて調整されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-223">Note that the control's borders are adjusted to fit the display text.</span></span>

4. <span data-ttu-id="ac1b0-224">コントロールをコントロールの一番左<xref:System.Windows.Forms.TextBox>に移動し、コントロールの<xref:System.Windows.Forms.TextBox>下端に揃えます。 <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="ac1b0-224">Move the <xref:System.Windows.Forms.Label> control to the left of the <xref:System.Windows.Forms.TextBox> control, so it is aligned with the bottom edge of the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="ac1b0-225">2つのコントロールの下端に沿って表示されるスナップ線に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-225">Note the snapline that appears along the bottom edges of the two controls.</span></span>

5. <span data-ttu-id="ac1b0-226"><xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.Label>テキストと<xref:System.Windows.Forms.TextBox>テキストが揃うまで、コントロールを少し上に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-226">Move the <xref:System.Windows.Forms.Label> control slightly upward, until the <xref:System.Windows.Forms.Label> text and the <xref:System.Windows.Forms.TextBox> text are aligned.</span></span> <span data-ttu-id="ac1b0-227">表示される別のスタイルのスナップ線を確認すると、両方のコントロールのテキストフィールドがアラインされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-227">Note the differently styled snapline that appears, indicating when the text fields of both controls are aligned.</span></span>

## <a name="using-snaplines-with-keyboard-navigation"></a><span data-ttu-id="ac1b0-228">キーボードナビゲーションでのスナップ線の使用</span><span class="sxs-lookup"><span data-stu-id="ac1b0-228">Using Snaplines with Keyboard Navigation</span></span>
 <span data-ttu-id="ac1b0-229">スナップ線は、キーボードの方向キーを使用して配置するときに、コントロールを整列するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-229">Snaplines help you align controls when you are arranging them using the keyboard's arrow keys.</span></span>

### <a name="to-use-snaplines-with-keyboard-navigation"></a><span data-ttu-id="ac1b0-230">キーボードナビゲーションでスナップ線を使用するには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-230">To use snaplines with keyboard navigation</span></span>

1. <span data-ttu-id="ac1b0-231"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-231">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="ac1b0-232">フォームの左上隅に配置します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-232">Place it in the upper-left corner of the form.</span></span>

2. <span data-ttu-id="ac1b0-233">CTRL キーを押しながら下方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-233">Press CTRL+DOWN ARROW.</span></span> <span data-ttu-id="ac1b0-234">コントロールが、最初に使用可能な水平方向の配置位置にフォームを下方向に移動することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-234">Note that the control moves down the form to the first available horizontal alignment position.</span></span>

3. <span data-ttu-id="ac1b0-235">CTRL キーを押しながら下方向キーを押すと、コントロールがフォームの下部に到達します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-235">Press CTRL+DOWN ARROW until the control reaches the bottom of the form.</span></span> <span data-ttu-id="ac1b0-236">フォームの下に移動すると、その位置に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-236">Note the positions it occupies as it moves down the form.</span></span>

4. <span data-ttu-id="ac1b0-237">CTRL + →キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-237">Press CTRL+RIGHT ARROW.</span></span> <span data-ttu-id="ac1b0-238">コントロールは、フォーム上で、最初に使用可能な垂直方向の配置位置に移動することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-238">Note that the control moves across the form to the first available vertical alignment position.</span></span>

5. <span data-ttu-id="ac1b0-239">CTRL キーを押しながら右方向キーを押すと、コントロールがフォームの側に到達します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-239">Press CTRL+RIGHT ARROW until the control reaches the side of the form.</span></span> <span data-ttu-id="ac1b0-240">フォーム間を移動するときに占有される位置に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-240">Note the positions it occupies as it moves across the form.</span></span>

6. <span data-ttu-id="ac1b0-241">方向キーの組み合わせを使用して、コントロールをフォームの周囲に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-241">Move the control around the form with a combination of arrow keys.</span></span> <span data-ttu-id="ac1b0-242">コントロールが占有する位置と、コントロールに付随するスナップ線をメモします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-242">Note the positions the control occupies and the snaplines that accompany them.</span></span>

7. <span data-ttu-id="ac1b0-243">SHIFT + 任意の方向キーを押して<xref:System.Windows.Forms.Button> 、1ピクセルずつインクリメントしてコントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-243">Press SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control by increments of one pixel.</span></span>

8. <span data-ttu-id="ac1b0-244">CTRL + SHIFT + 任意の方向キーを押して<xref:System.Windows.Forms.Button> 、スナップ線のインクリメントでコントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-244">Press CTRL+SHIFT+any arrow key to resize the <xref:System.Windows.Forms.Button> control in snapline increments.</span></span>

## <a name="snaplines-and-layout-panels"></a><span data-ttu-id="ac1b0-245">スナップ線とレイアウトパネル</span><span class="sxs-lookup"><span data-stu-id="ac1b0-245">Snaplines and Layout Panels</span></span>
 <span data-ttu-id="ac1b0-246">スナップ線はレイアウトパネル内で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-246">Snaplines are disabled within layout panels.</span></span>

### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="ac1b0-247">スナップガイドラインを選択的に無効にするには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-247">To selectively disable snaplines</span></span>

1. <span data-ttu-id="ac1b0-248"><xref:System.Windows.Forms.TableLayoutPanel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-248">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="ac1b0-249"><xref:System.Windows.Forms.Button> ツールボックス **の**コントロール アイコンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-249">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox**.</span></span> <span data-ttu-id="ac1b0-250"><xref:System.Windows.Forms.TableLayoutPanel>コントロールの最初のセルに新しいボタンコントロールが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-250">Note that a new button control appears in the <xref:System.Windows.Forms.TableLayoutPanel> control's first cell.</span></span>

3. <span data-ttu-id="ac1b0-251">**ツールボックス**のコントロール<xref:System.Windows.Forms.Button>アイコンを2回ダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-251">Double-click the <xref:System.Windows.Forms.Button> control icon in the **Toolbox** twice more.</span></span> <span data-ttu-id="ac1b0-252">これにより、 <xref:System.Windows.Forms.TableLayoutPanel>コントロールに1つの空のセルが残されます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-252">This leaves one empty cell in the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

4. <span data-ttu-id="ac1b0-253">コントロールを<xref:System.Windows.Forms.Button> **[ツールボックス]** から<xref:System.Windows.Forms.TableLayoutPanel>コントロールの空のセルにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-253">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the empty cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="ac1b0-254">スナップ線は表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-254">Note that no snaplines appear.</span></span>

5. <span data-ttu-id="ac1b0-255">コントロールをコントロール<xref:System.Windows.Forms.TableLayoutPanel>の外にドラッグ<xref:System.Windows.Forms.TableLayoutPanel>し、コントロールの周囲に移動します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="ac1b0-255">Drag the <xref:System.Windows.Forms.Button> control out of the <xref:System.Windows.Forms.TableLayoutPanel> control and move it around the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="ac1b0-256">スナップ線が再び表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-256">Note that snaplines appear again.</span></span>

## <a name="disabling-snaplines"></a><span data-ttu-id="ac1b0-257">スナップガイドラインの無効化</span><span class="sxs-lookup"><span data-stu-id="ac1b0-257">Disabling Snaplines</span></span>
 <span data-ttu-id="ac1b0-258">スナップ線は既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-258">Snaplines are turned on by default.</span></span> <span data-ttu-id="ac1b0-259">スナップ線は選択的に無効にすることも、デザイン環境で無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-259">You can disable snaplines selectively, or you can disable them in the design environment.</span></span>

### <a name="to-selectively-disable-snaplines"></a><span data-ttu-id="ac1b0-260">スナップガイドラインを選択的に無効にするには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-260">To selectively disable snaplines</span></span>

- <span data-ttu-id="ac1b0-261">ALT キーを押しながら、コントロールをフォームの上に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-261">Press the ALT key and while moving a control around the form.</span></span>

     <span data-ttu-id="ac1b0-262">スナップ線は表示されず、コントロールは潜在的な配置位置にスナップされません。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-262">Note that no snaplines appear and the control does not snap to any potential alignment positions.</span></span>

### <a name="to-disable-snaplines-in-the-design-environment"></a><span data-ttu-id="ac1b0-263">デザイン環境でスナップガイドラインを無効にするには</span><span class="sxs-lookup"><span data-stu-id="ac1b0-263">To disable snaplines in the design environment</span></span>

1. <span data-ttu-id="ac1b0-264">**[ツール]** メニューの **[オプション]** ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-264">From the **Tools** menu, open the **Options** dialog box.</span></span> <span data-ttu-id="ac1b0-265">[Windows フォームデザイナー] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-265">Open the Windows Forms Designer dialog box.</span></span> <span data-ttu-id="ac1b0-266">詳細については、「 [全般、Windows フォーム デザイナー、オプション ダイアログ ボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))です。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-266">For details, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span>

2. <span data-ttu-id="ac1b0-267">**[全般]** ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-267">Select the **General** node.</span></span> <span data-ttu-id="ac1b0-268">**[レイアウトモード]** セクションで、選択範囲を**スナップガイドライン**から**SnapToGrid**に変更します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-268">In the **Layout Mode** section, change the selection from **SnapLines** to **SnapToGrid**.</span></span>

3. <span data-ttu-id="ac1b0-269">[OK] をクリックして設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-269">Click OK to apply the setting.</span></span>

4. <span data-ttu-id="ac1b0-270">フォーム上のコントロールを選択し、他のコントロールの周囲に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-270">Select a control on your form and move it around the other controls.</span></span> <span data-ttu-id="ac1b0-271">スナップ線が表示されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-271">Note that snaplines do not appear.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac1b0-272">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac1b0-272">Next Steps</span></span>
 <span data-ttu-id="ac1b0-273">スナップ線は、フォーム上にコントロールを配置するための直感的な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-273">Snaplines offer an intuitive means of aligning controls on your form.</span></span> <span data-ttu-id="ac1b0-274">さらに詳しく調べるための推奨事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-274">Suggestions for more exploration include:</span></span>

- <span data-ttu-id="ac1b0-275">コントロールを別<xref:System.Windows.Forms.GroupBox> <xref:System.Windows.Forms.GroupBox>のコントロール内に入れ子にしてみてください。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-275">Try nesting a <xref:System.Windows.Forms.GroupBox> control within another <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ac1b0-276"><xref:System.Windows.Forms.Button>子<xref:System.Windows.Forms.GroupBox>コントロール内にコントロールを配置し、もう1つは親コントロール内に配置します。 <xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="ac1b0-276">Place a <xref:System.Windows.Forms.Button> control within the child <xref:System.Windows.Forms.GroupBox> control, and another within the parent <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="ac1b0-277"><xref:System.Windows.Forms.Button>コントロールを移動して、スナップ線がコンテナーの境界を越えていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-277">Move the <xref:System.Windows.Forms.Button> controls around to see how the snaplines cross container boundaries.</span></span>

- <span data-ttu-id="ac1b0-278">コントロールの列<xref:System.Windows.Forms.TextBox>と、コントロールの<xref:System.Windows.Forms.Label>対応する列を作成します。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-278">Create a column of <xref:System.Windows.Forms.TextBox> controls and a corresponding column of <xref:System.Windows.Forms.Label> controls.</span></span> <span data-ttu-id="ac1b0-279"><xref:System.Windows.Forms.Label> `true`コントロールのプロパティの値をに設定します。<xref:System.Windows.Forms.Control.AutoSize%2A></span><span class="sxs-lookup"><span data-stu-id="ac1b0-279">Set the value of the <xref:System.Windows.Forms.Label> controls' <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="ac1b0-280">コントロールを移動するに<xref:System.Windows.Forms.Label>は、スナップ線を使用して、表示される<xref:System.Windows.Forms.TextBox>テキストがコントロール内のテキストに合わせられるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-280">Use snaplines to move the <xref:System.Windows.Forms.Label> controls so their displayed text is aligned with the text in the <xref:System.Windows.Forms.TextBox> controls.</span></span>

 <span data-ttu-id="ac1b0-281">Windows ユーザーインターフェイスの設計の詳細については、「 *Microsoft windows のユーザーエクスペリエンス」、「ユーザーインターフェイスの開発者とデザイナーの公式ガイドライン*」 REDMOND、WA を参照してください。Microsoft Press、1999。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-281">For information about Windows user interface design, see the book *Microsoft Windows User Experience, Official Guidelines for User Interface Developers and Designers* Redmond, WA: Microsoft Press, 1999.</span></span> <span data-ttu-id="ac1b0-282">(USBN:0-7356-0566-1)。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-282">(USBN: 0-7356-0566-1).</span></span>

## <a name="see-also"></a><span data-ttu-id="ac1b0-283">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac1b0-283">See also</span></span>

- <xref:System.Windows.Forms.Design.Behavior.SnapLine>
- [<span data-ttu-id="ac1b0-284">チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-284">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="ac1b0-285">チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-285">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="ac1b0-286">チュートリアル: パディング、余白、AutoSize プロパティを使用して Windows フォームコントロールをレイアウトする</span><span class="sxs-lookup"><span data-stu-id="ac1b0-286">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
- [<span data-ttu-id="ac1b0-287">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="ac1b0-287">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
