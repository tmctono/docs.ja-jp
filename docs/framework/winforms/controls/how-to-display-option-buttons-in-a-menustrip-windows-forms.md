---
title: '方法: MenuStrip にオプションボタンを表示する (Windows フォーム)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 94d683369edd6583ad8b01c2ce3f393567a5ed75
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971933"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="14bfb-102">方法: MenuStrip にオプションボタンを表示する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="14bfb-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="14bfb-103">オプションボタンは、オプションボタンとも呼ばれ、ユーザーが一度に1つだけ選択できる点を除いて、チェックボックスに似ています。</span><span class="sxs-lookup"><span data-stu-id="14bfb-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="14bfb-104">既定では、 <xref:System.Windows.Forms.ToolStripMenuItem>クラスにはオプションボタンの動作が用意されていませんが、クラスには、 <xref:System.Windows.Forms.MenuStrip>コントロールのメニュー項目に対してオプションボタンの動作を実装するようにカスタマイズできるチェックボックスの動作が用意されています。</span><span class="sxs-lookup"><span data-stu-id="14bfb-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="14bfb-105">メニュー項目の`true`プロパティがの場合、ユーザーは項目をクリックしてチェックマークの表示を切り替えることができます。 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A></span><span class="sxs-lookup"><span data-stu-id="14bfb-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="14bfb-106">プロパティ<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>は、項目の現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="14bfb-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="14bfb-107">基本的なオプションボタンの動作を実装するには、項目が選択されているときに<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> 、前に選択した項目`false`のプロパティをに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14bfb-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="14bfb-108">次の手順では、 <xref:System.Windows.Forms.ToolStripMenuItem>クラスを継承するクラスにこの機能と追加の機能を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="14bfb-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="14bfb-109">クラス`ToolStripRadioButtonMenuItem`は、 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> や<xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>などのメンバーをオーバーライドして、オプションボタンの選択動作と外観を提供します。</span><span class="sxs-lookup"><span data-stu-id="14bfb-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="14bfb-110">また、このクラスは、 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>親項目が選択されていない場合にサブメニューのオプションが無効になるように、プロパティをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="14bfb-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="14bfb-111">オプションボタンの選択動作を実装するには</span><span class="sxs-lookup"><span data-stu-id="14bfb-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="14bfb-112">項目の<xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>選択を`true`有効にするには、プロパティをに初期化します。</span><span class="sxs-lookup"><span data-stu-id="14bfb-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="14bfb-113">新しい項目<xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>を選択したときに、前に選択した項目の選択を解除するには、メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="14bfb-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="14bfb-114"><xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A>メソッドをオーバーライドして、既に選択されている項目をクリックしても選択内容がクリアされないようにします。</span><span class="sxs-lookup"><span data-stu-id="14bfb-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="14bfb-115">オプションボタンの項目の外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="14bfb-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="14bfb-116">クラスを使用して、既定のチェックマークをオプションボタンに置き換えるには、メソッドを<xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>オーバーライドします。 <xref:System.Windows.Forms.RadioButtonRenderer></span><span class="sxs-lookup"><span data-stu-id="14bfb-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="14bfb-117"><xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> 、、、および<xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A>の各メソッドをオーバーライドしてマウスの状態を追跡し、メソッドが適切なオプションボタンの状態を描画するようにします。 <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A></span><span class="sxs-lookup"><span data-stu-id="14bfb-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="14bfb-118">親項目が選択されていないときにサブメニューのオプションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="14bfb-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="14bfb-119"><xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> の<xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A>値と値の両方を持つ親項目がある場合に、項目が無効になるように、プロパティをオーバーライドします。`false` `true`</span><span class="sxs-lookup"><span data-stu-id="14bfb-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="14bfb-120">親アイテム<xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>の<xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>イベントをサブスクライブするには、メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="14bfb-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="14bfb-121">親項目<xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>のイベントのハンドラーで、項目を無効にして、新しい有効な状態で表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="14bfb-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="14bfb-122">例</span><span class="sxs-lookup"><span data-stu-id="14bfb-122">Example</span></span>

<span data-ttu-id="14bfb-123">次のコード例では、 `ToolStripRadioButtonMenuItem`完全なクラス<xref:System.Windows.Forms.Form>と、オプション`Program`ボタンの動作を示すクラスとクラスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="14bfb-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="14bfb-124">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="14bfb-124">Compiling the Code</span></span>

<span data-ttu-id="14bfb-125">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14bfb-125">This example requires:</span></span>

- <span data-ttu-id="14bfb-126">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="14bfb-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="14bfb-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="14bfb-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="14bfb-128">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="14bfb-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="14bfb-129">方法: カスタム ToolStripRenderer を実装する</span><span class="sxs-lookup"><span data-stu-id="14bfb-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
