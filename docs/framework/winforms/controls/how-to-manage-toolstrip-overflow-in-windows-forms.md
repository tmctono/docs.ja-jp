---
title: '方法: Windows フォームで ToolStrip オーバーフローを管理します。'
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
ms.openlocfilehash: 53f610a728925d454a8833a49e705818f027aec5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913758"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="67463-102">方法: Windows フォームで ToolStrip オーバーフローを管理します。</span><span class="sxs-lookup"><span data-stu-id="67463-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="67463-103">ときにすべての項目を<xref:System.Windows.Forms.ToolStrip>コントロールが与えられたスペースに収まらないでオーバーフロー機能を有効にすることができます、<xref:System.Windows.Forms.ToolStrip>固有のオーバーフロー動作を決定し、 <xref:System.Windows.Forms.ToolStripItem>s。</span><span class="sxs-lookup"><span data-stu-id="67463-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="67463-104">追加すると<xref:System.Windows.Forms.ToolStripItem>に割り当てられた時間はより多くの領域を必要とする、<xref:System.Windows.Forms.ToolStrip>フォームの現在のサイズを指定、<xref:System.Windows.Forms.ToolStripOverflowButton>で自動的に表示されます、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="67463-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="67463-105"><xref:System.Windows.Forms.ToolStripOverflowButton>が表示されたら、オーバーフローが有効な項目がドロップダウンのオーバーフロー メニューに移動します。</span><span class="sxs-lookup"><span data-stu-id="67463-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="67463-106">これを使用すると、カスタマイズ、および優先順位を付ける方法、<xref:System.Windows.Forms.ToolStrip>項目は、さまざまなフォームのサイズを正しく調整。</span><span class="sxs-lookup"><span data-stu-id="67463-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="67463-107">使用して、オーバーフローになったとき、項目の外観を変更することも、<xref:System.Windows.Forms.ToolStripItem.Placement%2A>と<xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType>プロパティおよび<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>イベント。</span><span class="sxs-lookup"><span data-stu-id="67463-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="67463-108">複数のデザイン時または実行時に、フォームを拡大する場合<xref:System.Windows.Forms.ToolStripItem>s は、メイン表示できる<xref:System.Windows.Forms.ToolStrip>と<xref:System.Windows.Forms.ToolStripOverflowButton>フォームのサイズを小さくまでも表示されなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67463-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="67463-109">ToolStrip コントロールのオーバーフローを有効にするには</span><span class="sxs-lookup"><span data-stu-id="67463-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="67463-110">いることを確認、<xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>プロパティに設定されていない`false`の<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="67463-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="67463-111">既定値は `True` です。</span><span class="sxs-lookup"><span data-stu-id="67463-111">The default is `True`.</span></span>

     <span data-ttu-id="67463-112">ときに<xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>は`True`(既定)、<xref:System.Windows.Forms.ToolStripItem>ドロップダウンのオーバーフロー メニューに送信されるときのコンテンツ、<xref:System.Windows.Forms.ToolStripItem>水平方向の幅を超える<xref:System.Windows.Forms.ToolStrip>または垂直方向の高さ<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="67463-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="67463-113">特定の ToolStripItem のオーバーフロー動作を指定するには</span><span class="sxs-lookup"><span data-stu-id="67463-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="67463-114">設定、<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>のプロパティ、<xref:System.Windows.Forms.ToolStripItem>に目的の値。</span><span class="sxs-lookup"><span data-stu-id="67463-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="67463-115">可能性は`Always`、 `Never`、および`AsNeeded`します。</span><span class="sxs-lookup"><span data-stu-id="67463-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="67463-116">既定値は `AsNeeded` です。</span><span class="sxs-lookup"><span data-stu-id="67463-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="67463-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="67463-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="67463-118">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="67463-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="67463-119">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="67463-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="67463-120">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="67463-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
