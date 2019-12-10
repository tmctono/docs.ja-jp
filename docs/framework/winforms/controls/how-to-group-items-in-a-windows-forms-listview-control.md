---
title: '方法 : Windows フォーム ListView コントロールの項目をグループ化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: 1b716498ec5a45fbde499a1f53b2bdccd28a7176
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960160"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="5ee32-102">方法 : Windows フォーム ListView コントロールの項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="5ee32-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="5ee32-103"><xref:System.Windows.Forms.ListView> コントロールのグループ化機能を使用すると、関連する項目のセットをグループに表示できます。</span><span class="sxs-lookup"><span data-stu-id="5ee32-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="5ee32-104">これらのグループは、グループタイトルを含む横方向のグループヘッダーによって画面上で区切られます。</span><span class="sxs-lookup"><span data-stu-id="5ee32-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="5ee32-105"><xref:System.Windows.Forms.ListView> グループを使用すると、項目をアルファベット順、日付順、または他の論理グループ別にグループ化することで、大きなリストを簡単に移動できます。</span><span class="sxs-lookup"><span data-stu-id="5ee32-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="5ee32-106">次の図は、グループ化された項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="5ee32-106">The following image shows some grouped items.</span></span>  
  
 ![奇数および偶数の ListView グループのスクリーンショット。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 <span data-ttu-id="5ee32-108">グループ化を有効にするには、まずデザイナーまたはプログラムを使用して、1つ以上のグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ee32-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="5ee32-109">グループを定義した後、<xref:System.Windows.Forms.ListView> 項目をグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5ee32-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="5ee32-110">プログラムを使用して、あるグループから別のグループに項目を移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ee32-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="5ee32-111">グループを追加するには</span><span class="sxs-lookup"><span data-stu-id="5ee32-111">To add groups</span></span>  
  
1. <span data-ttu-id="5ee32-112"><xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> コレクションの <xref:System.Windows.Forms.ListView.Groups%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ee32-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="5ee32-113">グループを削除するには</span><span class="sxs-lookup"><span data-stu-id="5ee32-113">To remove groups</span></span>  
  
1. <span data-ttu-id="5ee32-114"><xref:System.Windows.Forms.ListView.Groups%2A> コレクションの <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> または <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ee32-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="5ee32-115"><xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> メソッドは、1つのグループを削除します。<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> メソッドは、一覧からすべてのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="5ee32-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5ee32-116">グループを削除しても、そのグループ内の項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="5ee32-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="5ee32-117">グループに項目を割り当てる、またはグループ間で項目を移動するには</span><span class="sxs-lookup"><span data-stu-id="5ee32-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="5ee32-118">個々の項目の <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5ee32-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="5ee32-119">参照</span><span class="sxs-lookup"><span data-stu-id="5ee32-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="5ee32-120">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="5ee32-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="5ee32-121">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="5ee32-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="5ee32-122">方法: Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="5ee32-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
