---
title: '方法: ToolStripMenuItems を無効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: a480cd29eef1a79a69f702eed7cd02c28d7ea3de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954228"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="528a8-102">方法: ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="528a8-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="528a8-103">制限またはユーザーが実行を有効にして、ユーザーのアクティビティへの応答でのメニュー項目を無効にすると、コマンドの範囲を広げることができます。</span><span class="sxs-lookup"><span data-stu-id="528a8-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="528a8-104">これらが作成されますが、これで調整時にメニュー項目が既定で有効に、<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="528a8-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="528a8-105">デザイン時にこのプロパティを操作することができます、**プロパティ**ウィンドウまたはプログラムによってコードで設定します。</span><span class="sxs-lookup"><span data-stu-id="528a8-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="528a8-106">メニュー項目をプログラムで無効にするには</span><span class="sxs-lookup"><span data-stu-id="528a8-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="528a8-107">メニュー項目のプロパティを設定するメソッド内で設定するコードを追加、<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="528a8-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="528a8-108">メニューの最初または最上位のメニュー項目を無効にすると、メニュー内に含まれるすべてのメニュー項目を非表示になりますが、それらを無効にしません。</span><span class="sxs-lookup"><span data-stu-id="528a8-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="528a8-109">同様に、サブメニュー項目を持つメニュー項目を無効にする項目のサブメニュー項目を非表示になりますが、それらを無効にしません。</span><span class="sxs-lookup"><span data-stu-id="528a8-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="528a8-110">指定されたメニューのすべてのコマンドがユーザーに使用可能な場合は、これは、ユーザー インターフェイスを簡潔に非表示にして、メニュー全体を無効にすることをお勧めプログラミングと見なされます。</span><span class="sxs-lookup"><span data-stu-id="528a8-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="528a8-111">非表示にして、メニューを無効にして、単独で非表示にしてもアクセスするショートカット キーを使用してメニュー コマンドのために、すべてのアイテムと、メニューのサブメニュー項目を無効にするください。</span><span class="sxs-lookup"><span data-stu-id="528a8-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="528a8-112">設定、<xref:System.Windows.Forms.ToolStripItem.Visible%2A>トップレベルのメニュー項目のプロパティ`false`メニュー全体を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="528a8-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528a8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="528a8-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="528a8-114">方法: ToolStripMenuItems を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="528a8-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="528a8-115">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="528a8-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
