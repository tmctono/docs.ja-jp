---
title: '方法: Windows フォーム上のタブ オーダーを設定する'
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8a0a1c76b996f10de0ca963c5d8bdc2325a3f6b6
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987097"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a><span data-ttu-id="73d4b-102">方法: Windows フォームのタブオーダーを設定する</span><span class="sxs-lookup"><span data-stu-id="73d4b-102">How to: Set the tab order on Windows Forms</span></span>

<span data-ttu-id="73d4b-103">タブオーダーは、Tab キーを押すことによって、ユーザーがあるコントロールから別のコントロールにフォーカスを移動する順序です。</span><span class="sxs-lookup"><span data-stu-id="73d4b-103">The tab order is the order in which a user moves focus from one control to another by pressing the Tab key.</span></span> <span data-ttu-id="73d4b-104">各フォームには、独自のタブオーダーがあります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-104">Each form has its own tab order.</span></span> <span data-ttu-id="73d4b-105">既定では、タブオーダーは、コントロールを作成した順序と同じです。</span><span class="sxs-lookup"><span data-stu-id="73d4b-105">By default, the tab order is the same as the order in which you created the controls.</span></span> <span data-ttu-id="73d4b-106">タブオーダー番号は0から始まります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-106">Tab-order numbering begins with zero.</span></span>

## <a name="to-set-the-tab-order-of-a-control"></a><span data-ttu-id="73d4b-107">コントロールのタブオーダーを設定するには</span><span class="sxs-lookup"><span data-stu-id="73d4b-107">To set the tab order of a control</span></span>

