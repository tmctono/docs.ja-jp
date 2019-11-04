---
title: 'チュートリアル : Padding、Margin、および AutoSize プロパティを使用した Windows フォーム コントロールのレイアウト'
ms.date: 03/30/2017
f1_keywords:
- Margin.Bottom
- Margin.Left
- Margin.Top
- Margin.All
- Margin.Right
helpviewer_keywords:
- Margin property [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], layout
- AutoSize property [Windows Forms], walkthroughs
- Padding property [Windows Forms], walkthroughs
- layout [Windows Forms], margins and padding
- Windows Forms, layout
ms.assetid: f8ae2a6b-db13-4630-8e25-d104091205c7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 76c880c208355b01d0fbaf46cf58091ad147846b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460601"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="a41f2-102">チュートリアル: padding、margin、および AutoSize プロパティを使用してコントロールをレイアウトする</span><span class="sxs-lookup"><span data-stu-id="a41f2-102">Walkthrough: Lay out controls with padding, margins, and the AutoSize property</span></span>

<span data-ttu-id="a41f2-103">フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。</span><span class="sxs-lookup"><span data-stu-id="a41f2-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="a41f2-104">Visual Studio の**Windows フォームデザイナー**には、これを実現するためのさまざまなレイアウトツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a41f2-104">The **Windows Forms Designer** in Visual Studio gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="a41f2-105">最も重要なのは、すべての Windows フォームコントロールに存在する <xref:System.Windows.Forms.Control.Margin%2A>、<xref:System.Windows.Forms.Control.Padding%2A>、および <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティです。</span><span class="sxs-lookup"><span data-stu-id="a41f2-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>

<span data-ttu-id="a41f2-106"><xref:System.Windows.Forms.Control.Margin%2A> プロパティは、その他のコントロールで、コントロールの枠線からの指定された距離を保持するコントロールの周囲のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>

<span data-ttu-id="a41f2-107"><xref:System.Windows.Forms.Control.Padding%2A> プロパティは、コントロールの内容 (<xref:System.Windows.Forms.Control.Text%2A> プロパティの値など) で、コントロールの枠線からの指定した距離を保持するコントロールの内部のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>

<span data-ttu-id="a41f2-108">次の図は、コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティと <xref:System.Windows.Forms.Control.Margin%2A> プロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="a41f2-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>

![Windows フォーム コントロールのパディングとマージン](./media/vs-winformpadmargin.gif)

<span data-ttu-id="a41f2-110"><xref:System.Windows.Forms.Control.AutoSize%2A> プロパティは、コントロールの内容に合わせて自動的にサイズを変更するようにコントロールに指示します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="a41f2-111">元の <xref:System.Windows.Forms.Control.Size%2A> プロパティの値よりも小さいサイズになることはなく、<xref:System.Windows.Forms.Control.Padding%2A> プロパティの値が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a41f2-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a41f2-112">Prerequisites</span></span>

<span data-ttu-id="a41f2-113">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="a41f2-113">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a41f2-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="a41f2-114">Create the project</span></span>

1. <span data-ttu-id="a41f2-115">Visual Studio で、`LayoutExample`という名前の**Windows アプリケーション**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-115">In Visual Studio, create a **Windows Application** project called `LayoutExample`.</span></span>

2. <span data-ttu-id="a41f2-116">**Windows フォームデザイナー**でフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-116">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="set-margins-for-controls"></a><span data-ttu-id="a41f2-117">コントロールの余白を設定する</span><span class="sxs-lookup"><span data-stu-id="a41f2-117">Set margins for controls</span></span>

<span data-ttu-id="a41f2-118"><xref:System.Windows.Forms.Control.Margin%2A> プロパティを使用して、コントロール間の既定の距離を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-118">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="a41f2-119">コントロールを別のコントロールに移動すると、2つのコントロールの余白を示すスナップ線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-119">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="a41f2-120">移動するコントロールは、余白で定義されている距離にもスナップされます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-120">The control you are moving will also snap to the distance defined by the margins.</span></span>

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="a41f2-121">Margin プロパティを使用してフォーム上のコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="a41f2-121">Arrange controls on your form using the Margin property</span></span>

