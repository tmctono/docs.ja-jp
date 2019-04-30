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
ms.openlocfilehash: da1b76a7019f364e7463a8345aa80d9a9bd6089e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012785"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="ed732-102">MainMenu コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ed732-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="ed732-103"><xref:System.Windows.Forms.MenuStrip>と<xref:System.Windows.Forms.ContextMenuStrip>が置換または追加する機能、<xref:System.Windows.Forms.MainMenu>と<xref:System.Windows.Forms.ContextMenu>、以前のバージョン コントロール<xref:System.Windows.Forms.MainMenu>と<xref:System.Windows.Forms.ContextMenu>を選択した場合に、旧バージョンとの互換性と将来の使用のため保持されます。</span><span class="sxs-lookup"><span data-stu-id="ed732-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="ed732-104">Windows フォーム<xref:System.Windows.Forms.MainMenu>コンポーネントには、実行時にメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed732-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="ed732-105">メイン メニューおよび個々 の項目のすべてのサブメニューは<xref:System.Windows.Forms.MenuItem>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed732-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="ed732-106">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="ed732-106">Key Properties</span></span>  
 <span data-ttu-id="ed732-107">メニュー項目は、設定して既定の項目として指定できる、<xref:System.Windows.Forms.MenuItem.DefaultItem%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="ed732-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="ed732-108">メニューをクリックすると、太字のテキストで、既定の項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed732-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="ed732-109">メニュー項目の<xref:System.Windows.Forms.MenuItem.Checked%2A>プロパティが`true`または`false`、メニュー項目が選択されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ed732-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="ed732-110">メニュー項目の<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>プロパティが選択された項目の外観をカスタマイズ: 場合<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>に設定されている`true`場合に、項目の横にあるラジオ ボタンが表示されます<xref:System.Windows.Forms.MenuItem.RadioCheck%2A>に設定されている`false`項目の横にあるチェック マークが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed732-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed732-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed732-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="ed732-112">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="ed732-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
