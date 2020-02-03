---
title: コントロールのタブオーダーを設定する
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 5d53e411bda0279271e4f73e1842c52fd6d9b3a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746836"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a><span data-ttu-id="c1a12-102">方法: Windows フォームのタブオーダーを設定する</span><span class="sxs-lookup"><span data-stu-id="c1a12-102">How to: Set the tab order on Windows Forms</span></span>

<span data-ttu-id="c1a12-103">タブオーダーは、Tab キーを押すことによって、ユーザーがあるコントロールから別のコントロールにフォーカスを移動する順序です。</span><span class="sxs-lookup"><span data-stu-id="c1a12-103">The tab order is the order in which a user moves focus from one control to another by pressing the Tab key.</span></span> <span data-ttu-id="c1a12-104">各フォームには、独自のタブオーダーがあります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-104">Each form has its own tab order.</span></span> <span data-ttu-id="c1a12-105">既定では、タブオーダーは、コントロールを作成した順序と同じです。</span><span class="sxs-lookup"><span data-stu-id="c1a12-105">By default, the tab order is the same as the order in which you created the controls.</span></span> <span data-ttu-id="c1a12-106">タブオーダー番号は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-106">Tab-order numbering begins with zero.</span></span>

## <a name="to-set-the-tab-order-of-a-control"></a><span data-ttu-id="c1a12-107">コントロールのタブオーダーを設定するには</span><span class="sxs-lookup"><span data-stu-id="c1a12-107">To set the tab order of a control</span></span>

