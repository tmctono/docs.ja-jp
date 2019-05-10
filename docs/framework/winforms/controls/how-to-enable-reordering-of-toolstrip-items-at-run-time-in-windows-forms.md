---
title: '方法: Windows フォームでの実行時に ToolStrip 項目を並べ替えを有効にします。'
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
ms.openlocfilehash: 46a5a70206e7620341a484912c7fada82d64747a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609848"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="fca6a-102">方法: Windows フォームでの実行時に ToolStrip 項目を並べ替えを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fca6a-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="fca6a-103">再配置するユーザーを有効にすることができます<xref:System.Windows.Forms.ToolStripItem>のコントロールに対して、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="fca6a-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="fca6a-104">実行時に ToolStripItem 再配置を有効にするには</span><span class="sxs-lookup"><span data-stu-id="fca6a-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
- <span data-ttu-id="fca6a-105"><xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fca6a-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="fca6a-106">既定では、<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>は`false`します。</span><span class="sxs-lookup"><span data-stu-id="fca6a-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="fca6a-107">ALT キーを押しながらマウスの左ボタンをドラッグする、実行時にユーザーを保持して、<xref:System.Windows.Forms.ToolStripItem>で別の場所に、<xref:System.Windows.Forms.ToolStrip>します。</span><span class="sxs-lookup"><span data-stu-id="fca6a-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fca6a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="fca6a-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="fca6a-109">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="fca6a-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="fca6a-110">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="fca6a-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="fca6a-111">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="fca6a-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
