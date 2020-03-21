---
title: ツリー ビュー コントロールを使用したノードの追加と削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142213"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="564b9-102">方法 : Windows フォーム TreeView コントロールでノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="564b9-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="564b9-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールは、最上位のノードを<xref:System.Windows.Forms.TreeView.Nodes%2A>コレクションに格納します。</span><span class="sxs-lookup"><span data-stu-id="564b9-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="564b9-104">また<xref:System.Windows.Forms.TreeNode>、子ノードを<xref:System.Windows.Forms.TreeNode.Nodes%2A>格納する独自のコレクションも用意されています。</span><span class="sxs-lookup"><span data-stu-id="564b9-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="564b9-105">どちらのコレクション プロパティも<xref:System.Windows.Forms.TreeNodeCollection>type で、ノード階層の単一レベルでノードを追加、削除、および再配置できる標準コレクション メンバーを提供します。</span><span class="sxs-lookup"><span data-stu-id="564b9-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="564b9-106">プログラムでノードを追加するには</span><span class="sxs-lookup"><span data-stu-id="564b9-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="564b9-107">ツリー<xref:System.Windows.Forms.TreeNodeCollection.Add%2A>ビューのプロパティの<xref:System.Windows.Forms.TreeView.Nodes%2A>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="564b9-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="564b9-108">プログラムによってノードを削除するには</span><span class="sxs-lookup"><span data-stu-id="564b9-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="564b9-109">ツリー<xref:System.Windows.Forms.TreeNodeCollection.Remove%2A>ビューのプロパティのメソッドを使用<xref:System.Windows.Forms.TreeView.Nodes%2A>して単一のノードを削除するか、<xref:System.Windows.Forms.TreeNodeCollection.Clear%2A>すべてのノードをクリアするメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="564b9-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="564b9-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="564b9-110">See also</span></span>

- [<span data-ttu-id="564b9-111">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="564b9-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="564b9-112">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="564b9-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="564b9-113">方法: Windows フォーム TreeView コントロールのアイコンを設定する</span><span class="sxs-lookup"><span data-stu-id="564b9-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="564b9-114">方法 : Windows フォーム TreeView コントロールのすべてのノードを反復処理する</span><span class="sxs-lookup"><span data-stu-id="564b9-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="564b9-115">方法 : クリックされた TreeView ノードを判別する</span><span class="sxs-lookup"><span data-stu-id="564b9-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="564b9-116">方法 : TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加する</span><span class="sxs-lookup"><span data-stu-id="564b9-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
