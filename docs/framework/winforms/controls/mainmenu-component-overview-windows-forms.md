---
title: MainMenu コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952135"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="be770-102">MainMenu コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="be770-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="be770-103"><xref:System.Windows.Forms.MainMenu> とは、<xref:System.Windows.Forms.ContextMenu>以前のバージョン<xref:System.Windows.Forms.MainMenu>のとのコントロールに置き換えて機能を追加しますが、を選択した場合は、下位互換性と将来の使用の両方で保持されます。<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="be770-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="be770-104">Windows フォーム<xref:System.Windows.Forms.MainMenu>コンポーネントは、実行時にメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="be770-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="be770-105">メインメニューのすべてのサブメニューと個々の<xref:System.Windows.Forms.MenuItem>項目はオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="be770-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="be770-106">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="be770-106">Key Properties</span></span>  
 <span data-ttu-id="be770-107">メニュー項目は、 <xref:System.Windows.Forms.MenuItem.DefaultItem%2A>プロパティをに設定する`true`ことによって、既定の項目として指定できます。</span><span class="sxs-lookup"><span data-stu-id="be770-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="be770-108">メニューがクリックされると、既定の項目が太字で表示されます。</span><span class="sxs-lookup"><span data-stu-id="be770-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="be770-109">メニュー項目の<xref:System.Windows.Forms.MenuItem.Checked%2A>プロパティは、また`true`は`false`のいずれかで、メニュー項目が選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="be770-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="be770-110">メニュー <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>項目のプロパティは、選択した項目の外観をカスタマイズ<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>します。 `true`がに設定されている場合、項目の<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>横にオプション`false`ボタンが表示されます。がに設定されている場合は、項目の横にチェックマークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be770-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be770-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="be770-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="be770-112">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="be770-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
