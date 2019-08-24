---
title: '方法: Windows フォームにコントロールを固定する'
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94fa6fe90e5583a3bfecf376af59d53f6d8528af
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987503"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="2a7f4-102">方法: Windows フォームのアンカーコントロール</span><span class="sxs-lookup"><span data-stu-id="2a7f4-102">How to: Anchor controls on Windows Forms</span></span>

<span data-ttu-id="2a7f4-103">実行時にユーザーがサイズ変更できるフォームをデザインする場合は、フォーム上のコントロールのサイズと位置が適切に変更される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-103">If you're designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="2a7f4-104">フォームを使用してコントロールのサイズを動的に変更<xref:System.Windows.Forms.Control.Anchor%2A>するには、Windows フォームコントロールのプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="2a7f4-105">プロパティ<xref:System.Windows.Forms.Control.Anchor%2A>は、コントロールのアンカー位置を定義します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="2a7f4-106">コントロールがフォームに固定され、フォームのサイズが変更されると、コントロールは、コントロールとアンカー位置との距離を維持します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="2a7f4-107">たとえば、フォームのサイズが変更<xref:System.Windows.Forms.TextBox>されたときにフォームの左端、右端、および下端に固定されているコントロールがある場合は<xref:System.Windows.Forms.TextBox> 、フォームの右端と左端から同じ距離が維持されるように、コントロールが水平方向にサイズ変更されます。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="2a7f4-108">また、コントロールは、その位置が常にフォームの下端から同じ距離になるように垂直方向に配置されます。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="2a7f4-109">コントロールが固定されておらず、フォームのサイズが変更されている場合は、フォームの端を基準としたコントロールの位置が変更されます。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>

<span data-ttu-id="2a7f4-110">プロパティ<xref:System.Windows.Forms.Control.Anchor%2A>は、 <xref:System.Windows.Forms.Control.AutoSize%2A>プロパティと対話します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="2a7f4-111">詳細については、「 [AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="anchor-a-control-on-a-form"></a><span data-ttu-id="2a7f4-112">フォームにコントロールを固定する</span><span class="sxs-lookup"><span data-stu-id="2a7f4-112">Anchor a control on a form</span></span>

1. <span data-ttu-id="2a7f4-113">Visual Studio で、アンカーするコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-113">In Visual Studio, select the control you want to anchor.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2a7f4-114">複数のコントロールを同時に固定するには、CTRL キーを押しながら各コントロールをクリックして選択し、この手順の残りの部分を実行します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-114">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>

2. <span data-ttu-id="2a7f4-115">**[プロパティ]** ウィンドウで、 <xref:System.Windows.Forms.Control.Anchor%2A>プロパティの右側にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-115">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>

     <span data-ttu-id="2a7f4-116">クロスを示すエディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-116">An editor is displayed that shows a cross.</span></span>

3. <span data-ttu-id="2a7f4-117">アンカーを設定するには、交差部分の上、左、右、または下のセクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-117">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>

     <span data-ttu-id="2a7f4-118">既定では、コントロールは上と左に固定されています。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-118">Controls are anchored to the top and left by default.</span></span>

4. <span data-ttu-id="2a7f4-119">アンカーされているコントロールの辺をクリアするには、クロスの arm をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-119">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>

5. <span data-ttu-id="2a7f4-120"><xref:System.Windows.Forms.Control.Anchor%2A>プロパティエディターを閉じるには、 <xref:System.Windows.Forms.Control.Anchor%2A>プロパティ名をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-120">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>

<span data-ttu-id="2a7f4-121">実行時にフォームを表示すると、フォームの端と同じ距離に配置されたままになるようにコントロールのサイズが変更されます。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-121">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="2a7f4-122">固定されたエッジからの距離は、コントロールが Windows フォームデザイナーに配置されているときに定義されている距離と常に同じままです。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-122">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>

> [!NOTE]
> <span data-ttu-id="2a7f4-123"><xref:System.Windows.Forms.ComboBox>コントロールなどの特定のコントロールの高さには制限があります。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-123">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="2a7f4-124">コントロールをフォームまたはコンテナーの下部に固定すると、コントロールの高さの制限を超えることはありません。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-124">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>

<span data-ttu-id="2a7f4-125">継承された`Protected`コントロールを固定できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-125">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="2a7f4-126">コントロールのアクセスレベルを変更するには、[ `Modifiers` **プロパティ**] ウィンドウでプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="2a7f4-126">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a7f4-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a7f4-127">See also</span></span>

- [<span data-ttu-id="2a7f4-128">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="2a7f4-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="2a7f4-129">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="2a7f4-129">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="2a7f4-130">方法: Windows フォームにコントロールをドッキングする</span><span class="sxs-lookup"><span data-stu-id="2a7f4-130">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="2a7f4-131">チュートリアル: FlowLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="2a7f4-131">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="2a7f4-132">チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="2a7f4-132">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="2a7f4-133">チュートリアル: パディング、余白、AutoSize プロパティを使用して Windows フォームコントロールをレイアウトする</span><span class="sxs-lookup"><span data-stu-id="2a7f4-133">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
