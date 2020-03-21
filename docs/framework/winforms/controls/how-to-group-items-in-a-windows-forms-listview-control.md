---
title: リストビュー コントロールのアイテムをグループ化する
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
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141992"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="518e4-102">方法 : Windows フォーム ListView コントロールの項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="518e4-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="518e4-103">コントロールのグループ化機能を<xref:System.Windows.Forms.ListView>使用すると、関連する項目セットをグループに表示できます。</span><span class="sxs-lookup"><span data-stu-id="518e4-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="518e4-104">これらのグループは、グループ タイトルを含む水平方向のグループ ヘッダーによって画面上で区切られます。</span><span class="sxs-lookup"><span data-stu-id="518e4-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="518e4-105">グループを使用<xref:System.Windows.Forms.ListView>すると、項目をアルファベット順、日付順、またはその他の論理的なグループ分けによってグループ化することで、大きなリストの移動を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="518e4-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="518e4-106">次の図は、いくつかのグループ化された項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="518e4-106">The following image shows some grouped items.</span></span>  
  
 ![奇数および偶数のリストビュー グループのスクリーンショット。](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 <span data-ttu-id="518e4-108">グループ化を有効にするには、まずデザイナーまたはプログラムで 1 つ以上のグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="518e4-108">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="518e4-109">グループを定義した後、グループにアイテムを<xref:System.Windows.Forms.ListView>割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="518e4-109">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="518e4-110">また、プログラムによって、あるグループから別のグループに項目を移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="518e4-110">You can also move items from one group to another programmatically.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="518e4-111">グループを追加するには</span><span class="sxs-lookup"><span data-stu-id="518e4-111">To add groups</span></span>  
  
1. <span data-ttu-id="518e4-112"><xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> コレクションの <xref:System.Windows.Forms.ListView.Groups%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="518e4-112">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="518e4-113">グループを削除するには</span><span class="sxs-lookup"><span data-stu-id="518e4-113">To remove groups</span></span>  
  
1. <span data-ttu-id="518e4-114">コレクションの<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> or メソッド<xref:System.Windows.Forms.ListView.Groups%2A>を使用します。</span><span class="sxs-lookup"><span data-stu-id="518e4-114">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="518e4-115">この<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>メソッドは、1 つのグループを削除します。メソッド<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>は、リストからすべてのグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="518e4-115">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="518e4-116">グループを削除しても、そのグループ内の項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="518e4-116">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="518e4-117">グループにアイテムを割り当てるか、グループ間でアイテムを移動するには</span><span class="sxs-lookup"><span data-stu-id="518e4-117">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="518e4-118">個々の<xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>項目のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="518e4-118">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="518e4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="518e4-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="518e4-120">ListView コントロール</span><span class="sxs-lookup"><span data-stu-id="518e4-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="518e4-121">ListView コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="518e4-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="518e4-122">方法 : Windows フォーム ListView コントロールで項目を追加および削除する</span><span class="sxs-lookup"><span data-stu-id="518e4-122">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
