---
title: '方法: ショートカット メニューを TreeView ノードに追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: f818cccb3103866af993f1aff527a9c1a7c82109
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294174"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="41fd7-102">方法: ショートカット メニューを TreeView ノードに追加する</span><span class="sxs-lookup"><span data-stu-id="41fd7-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="41fd7-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールは、ファイルと Windows エクスプ ローラーの左側のウィンドウに表示されるフォルダーと同様に、ノードの階層を表示します。</span><span class="sxs-lookup"><span data-stu-id="41fd7-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="41fd7-104">設定して、<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>プロパティに提供できる状況依存の操作、ユーザーを右クリックすると、<xref:System.Windows.Forms.TreeView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="41fd7-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="41fd7-105">関連付けることによって、<xref:System.Windows.Forms.ContextMenuStrip>個々 のコンポーネント<xref:System.Windows.Forms.TreeNode>項目のショートカット メニューの機能レベルをカスタマイズを追加することができます、<xref:System.Windows.Forms.TreeView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="41fd7-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="41fd7-106">プログラムで TreeNode にショートカット メニューを関連付ける</span><span class="sxs-lookup"><span data-stu-id="41fd7-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1. <span data-ttu-id="41fd7-107">インスタンスを作成、<xref:System.Windows.Forms.TreeView>適切なプロパティの設定で制御する、ルートを作成<xref:System.Windows.Forms.TreeNode>サブノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="41fd7-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2. <span data-ttu-id="41fd7-108">インスタンスを作成、<xref:System.Windows.Forms.ContextMenuStrip>コンポーネント、し、追加、<xref:System.Windows.Forms.ToolStripMenuItem>の各操作の実行時に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="41fd7-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3. <span data-ttu-id="41fd7-109">設定、 <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> 、適切なプロパティ<xref:System.Windows.Forms.TreeNode>を作成するショートカット メニューにします。</span><span class="sxs-lookup"><span data-stu-id="41fd7-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4. <span data-ttu-id="41fd7-110">このプロパティが設定されている場合、ノードを右クリックすると、ショートカット メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41fd7-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="41fd7-111">次のコード例は、基本的なを作成します。<xref:System.Windows.Forms.TreeView>と<xref:System.Windows.Forms.ContextMenuStrip>ルートに関連付けられている<xref:System.Windows.Forms.TreeNode>の、<xref:System.Windows.Forms.TreeView>します。</span><span class="sxs-lookup"><span data-stu-id="41fd7-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="41fd7-112">メニューの選択肢に合わせてカスタマイズする必要があります、<xref:System.Windows.Forms.TreeView>を開発しています。</span><span class="sxs-lookup"><span data-stu-id="41fd7-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="41fd7-113">さらに、処理するコードを記述するが、<xref:System.Windows.Forms.ToolStripItem.Click>これらのメニュー項目のイベント。</span><span class="sxs-lookup"><span data-stu-id="41fd7-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="41fd7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="41fd7-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="41fd7-115">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="41fd7-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
