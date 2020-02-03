---
title: '方法 : ToolStrip オーバーフローを管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736147"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="20641-102">方法 : Windows フォームの ToolStrip オーバーフローを管理する</span><span class="sxs-lookup"><span data-stu-id="20641-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="20641-103"><xref:System.Windows.Forms.ToolStrip> コントロールのすべての項目が割り当てられた領域に収まらない場合は、<xref:System.Windows.Forms.ToolStrip> でオーバーフロー機能を有効にし、特定の <xref:System.Windows.Forms.ToolStripItem>s のオーバーフロー動作を決定できます。</span><span class="sxs-lookup"><span data-stu-id="20641-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="20641-104">フォームの現在のサイズに <xref:System.Windows.Forms.ToolStrip> 割り当てられているよりも多くの領域を必要とする <xref:System.Windows.Forms.ToolStripItem>を追加すると、<xref:System.Windows.Forms.ToolStrip>に <xref:System.Windows.Forms.ToolStripOverflowButton> が自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="20641-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="20641-105"><xref:System.Windows.Forms.ToolStripOverflowButton> が表示され、オーバーフローに対応する項目がドロップダウンオーバーフローメニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="20641-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="20641-106">これにより、<xref:System.Windows.Forms.ToolStrip> 項目がさまざまなフォームサイズに適切に調整される方法をカスタマイズし、優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="20641-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="20641-107">また、<xref:System.Windows.Forms.ToolStripItem.Placement%2A> と <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> のプロパティと <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> イベントを使用して、項目がオーバーフローになったときの外観を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="20641-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="20641-108">デザイン時または実行時にフォームを拡大すると、メイン <xref:System.Windows.Forms.ToolStrip> により多くの <xref:System.Windows.Forms.ToolStripItem>が表示され、フォームのサイズを小さくするまで <xref:System.Windows.Forms.ToolStripOverflowButton> が消えてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20641-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="20641-109">ToolStrip コントロールでオーバーフローを有効にするには</span><span class="sxs-lookup"><span data-stu-id="20641-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="20641-110"><xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> プロパティが <xref:System.Windows.Forms.ToolStrip>の `false` に設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="20641-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="20641-111">既定では、 `True`です。</span><span class="sxs-lookup"><span data-stu-id="20641-111">The default is `True`.</span></span>

     <span data-ttu-id="20641-112"><xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> が `True` (既定値) の場合、<xref:System.Windows.Forms.ToolStripItem> のコンテンツが水平方向の <xref:System.Windows.Forms.ToolStrip> の幅または垂直 <xref:System.Windows.Forms.ToolStrip>の高さを超えたときに、<xref:System.Windows.Forms.ToolStripItem> がドロップダウンオーバーフローメニューに送信されます。</span><span class="sxs-lookup"><span data-stu-id="20641-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="20641-113">特定の ToolStripItem のオーバーフロー動作を指定するには</span><span class="sxs-lookup"><span data-stu-id="20641-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="20641-114"><xref:System.Windows.Forms.ToolStripItem> の <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="20641-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="20641-115">`Always`、`Never`、`AsNeeded`の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20641-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="20641-116">既定では、 `AsNeeded`です。</span><span class="sxs-lookup"><span data-stu-id="20641-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="20641-117">参照</span><span class="sxs-lookup"><span data-stu-id="20641-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="20641-118">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="20641-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="20641-119">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="20641-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="20641-120">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="20641-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