1. <span data-ttu-id="c1a12-108">Visual Studio の **[表示]** メニューで、 **[タブオーダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a12-108">In Visual Studio, on the **View** menu, select **Tab Order**.</span></span>

   <span data-ttu-id="c1a12-109">これにより、フォームのタブオーダー選択モードがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-109">This activates the tab-order selection mode on the form.</span></span> <span data-ttu-id="c1a12-110">各コントロールの左上隅に、(<xref:System.Windows.Forms.Control.TabIndex%2A> のプロパティを表す) 数値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-110">A number (representing the <xref:System.Windows.Forms.Control.TabIndex%2A> property) appears in the upper-left corner of each control.</span></span>

2. <span data-ttu-id="c1a12-111">コントロールを順番にクリックして、目的のタブオーダーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c1a12-111">Click the controls sequentially to establish the tab order you want.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c1a12-112">タブオーダー内のコントロールの位置は、0以上の任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-112">A control's place within the tab order can be set to any value greater than or equal to 0.</span></span> <span data-ttu-id="c1a12-113">重複が発生すると、2つのコントロールの z オーダーが評価され、上のコントロールが最初にタブになります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-113">When duplicates occur, the z-order of the two controls is evaluated and the control on top is tabbed to first.</span></span> <span data-ttu-id="c1a12-114">(Z オーダーは、フォームの z 軸の [奥行] に沿ったフォーム上のコントロールの視覚的なレイヤーです。</span><span class="sxs-lookup"><span data-stu-id="c1a12-114">(The z-order is the visual layering of controls on a form along the form's z-axis [depth].</span></span> <span data-ttu-id="c1a12-115">Z オーダーは、他のコントロールの前にあるコントロールを決定します。)Z オーダーの詳細については、「 [Windows フォームのオブジェクトのレイヤー](how-to-layer-objects-on-windows-forms.md)化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a12-115">The z-order determines which controls are in front of other controls.) For more information on z-order, see [Layering Objects on Windows Forms](how-to-layer-objects-on-windows-forms.md).</span></span>

3. <span data-ttu-id="c1a12-116">終了したら、 **[表示]** メニューの **[タブオーダー]** をもう一度選択して、タブオーダーモードを終了します。</span><span class="sxs-lookup"><span data-stu-id="c1a12-116">When you have finished, select **Tab Order** on the **View** menu again to leave tab order mode.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c1a12-117">フォーカスを取得できないコントロール、および無効になったコントロールと非表示のコントロールには、<xref:System.Windows.Forms.Control.TabIndex%2A> プロパティはなく、タブオーダーには含まれません。</span><span class="sxs-lookup"><span data-stu-id="c1a12-117">Controls that cannot get the focus, as well as disabled and invisible controls, do not have a <xref:System.Windows.Forms.Control.TabIndex%2A> property and are not included in the tab order.</span></span> <span data-ttu-id="c1a12-118">ユーザーが Tab キーを押すと、これらのコントロールはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-118">As a user presses the Tab key, these controls are skipped.</span></span>

<span data-ttu-id="c1a12-119">または、[<xref:System.Windows.Forms.Control.TabIndex%2A>] プロパティを使用して、プロパティウィンドウにタブオーダーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-119">Alternatively, tab order can be set in the Properties window using the <xref:System.Windows.Forms.Control.TabIndex%2A> property.</span></span> <span data-ttu-id="c1a12-120">コントロールの <xref:System.Windows.Forms.Control.TabIndex%2A> プロパティは、タブオーダー内での位置を決定します。</span><span class="sxs-lookup"><span data-stu-id="c1a12-120">The <xref:System.Windows.Forms.Control.TabIndex%2A> property of a control determines where it is positioned in the tab order.</span></span> <span data-ttu-id="c1a12-121">既定では、描画された最初のコントロールの <xref:System.Windows.Forms.Control.TabIndex%2A> 値は0、2番目のコントロールの <xref:System.Windows.Forms.Control.TabIndex%2A> は1のようになります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-121">By default, the first control drawn has a <xref:System.Windows.Forms.Control.TabIndex%2A> value of 0, the second has a <xref:System.Windows.Forms.Control.TabIndex%2A> of 1, and so on.</span></span>

<span data-ttu-id="c1a12-122">また、既定では、<xref:System.Windows.Forms.GroupBox> コントロールには、整数である独自の <xref:System.Windows.Forms.Control.TabIndex%2A> 値があります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-122">Additionally, by default, a <xref:System.Windows.Forms.GroupBox> control has its own <xref:System.Windows.Forms.Control.TabIndex%2A> value, which is a whole number.</span></span> <span data-ttu-id="c1a12-123"><xref:System.Windows.Forms.GroupBox> コントロール自体には、実行時にフォーカスを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="c1a12-123">A <xref:System.Windows.Forms.GroupBox> control itself cannot have focus at run time.</span></span> <span data-ttu-id="c1a12-124">したがって、<xref:System.Windows.Forms.GroupBox> 内の各コントロールには、0から始まる独自の decimal <xref:System.Windows.Forms.Control.TabIndex%2A> 値があります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-124">Thus, each control within a <xref:System.Windows.Forms.GroupBox> has its own decimal <xref:System.Windows.Forms.Control.TabIndex%2A> value, beginning with .0.</span></span> <span data-ttu-id="c1a12-125">当然ながら、<xref:System.Windows.Forms.GroupBox> コントロールの <xref:System.Windows.Forms.Control.TabIndex%2A> がインクリメントされると、そのコントロール内のコントロールがそれに応じてインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-125">Naturally, as the <xref:System.Windows.Forms.Control.TabIndex%2A> of a <xref:System.Windows.Forms.GroupBox> control is incremented, the controls within it will be incremented accordingly.</span></span> <span data-ttu-id="c1a12-126"><xref:System.Windows.Forms.Control.TabIndex%2A> 値を5から6に変更した場合、そのグループの最初のコントロールの <xref:System.Windows.Forms.Control.TabIndex%2A> 値は自動的に6.0 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-126">If you changed a <xref:System.Windows.Forms.Control.TabIndex%2A> value from 5 to 6, the <xref:System.Windows.Forms.Control.TabIndex%2A> value of the first control in its group automatically changes to 6.0, and so on.</span></span>

<span data-ttu-id="c1a12-127">最後に、フォーム上の多くのコントロールは、タブオーダーではスキップできます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-127">Finally, any control of the many on your form can be skipped in the tab order.</span></span> <span data-ttu-id="c1a12-128">通常、実行時に Tab キーを連続して押すと、各コントロールがタブオーダーで選択されます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-128">Usually, pressing Tab successively at run time selects each control in the tab order.</span></span> <span data-ttu-id="c1a12-129"><xref:System.Windows.Forms.Control.TabStop%2A> プロパティをオフにすると、フォームのタブオーダーでコントロールを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="c1a12-129">By turning off the <xref:System.Windows.Forms.Control.TabStop%2A> property, you can make a control be passed over in the tab order of the form.</span></span>

## <a name="to-remove-a-control-from-the-tab-order"></a><span data-ttu-id="c1a12-130">タブオーダーからコントロールを削除するには</span><span class="sxs-lookup"><span data-stu-id="c1a12-130">To remove a control from the tab order</span></span>

<span data-ttu-id="c1a12-131">**[プロパティ]** ウィンドウで、コントロールの <xref:System.Windows.Forms.Control.TabStop%2A> プロパティを**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="c1a12-131">Set the control's <xref:System.Windows.Forms.Control.TabStop%2A> property to **false** in the **Properties** window.</span></span>

<span data-ttu-id="c1a12-132">Tab キーを使用してコントロールを巡回するときにコントロールがスキップされた場合でも、<xref:System.Windows.Forms.Control.TabStop%2A> プロパティが `false` に設定されているコントロールは、タブオーダー内でその位置を維持します。</span><span class="sxs-lookup"><span data-stu-id="c1a12-132">A control whose <xref:System.Windows.Forms.Control.TabStop%2A> property has been set to `false` still maintains its position in the tab order, even though the control is skipped when you cycle through the controls with the Tab key.</span></span>

> [!NOTE]
> <span data-ttu-id="c1a12-133">ラジオボタングループには、実行時に1つのタブストップがあります。</span><span class="sxs-lookup"><span data-stu-id="c1a12-133">A radio button group has a single tab stop at run time.</span></span> <span data-ttu-id="c1a12-134">選択したボタン ([<xref:System.Windows.Forms.RadioButton.Checked%2A>] プロパティが [`true`] に設定されているボタン) では、[<xref:System.Windows.Forms.Control.TabStop%2A>] プロパティが [`true`] に自動的に設定されます。一方、他のボタンでは <xref:System.Windows.Forms.Control.TabStop%2A> プロパティが `false`に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c1a12-134">The selected button (that is, the button with its <xref:System.Windows.Forms.RadioButton.Checked%2A> property set to `true`) has its <xref:System.Windows.Forms.Control.TabStop%2A> property automatically set to `true`, while the other buttons have their <xref:System.Windows.Forms.Control.TabStop%2A> property set to `false`.</span></span> <span data-ttu-id="c1a12-135"><xref:System.Windows.Forms.RadioButton> コントロールのグループ化の詳細については、「 [Set Windows フォーム RadioButton コントロールをセットとして機能させる](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1a12-135">For more information about grouping <xref:System.Windows.Forms.RadioButton> controls, see [Grouping Windows Forms RadioButton Controls to Function as a Set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1a12-136">参照</span><span class="sxs-lookup"><span data-stu-id="c1a12-136">See also</span></span>

- [<span data-ttu-id="c1a12-137">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="c1a12-137">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="c1a12-138">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="c1a12-138">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="c1a12-139">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="c1a12-139">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
