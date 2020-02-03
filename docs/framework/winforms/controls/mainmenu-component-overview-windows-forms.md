---
title: MainMenu コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745116"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="c8ae6-102">MainMenu コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="c8ae6-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="c8ae6-103"><xref:System.Windows.Forms.MenuStrip> と <xref:System.Windows.Forms.ContextMenuStrip> によって、以前のバージョンの <xref:System.Windows.Forms.MainMenu> および <xref:System.Windows.Forms.ContextMenu> のコントロールに置き換えられ、機能が追加されますが、<xref:System.Windows.Forms.MainMenu> と <xref:System.Windows.Forms.ContextMenu> は下位互換性と将来の使用の両方のために保持されます。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="c8ae6-104">Windows フォーム <xref:System.Windows.Forms.MainMenu> コンポーネントは、実行時にメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="c8ae6-105">メインメニューのすべてのサブメニューと個々の項目は <xref:System.Windows.Forms.MenuItem> オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="c8ae6-106">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="c8ae6-106">Key Properties</span></span>  
 <span data-ttu-id="c8ae6-107">メニュー項目を既定の項目として指定するには、[<xref:System.Windows.Forms.MenuItem.DefaultItem%2A>] プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="c8ae6-108">メニューがクリックされると、既定の項目が太字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="c8ae6-109">メニュー項目の <xref:System.Windows.Forms.MenuItem.Checked%2A> プロパティは `true` または `false`のいずれかで、メニュー項目が選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="c8ae6-110">メニュー項目の <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> プロパティによって、選択した項目の外観がカスタマイズされます。 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> が `true`に設定されている場合は、項目の横にラジオボタンが表示されます。<xref:System.Windows.Forms.MenuItem.RadioCheck%2A> が `false`に設定されている場合は、項目の横にチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c8ae6-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ae6-111">参照</span><span class="sxs-lookup"><span data-stu-id="c8ae6-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="c8ae6-112">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="c8ae6-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
