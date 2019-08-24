---
title: 'チュートリアル: Padding、Margin、AutoSize プロパティを使用した Windows フォーム コントロールのレイアウト'
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: daf0c6495b89033e75c27a1ff0cbceaff9d85f34
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987169"
---
# <a name="walkthrough-lay-out-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="f27ef-102">チュートリアル: 余白、余白、および AutoSize プロパティを使用してコントロールをレイアウトします</span><span class="sxs-lookup"><span data-stu-id="f27ef-102">Walkthrough: Lay out controls with padding, margins, and the AutoSize property</span></span>

<span data-ttu-id="f27ef-103">フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。</span><span class="sxs-lookup"><span data-stu-id="f27ef-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="f27ef-104">Visual Studio の**Windows フォームデザイナー**には、これを実現するためのさまざまなレイアウトツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f27ef-104">The **Windows Forms Designer** in Visual Studio gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="f27ef-105">最も重要なのは<xref:System.Windows.Forms.Control.Margin%2A>、すべての Windows フォームコントロールに存在する、 <xref:System.Windows.Forms.Control.Padding%2A>、、および<xref:System.Windows.Forms.Control.AutoSize%2A>の各プロパティです。</span><span class="sxs-lookup"><span data-stu-id="f27ef-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>

<span data-ttu-id="f27ef-106"><xref:System.Windows.Forms.Control.Margin%2A> プロパティは、その他のコントロールで、コントロールの枠線からの指定された距離を保持するコントロールの周囲のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>

<span data-ttu-id="f27ef-107"><xref:System.Windows.Forms.Control.Padding%2A> プロパティは、コントロールの内容 (<xref:System.Windows.Forms.Control.Text%2A> プロパティの値など) で、コントロールの枠線からの指定した距離を保持するコントロールの内部のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>

<span data-ttu-id="f27ef-108">次の図は、コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティと <xref:System.Windows.Forms.Control.Margin%2A> プロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="f27ef-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>

![Windows フォーム コントロールのパディングとマージン](./media/vs-winformpadmargin.gif)

<span data-ttu-id="f27ef-110">プロパティ<xref:System.Windows.Forms.Control.AutoSize%2A>は、コントロールがその内容に自動的にサイズを変更するように指示します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="f27ef-111">元<xref:System.Windows.Forms.Control.Size%2A>のプロパティの値よりも小さいサイズになることはなく、 <xref:System.Windows.Forms.Control.Padding%2A>プロパティの値が考慮されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f27ef-112">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f27ef-112">Prerequisites</span></span>

<span data-ttu-id="f27ef-113">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="f27ef-113">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f27ef-114">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="f27ef-114">Create the project</span></span>

1. <span data-ttu-id="f27ef-115">Visual Studio で、という名前`LayoutExample`の**Windows アプリケーション**プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-115">In Visual Studio, create a **Windows Application** project called `LayoutExample`.</span></span>

2. <span data-ttu-id="f27ef-116">**Windows フォームデザイナー**でフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-116">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="set-margins-for-controls"></a><span data-ttu-id="f27ef-117">コントロールの余白を設定する</span><span class="sxs-lookup"><span data-stu-id="f27ef-117">Set margins for controls</span></span>

<span data-ttu-id="f27ef-118">コントロール間の既定の距離は、 <xref:System.Windows.Forms.Control.Margin%2A>プロパティを使用して設定できます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-118">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="f27ef-119">コントロールを別のコントロールに移動すると、2つのコントロールの余白を示すスナップ線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-119">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="f27ef-120">移動するコントロールは、余白で定義されている距離にもスナップされます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-120">The control you are moving will also snap to the distance defined by the margins.</span></span>

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="f27ef-121">Margin プロパティを使用してフォーム上のコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="f27ef-121">Arrange controls on your form using the Margin property</span></span>

