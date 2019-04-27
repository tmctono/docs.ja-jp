---
title: '方法: GridView を実装する ListView の項目をグループ化する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: b3dd6891976a942b299c87fca25e430e9ee59a51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910274"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="f19af-102">方法: GridView を実装する ListView の項目をグループ化する</span><span class="sxs-lookup"><span data-stu-id="f19af-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="f19af-103">この例では、グループ内の項目の表示、<xref:System.Windows.Controls.GridView>の表示モード、<xref:System.Windows.Controls.ListView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f19af-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f19af-104">例</span><span class="sxs-lookup"><span data-stu-id="f19af-104">Example</span></span>  
 <span data-ttu-id="f19af-105">内の項目のグループを表示する、 <xref:System.Windows.Controls.ListView>、定義、<xref:System.Windows.Data.CollectionViewSource>します。</span><span class="sxs-lookup"><span data-stu-id="f19af-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="f19af-106">次の例は、<xref:System.Windows.Data.CollectionViewSource>の値に基づいてデータ項目をグループ化、`Catalog`データ フィールド。</span><span class="sxs-lookup"><span data-stu-id="f19af-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="f19af-107">次の例のセット、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>の<xref:System.Windows.Controls.ListView>を<xref:System.Windows.Data.CollectionViewSource>前の例を定義します。</span><span class="sxs-lookup"><span data-stu-id="f19af-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="f19af-108">また、<xref:System.Windows.Controls.ItemsControl.GroupStyle%2A>を実装する、<xref:System.Windows.Controls.Expander>コントロール。</span><span class="sxs-lookup"><span data-stu-id="f19af-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="f19af-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="f19af-109">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="f19af-110">方法トピック</span><span class="sxs-lookup"><span data-stu-id="f19af-110">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="f19af-111">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="f19af-111">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="f19af-112">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="f19af-112">GridView Overview</span></span>](gridview-overview.md)
