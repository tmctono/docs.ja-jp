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
ms.openlocfilehash: eb2d75b7c18aa2e65c5e90749852383eea7985b3
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880676"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="89d75-102">方法: Windows フォーム TreeView コントロールのアイコンを設定する</span><span class="sxs-lookup"><span data-stu-id="89d75-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="89d75-103">Windows フォーム<xref:System.Windows.Forms.TreeView>コントロールは、各ノードの横にアイコンを表示できます。</span><span class="sxs-lookup"><span data-stu-id="89d75-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="89d75-104">アイコンは、ノードのテキストのすぐ左に配置されます。</span><span class="sxs-lookup"><span data-stu-id="89d75-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="89d75-105">これらのアイコンを表示するには、ツリー ビューを関連付ける必要があります、<xref:System.Windows.Forms.ImageList>コントロール。</span><span class="sxs-lookup"><span data-stu-id="89d75-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="89d75-106">イメージ リストの詳細については、次を参照してください。 [ImageList コンポーネント](imagelist-component-windows-forms.md)と[方法。追加または削除のイメージで、Windows フォームの ImageList コンポーネント](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="89d75-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89d75-107">Microsoft .NET Framework version 1.1 でのバグが表示されないイメージを防止<xref:System.Windows.Forms.TreeView>ノード アプリケーションが呼び出す<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="89d75-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="89d75-108">このバグを回避するには、呼び出す<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>で、`Main`メソッドをすぐに呼び出して<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>します。</span><span class="sxs-lookup"><span data-stu-id="89d75-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="89d75-109">このバグを修正[!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="89d75-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="89d75-110">ツリー ビューでイメージを表示するには</span><span class="sxs-lookup"><span data-stu-id="89d75-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="89d75-111">設定、<xref:System.Windows.Forms.TreeView>コントロールの<xref:System.Windows.Forms.TreeView.ImageList%2A>プロパティを既存の<xref:System.Windows.Forms.ImageList>を使用するコントロール。</span><span class="sxs-lookup"><span data-stu-id="89d75-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="89d75-112">デザイナーの [プロパティ] ウィンドウまたはコードでは、これらのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="89d75-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="89d75-113">ノードの設定<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>と<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="89d75-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="89d75-114"><xref:System.Windows.Forms.TreeNode.ImageIndex%2A>プロパティは、ノードの標準的な展開の状態に表示されるイメージを決定します。 および<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>プロパティ ノードの選択された状態に表示されるイメージを決定します。</span><span class="sxs-lookup"><span data-stu-id="89d75-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="89d75-115">コードでは、または、TreeNode エディター内で、これらのプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="89d75-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="89d75-116">TreeNode エディターを開くには、省略記号ボタンをクリックします。 ( ![。 Visual Studio の [プロパティ] ウィンドウで、省略記号ボタン (…)](./media/visual-studio-ellipsis-button.png)) 横に、 <xref:System.Windows.Forms.TreeView.Nodes%2A> [プロパティ] ウィンドウのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="89d75-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89d75-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="89d75-117">See also</span></span>

- [<span data-ttu-id="89d75-118">TreeView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="89d75-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="89d75-119">方法: 追加して、Windows フォーム TreeView コントロールでノードを削除</span><span class="sxs-lookup"><span data-stu-id="89d75-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="89d75-120">方法: Windows フォーム TreeView コントロールのすべてのノードを反復処理します。</span><span class="sxs-lookup"><span data-stu-id="89d75-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="89d75-121">方法: クリックしてされた TreeView ノードを決定します。</span><span class="sxs-lookup"><span data-stu-id="89d75-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="89d75-122">方法: TreeView コントロールまたは ListView コントロール (Windows フォーム) にカスタム情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="89d75-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
