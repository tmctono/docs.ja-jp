---
title: ContextMenuStrip コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962158"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="c03cf-102">ContextMenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="c03cf-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="c03cf-103">コントロールは、コントロール<xref:System.Windows.Forms.ContextMenu>に置き換えられ、機能が追加さ<xref:System.Windows.Forms.ContextMenu>れます。ただし、コントロールは旧バージョンとの互換性を維持するために残されています。 <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="c03cf-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="c03cf-104">ショートカットメニュー (コンテキストメニューとも呼ばれます) は、ユーザーがマウスの右ボタンをクリックしたときにマウスの位置に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c03cf-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="c03cf-105">ショートカット*メニュー*では、クライアント領域またはマウスポインターの位置にあるコントロールのオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c03cf-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="c03cf-106">コントロールは、新しい<xref:System.Windows.Forms.ToolStrip>および関連するコントロールとシームレスに連携するように設計されて<xref:System.Windows.Forms.ContextMenuStrip>いますが、他のコントロールとも簡単に関連付けることができます。 <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="c03cf-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="c03cf-107">次の表は、重要<xref:System.Windows.Forms.ContextMenuStrip>な関連クラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="c03cf-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="c03cf-108">クラス</span><span class="sxs-lookup"><span data-stu-id="c03cf-108">Class</span></span>|<span data-ttu-id="c03cf-109">説明</span><span class="sxs-lookup"><span data-stu-id="c03cf-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="c03cf-110"><xref:System.Windows.Forms.MenuStrip>または<xref:System.Windows.Forms.ContextMenuStrip>に表示される選択可能なオプションを表します。</span><span class="sxs-lookup"><span data-stu-id="c03cf-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="c03cf-111">ユーザーが<xref:System.Windows.Forms.ToolStripDropDownButton>または上位レベルのメニュー項目をクリックしたときに表示される一覧から1つの項目を選択できるようにするコントロールを表します。</span><span class="sxs-lookup"><span data-stu-id="c03cf-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="c03cf-112">クリックしたときに表示さ<xref:System.Windows.Forms.ToolStripItem>れるドロップダウン項目から派生したコントロールの基本機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c03cf-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c03cf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c03cf-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
