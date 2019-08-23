---
title: '方法: Windows フォーム ContextMenu コンポーネントのメニュー項目を追加および削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 5d1862b1fc1398f0f8c2217b51c4efb93db639af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957019"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="c1860-102">方法: Windows フォーム ContextMenu コンポーネントのメニュー項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="c1860-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="c1860-103">Windows フォームでショートカットメニュー項目を追加および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c1860-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="c1860-104">Windows フォーム<xref:System.Windows.Forms.ContextMenu>コンポーネントには、選択したオブジェクトに関連する頻繁に使用するコマンドのメニューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c1860-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="c1860-105"><xref:System.Windows.Forms.MenuItem> オブジェクト<xref:System.Windows.Forms.Menu.MenuItems%2A>をコレクションに追加することで、ショートカットメニューに項目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c1860-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="c1860-106">ショートカットメニューから項目を完全に削除することができます。ただし、実行時には、代わりに項目を非表示にしたり無効にしたりする方が適切な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1860-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c1860-107"><xref:System.Windows.Forms.MainMenu> とは、<xref:System.Windows.Forms.ContextMenu>以前のバージョン<xref:System.Windows.Forms.MainMenu>のとのコントロールに置き換えて機能を追加しますが、を選択した場合は、下位互換性と将来の使用の両方で保持されます。<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="c1860-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="c1860-108">ショートカットメニューから項目を削除するには</span><span class="sxs-lookup"><span data-stu-id="c1860-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="c1860-109">特定のメニュー <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A>項目を削除<xref:System.Windows.Forms.Menu.MenuItems%2A>するに<xref:System.Windows.Forms.ContextMenu>は、コンポーネントのコレクションのメソッドまたはメソッドを使用します。 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="c1860-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="c1860-110">\- または -</span><span class="sxs-lookup"><span data-stu-id="c1860-110">-or-</span></span>  
  
2. <span data-ttu-id="c1860-111">コンポーネントの`MenuItems`コレクションのメソッドを使用して、メニューからすべての項目を削除します。 `Clear` <xref:System.Windows.Forms.ContextMenu></span><span class="sxs-lookup"><span data-stu-id="c1860-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c1860-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1860-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="c1860-113">ContextMenu コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c1860-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="c1860-114">ContextMenu コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="c1860-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
