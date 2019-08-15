---
title: '方法: デザイナーを使用して ToolStripMenuItems を無効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: fd80a6543c83ae957cd9c51b068d0702559f0925
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040273"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="31895-102">方法: デザイナーを使用して ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="31895-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="31895-103">ユーザーの操作に応じてメニュー項目を有効または無効にすることによって、ユーザーが実行できるコマンドを制限または拡大できます。</span><span class="sxs-lookup"><span data-stu-id="31895-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="31895-104">メニュー項目は、作成時に既定で有効になりますが、プロパティを<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>使用して調整できます。</span><span class="sxs-lookup"><span data-stu-id="31895-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="31895-105">このプロパティは、デザイン時に **[プロパティ]** ウィンドウで操作することも、コードで設定することによってプログラムで操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="31895-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="31895-106">詳細については、「[方法 :ToolStripMenuItems](how-to-disable-toolstripmenuitems.md)を無効にします。</span><span class="sxs-lookup"><span data-stu-id="31895-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="31895-107">デザイン時にメニュー項目を無効にするには</span><span class="sxs-lookup"><span data-stu-id="31895-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="31895-108">フォームでメニュー項目を選択した状態で、 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>プロパティを`false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="31895-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    >  <span data-ttu-id="31895-109">メニューの1つ目または最上位レベルのメニュー項目を無効にすると、メニュー内に含まれるすべてのメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="31895-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="31895-110">同様に、サブメニュー項目を含むメニュー項目を無効にすると、サブメニュー項目が無効になります。</span><span class="sxs-lookup"><span data-stu-id="31895-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="31895-111">特定のメニューのすべてのコマンドをユーザーが使用できない場合は、そのメニュー全体を非表示にして無効にすることをお勧めします。これにより、クリーンなユーザーインターフェイスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="31895-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="31895-112">非表示にすると、ショートカットキーを使用してメニューコマンドにアクセスできなくなるため、メニューを非表示にしたり無効にしたりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31895-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="31895-113">トップレベルメニュー項目の`false` プロパティをに設定すると、メニュー全体が非表示になります。<xref:System.Windows.Forms.ToolStripItem.Visible%2A></span><span class="sxs-lookup"><span data-stu-id="31895-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="31895-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="31895-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="31895-115">方法: ToolStripMenuItems の非表示</span><span class="sxs-lookup"><span data-stu-id="31895-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="31895-116">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="31895-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
