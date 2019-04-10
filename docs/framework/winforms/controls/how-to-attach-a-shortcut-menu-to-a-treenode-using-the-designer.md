---
title: '方法: デザイナーを使用して TreeNode にショートカット メニューを割り当てる'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 1cc90ed9a103c41dbf85e39a43d307b1c0422603
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191446"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="7ce64-102">方法: デザイナーを使用して TreeNode にショートカット メニューを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7ce64-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="7ce64-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールは、ファイルと Windows オペレーティング システムで Windows エクスプ ローラーの機能の左側のウィンドウに表示されるフォルダーと同様に、ノードの階層を表示します。</span><span class="sxs-lookup"><span data-stu-id="7ce64-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="7ce64-104">設定して、<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>プロパティに提供できる状況依存の操作、ユーザーを右クリックすると、<xref:System.Windows.Forms.TreeView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="7ce64-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="7ce64-105">関連付けることによって、<xref:System.Windows.Forms.ContextMenuStrip>個々 のコンポーネント<xref:System.Windows.Forms.TreeNode>項目のショートカット メニューの機能レベルをカスタマイズを追加することができます、<xref:System.Windows.Forms.TreeView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="7ce64-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ce64-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7ce64-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7ce64-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7ce64-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7ce64-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ce64-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="7ce64-109">デザイン時に TreeNode にショートカット メニューを関連付ける</span><span class="sxs-lookup"><span data-stu-id="7ce64-109">To associate a shortcut menu with a TreeNode at design time</span></span>  
  
1.  <span data-ttu-id="7ce64-110">追加、<xref:System.Windows.Forms.TreeView>をフォームに制御し、ノードを追加し、<xref:System.Windows.Forms.TreeView>に応じて。</span><span class="sxs-lookup"><span data-stu-id="7ce64-110">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="7ce64-111">詳細については、「[方法 :追加し、削除のノードで、Windows フォーム TreeView コントロール](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ce64-111">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>  
  
2.  <span data-ttu-id="7ce64-112">追加、<xref:System.Windows.Forms.ContextMenuStrip>コンポーネントをフォームにし、実行時に使用できるようにするノード レベルの操作を表すショートカット メニューにメニュー項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="7ce64-112">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="7ce64-113">詳細については、「[方法 :メニュー項目を ContextMenuStrip に追加](how-to-add-menu-items-to-a-contextmenustrip.md)します。</span><span class="sxs-lookup"><span data-stu-id="7ce64-113">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>  
  
3.  <span data-ttu-id="7ce64-114">もう一度開きます、 **TreeNodeEditor**の ダイアログ ボックス、<xref:System.Windows.Forms.TreeView>制御で、編集、および設定するノードを選択します。 その<xref:System.Windows.Forms.ContextMenuStrip>プロパティを追加したショートカット メニューを。</span><span class="sxs-lookup"><span data-stu-id="7ce64-114">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>  
  
4.  <span data-ttu-id="7ce64-115">このプロパティが設定されている場合、ノードを右クリックすると、ショートカット メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7ce64-115">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
     <span data-ttu-id="7ce64-116">さらに、処理するコードを記述するが、<xref:System.Windows.Forms.ToolStripItem.Click>これらのメニュー項目のイベント。</span><span class="sxs-lookup"><span data-stu-id="7ce64-116">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce64-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ce64-117">See also</span></span>

- [<span data-ttu-id="7ce64-118">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="7ce64-118">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="7ce64-119">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="7ce64-119">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="7ce64-120">ContextMenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="7ce64-120">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
