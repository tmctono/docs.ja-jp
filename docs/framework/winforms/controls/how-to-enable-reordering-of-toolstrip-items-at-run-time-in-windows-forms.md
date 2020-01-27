---
title: '方法 : 実行時に ToolStrip 項目を並べ替えできるようにする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745479"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="caa9c-102">方法 : Windows フォーム内で実行時に ToolStrip 項目を並べ替えできるようにする</span><span class="sxs-lookup"><span data-stu-id="caa9c-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="caa9c-103">ユーザーが <xref:System.Windows.Forms.ToolStrip>上で <xref:System.Windows.Forms.ToolStripItem> コントロールを再配置できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="caa9c-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="caa9c-104">実行時に ToolStripItem の再配置を有効にするには</span><span class="sxs-lookup"><span data-stu-id="caa9c-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
- <span data-ttu-id="caa9c-105"><xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="caa9c-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="caa9c-106">既定では、<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> は `false`です。</span><span class="sxs-lookup"><span data-stu-id="caa9c-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="caa9c-107">実行時には、ユーザーは ALT キーを押したままマウスの左ボタンを押すと、<xref:System.Windows.Forms.ToolStripItem> が <xref:System.Windows.Forms.ToolStrip>上の別の場所にドラッグされます。</span><span class="sxs-lookup"><span data-stu-id="caa9c-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="caa9c-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="caa9c-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="caa9c-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="caa9c-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="caa9c-110">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="caa9c-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="caa9c-111">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="caa9c-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