1. <span data-ttu-id="f27ef-122"><xref:System.Windows.Forms.Button> **ツールボックス**からフォームに2つのコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-122">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="f27ef-123"><xref:System.Windows.Forms.Button>コントロールの1つを選択し、ほぼタッチするまで、そのコントロールの近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-123">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>

   <span data-ttu-id="f27ef-124">これらの間に表示されるスナップ線を観察します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-124">Observe the snapline that appears between them.</span></span> <span data-ttu-id="f27ef-125">この距離は、2つのコントロール<xref:System.Windows.Forms.Control.Margin%2A>の値の合計です。</span><span class="sxs-lookup"><span data-stu-id="f27ef-125">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="f27ef-126">移動しようとしているコントロールは、この距離にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-126">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="f27ef-127">詳細について[は、「チュートリアル:スナップ線](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)を使用した Windows フォーム上のコントロールの配置。</span><span class="sxs-lookup"><span data-stu-id="f27ef-127">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

3. <span data-ttu-id="f27ef-128"><xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Padding.All%2A>[プロパティ] ウィンドウでエントリを展開し、プロパティを**20**に設定して、いずれかのコントロールのプロパティを変更します。<xref:System.Windows.Forms.Control.Margin%2A></span><span class="sxs-lookup"><span data-stu-id="f27ef-128">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

4. <span data-ttu-id="f27ef-129"><xref:System.Windows.Forms.Button>コントロールの1つを選択し、そのコントロールの近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-129">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>

   <span data-ttu-id="f27ef-130">余白の値の合計を定義するスナップ線が長くなり、コントロールが他のコントロールから離れた距離にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-130">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>

5. <span data-ttu-id="f27ef-131"><xref:System.Windows.Forms.Padding.Top%2A> <xref:System.Windows.Forms.Control.Margin%2A> <xref:System.Windows.Forms.Control.Margin%2A> [プロパティ] ウィンドウでエントリを展開し、プロパティを**5**に設定して、選択したコントロールのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-131">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to **5**.</span></span>

6. <span data-ttu-id="f27ef-132">選択したコントロールを他のコントロールの下に移動し、スナップ線が短くなっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-132">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="f27ef-133">選択したコントロールを他のコントロールの左側に移動し、スナップ線が手順 4. で観察した値を保持していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-133">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>

7. <span data-ttu-id="f27ef-134"><xref:System.Windows.Forms.Control.Margin%2A> プロパティ<xref:System.Windows.Forms.Padding.Top%2A> <xref:System.Windows.Forms.Padding.All%2A> 、 、、、の各側面を異なる値に設定することも、プロパティを使用してすべて同じ値に設定することもできます。<xref:System.Windows.Forms.Padding.Right%2A> <xref:System.Windows.Forms.Padding.Left%2A> <xref:System.Windows.Forms.Padding.Bottom%2A></span><span class="sxs-lookup"><span data-stu-id="f27ef-134">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>

## <a name="set-padding-for-controls"></a><span data-ttu-id="f27ef-135">コントロールの埋め込みを設定する</span><span class="sxs-lookup"><span data-stu-id="f27ef-135">Set padding for controls</span></span>

<span data-ttu-id="f27ef-136">アプリケーションに必要な正確なレイアウトを実現するために、コントロールには多くの場合、子コントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-136">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="f27ef-137">親コントロールの境界線に対する子コントロールの境界線の距離を指定する場合は、子<xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Margin%2A>コントロールのプロパティと共に親コントロールのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-137">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="f27ef-138">プロパティ<xref:System.Windows.Forms.Control.Padding%2A>は、コントロールのコンテンツ ( <xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティなど) の境界への近接を制御するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-138">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>

### <a name="arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="f27ef-139">パディングを使用してフォームにコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="f27ef-139">Arrange controls on your form using padding</span></span>

1. <span data-ttu-id="f27ef-140"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-140">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="f27ef-141"><xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティの値を**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-141">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="f27ef-142">プロパティを<xref:System.Windows.Forms.Control.Padding%2A>変更するには<xref:System.Windows.Forms.Control.Padding%2A> 、 **[プロパティ]** ウィンドウでエントリを<xref:System.Windows.Forms.Padding.All%2A>展開し、プロパティを**5**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-142">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="f27ef-143">コントロールが拡張され、新しい埋め込み用の領域が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-143">The control expands to provide room for the new padding.</span></span>

