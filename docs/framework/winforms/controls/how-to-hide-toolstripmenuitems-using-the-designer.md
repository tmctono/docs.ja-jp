---
title: '方法: デザイナーを使用して ToolStripMenuItems を非表示にする'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 31c597a0e2cbf41484f19c8d4179823e9fb929ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317676"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="da437-102">方法: デザイナーを使用して ToolStripMenuItems を非表示にする</span><span class="sxs-lookup"><span data-stu-id="da437-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="da437-103">メニュー項目を非表示には、アプリケーションのユーザー インターフェイス (UI) を制御し、ユーザーのコマンドを制限する方法です。</span><span class="sxs-lookup"><span data-stu-id="da437-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="da437-104">多くの場合、すべてのメニュー項目が利用できない場合は、メニュー全体を非表示にするされます。</span><span class="sxs-lookup"><span data-stu-id="da437-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="da437-105">これは、ユーザーの混乱を表示します。</span><span class="sxs-lookup"><span data-stu-id="da437-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="da437-106">さらに、非表示だけでは、ユーザーはショートカット キーを使用してメニュー コマンドへのアクセスを非表示にして、メニューまたはメニュー項目を無効にする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da437-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="da437-107">メニュー項目を無効にする方法の詳細については、次を参照してください。[方法。デザイナーを使用して ToolStripMenuItems を無効にする](how-to-disable-toolstripmenuitems-using-the-designer.md)します。</span><span class="sxs-lookup"><span data-stu-id="da437-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da437-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da437-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="da437-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da437-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="da437-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da437-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="da437-111">トップレベル メニューとサブメニュー項目を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="da437-111">To hide a top-level menu and its submenu items</span></span>  
  
1. <span data-ttu-id="da437-112">トップレベルのメニュー項目を選択し、設定、<xref:System.Windows.Forms.ToolStripItem.Visible%2A>または<xref:System.Windows.Forms.ToolStripItem.Available%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="da437-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="da437-113">トップレベルのメニュー項目を非表示にすると、そのメニュー内のすべてのメニュー項目でも非表示します。</span><span class="sxs-lookup"><span data-stu-id="da437-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="da437-114">以外の場所をクリックすると、<xref:System.Windows.Forms.MenuStrip>設定後<xref:System.Windows.Forms.ToolStripItem.Visible%2A>に`false`、操作の実行時の効果を示すため、フォームから、全体の最上位メニュー項目とサブメニュー項目が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="da437-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="da437-115">デザイン時に非表示の最上位メニュー項目を表示する をクリックして、<xref:System.Windows.Forms.MenuStrip>で、**コンポーネント トレイ**の**ドキュメント アウトライン**、またはプロパティ グリッドの上部にあります。</span><span class="sxs-lookup"><span data-stu-id="da437-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da437-116">複数のドキュメント インターフェイス (MDI) 子メニューにマージする場合を除くメニュー全体を非表示にはことはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="da437-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="da437-117">サブメニュー項目を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="da437-117">To hide a submenu item</span></span>  
  
1. <span data-ttu-id="da437-118">サブメニュー項目を選択し、設定、<xref:System.Windows.Forms.ToolStripItem.Visible%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="da437-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="da437-119">サブメニュー項目を非表示にするときにそのまま表示デザイン時にフォーム上の作業をさらに簡単に選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="da437-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="da437-120">実行時に実際には表示されません。</span><span class="sxs-lookup"><span data-stu-id="da437-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da437-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="da437-121">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="da437-122">MenuStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="da437-122">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="da437-123">方法: デザイナーを使用して ToolStripMenuItems を無効にします。</span><span class="sxs-lookup"><span data-stu-id="da437-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