1. <span data-ttu-id="a41f2-122">**ツールボックス**から2つの <xref:System.Windows.Forms.Button> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-122">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="a41f2-123"><xref:System.Windows.Forms.Button> コントロールのいずれかを選択し、ほぼタッチするまで、そのコントロールの近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-123">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>

   <span data-ttu-id="a41f2-124">これらの間に表示されるスナップ線を観察します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-124">Observe the snapline that appears between them.</span></span> <span data-ttu-id="a41f2-125">この距離は、2つのコントロールの <xref:System.Windows.Forms.Control.Margin%2A> 値の合計です。</span><span class="sxs-lookup"><span data-stu-id="a41f2-125">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="a41f2-126">移動しようとしているコントロールは、この距離にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-126">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="a41f2-127">詳細については、「[チュートリアル: スナップ線を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-127">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

3. <span data-ttu-id="a41f2-128">**[プロパティ]** ウィンドウで <xref:System.Windows.Forms.Control.Margin%2A> エントリを展開し、[<xref:System.Windows.Forms.Padding.All%2A>] プロパティを**20**に設定して、いずれかのコントロールの <xref:System.Windows.Forms.Control.Margin%2A> プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-128">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

4. <span data-ttu-id="a41f2-129"><xref:System.Windows.Forms.Button> コントロールのいずれかを選択し、そのコントロールの近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-129">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>

   <span data-ttu-id="a41f2-130">余白の値の合計を定義するスナップ線が長くなり、コントロールが他のコントロールから離れた距離にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-130">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>

5. <span data-ttu-id="a41f2-131">**[プロパティ]** ウィンドウで <xref:System.Windows.Forms.Control.Margin%2A> エントリを展開し、[<xref:System.Windows.Forms.Padding.Top%2A>] プロパティを**5**に設定して、選択したコントロールの <xref:System.Windows.Forms.Control.Margin%2A> プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-131">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to **5**.</span></span>

6. <span data-ttu-id="a41f2-132">選択したコントロールを他のコントロールの下に移動し、スナップ線が短くなっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-132">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="a41f2-133">選択したコントロールを他のコントロールの左側に移動し、スナップ線が手順 4. で観察した値を保持していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-133">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>

7. <span data-ttu-id="a41f2-134"><xref:System.Windows.Forms.Control.Margin%2A> プロパティの各側面、<xref:System.Windows.Forms.Padding.Left%2A>、<xref:System.Windows.Forms.Padding.Top%2A>、<xref:System.Windows.Forms.Padding.Right%2A>、<xref:System.Windows.Forms.Padding.Bottom%2A>を異なる値に設定できます。また、<xref:System.Windows.Forms.Padding.All%2A> プロパティですべて同じ値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-134">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>

## <a name="set-padding-for-controls"></a><span data-ttu-id="a41f2-135">コントロールの埋め込みを設定する</span><span class="sxs-lookup"><span data-stu-id="a41f2-135">Set padding for controls</span></span>

<span data-ttu-id="a41f2-136">アプリケーションに必要な正確なレイアウトを実現するために、コントロールには多くの場合、子コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-136">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="a41f2-137">親コントロールの境界線に対する子コントロールの境界線の距離を指定する場合は、子コントロールの <xref:System.Windows.Forms.Control.Margin%2A> プロパティと共に、親コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-137">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="a41f2-138"><xref:System.Windows.Forms.Control.Padding%2A> プロパティは、コントロールのコンテンツ (たとえば、<xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティ) の境界線への近接を制御するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-138">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>

### <a name="arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="a41f2-139">パディングを使用してフォームにコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="a41f2-139">Arrange controls on your form using padding</span></span>

1. <span data-ttu-id="a41f2-140"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-140">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="a41f2-141"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-141">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="a41f2-142">**[プロパティ]** ウィンドウで <xref:System.Windows.Forms.Control.Padding%2A> エントリを展開し、[<xref:System.Windows.Forms.Padding.All%2A>] プロパティを**5**に設定して、<xref:System.Windows.Forms.Control.Padding%2A> プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-142">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="a41f2-143">コントロールが拡張され、新しい埋め込み用の領域が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-143">The control expands to provide room for the new padding.</span></span>

4. <span data-ttu-id="a41f2-144"><xref:System.Windows.Forms.GroupBox> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-144">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="a41f2-145">**[ツールボックス]** から [<xref:System.Windows.Forms.Button>] コントロールを <xref:System.Windows.Forms.GroupBox> コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-145">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="a41f2-146"><xref:System.Windows.Forms.Button> コントロールを <xref:System.Windows.Forms.GroupBox> コントロールの右下隅になるように配置します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-146">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>

   <span data-ttu-id="a41f2-147"><xref:System.Windows.Forms.Button> コントロールとして表示されるスナップ線が、<xref:System.Windows.Forms.GroupBox> コントロールの下と右の境界線に近づいていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-147">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="a41f2-148">これらのスナップ線は、<xref:System.Windows.Forms.Button>の <xref:System.Windows.Forms.Control.Margin%2A> プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="a41f2-148">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>

5. <span data-ttu-id="a41f2-149">**[プロパティ]** ウィンドウの <xref:System.Windows.Forms.Control.Padding%2A> エントリを展開し、[<xref:System.Windows.Forms.Padding.All%2A>] プロパティを**20**に設定して、<xref:System.Windows.Forms.GroupBox> コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-149">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

6. <span data-ttu-id="a41f2-150"><xref:System.Windows.Forms.GroupBox> コントロール内の <xref:System.Windows.Forms.Button> コントロールを選択し、<xref:System.Windows.Forms.GroupBox>の中央に移動します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-150">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>

   <span data-ttu-id="a41f2-151">スナップ線は、<xref:System.Windows.Forms.GroupBox> コントロールの境界から離れた場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-151">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="a41f2-152">この距離は、<xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Margin%2A> プロパティと <xref:System.Windows.Forms.GroupBox> コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティの合計です。</span><span class="sxs-lookup"><span data-stu-id="a41f2-152">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="size-controls-automatically"></a><span data-ttu-id="a41f2-153">コントロールを自動的にサイズ変更する</span><span class="sxs-lookup"><span data-stu-id="a41f2-153">Size controls automatically</span></span>

<span data-ttu-id="a41f2-154">アプリケーションによっては、デザイン時と同じように、実行時にコントロールのサイズが同じになることはありません。</span><span class="sxs-lookup"><span data-stu-id="a41f2-154">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="a41f2-155">たとえば、<xref:System.Windows.Forms.Button> コントロールのテキストはデータベースから取得できますが、その長さは事前にわかっていません。</span><span class="sxs-lookup"><span data-stu-id="a41f2-155">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length are not known in advance.</span></span>

<span data-ttu-id="a41f2-156"><xref:System.Windows.Forms.Control.AutoSize%2A> プロパティが `true`に設定されている場合、コントロールはその内容に合わせてサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-156">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="a41f2-157">詳細については、「 [AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-157">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="a41f2-158">AutoSize プロパティを使用してフォーム上のコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="a41f2-158">Arrange controls on your form using the AutoSize property</span></span>

1. <span data-ttu-id="a41f2-159"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-159">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="a41f2-160"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-160">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="a41f2-161"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティをこのボタンに変更すると、**その Text プロパティに長い文字列が**表示されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-161">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to **This button has a long string for its Text property**.</span></span>

   <span data-ttu-id="a41f2-162">変更をコミットすると、新しいテキストに合わせて <xref:System.Windows.Forms.Button> コントロールのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-162">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>

4. <span data-ttu-id="a41f2-163">別の <xref:System.Windows.Forms.Button> コントロールを **[ツールボックス]** からフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-163">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="a41f2-164"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティを "**このボタンには、テキストプロパティの長い文字列が含まれ**ています" に変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-164">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="a41f2-165">変更をコミットすると、<xref:System.Windows.Forms.Button> コントロールのサイズは変更されず、テキストはコントロールの右端でクリップされます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-165">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>

6. <span data-ttu-id="a41f2-166">**[プロパティ]** ウィンドウで <xref:System.Windows.Forms.Control.Padding%2A> エントリを展開し、[<xref:System.Windows.Forms.Padding.All%2A>] プロパティを**5**に設定して、<xref:System.Windows.Forms.Control.Padding%2A> プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-166">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="a41f2-167">コントロールの内部のテキストは、4辺すべてにクリップされます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-167">The text in the control's interior is clipped on all four sides.</span></span>

7. <span data-ttu-id="a41f2-168"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティを**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-168">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

   <span data-ttu-id="a41f2-169"><xref:System.Windows.Forms.Button> コントロールは、文字列全体をカバーするようにサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-169">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="a41f2-170">また、テキストの周囲に埋め込みが追加されているため、<xref:System.Windows.Forms.Button> コントロールが4つのすべての方向に展開されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-170">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>

8. <span data-ttu-id="a41f2-171"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-171">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="a41f2-172">フォームの右下隅近くに配置します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-172">Position it near the lower-right corner of the form.</span></span>

9. <span data-ttu-id="a41f2-173"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

10. <span data-ttu-id="a41f2-174"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Anchor%2A> プロパティを <xref:System.Windows.Forms.AnchorStyles.Right>、<xref:System.Windows.Forms.AnchorStyles.Bottom>に設定します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-174">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>

11. <span data-ttu-id="a41f2-175"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Text%2A> プロパティを "**このボタンには、テキストプロパティの長い文字列が含まれ**ています" に変更します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-175">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="a41f2-176">変更をコミットすると、<xref:System.Windows.Forms.Button> コントロールが左側に向かってサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-176">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="a41f2-177">一般に、自動サイズ変更では、<xref:System.Windows.Forms.Control.Anchor%2A> プロパティ設定とは逆の方向にコントロールのサイズが増加します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-177">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>

## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="a41f2-178">AutoSize および System.windows.forms.datagridviewcolumn.autosizemode プロパティ</span><span class="sxs-lookup"><span data-stu-id="a41f2-178">AutoSize and AutoSizeMode properties</span></span>

 <span data-ttu-id="a41f2-179">コントロールによっては、`AutoSizeMode` プロパティがサポートされています。これにより、コントロールの自動サイズ調整動作をよりきめ細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-179">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>

### <a name="use-the-autosizemode-property"></a><span data-ttu-id="a41f2-180">System.windows.forms.datagridviewcolumn.autosizemode プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="a41f2-180">Use the AutoSizeMode property</span></span>

1. <span data-ttu-id="a41f2-181"><xref:System.Windows.Forms.Panel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-181">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="a41f2-182"><xref:System.Windows.Forms.Panel> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-182">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="a41f2-183">**[ツールボックス]** から [<xref:System.Windows.Forms.Button>] コントロールを <xref:System.Windows.Forms.Panel> コントロールにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-183">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>

4. <span data-ttu-id="a41f2-184"><xref:System.Windows.Forms.Panel> コントロールの右下隅近くに <xref:System.Windows.Forms.Button> コントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-184">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

5. <span data-ttu-id="a41f2-185"><xref:System.Windows.Forms.Panel> コントロールを選択し、右下のサイズ変更ハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-185">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="a41f2-186"><xref:System.Windows.Forms.Panel> コントロールのサイズを大きくして小さくします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-186">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a41f2-187"><xref:System.Windows.Forms.Panel> コントロールのサイズは自由に変更できますが、<xref:System.Windows.Forms.Button> コントロールの右下隅の位置よりもサイズを小さくすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a41f2-187">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="a41f2-188">この動作は、`AutoSizeMode` プロパティの既定値 (<xref:System.Windows.Forms.AutoSizeMode.GrowOnly>) によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-188">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>

6. <span data-ttu-id="a41f2-189"><xref:System.Windows.Forms.Panel> コントロールの `AutoSizeMode` プロパティの値を <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>に設定します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-189">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>

   <span data-ttu-id="a41f2-190"><xref:System.Windows.Forms.Panel> コントロールは、<xref:System.Windows.Forms.Button> コントロールを囲むようにサイズを調整します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-190">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="a41f2-191"><xref:System.Windows.Forms.Panel> コントロールのサイズを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a41f2-191">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>

7. <span data-ttu-id="a41f2-192"><xref:System.Windows.Forms.Button> コントロールを <xref:System.Windows.Forms.Panel> コントロールの左上隅にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a41f2-192">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

   <span data-ttu-id="a41f2-193"><xref:System.Windows.Forms.Panel> コントロールは、<xref:System.Windows.Forms.Button> コントロールの新しい位置にサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-193">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a41f2-194">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a41f2-194">Next steps</span></span>

<span data-ttu-id="a41f2-195">Windows フォームアプリケーションにコントロールを配置するためのレイアウト機能は他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="a41f2-195">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="a41f2-196">いくつかの組み合わせを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-196">Here are some combinations you might try:</span></span>

- <span data-ttu-id="a41f2-197"><xref:System.Windows.Forms.TableLayoutPanel> コントロールを使用してフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-197">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="a41f2-198">詳細については、「[チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-198">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="a41f2-199"><xref:System.Windows.Forms.TableLayoutPanel> コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティの値、および子コントロールの <xref:System.Windows.Forms.Control.Margin%2A> プロパティを変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-199">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>

- <span data-ttu-id="a41f2-200"><xref:System.Windows.Forms.FlowLayoutPanel> コントロールを使用して同じ実験を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-200">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="a41f2-201">詳細については、「[チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-201">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>

- <span data-ttu-id="a41f2-202"><xref:System.Windows.Forms.Panel> コントロールにドッキングされた子コントロールを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="a41f2-202">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="a41f2-203"><xref:System.Windows.Forms.Control.Padding%2A> プロパティは、<xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> プロパティの一般的な実現方法であり、<xref:System.Windows.Forms.Panel> コントロールに子コントロールを配置し、子コントロールの <xref:System.Windows.Forms.Control.Dock%2A> プロパティを <xref:System.Windows.Forms.DockStyle.Fill>に設定することによって、このことを満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="a41f2-203">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="a41f2-204"><xref:System.Windows.Forms.Panel> コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティをさまざまな値に設定し、効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="a41f2-204">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="a41f2-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="a41f2-205">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [<span data-ttu-id="a41f2-206">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="a41f2-206">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="a41f2-207">チュートリアル: TableLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="a41f2-207">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="a41f2-208">チュートリアル: FlowLayoutPanel を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="a41f2-208">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="a41f2-209">チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="a41f2-209">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