4. <span data-ttu-id="f27ef-144"><xref:System.Windows.Forms.GroupBox> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-144">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="f27ef-145">コントロールを<xref:System.Windows.Forms.Button> **[ツールボックス]** からコントロールにドラッグします。<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="f27ef-145">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="f27ef-146">コントロールを<xref:System.Windows.Forms.GroupBox>コントロールの右下隅になるように配置します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f27ef-146">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>

   <span data-ttu-id="f27ef-147">コントロールとして表示される<xref:System.Windows.Forms.Button>スナップ線が、 <xref:System.Windows.Forms.GroupBox>コントロールの下と右の境界線に近づいていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-147">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="f27ef-148">これらのスナップ線は<xref:System.Windows.Forms.Control.Margin%2A> 、のプロパティ<xref:System.Windows.Forms.Button>に対応しています。</span><span class="sxs-lookup"><span data-stu-id="f27ef-148">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>

5. <span data-ttu-id="f27ef-149"><xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.Control.Padding%2A> **[プロパティ**] ウィンドウで<xref:System.Windows.Forms.Padding.All%2A>エントリを展開し、プロパティを**20**に設定して、コントロールのプロパティを変更します。<xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="f27ef-149">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **20**.</span></span>

6. <span data-ttu-id="f27ef-150">コントロール内の<xref:System.Windows.Forms.GroupBox>コントロールを選択し、の中央に移動します。 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="f27ef-150">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>

   <span data-ttu-id="f27ef-151">スナップ線は、 <xref:System.Windows.Forms.GroupBox>コントロールの境界から離れた位置に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-151">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="f27ef-152">この<xref:System.Windows.Forms.Button>距離は、コントロールの<xref:System.Windows.Forms.Control.Margin%2A>プロパティと<xref:System.Windows.Forms.GroupBox>コントロールの<xref:System.Windows.Forms.Control.Padding%2A>プロパティの合計です。</span><span class="sxs-lookup"><span data-stu-id="f27ef-152">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="size-controls-automatically"></a><span data-ttu-id="f27ef-153">コントロールを自動的にサイズ変更する</span><span class="sxs-lookup"><span data-stu-id="f27ef-153">Size controls automatically</span></span>

<span data-ttu-id="f27ef-154">アプリケーションによっては、デザイン時と同じように、実行時にコントロールのサイズが同じになることはありません。</span><span class="sxs-lookup"><span data-stu-id="f27ef-154">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="f27ef-155">たとえば、 <xref:System.Windows.Forms.Button>コントロールのテキストはデータベースから取得され、その長さは事前にわからない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f27ef-155">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length are not known in advance.</span></span>

<span data-ttu-id="f27ef-156">プロパティが<xref:System.Windows.Forms.Control.AutoSize%2A>に`true`設定されている場合、コントロールはその内容に合わせてサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-156">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="f27ef-157">詳細については、「 [AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f27ef-157">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="f27ef-158">AutoSize プロパティを使用してフォーム上のコントロールを配置する</span><span class="sxs-lookup"><span data-stu-id="f27ef-158">Arrange controls on your form using the AutoSize property</span></span>

1. <span data-ttu-id="f27ef-159"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-159">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="f27ef-160"><xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティの値を**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-160">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="f27ef-161">コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティをこのボタンに変更すると、**その Text プロパティに長い文字列が**表示されます。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f27ef-161">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to **This button has a long string for its Text property**.</span></span>

   <span data-ttu-id="f27ef-162">変更をコミットすると、新しい<xref:System.Windows.Forms.Button>テキストに合わせてコントロールのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-162">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>

