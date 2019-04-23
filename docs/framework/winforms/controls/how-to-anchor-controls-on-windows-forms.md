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
ms.openlocfilehash: b5550aef220ece09d5486421275b19a37bfe9011
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329779"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a><span data-ttu-id="00c8c-102">方法: Windows フォームにコントロールを固定する</span><span class="sxs-lookup"><span data-stu-id="00c8c-102">How to: Anchor Controls on Windows Forms</span></span>
<span data-ttu-id="00c8c-103">ユーザーが実行時にフォームをデザインする場合、フォーム上のコントロールをサイズを変更し、正しくの位置を変更します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-103">If you are designing a form that the user can resize at run time, the controls on your form should resize and reposition properly.</span></span> <span data-ttu-id="00c8c-104">動的フォームにコントロールのサイズを変更するには、使用することができます、 <xref:System.Windows.Forms.Control.Anchor%2A> Windows フォーム コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="00c8c-104">To resize controls dynamically with the form, you can use the <xref:System.Windows.Forms.Control.Anchor%2A> property of Windows Forms controls.</span></span> <span data-ttu-id="00c8c-105"><xref:System.Windows.Forms.Control.Anchor%2A>プロパティ、コントロールのアンカーの位置を定義します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-105">The <xref:System.Windows.Forms.Control.Anchor%2A> property defines an anchor position for the control.</span></span> <span data-ttu-id="00c8c-106">フォームにコントロールを固定すると、フォームのサイズが、コントロールは、コントロールとアンカー位置の間の距離を保持します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-106">When a control is anchored to a form and the form is resized, the control maintains the distance between the control and the anchor positions.</span></span> <span data-ttu-id="00c8c-107">ある場合など、<xref:System.Windows.Forms.TextBox>ようにフォームのサイズが、左、右、およびフォームの下端に固定されているコントロール、<xref:System.Windows.Forms.TextBox>フォームの右辺と左辺からの距離が維持されるため、水平方向にサイズ変更を制御します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-107">For example, if you have a <xref:System.Windows.Forms.TextBox> control that is anchored to the left, right, and bottom edges of the form, as the form is resized, the <xref:System.Windows.Forms.TextBox> control resizes horizontally so that it maintains the same distance from the right and left sides of the form.</span></span> <span data-ttu-id="00c8c-108">さらに、コントロール配置自体垂直方向にその場所は、フォームの下端から同じ距離では常にできるようにします。</span><span class="sxs-lookup"><span data-stu-id="00c8c-108">In addition, the control positions itself vertically so that its location is always the same distance from the bottom edge of the form.</span></span> <span data-ttu-id="00c8c-109">コントロールが固定されていないと、フォームのサイズが、フォームの端を基準としたコントロールの位置が変更されました。</span><span class="sxs-lookup"><span data-stu-id="00c8c-109">If a control is not anchored and the form is resized, the position of the control relative to the edges of the form is changed.</span></span>  
  
 <span data-ttu-id="00c8c-110"><xref:System.Windows.Forms.Control.Anchor%2A>プロパティの対話、<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="00c8c-110">The <xref:System.Windows.Forms.Control.Anchor%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="00c8c-111">詳細については、次を参照してください。 [AutoSize プロパティの概要](autosize-property-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-111">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00c8c-112">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00c8c-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="00c8c-113">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00c8c-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="00c8c-114">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00c8c-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-anchor-a-control-on-a-form"></a><span data-ttu-id="00c8c-115">フォームのコントロールを固定するには</span><span class="sxs-lookup"><span data-stu-id="00c8c-115">To anchor a control on a form</span></span>  
  
1. <span data-ttu-id="00c8c-116">固定するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-116">Select the control you want to anchor.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00c8c-117">CTRL キーを押しを選択し、各コントロールをクリックし、この手順の残りの部分で同時に複数のコントロールを固定できます。</span><span class="sxs-lookup"><span data-stu-id="00c8c-117">You can anchor multiple controls simultaneously by pressing the CTRL key, clicking each control to select it, and then following the rest of this procedure.</span></span>  
  
2. <span data-ttu-id="00c8c-118">**プロパティ** ウィンドウの右矢印をクリックして、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="00c8c-118">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span>  
  
     <span data-ttu-id="00c8c-119">クロス エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00c8c-119">An editor is displayed that shows a cross.</span></span>  
  
3. <span data-ttu-id="00c8c-120">アンカーを設定するには、上、左、右、またはクロスの下部のセクションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="00c8c-120">To set an anchor, click the top, left, right, or bottom section of the cross.</span></span>  
  
     <span data-ttu-id="00c8c-121">コントロールでは、上部に固定し、既定のまま。</span><span class="sxs-lookup"><span data-stu-id="00c8c-121">Controls are anchored to the top and left by default.</span></span>  
  
4. <span data-ttu-id="00c8c-122">固定されているコントロールの辺をクリアするには、その arm クロスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="00c8c-122">To clear a side of the control that has been anchored, click that arm of the cross.</span></span>  
  
5. <span data-ttu-id="00c8c-123">閉じるには、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティ エディターでは、クリックして、<xref:System.Windows.Forms.Control.Anchor%2A>プロパティ名をもう一度です。</span><span class="sxs-lookup"><span data-stu-id="00c8c-123">To close the <xref:System.Windows.Forms.Control.Anchor%2A> property editor, click the <xref:System.Windows.Forms.Control.Anchor%2A> property name again.</span></span>  
  
 <span data-ttu-id="00c8c-124">実行時にフォームが表示されたら、フォームの端からの距離を保持するコントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="00c8c-124">When your form is displayed at run time, the control resizes to remain positioned at the same distance from the edge of the form.</span></span> <span data-ttu-id="00c8c-125">アンカーの端からの距離の距離では、Windows フォーム デザイナーでコントロールを配置するときに定義されているように同じが常にです。</span><span class="sxs-lookup"><span data-stu-id="00c8c-125">The distance from the anchored edge always remains the same as the distance defined when the control is positioned in the Windows Forms Designer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00c8c-126">などの特定のコントロール、<xref:System.Windows.Forms.ComboBox>コントロールを高さが制限があります。</span><span class="sxs-lookup"><span data-stu-id="00c8c-126">Certain controls, such as the <xref:System.Windows.Forms.ComboBox> control, have a limit to their height.</span></span> <span data-ttu-id="00c8c-127">フォームまたはコンテナーの下にコントロールを固定すると、その高さの制限を超えるコントロールが強制はできません。</span><span class="sxs-lookup"><span data-stu-id="00c8c-127">Anchoring the control to the bottom of its form or container cannot force the control to exceed its height limit.</span></span>  
  
 <span data-ttu-id="00c8c-128">継承されたコントロールである必要があります`Protected`固定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="00c8c-128">Inherited controls must be `Protected` to be able to be anchored.</span></span> <span data-ttu-id="00c8c-129">コントロールのアクセス レベルを変更するには、次のように設定します。 その`Modifiers`プロパティ、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="00c8c-129">To change the access level of a control, set its `Modifiers` property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00c8c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="00c8c-130">See also</span></span>

- [<span data-ttu-id="00c8c-131">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="00c8c-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="00c8c-132">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="00c8c-132">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="00c8c-133">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="00c8c-133">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="00c8c-134">方法: Windows フォーム上のコントロールをドッキングします。</span><span class="sxs-lookup"><span data-stu-id="00c8c-134">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="00c8c-135">チュートリアル: FlowLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="00c8c-135">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="00c8c-136">チュートリアル: TableLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="00c8c-136">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="00c8c-137">チュートリアル: Windows フォーム コントロール Padding、Margin、および AutoSize プロパティをレイアウト</span><span class="sxs-lookup"><span data-stu-id="00c8c-137">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)
