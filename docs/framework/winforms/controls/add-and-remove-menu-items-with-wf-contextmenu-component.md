---
title: ContextMenu コンポーネントを使用したメニュー項目の追加と削除
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
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746268"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="42c13-102">方法 : Windows フォーム ContextMenu コンポーネントのメニュー項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="42c13-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="42c13-103">Windows フォームでショートカットメニュー項目を追加および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c13-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="42c13-104">Windows フォーム <xref:System.Windows.Forms.ContextMenu> コンポーネントには、選択したオブジェクトに関連する頻繁に使用するコマンドのメニューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="42c13-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="42c13-105"><xref:System.Windows.Forms.MenuItem> オブジェクトを <xref:System.Windows.Forms.Menu.MenuItems%2A> コレクションに追加することで、ショートカットメニューに項目を追加できます。</span><span class="sxs-lookup"><span data-stu-id="42c13-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="42c13-106">ショートカットメニューから項目を完全に削除することができます。ただし、実行時には、代わりに項目を非表示にしたり無効にしたりする方が適切な場合があります。</span><span class="sxs-lookup"><span data-stu-id="42c13-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="42c13-107"><xref:System.Windows.Forms.MenuStrip> と <xref:System.Windows.Forms.ContextMenuStrip> によって、以前のバージョンの <xref:System.Windows.Forms.MainMenu> および <xref:System.Windows.Forms.ContextMenu> のコントロールに置き換えられ、機能が追加されますが、<xref:System.Windows.Forms.MainMenu> と <xref:System.Windows.Forms.ContextMenu> は下位互換性と将来の使用の両方のために保持されます。</span><span class="sxs-lookup"><span data-stu-id="42c13-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="42c13-108">ショートカットメニューから項目を削除するには</span><span class="sxs-lookup"><span data-stu-id="42c13-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="42c13-109"><xref:System.Windows.Forms.ContextMenu> コンポーネントの <xref:System.Windows.Forms.Menu.MenuItems%2A> コレクションの <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> または <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> メソッドを使用して、特定のメニュー項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="42c13-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
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
  
     <span data-ttu-id="42c13-110">または</span><span class="sxs-lookup"><span data-stu-id="42c13-110">-or-</span></span>  
  
2. <span data-ttu-id="42c13-111"><xref:System.Windows.Forms.ContextMenu> コンポーネントの `MenuItems` コレクションの `Clear` メソッドを使用して、メニューからすべての項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="42c13-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="42c13-112">参照</span><span class="sxs-lookup"><span data-stu-id="42c13-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="42c13-113">ContextMenu コンポーネント</span><span class="sxs-lookup"><span data-stu-id="42c13-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="42c13-114">ContextMenu コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="42c13-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