4. <span data-ttu-id="f27ef-163"><xref:System.Windows.Forms.Button> **ツールボックス**から別のコントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-163">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="f27ef-164">コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティを "**このボタンには、テキストプロパティの長い文字列が含まれています**" に変更します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f27ef-164">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="f27ef-165">変更をコミットすると、 <xref:System.Windows.Forms.Button>コントロールのサイズが変更されず、テキストがコントロールの右端でクリップされます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-165">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>

6. <span data-ttu-id="f27ef-166">プロパティを<xref:System.Windows.Forms.Control.Padding%2A>変更するには<xref:System.Windows.Forms.Control.Padding%2A> 、 **[プロパティ]** ウィンドウでエントリを<xref:System.Windows.Forms.Padding.All%2A>展開し、プロパティを**5**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-166">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to **5**.</span></span>

   <span data-ttu-id="f27ef-167">コントロールの内部のテキストは、4辺すべてにクリップされます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-167">The text in the control's interior is clipped on all four sides.</span></span>

7. <span data-ttu-id="f27ef-168">コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティを true に変更します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f27ef-168">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

   <span data-ttu-id="f27ef-169">コントロール<xref:System.Windows.Forms.Button>は、文字列全体をカバーするようにサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-169">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="f27ef-170">また、テキストの周囲に埋め込みが追加され<xref:System.Windows.Forms.Button>ているため、コントロールが4つの方向に広がります。</span><span class="sxs-lookup"><span data-stu-id="f27ef-170">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>

8. <span data-ttu-id="f27ef-171"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-171">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="f27ef-172">フォームの右下隅近くに配置します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-172">Position it near the lower-right corner of the form.</span></span>

9. <span data-ttu-id="f27ef-173"><xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティの値を**true**に変更します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-173">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

10. <span data-ttu-id="f27ef-174">コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを、 <xref:System.Windows.Forms.AnchorStyles.Right>に設定します。<xref:System.Windows.Forms.AnchorStyles.Bottom> <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f27ef-174">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>

11. <span data-ttu-id="f27ef-175">コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティを "**このボタンには、テキストプロパティの長い文字列が含まれています**" に変更します。 <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="f27ef-175">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

   <span data-ttu-id="f27ef-176">変更をコミットすると、コントロール<xref:System.Windows.Forms.Button>は左に向かってサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-176">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="f27ef-177">一般に、自動サイズ変更では、 <xref:System.Windows.Forms.Control.Anchor%2A>プロパティ設定とは逆の方向にコントロールのサイズが増加します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-177">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>

## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="f27ef-178">AutoSize および System.windows.forms.datagridviewcolumn.autosizemode プロパティ</span><span class="sxs-lookup"><span data-stu-id="f27ef-178">AutoSize and AutoSizeMode properties</span></span>

 <span data-ttu-id="f27ef-179">一部のコントロールで`AutoSizeMode`は、プロパティをサポートしています。これにより、コントロールの自動サイズ変更動作をより細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-179">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>

### <a name="use-the-autosizemode-property"></a><span data-ttu-id="f27ef-180">System.windows.forms.datagridviewcolumn.autosizemode プロパティを使用する</span><span class="sxs-lookup"><span data-stu-id="f27ef-180">Use the AutoSizeMode property</span></span>

1. <span data-ttu-id="f27ef-181"><xref:System.Windows.Forms.Panel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-181">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="f27ef-182"><xref:System.Windows.Forms.Panel>コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティの値を**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-182">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to **true**.</span></span>

3. <span data-ttu-id="f27ef-183">コントロールを<xref:System.Windows.Forms.Button> **[ツールボックス]** からコントロールにドラッグします。<xref:System.Windows.Forms.Panel></span><span class="sxs-lookup"><span data-stu-id="f27ef-183">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>

4. <span data-ttu-id="f27ef-184"><xref:System.Windows.Forms.Button> コントロール<xref:System.Windows.Forms.Panel>の右下隅の近くにコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-184">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

