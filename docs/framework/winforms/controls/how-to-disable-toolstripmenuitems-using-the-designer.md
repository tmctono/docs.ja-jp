---
title: '方法: デザイナーを使用して ToolStripMenuItems を無効にする'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 9965825458afcd50b29699c3b89ed506078e04d9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338060"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="2a1ca-102">方法: デザイナーを使用して ToolStripMenuItems を無効にする</span><span class="sxs-lookup"><span data-stu-id="2a1ca-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="2a1ca-103">制限またはユーザーが実行を有効にして、ユーザーのアクティビティへの応答でのメニュー項目を無効にすると、コマンドの範囲を広げることができます。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="2a1ca-104">これらが作成されますが、これで調整時にメニュー項目が既定で有効に、<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="2a1ca-105">デザイン時にこのプロパティを操作することができます、**プロパティ**ウィンドウまたはプログラムによってコードで設定します。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="2a1ca-106">詳細については、「[方法 :ToolStripMenuItems を無効にする](how-to-disable-toolstripmenuitems.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a1ca-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2a1ca-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2a1ca-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="2a1ca-110">デザイン時にメニュー項目を無効にするには</span><span class="sxs-lookup"><span data-stu-id="2a1ca-110">To disable a menu item at design time</span></span>  
  
1. <span data-ttu-id="2a1ca-111">フォームで選択されたメニュー項目を設定、<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2a1ca-112">メニューの最初または最上位のメニュー項目を無効にするには、メニュー内に含まれるすべてのメニュー項目が無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="2a1ca-113">同様に、サブメニュー項目を持つメニュー項目を無効にするには、項目のサブメニュー項目が無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="2a1ca-114">指定されたメニューのすべてのコマンドがユーザーに使用可能な場合は、これは、ユーザー インターフェイスを簡潔に非表示にして、メニュー全体を無効にすることをお勧めプログラミングと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="2a1ca-115">非表示にする必要があり、単独で非表示がショートカット キーを使用してメニュー コマンドにアクセスを妨げないもの、メニューを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="2a1ca-116">設定、<xref:System.Windows.Forms.ToolStripItem.Visible%2A>トップレベルのメニュー項目のプロパティ`false`メニュー全体を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1ca-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a1ca-117">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="2a1ca-118">方法: ToolStripMenuItems を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="2a1ca-118">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="2a1ca-119">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2a1ca-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
