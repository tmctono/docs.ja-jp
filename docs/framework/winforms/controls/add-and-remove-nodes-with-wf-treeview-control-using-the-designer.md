---
title: '方法: デザイナーで Windows フォーム TreeView コントロールを使ってノードを追加および削除する'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040072"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="85897-102">方法: デザイナーで Windows フォーム TreeView コントロールを使ってノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="85897-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>

<span data-ttu-id="85897-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールではノードが階層構造で表示されるため、ノードを追加するときは、その親ノードに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85897-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>

<span data-ttu-id="85897-104">次の手順では、 <xref:System.Windows.Forms.TreeView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="85897-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="85897-105">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="85897-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="85897-106">デザイナーでノードを追加または削除するには</span><span class="sxs-lookup"><span data-stu-id="85897-106">To add or remove nodes in the designer</span></span>

1. <span data-ttu-id="85897-107"><xref:System.Windows.Forms.TreeView> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="85897-107">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>

2. <span data-ttu-id="85897-108">**[プロパティ]** ウィンドウで、プロパティの横![に**ある省略記号 (省略**記号ボタン ([...])](./media/visual-studio-ellipsis-button.png)をクリックして、 <xref:System.Windows.Forms.TreeView.Nodes%2A>プロパティの横にある [プロパティウィンドウ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85897-108">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>

     <span data-ttu-id="85897-109">**TreeNode エディター**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="85897-109">The **TreeNode Editor** appears.</span></span>

3. <span data-ttu-id="85897-110">ノードを追加するには、ルートノードが存在している必要があります。存在しない場合は、まず **[ルートの追加]** ボタンをクリックしてルートを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85897-110">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="85897-111">その後、ルートまたは他の任意のノードを選択し、 **[子の追加]** ボタンをクリックして、子ノードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="85897-111">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>

4. <span data-ttu-id="85897-112">ノードを削除するには、削除するノードを選択し、 **[削除]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85897-112">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="85897-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="85897-113">See also</span></span>

- [<span data-ttu-id="85897-114">TreeView コントロール</span><span class="sxs-lookup"><span data-stu-id="85897-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="85897-115">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="85897-115">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="85897-116">方法: Windows フォーム TreeView コントロールのアイコンを設定する</span><span class="sxs-lookup"><span data-stu-id="85897-116">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="85897-117">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="85897-117">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="85897-118">方法: クリックされた TreeView ノードを確認する</span><span class="sxs-lookup"><span data-stu-id="85897-118">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="85897-119">方法: TreeView コントロールまたは ListView コントロールにカスタム情報を追加する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="85897-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