5. <span data-ttu-id="f27ef-185"><xref:System.Windows.Forms.Panel>コントロールを選択し、右下のサイズ変更ハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-185">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="f27ef-186">コントロールの<xref:System.Windows.Forms.Panel>サイズを大きくしたり小さくしたりします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-186">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f27ef-187"><xref:System.Windows.Forms.Panel>コントロールのサイズは自由に変更できますが、 <xref:System.Windows.Forms.Button>コントロールの右下隅の位置よりもサイズを小さくすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f27ef-187">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="f27ef-188">この動作は、 `AutoSizeMode`プロパティ<xref:System.Windows.Forms.AutoSizeMode.GrowOnly>の既定値であるによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-188">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>

6. <span data-ttu-id="f27ef-189"><xref:System.Windows.Forms.Panel>コントロール<xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>の`AutoSizeMode`プロパティの値をに設定します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-189">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>

   <span data-ttu-id="f27ef-190">コントロールは、コントロールを<xref:System.Windows.Forms.Button>囲むようにサイズを調整します。 <xref:System.Windows.Forms.Panel></span><span class="sxs-lookup"><span data-stu-id="f27ef-190">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="f27ef-191">コントロールの<xref:System.Windows.Forms.Panel>サイズを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f27ef-191">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>

7. <span data-ttu-id="f27ef-192"><xref:System.Windows.Forms.Button> コントロール<xref:System.Windows.Forms.Panel>の左上隅にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f27ef-192">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

   <span data-ttu-id="f27ef-193">コントロール<xref:System.Windows.Forms.Panel>は、 <xref:System.Windows.Forms.Button>コントロールの新しい位置にサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="f27ef-193">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f27ef-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="f27ef-194">Next steps</span></span>

<span data-ttu-id="f27ef-195">Windows フォームアプリケーションにコントロールを配置するためのレイアウト機能は他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="f27ef-195">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="f27ef-196">いくつかの組み合わせを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-196">Here are some combinations you might try:</span></span>

- <span data-ttu-id="f27ef-197"><xref:System.Windows.Forms.TableLayoutPanel>コントロールを使用してフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-197">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="f27ef-198">詳細について[は、「チュートリアル:TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)を使用して Windows フォームのコントロールを配置する。</span><span class="sxs-lookup"><span data-stu-id="f27ef-198">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="f27ef-199"><xref:System.Windows.Forms.TableLayoutPanel>コントロール<xref:System.Windows.Forms.Control.Margin%2A>の<xref:System.Windows.Forms.Control.Padding%2A>プロパティの値、および子コントロールのプロパティを変更してみてください。</span><span class="sxs-lookup"><span data-stu-id="f27ef-199">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>

- <span data-ttu-id="f27ef-200"><xref:System.Windows.Forms.FlowLayoutPanel>コントロールを使用して同じ実験を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f27ef-200">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="f27ef-201">詳細について[は、「チュートリアル:FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)を使用して Windows フォームのコントロールを配置する。</span><span class="sxs-lookup"><span data-stu-id="f27ef-201">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>

- <span data-ttu-id="f27ef-202"><xref:System.Windows.Forms.Panel>コントロールにドッキングされた子コントロールを試してみてください。</span><span class="sxs-lookup"><span data-stu-id="f27ef-202">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="f27ef-203">プロパティは、 <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>プロパティのより一般的な実現方法であり、子コントロールを<xref:System.Windows.Forms.Panel>コントロールに配置し、子コントロールの<xref:System.Windows.Forms.Control.Dock%2A>プロパティをに設定することによって、このことを満たすことができます。 <xref:System.Windows.Forms.Control.Padding%2A> <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="f27ef-203">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="f27ef-204"><xref:System.Windows.Forms.Panel>コントロールの<xref:System.Windows.Forms.Control.Padding%2A>プロパティをさまざまな値に設定し、効果を確認します。</span><span class="sxs-lookup"><span data-stu-id="f27ef-204">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="f27ef-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="f27ef-205">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [<span data-ttu-id="f27ef-206">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="f27ef-206">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="f27ef-207">チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="f27ef-207">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="f27ef-208">チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="f27ef-208">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="f27ef-209">チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="f27ef-209">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
