---
title: '方法: TreeView での TreeViewItem の検索'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
ms.openlocfilehash: ad72c7a7fb11dfe605db4119dde831b47dd7c5a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962090"
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="aa68a-102">方法: TreeView での TreeViewItem の検索</span><span class="sxs-lookup"><span data-stu-id="aa68a-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="aa68a-103">コントロール<xref:System.Windows.Controls.TreeView>は、階層データを表示する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa68a-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="aa68a-104">がデータソースにバインドされている場合<xref:System.Windows.Controls.TreeView.SelectedItem%2A> 、プロパティは、選択したデータオブジェクトを迅速に取得するための便利な方法を提供します。 <xref:System.Windows.Controls.TreeView></span><span class="sxs-lookup"><span data-stu-id="aa68a-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="aa68a-105">通常は、基になるデータオブジェクトを操作することをお勧めします。ただし、を含む<xref:System.Windows.Controls.TreeViewItem>データをプログラムで操作することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa68a-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="aa68a-106">たとえば、プログラムを使用して<xref:System.Windows.Controls.TreeViewItem>を展開したり、 <xref:System.Windows.Controls.TreeView>で別の項目を選択したりする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa68a-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="aa68a-107">特定のデータ<xref:System.Windows.Controls.TreeViewItem>オブジェクトを含むを検索するには、 <xref:System.Windows.Controls.TreeView>の各レベルを走査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa68a-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="aa68a-108">の項目を仮想<xref:System.Windows.Controls.TreeView>化して、パフォーマンスを向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="aa68a-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="aa68a-109">項目が仮想化される可能性がある場合は、を<xref:System.Windows.Controls.TreeViewItem>認識してデータオブジェクトが含まれているかどうかを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="aa68a-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa68a-110">例</span><span class="sxs-lookup"><span data-stu-id="aa68a-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="aa68a-111">説明</span><span class="sxs-lookup"><span data-stu-id="aa68a-111">Description</span></span>  
 <span data-ttu-id="aa68a-112">次の例では<xref:System.Windows.Controls.TreeView> 、特定のオブジェクトを検索し、それを<xref:System.Windows.Controls.TreeViewItem>含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="aa68a-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="aa68a-113">この例では、 <xref:System.Windows.Controls.TreeViewItem>子項目を検索できるように、各がインスタンス化されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aa68a-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="aa68a-114">この例は、が仮想<xref:System.Windows.Controls.TreeView>化された項目を使用しない場合にも機能します。</span><span class="sxs-lookup"><span data-stu-id="aa68a-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa68a-115">次の例では、 <xref:System.Windows.Controls.TreeView>基になるデータモデルに関係なく、すべての<xref:System.Windows.Controls.TreeViewItem>に対して機能し、オブジェクトが見つかるまではすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="aa68a-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="aa68a-116">パフォーマンスが向上するもう1つの方法は、指定されたオブジェクトのデータモデルを検索し、データ階層内での位置を追跡し<xref:System.Windows.Controls.TreeViewItem> 、 <xref:System.Windows.Controls.TreeView>で対応するを見つけることです。</span><span class="sxs-lookup"><span data-stu-id="aa68a-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="aa68a-117">ただし、パフォーマンスが優れている手法では、データモデルに関する知識が必要であり、 <xref:System.Windows.Controls.TreeView>特定のに対して一般化することはできません。</span><span class="sxs-lookup"><span data-stu-id="aa68a-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="aa68a-118">コード</span><span class="sxs-lookup"><span data-stu-id="aa68a-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="aa68a-119">前のコードは、という<xref:System.Windows.Controls.VirtualizingStackPanel>名前`BringIntoView`のメソッドを公開するカスタムに依存しています。</span><span class="sxs-lookup"><span data-stu-id="aa68a-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="aa68a-120">次のコードは、カスタム<xref:System.Windows.Controls.VirtualizingStackPanel>を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa68a-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="aa68a-121">次の XAML は、カスタム<xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.VirtualizingStackPanel>を使用するを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aa68a-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="aa68a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa68a-122">See also</span></span>

- [<span data-ttu-id="aa68a-123">TreeView のパフォーマンスを改善する</span><span class="sxs-lookup"><span data-stu-id="aa68a-123">Improve the Performance of a TreeView</span></span>](how-to-improve-the-performance-of-a-treeview.md)
