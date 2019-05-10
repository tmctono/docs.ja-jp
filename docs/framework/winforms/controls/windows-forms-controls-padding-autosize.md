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
ms.openlocfilehash: 997db37369e52a024b53254117291a1e31555487
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211333"
---
# <a name="walkthrough-laying-out-windows-forms-controls-with-padding-margins-and-the-autosize-property"></a><span data-ttu-id="55860-102">チュートリアル: Padding、Margin、AutoSize プロパティを使用した Windows フォーム コントロールのレイアウト</span><span class="sxs-lookup"><span data-stu-id="55860-102">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>

<span data-ttu-id="55860-103">フォーム上のコントロールを正確に配置することは、多くのアプリケーションで優先度の高い作業です。</span><span class="sxs-lookup"><span data-stu-id="55860-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="55860-104">**Windows フォーム デザイナー** Visual Studio でツールを提供する多くのレイアウトにこれを実現します。</span><span class="sxs-lookup"><span data-stu-id="55860-104">The **Windows Forms Designer** in Visual Studio gives you many layout tools to accomplish this.</span></span> <span data-ttu-id="55860-105">3 つ最も重要なは、 <xref:System.Windows.Forms.Control.Margin%2A>、 <xref:System.Windows.Forms.Control.Padding%2A>、および<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティで、すべての Windows フォーム コントロールの上に存在します。</span><span class="sxs-lookup"><span data-stu-id="55860-105">Three of the most important are the <xref:System.Windows.Forms.Control.Margin%2A>, <xref:System.Windows.Forms.Control.Padding%2A>, and <xref:System.Windows.Forms.Control.AutoSize%2A> properties, which are present on all Windows Forms controls.</span></span>

 <span data-ttu-id="55860-106"><xref:System.Windows.Forms.Control.Margin%2A> プロパティは、その他のコントロールで、コントロールの枠線からの指定された距離を保持するコントロールの周囲のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="55860-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>

 <span data-ttu-id="55860-107"><xref:System.Windows.Forms.Control.Padding%2A> プロパティは、コントロールの内容 (<xref:System.Windows.Forms.Control.Text%2A> プロパティの値など) で、コントロールの枠線からの指定した距離を保持するコントロールの内部のスペースを定義します。</span><span class="sxs-lookup"><span data-stu-id="55860-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>

 <span data-ttu-id="55860-108">次の図は、コントロールの <xref:System.Windows.Forms.Control.Padding%2A> プロパティと <xref:System.Windows.Forms.Control.Margin%2A> プロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="55860-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>

 <span data-ttu-id="55860-109">![フォーム コントロールの Windows のパディングとマージン](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="55860-109">![Padding And Margin for Windows Forms Controls](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>

 <span data-ttu-id="55860-110"><xref:System.Windows.Forms.Control.AutoSize%2A>プロパティは自動的にその内容をそれ自体のサイズのコントロールに指示します。</span><span class="sxs-lookup"><span data-stu-id="55860-110">The <xref:System.Windows.Forms.Control.AutoSize%2A> property tells a control to automatically size itself to its contents.</span></span> <span data-ttu-id="55860-111">自身の元の値より小さいサイズがない<xref:System.Windows.Forms.Control.Size%2A>プロパティ、およびそれがの値のアカウントがその<xref:System.Windows.Forms.Control.Padding%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55860-111">It will not resize itself to be smaller than the value of its original <xref:System.Windows.Forms.Control.Size%2A> property, and it will account for the value of its <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

 <span data-ttu-id="55860-112">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="55860-112">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="55860-113">Windows フォーム プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="55860-113">Creating a Windows Forms project</span></span>

- <span data-ttu-id="55860-114">コントロールのマージンの設定</span><span class="sxs-lookup"><span data-stu-id="55860-114">Setting Margins for Your Controls</span></span>

- <span data-ttu-id="55860-115">コントロールの埋め込みの設定</span><span class="sxs-lookup"><span data-stu-id="55860-115">Setting Padding for Your Controls</span></span>

- <span data-ttu-id="55860-116">コントロールを自動的にサイズ変更</span><span class="sxs-lookup"><span data-stu-id="55860-116">Automatically Sizing Your Controls</span></span>

 <span data-ttu-id="55860-117">終了すると、これらの重要なレイアウト機能が果たす役割について理解できます。</span><span class="sxs-lookup"><span data-stu-id="55860-117">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55860-118">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="55860-118">Prerequisites</span></span>

<span data-ttu-id="55860-119">Visual Studio でこのチュートリアルを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55860-119">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="55860-120">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="55860-120">Create the project</span></span>

1. <span data-ttu-id="55860-121">Visual Studio で、作成、 **Windows アプリケーション**という名前のプロジェクト`LayoutExample`します。</span><span class="sxs-lookup"><span data-stu-id="55860-121">In Visual Studio, create a **Windows Application** project called `LayoutExample`.</span></span> <span data-ttu-id="55860-122">詳細については、「[方法 :Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)です。</span><span class="sxs-lookup"><span data-stu-id="55860-122">For more information, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) .</span></span>

2. <span data-ttu-id="55860-123">フォームを選択、 **Windows フォーム デザイナー**します。</span><span class="sxs-lookup"><span data-stu-id="55860-123">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="setting-margins-for-your-controls"></a><span data-ttu-id="55860-124">コントロールのマージンの設定</span><span class="sxs-lookup"><span data-stu-id="55860-124">Setting Margins for Your Controls</span></span>

<span data-ttu-id="55860-125">使用して、コントロールの間で既定の距離を設定することができます、<xref:System.Windows.Forms.Control.Margin%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55860-125">You can set the default distance between your controls using the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="55860-126">コントロールを移動するときに、別のコントロールに十分、2 つのコントロールの余白を示すスナップ線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55860-126">When you move a control close enough to another control, you will see a snapline that shows the margins for the two controls.</span></span> <span data-ttu-id="55860-127">移動中のコントロールも、余白で定義された距離にスナップします。</span><span class="sxs-lookup"><span data-stu-id="55860-127">The control you are moving will also snap to the distance defined by the margins.</span></span>

### <a name="arrange-controls-on-your-form-using-the-margin-property"></a><span data-ttu-id="55860-128">Margin プロパティを使用して、フォーム上のコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="55860-128">Arrange controls on your form using the Margin property</span></span>

1. <span data-ttu-id="55860-129">2 つをドラッグして<xref:System.Windows.Forms.Button>コントロールを**ツールボックス**フォームにします。</span><span class="sxs-lookup"><span data-stu-id="55860-129">Drag two <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="55860-130">いずれかの選択、<xref:System.Windows.Forms.Button>を制御し、それらはほとんど触れることまで、その他の近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="55860-130">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other, until they are almost touching.</span></span>

     <span data-ttu-id="55860-131">それらの間に表示されるスナップ線を確認します。</span><span class="sxs-lookup"><span data-stu-id="55860-131">Observe the snapline that appears between them.</span></span> <span data-ttu-id="55860-132">この距離は、2 つのコントロールの<xref:System.Windows.Forms.Control.Margin%2A>値。</span><span class="sxs-lookup"><span data-stu-id="55860-132">This distance is the sum of the two controls' <xref:System.Windows.Forms.Control.Margin%2A> values.</span></span> <span data-ttu-id="55860-133">移動中のコントロールは、この距離にスナップされます。</span><span class="sxs-lookup"><span data-stu-id="55860-133">The control you are moving snaps to this distance.</span></span> <span data-ttu-id="55860-134">詳細については、次を参照してください。[チュートリアル。フォームのスナップ線を使用して Windows 上のコントロール](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)します。</span><span class="sxs-lookup"><span data-stu-id="55860-134">For details, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

3. <span data-ttu-id="55860-135">変更、<xref:System.Windows.Forms.Control.Margin%2A>を展開して、コントロールのいずれかのプロパティ、<xref:System.Windows.Forms.Control.Margin%2A>内のエントリ、**プロパティ**ウィンドウと設定、<xref:System.Windows.Forms.Padding.All%2A>プロパティを 20 にします。</span><span class="sxs-lookup"><span data-stu-id="55860-135">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of one of the controls by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 20.</span></span>

4. <span data-ttu-id="55860-136">いずれかの選択、<xref:System.Windows.Forms.Button>を制御し、その他の近くに移動します。</span><span class="sxs-lookup"><span data-stu-id="55860-136">Select one of the <xref:System.Windows.Forms.Button> controls and move it close to the other.</span></span>

     <span data-ttu-id="55860-137">スナップ線を定義する余白の値の合計が長いと、コントロールが他のコントロールからの距離が長くにスナップされます。</span><span class="sxs-lookup"><span data-stu-id="55860-137">The snapline defining the sum of the margin values is longer and that the control snaps to a greater distance from the other control.</span></span>

5. <span data-ttu-id="55860-138">変更、<xref:System.Windows.Forms.Control.Margin%2A>を展開して、選択したコントロールのプロパティ、<xref:System.Windows.Forms.Control.Margin%2A>内のエントリ、**プロパティ**ウィンドウと設定、<xref:System.Windows.Forms.Padding.Top%2A>プロパティを 5 にします。</span><span class="sxs-lookup"><span data-stu-id="55860-138">Change the <xref:System.Windows.Forms.Control.Margin%2A> property of the selected control by expanding the <xref:System.Windows.Forms.Control.Margin%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.Top%2A> property to 5.</span></span>

6. <span data-ttu-id="55860-139">その他のコントロールの下の選択したコントロールを移動し、スナップ線が短いことを確認します。</span><span class="sxs-lookup"><span data-stu-id="55860-139">Move the selected control below the other control and observe that the snapline is shorter.</span></span> <span data-ttu-id="55860-140">選択したコントロールを他のコントロールの左に移動し、スナップ線が手順 4. で計測された値を保持することを確認します。</span><span class="sxs-lookup"><span data-stu-id="55860-140">Move the selected control to the left of the other control and observe that the snapline retains the value observed in step 4.</span></span>

7. <span data-ttu-id="55860-141">それぞれの側面を設定することができます、<xref:System.Windows.Forms.Control.Margin%2A>プロパティ、 <xref:System.Windows.Forms.Padding.Left%2A>、 <xref:System.Windows.Forms.Padding.Top%2A>、 <xref:System.Windows.Forms.Padding.Right%2A>、 <xref:System.Windows.Forms.Padding.Bottom%2A>、または別の値と同じ値にすべてを設定することができます、<xref:System.Windows.Forms.Padding.All%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55860-141">You can set each of the aspects of the <xref:System.Windows.Forms.Control.Margin%2A> property, <xref:System.Windows.Forms.Padding.Left%2A>, <xref:System.Windows.Forms.Padding.Top%2A>, <xref:System.Windows.Forms.Padding.Right%2A>, <xref:System.Windows.Forms.Padding.Bottom%2A>, to different values, or you can set them all to the same value with the <xref:System.Windows.Forms.Padding.All%2A> property.</span></span>

## <a name="setting-padding-for-your-controls"></a><span data-ttu-id="55860-142">コントロールの埋め込みの設定</span><span class="sxs-lookup"><span data-stu-id="55860-142">Setting Padding for Your Controls</span></span>

<span data-ttu-id="55860-143">アプリケーションに必要な正確なレイアウトを実現するために、コントロールは多くの場合、子コントロールを含まれます。</span><span class="sxs-lookup"><span data-stu-id="55860-143">To achieve the precise layout required for your application, your controls will often contain child controls.</span></span> <span data-ttu-id="55860-144">親コントロールの境界線に子コントロールの境界線の近接度を指定する場合を使用して、親コントロールの<xref:System.Windows.Forms.Control.Padding%2A>と共に子コントロールのプロパティ<xref:System.Windows.Forms.Control.Margin%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55860-144">When you want to specify the proximity of the child control's border to the parent control's border, use the parent control's <xref:System.Windows.Forms.Control.Padding%2A> property in conjunction with the child control's <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span> <span data-ttu-id="55860-145"><xref:System.Windows.Forms.Control.Padding%2A>コントロールのコンテンツの近接度を制御するプロパティを使用しても (たとえば、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティ) の境界線にします。</span><span class="sxs-lookup"><span data-stu-id="55860-145">The <xref:System.Windows.Forms.Control.Padding%2A> property is also used to control the proximity of a control's content (for example, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property) to its borders.</span></span>

### <a name="arrange-controls-on-your-form-using-padding"></a><span data-ttu-id="55860-146">パディングを使用して、フォーム上のコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="55860-146">Arrange controls on your form using padding</span></span>

1. <span data-ttu-id="55860-147"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="55860-147">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="55860-148"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を `true`に変更します。</span><span class="sxs-lookup"><span data-stu-id="55860-148">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>

3. <span data-ttu-id="55860-149">変更、<xref:System.Windows.Forms.Control.Padding%2A>プロパティを展開して、<xref:System.Windows.Forms.Control.Padding%2A>内のエントリ、**プロパティ**ウィンドウと設定、<xref:System.Windows.Forms.Padding.All%2A>プロパティを 5 にします。</span><span class="sxs-lookup"><span data-stu-id="55860-149">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 5.</span></span>

     <span data-ttu-id="55860-150">コントロールを拡張する新しい埋め込みのために確保します。</span><span class="sxs-lookup"><span data-stu-id="55860-150">The control expands to provide room for the new padding.</span></span>

4. <span data-ttu-id="55860-151"><xref:System.Windows.Forms.GroupBox> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="55860-151">Drag a <xref:System.Windows.Forms.GroupBox> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="55860-152">ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**に、<xref:System.Windows.Forms.GroupBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-152">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="55860-153">位置、<xref:System.Windows.Forms.Button>制御の右下隅のフラッシュができるので、<xref:System.Windows.Forms.GroupBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-153">Position the <xref:System.Windows.Forms.Button> control so it is flush with the lower-right corner of the <xref:System.Windows.Forms.GroupBox> control.</span></span>

     <span data-ttu-id="55860-154">として表示されるスナップ線を観察、<xref:System.Windows.Forms.Button>下および右の境界線のコントロールが近づく、<xref:System.Windows.Forms.GroupBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-154">Observe the snaplines that appear as the <xref:System.Windows.Forms.Button> control approaches the bottom and right borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="55860-155">これらのスナップ線が対応する、<xref:System.Windows.Forms.Control.Margin%2A>のプロパティ、<xref:System.Windows.Forms.Button>します。</span><span class="sxs-lookup"><span data-stu-id="55860-155">These snaplines correspond to the <xref:System.Windows.Forms.Control.Margin%2A> property of the <xref:System.Windows.Forms.Button>.</span></span>

5. <span data-ttu-id="55860-156">変更、<xref:System.Windows.Forms.GroupBox>コントロールの<xref:System.Windows.Forms.Control.Padding%2A>プロパティを展開して、<xref:System.Windows.Forms.Control.Padding%2A>内のエントリ、**プロパティ**ウィンドウと設定、<xref:System.Windows.Forms.Padding.All%2A>プロパティを 20 にします。</span><span class="sxs-lookup"><span data-stu-id="55860-156">Change the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 20.</span></span>

6. <span data-ttu-id="55860-157">選択、<xref:System.Windows.Forms.Button>コントロール内の<xref:System.Windows.Forms.GroupBox>を制御しの中央に移動、<xref:System.Windows.Forms.GroupBox>します。</span><span class="sxs-lookup"><span data-stu-id="55860-157">Select the <xref:System.Windows.Forms.Button> control within the <xref:System.Windows.Forms.GroupBox> control and move it toward the center of the <xref:System.Windows.Forms.GroupBox>.</span></span>

     <span data-ttu-id="55860-158">枠線から遠隔地にスナップ線が表示される、<xref:System.Windows.Forms.GroupBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-158">The snaplines appear at a greater distance from the borders of the <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="55860-159">この距離の合計、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Margin%2A>プロパティおよび<xref:System.Windows.Forms.GroupBox>コントロールの<xref:System.Windows.Forms.Control.Padding%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="55860-159">This distance is the sum of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Margin%2A> property and the <xref:System.Windows.Forms.GroupBox> control's <xref:System.Windows.Forms.Control.Padding%2A> property.</span></span>

## <a name="automatically-sizing-your-controls"></a><span data-ttu-id="55860-160">コントロールを自動的にサイズ変更</span><span class="sxs-lookup"><span data-stu-id="55860-160">Automatically Sizing Your Controls</span></span>

<span data-ttu-id="55860-161">一部のアプリケーションでコントロールのサイズはいないと同じである実行時にデザイン時にでした。</span><span class="sxs-lookup"><span data-stu-id="55860-161">In some applications, the size of a control will not be the same at run time as it was at design time.</span></span> <span data-ttu-id="55860-162">テキストを<xref:System.Windows.Forms.Button>コントロールなどの可能性がありますがから取得した、データベースをその長さが事前にわかっていません。</span><span class="sxs-lookup"><span data-stu-id="55860-162">The text of a <xref:System.Windows.Forms.Button> control, for example, may be taken from a database, and its length will not be known in advance.</span></span>

<span data-ttu-id="55860-163">ときに、<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティに設定されて`true`、そのコンテンツへ自体、コントロールのサイズが。</span><span class="sxs-lookup"><span data-stu-id="55860-163">When the <xref:System.Windows.Forms.Control.AutoSize%2A> property is set to `true`, the control will size itself to its content.</span></span> <span data-ttu-id="55860-164">詳細については、次を参照してください。 [AutoSize プロパティの概要](autosize-property-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="55860-164">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

### <a name="arrange-controls-on-your-form-using-the-autosize-property"></a><span data-ttu-id="55860-165">AutoSize プロパティを使用して、フォーム上のコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="55860-165">Arrange controls on your form using the AutoSize property</span></span>

1. <span data-ttu-id="55860-166"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="55860-166">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="55860-167"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を `true`に変更します。</span><span class="sxs-lookup"><span data-stu-id="55860-167">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>

3. <span data-ttu-id="55860-168">変更、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティを"**このボタンがテキスト プロパティの長い文字列**"。</span><span class="sxs-lookup"><span data-stu-id="55860-168">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property**."</span></span>

     <span data-ttu-id="55860-169">変更をコミットすると、<xref:System.Windows.Forms.Button>コントロールでは、新しいテキストが収まるようにサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="55860-169">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself to fit the new text.</span></span>

4. <span data-ttu-id="55860-170">もう 1 つドラッグ<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**フォームにします。</span><span class="sxs-lookup"><span data-stu-id="55860-170">Drag another <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span>

5. <span data-ttu-id="55860-171">変更、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティを"**このボタンがテキスト プロパティの長い文字列**"。</span><span class="sxs-lookup"><span data-stu-id="55860-171">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

     <span data-ttu-id="55860-172">変更をコミットすると、<xref:System.Windows.Forms.Button>コントロール サイズ変更されない、自体と、コントロールの右端でのテキストが切り取られます。</span><span class="sxs-lookup"><span data-stu-id="55860-172">When you commit the change, the <xref:System.Windows.Forms.Button> control does not resize itself, and the text is clipped by the right edge of the control.</span></span>

6. <span data-ttu-id="55860-173">変更、<xref:System.Windows.Forms.Control.Padding%2A>プロパティを展開して、<xref:System.Windows.Forms.Control.Padding%2A>内のエントリ、**プロパティ**ウィンドウと設定、<xref:System.Windows.Forms.Padding.All%2A>プロパティを 5 にします。</span><span class="sxs-lookup"><span data-stu-id="55860-173">Change the <xref:System.Windows.Forms.Control.Padding%2A> property by expanding the <xref:System.Windows.Forms.Control.Padding%2A> entry in the **Properties** window and setting the <xref:System.Windows.Forms.Padding.All%2A> property to 5.</span></span>

     <span data-ttu-id="55860-174">コントロールの内部でテキストが、4 辺すべてにつき切り取られます。</span><span class="sxs-lookup"><span data-stu-id="55860-174">The text in the control's interior is clipped on all four sides.</span></span>

7. <span data-ttu-id="55860-175">変更、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="55860-175">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>

     <span data-ttu-id="55860-176"><xref:System.Windows.Forms.Button>自体文字列全体を囲むようにコントロールをサイズ変更します。</span><span class="sxs-lookup"><span data-stu-id="55860-176">The <xref:System.Windows.Forms.Button> control resizes itself to encompass the entire string.</span></span> <span data-ttu-id="55860-177">テキストを囲むパディングが追加されても、原因、<xref:System.Windows.Forms.Button>コントロールをすべて次の 4 つの方向に展開します。</span><span class="sxs-lookup"><span data-stu-id="55860-177">Also, padding has been added around the text, causing the <xref:System.Windows.Forms.Button> control to expand in all four directions.</span></span>

8. <span data-ttu-id="55860-178"><xref:System.Windows.Forms.Button> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="55860-178">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto your form.</span></span> <span data-ttu-id="55860-179">フォームの右下隅近くに配置します。</span><span class="sxs-lookup"><span data-stu-id="55860-179">Position it near the lower-right corner of the form.</span></span>

9. <span data-ttu-id="55860-180"><xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.AutoSize%2A> プロパティの値を `true`に変更します。</span><span class="sxs-lookup"><span data-stu-id="55860-180">Change the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>

10. <span data-ttu-id="55860-181">設定、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Anchor%2A>プロパティを<xref:System.Windows.Forms.AnchorStyles.Right>、<xref:System.Windows.Forms.AnchorStyles.Bottom>します。</span><span class="sxs-lookup"><span data-stu-id="55860-181">Set the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.Right>, <xref:System.Windows.Forms.AnchorStyles.Bottom>.</span></span>

11. <span data-ttu-id="55860-182">変更、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Text%2A>プロパティを"**このボタンがテキスト プロパティの長い文字列**"。</span><span class="sxs-lookup"><span data-stu-id="55860-182">Change the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Text%2A> property to "**This button has a long string for its Text property.**"</span></span>

     <span data-ttu-id="55860-183">変更をコミットすると、<xref:System.Windows.Forms.Button>コントロールは左方向サイズ変更します。</span><span class="sxs-lookup"><span data-stu-id="55860-183">When you commit the change, the <xref:System.Windows.Forms.Button> control resizes itself toward the left.</span></span> <span data-ttu-id="55860-184">自動サイズ変更が反対方向にコントロールのサイズを大きく一般に、その<xref:System.Windows.Forms.Control.Anchor%2A>プロパティの設定。</span><span class="sxs-lookup"><span data-stu-id="55860-184">In general, automatic sizing will increase the size of a control in the direction opposite its <xref:System.Windows.Forms.Control.Anchor%2A> property setting.</span></span>

## <a name="autosize-and-autosizemode-properties"></a><span data-ttu-id="55860-185">自動サイズ調整と AutoSizeMode プロパティ</span><span class="sxs-lookup"><span data-stu-id="55860-185">AutoSize and AutoSizeMode Properties</span></span>

 <span data-ttu-id="55860-186">一部のコントロールのサポート、`AutoSizeMode`プロパティ、コントロールの自動サイズ変更動作をより細かく管理できます。</span><span class="sxs-lookup"><span data-stu-id="55860-186">Some controls support the `AutoSizeMode` property, which gives you more fine-grained control over the automatic sizing behavior of a control.</span></span>

### <a name="use-the-autosizemode-property"></a><span data-ttu-id="55860-187">AutoSizeMode プロパティを使用して、</span><span class="sxs-lookup"><span data-stu-id="55860-187">Use the AutoSizeMode property</span></span>

1. <span data-ttu-id="55860-188"><xref:System.Windows.Forms.Panel> ツールボックス **から** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="55860-188">Drag a <xref:System.Windows.Forms.Panel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="55860-189">値を設定、<xref:System.Windows.Forms.Panel>コントロールの<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="55860-189">Set the value of the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span>

3. <span data-ttu-id="55860-190">ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**に、<xref:System.Windows.Forms.Panel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-190">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the <xref:System.Windows.Forms.Panel> control.</span></span>

4. <span data-ttu-id="55860-191">場所、<xref:System.Windows.Forms.Button>の右上隅のコントロール、<xref:System.Windows.Forms.Panel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-191">Place the <xref:System.Windows.Forms.Button> control near the lower-right corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

5. <span data-ttu-id="55860-192">選択、<xref:System.Windows.Forms.Panel>を制御し、右下のサイズ変更ハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="55860-192">Select the <xref:System.Windows.Forms.Panel> control and grab the lower-right sizing handle.</span></span> <span data-ttu-id="55860-193">サイズ変更、<xref:System.Windows.Forms.Panel>コントロールを大きくしたり小さくします。</span><span class="sxs-lookup"><span data-stu-id="55860-193">Resize the <xref:System.Windows.Forms.Panel> control to be larger and smaller.</span></span>

    > [!NOTE]
    > <span data-ttu-id="55860-194">サイズを変更することが自由に、<xref:System.Windows.Forms.Panel>コントロールがサイズを調整できないことの位置より小さい、<xref:System.Windows.Forms.Button>コントロールの右上隅にあります。</span><span class="sxs-lookup"><span data-stu-id="55860-194">You can freely resize the <xref:System.Windows.Forms.Panel> control, but you cannot size it smaller than the position of the <xref:System.Windows.Forms.Button> control's lower-right corner.</span></span> <span data-ttu-id="55860-195">この動作がの既定値で指定された、`AutoSizeMode`プロパティ<xref:System.Windows.Forms.AutoSizeMode.GrowOnly>します。</span><span class="sxs-lookup"><span data-stu-id="55860-195">This behavior is specified by the default value of the `AutoSizeMode` property, which is <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>.</span></span>

6. <span data-ttu-id="55860-196">値を設定、<xref:System.Windows.Forms.Panel>コントロールの`AutoSizeMode`プロパティを<xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>します。</span><span class="sxs-lookup"><span data-stu-id="55860-196">Set the value of the <xref:System.Windows.Forms.Panel> control's `AutoSizeMode` property to <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>.</span></span>

     <span data-ttu-id="55860-197"><xref:System.Windows.Forms.Panel>コントロールのサイズを囲む、<xref:System.Windows.Forms.Button>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-197">The <xref:System.Windows.Forms.Panel> control sizes itself to surround the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="55860-198">サイズを変更することはできません、<xref:System.Windows.Forms.Panel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-198">You cannot resize the <xref:System.Windows.Forms.Panel> control.</span></span>

7. <span data-ttu-id="55860-199">ドラッグ、<xref:System.Windows.Forms.Button>コントロールの左上隅に向かって、<xref:System.Windows.Forms.Panel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-199">Drag the <xref:System.Windows.Forms.Button> control toward the upper-left corner of the <xref:System.Windows.Forms.Panel> control.</span></span>

     <span data-ttu-id="55860-200"><xref:System.Windows.Forms.Panel>にコントロールをサイズ変更、<xref:System.Windows.Forms.Button>コントロールの新しい位置。</span><span class="sxs-lookup"><span data-stu-id="55860-200">The <xref:System.Windows.Forms.Panel> control resizes to the <xref:System.Windows.Forms.Button> control's new position.</span></span>

## <a name="next-steps"></a><span data-ttu-id="55860-201">次の手順</span><span class="sxs-lookup"><span data-stu-id="55860-201">Next steps</span></span>

<span data-ttu-id="55860-202">Windows フォーム アプリケーションでコントロールの配置の他の多くのレイアウト機能があります。</span><span class="sxs-lookup"><span data-stu-id="55860-202">There are many other layout features for arranging controls in your Windows Forms applications.</span></span> <span data-ttu-id="55860-203">アクセスしてみて、いくつかの組み合わせを次に示します。</span><span class="sxs-lookup"><span data-stu-id="55860-203">Here are some combinations you might try:</span></span>

- <span data-ttu-id="55860-204">使用してフォームを構築、<xref:System.Windows.Forms.TableLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-204">Build a form using a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="55860-205">詳細については、次を参照してください。[チュートリアル。TableLayoutPanel を使用して Windows フォーム コントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)します。</span><span class="sxs-lookup"><span data-stu-id="55860-205">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span> <span data-ttu-id="55860-206">値を変更してみて、<xref:System.Windows.Forms.TableLayoutPanel>コントロールの<xref:System.Windows.Forms.Control.Padding%2A>プロパティだけでなく<xref:System.Windows.Forms.Control.Margin%2A>その子コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="55860-206">Try changing the values of the <xref:System.Windows.Forms.TableLayoutPanel> control's <xref:System.Windows.Forms.Control.Padding%2A> property, as well as the <xref:System.Windows.Forms.Control.Margin%2A> property on its child controls.</span></span>

- <span data-ttu-id="55860-207">使用して同じ実験を実行してください、<xref:System.Windows.Forms.FlowLayoutPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-207">Try the same experiment using a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="55860-208">詳細については、次を参照してください。[チュートリアル。FlowLayoutPanel を使用して Windows フォーム コントロールの配置](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)します。</span><span class="sxs-lookup"><span data-stu-id="55860-208">For details, see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>

- <span data-ttu-id="55860-209">子コントロールのドッキングを使用した実験を<xref:System.Windows.Forms.Panel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="55860-209">Experiment with docking child controls in a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="55860-210"><xref:System.Windows.Forms.Control.Padding%2A>プロパティの全般的な実現は、<xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>プロパティを満たすことが自分子コントロールを配置することで大文字と小文字である、<xref:System.Windows.Forms.Panel>コントロールと子コントロールの設定<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="55860-210">The <xref:System.Windows.Forms.Control.Padding%2A> property is a more general realization of the <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A> property, and you can satisfy yourself that this is the case by putting a child control in a <xref:System.Windows.Forms.Panel> control and setting the child control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="55860-211">設定、<xref:System.Windows.Forms.Panel>コントロールの<xref:System.Windows.Forms.Control.Padding%2A>プロパティをさまざまな値の影響に注意してください。</span><span class="sxs-lookup"><span data-stu-id="55860-211">Set the <xref:System.Windows.Forms.Panel> control's <xref:System.Windows.Forms.Control.Padding%2A> property to various values and note the effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="55860-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="55860-212">See also</span></span>

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.ScrollableControl.DockPadding%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- [<span data-ttu-id="55860-213">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="55860-213">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="55860-214">チュートリアル: TableLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="55860-214">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="55860-215">チュートリアル: FlowLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="55860-215">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="55860-216">チュートリアル: スナップ線を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="55860-216">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
