---
title: '方法: マウス ポインターが ToolStripItem 上にあることを検出する'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 09fd9f2f9b8cc44b6c04b829bf2854bea4aa8cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054264"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ba6c7-102">方法: マウス ポインターが ToolStripItem 上にあることを検出する</span><span class="sxs-lookup"><span data-stu-id="ba6c7-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="ba6c7-103">マウス ポインターが上を検出するために、次の手順を使用して、<xref:System.Windows.Forms.ToolStripItem>します。</span><span class="sxs-lookup"><span data-stu-id="ba6c7-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="ba6c7-104">ポインターが toolstripitem を検出するには</span><span class="sxs-lookup"><span data-stu-id="ba6c7-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
- <span data-ttu-id="ba6c7-105">使用して、<xref:System.Windows.Forms.ToolStripItem.Selected%2A>をアイテムのプロパティ<xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>は`true`します。</span><span class="sxs-lookup"><span data-stu-id="ba6c7-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="ba6c7-106">これによりを同期することから、<xref:System.Windows.Forms.ToolStripItem.MouseEnter>と<xref:System.Windows.Forms.ToolStripItem.MouseLeave>イベント。</span><span class="sxs-lookup"><span data-stu-id="ba6c7-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6c7-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba6c7-107">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="ba6c7-108">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ba6c7-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
