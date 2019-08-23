---
title: '方法: Windows フォーム TreeView コントロールのアイコンを設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909806"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="4ca9a-102">方法: Windows フォーム TreeView コントロールのアイコンを設定する</span><span class="sxs-lookup"><span data-stu-id="4ca9a-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="4ca9a-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールでは、各ノードの横にアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="4ca9a-104">アイコンがノードテキストのすぐ左に配置されます。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="4ca9a-105">これらのアイコンを表示するには、ツリービューを<xref:System.Windows.Forms.ImageList>コントロールに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="4ca9a-106">イメージリストの詳細については、「 [ImageList コンポーネント](imagelist-component-windows-forms.md)」および[「方法:Windows フォーム ImageList コンポーネント](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)を使用してイメージを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ca9a-107">Microsoft .NET Framework バージョン1.1 のバグにより、アプリケーションがを<xref:System.Windows.Forms.TreeView>呼び出す<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>ときに、イメージがノードに表示されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4ca9a-108">このバグを回避するには<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 、を`Main`呼び出し<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>た直後にメソッドでを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="4ca9a-109">このバグは .NET Framework 2.0 で修正されています。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-109">This bug is fixed in .NET Framework 2.0.</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="4ca9a-110">ツリービューでイメージを表示するには</span><span class="sxs-lookup"><span data-stu-id="4ca9a-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="4ca9a-111">コントロールの<xref:System.Windows.Forms.TreeView.ImageList%2A>プロパティを、使用する既存<xref:System.Windows.Forms.ImageList>のコントロールに設定します。 <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="4ca9a-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="4ca9a-112">これらのプロパティは、デザイナーでプロパティウィンドウまたはコードで設定できます。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="4ca9a-113">ノードの<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>プロパティと<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="4ca9a-114">プロパティ<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>は、ノードの通常の状態と展開された状態に表示さ<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>れるイメージを決定し、プロパティはノードの選択された状態に表示されるイメージを決定します。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="4ca9a-115">これらのプロパティは、コードで設定することも、TreeNode エディター内で設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="4ca9a-116">TreeNode エディターを開くには、プロパティウィンドウのプロパティの![ <xref:System.Windows.Forms.TreeView.Nodes%2A>横にある省略記号ボタン ([...] プロパティウィンドウ](./media/visual-studio-ellipsis-button.png)) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4ca9a-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ca9a-117">See also</span></span>

- [<span data-ttu-id="4ca9a-118">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4ca9a-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="4ca9a-119">方法: Windows フォーム TreeView コントロールを使用してノードを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="4ca9a-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="4ca9a-120">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="4ca9a-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="4ca9a-121">方法: クリックされた TreeView ノードを確認する</span><span class="sxs-lookup"><span data-stu-id="4ca9a-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="4ca9a-122">方法: TreeView コントロールまたは ListView コントロールにカスタム情報を追加する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="4ca9a-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