1. <span data-ttu-id="73d4b-108">Visual Studio の **[表示]** メニューで、 **[タブオーダー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="73d4b-108">In Visual Studio, on the **View** menu, select **Tab Order**.</span></span>

   <span data-ttu-id="73d4b-109">これにより、フォームのタブオーダー選択モードがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-109">This activates the tab-order selection mode on the form.</span></span> <span data-ttu-id="73d4b-110">各コントロールの左上隅<xref:System.Windows.Forms.Control.TabIndex%2A>に、(プロパティを表す) 数値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-110">A number (representing the <xref:System.Windows.Forms.Control.TabIndex%2A> property) appears in the upper-left corner of each control.</span></span>

2. <span data-ttu-id="73d4b-111">コントロールを順番にクリックして、目的のタブオーダーを設定します。</span><span class="sxs-lookup"><span data-stu-id="73d4b-111">Click the controls sequentially to establish the tab order you want.</span></span>

   > [!NOTE]
   > <span data-ttu-id="73d4b-112">タブオーダー内のコントロールの位置は、0以上の任意の値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-112">A control's place within the tab order can be set to any value greater than or equal to 0.</span></span> <span data-ttu-id="73d4b-113">重複が発生すると、2つのコントロールの z オーダーが評価され、上のコントロールが最初にタブになります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-113">When duplicates occur, the z-order of the two controls is evaluated and the control on top is tabbed to first.</span></span> <span data-ttu-id="73d4b-114">(Z オーダーは、フォームの z 軸の [奥行] に沿ったフォーム上のコントロールの視覚的なレイヤーです。</span><span class="sxs-lookup"><span data-stu-id="73d4b-114">(The z-order is the visual layering of controls on a form along the form's z-axis [depth].</span></span> <span data-ttu-id="73d4b-115">Z オーダーは、他のコントロールの前にあるコントロールを決定します。)Z オーダーの詳細については、「 [Windows フォームのオブジェクトのレイヤー](how-to-layer-objects-on-windows-forms.md)化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d4b-115">The z-order determines which controls are in front of other controls.) For more information on z-order, see [Layering Objects on Windows Forms](how-to-layer-objects-on-windows-forms.md).</span></span>

3. <span data-ttu-id="73d4b-116">終了したら、 **[表示]** メニューの **[タブオーダー]** をもう一度選択して、タブオーダーモードを終了します。</span><span class="sxs-lookup"><span data-stu-id="73d4b-116">When you have finished, select **Tab Order** on the **View** menu again to leave tab order mode.</span></span>

   > [!NOTE]
   > <span data-ttu-id="73d4b-117">フォーカスを取得できず、無効になったコントロールや非表示のコントロールでも、 <xref:System.Windows.Forms.Control.TabIndex%2A>プロパティはなく、タブオーダーには含まれません。</span><span class="sxs-lookup"><span data-stu-id="73d4b-117">Controls that cannot get the focus, as well as disabled and invisible controls, do not have a <xref:System.Windows.Forms.Control.TabIndex%2A> property and are not included in the tab order.</span></span> <span data-ttu-id="73d4b-118">ユーザーが Tab キーを押すと、これらのコントロールはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-118">As a user presses the Tab key, these controls are skipped.</span></span>

<span data-ttu-id="73d4b-119">また、 <xref:System.Windows.Forms.Control.TabIndex%2A>プロパティを使用して、プロパティウィンドウでタブオーダーを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-119">Alternatively, tab order can be set in the Properties window using the <xref:System.Windows.Forms.Control.TabIndex%2A> property.</span></span> <span data-ttu-id="73d4b-120">コントロール<xref:System.Windows.Forms.Control.TabIndex%2A>のプロパティは、タブオーダー内での位置を決定します。</span><span class="sxs-lookup"><span data-stu-id="73d4b-120">The <xref:System.Windows.Forms.Control.TabIndex%2A> property of a control determines where it is positioned in the tab order.</span></span> <span data-ttu-id="73d4b-121">既定では、描画<xref:System.Windows.Forms.Control.TabIndex%2A>された最初のコントロールの値は0、2番目のコントロールのは<xref:System.Windows.Forms.Control.TabIndex%2A> 1、などです。</span><span class="sxs-lookup"><span data-stu-id="73d4b-121">By default, the first control drawn has a <xref:System.Windows.Forms.Control.TabIndex%2A> value of 0, the second has a <xref:System.Windows.Forms.Control.TabIndex%2A> of 1, and so on.</span></span>

<span data-ttu-id="73d4b-122">また、既定<xref:System.Windows.Forms.GroupBox>では、コントロールには、 <xref:System.Windows.Forms.Control.TabIndex%2A>整数である独自の値があります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-122">Additionally, by default, a <xref:System.Windows.Forms.GroupBox> control has its own <xref:System.Windows.Forms.Control.TabIndex%2A> value, which is a whole number.</span></span> <span data-ttu-id="73d4b-123">コントロール<xref:System.Windows.Forms.GroupBox>自体には、実行時にフォーカスを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="73d4b-123">A <xref:System.Windows.Forms.GroupBox> control itself cannot have focus at run time.</span></span> <span data-ttu-id="73d4b-124">したがって、内<xref:System.Windows.Forms.GroupBox>の各コントロールには、0から始まる独自の10進<xref:System.Windows.Forms.Control.TabIndex%2A>値があります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-124">Thus, each control within a <xref:System.Windows.Forms.GroupBox> has its own decimal <xref:System.Windows.Forms.Control.TabIndex%2A> value, beginning with .0.</span></span> <span data-ttu-id="73d4b-125">当然ながら、 <xref:System.Windows.Forms.GroupBox>コントロール<xref:System.Windows.Forms.Control.TabIndex%2A>のがインクリメントされると、その中のコントロールがそれに応じてインクリメントされます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-125">Naturally, as the <xref:System.Windows.Forms.Control.TabIndex%2A> of a <xref:System.Windows.Forms.GroupBox> control is incremented, the controls within it will be incremented accordingly.</span></span> <span data-ttu-id="73d4b-126">値を<xref:System.Windows.Forms.Control.TabIndex%2A> 5 から6に変更した場合、 <xref:System.Windows.Forms.Control.TabIndex%2A>そのグループの最初のコントロールの値は自動的に6.0 に変更されます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-126">If you changed a <xref:System.Windows.Forms.Control.TabIndex%2A> value from 5 to 6, the <xref:System.Windows.Forms.Control.TabIndex%2A> value of the first control in its group automatically changes to 6.0, and so on.</span></span>

<span data-ttu-id="73d4b-127">最後に、フォーム上の多くのコントロールは、タブオーダーではスキップできます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-127">Finally, any control of the many on your form can be skipped in the tab order.</span></span> <span data-ttu-id="73d4b-128">通常、実行時に Tab キーを連続して押すと、各コントロールがタブオーダーで選択されます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-128">Usually, pressing Tab successively at run time selects each control in the tab order.</span></span> <span data-ttu-id="73d4b-129"><xref:System.Windows.Forms.Control.TabStop%2A>プロパティをオフにすると、フォームのタブオーダーでコントロールを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-129">By turning off the <xref:System.Windows.Forms.Control.TabStop%2A> property, you can make a control be passed over in the tab order of the form.</span></span>

## <a name="to-remove-a-control-from-the-tab-order"></a><span data-ttu-id="73d4b-130">タブオーダーからコントロールを削除するには</span><span class="sxs-lookup"><span data-stu-id="73d4b-130">To remove a control from the tab order</span></span>

<span data-ttu-id="73d4b-131">[プロパティ] ウィンドウ<xref:System.Windows.Forms.Control.TabStop%2A>で、コントロールのプロパティを**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="73d4b-131">Set the control's <xref:System.Windows.Forms.Control.TabStop%2A> property to **false** in the **Properties** window.</span></span>

<span data-ttu-id="73d4b-132">Tab キーを<xref:System.Windows.Forms.Control.TabStop%2A>使用してコントロールを`false`巡回するときにコントロールがスキップされる場合でも、プロパティがに設定されているコントロールは、タブオーダーの位置を維持します。</span><span class="sxs-lookup"><span data-stu-id="73d4b-132">A control whose <xref:System.Windows.Forms.Control.TabStop%2A> property has been set to `false` still maintains its position in the tab order, even though the control is skipped when you cycle through the controls with the Tab key.</span></span>

> [!NOTE]
> <span data-ttu-id="73d4b-133">ラジオボタングループには、実行時に1つのタブストップがあります。</span><span class="sxs-lookup"><span data-stu-id="73d4b-133">A radio button group has a single tab stop at run time.</span></span> <span data-ttu-id="73d4b-134">選択した<xref:System.Windows.Forms.RadioButton.Checked%2A>ボタン (プロパティがに`true`設定されているボタン) <xref:System.Windows.Forms.Control.TabStop%2A>では、プロパティが自動的`true`に<xref:System.Windows.Forms.Control.TabStop%2A>に設定され、他のボタンの`false`プロパティはに設定されます。</span><span class="sxs-lookup"><span data-stu-id="73d4b-134">The selected button (that is, the button with its <xref:System.Windows.Forms.RadioButton.Checked%2A> property set to `true`) has its <xref:System.Windows.Forms.Control.TabStop%2A> property automatically set to `true`, while the other buttons have their <xref:System.Windows.Forms.Control.TabStop%2A> property set to `false`.</span></span> <span data-ttu-id="73d4b-135">コントロールのグループ化<xref:System.Windows.Forms.RadioButton>の詳細については、「 [Set Windows フォーム RadioButton コントロールをセットとして機能させる](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73d4b-135">For more information about grouping <xref:System.Windows.Forms.RadioButton> controls, see [Grouping Windows Forms RadioButton Controls to Function as a Set](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="73d4b-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="73d4b-136">See also</span></span>

- [<span data-ttu-id="73d4b-137">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="73d4b-137">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="73d4b-138">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="73d4b-138">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="73d4b-139">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="73d4b-139">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
