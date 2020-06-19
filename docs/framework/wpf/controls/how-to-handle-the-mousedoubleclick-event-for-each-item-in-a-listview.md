---
title: '方法: ListView の各項目の MouseDoubleClick イベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646108"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="a0c0e-102">方法: ListView の各項目の MouseDoubleClick イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="a0c0e-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="a0c0e-103"><xref:System.Windows.Controls.ListView> 内の項目に対するイベントを処理するには、各 <xref:System.Windows.Controls.ListViewItem> にイベント ハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0c0e-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="a0c0e-104"><xref:System.Windows.Controls.ListView> がデータ ソースにバインドされている場合は、<xref:System.Windows.Controls.ListViewItem> を明示的には作成しませんが、<xref:System.Windows.Controls.ListViewItem> のスタイルに <xref:System.Windows.EventSetter> を追加することで、各項目のイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="a0c0e-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0c0e-105">例</span><span class="sxs-lookup"><span data-stu-id="a0c0e-105">Example</span></span>  
 <span data-ttu-id="a0c0e-106">次の例では、データ バインドされた <xref:System.Windows.Controls.ListView> を作成し、<xref:System.Windows.Style> を作成して、各 <xref:System.Windows.Controls.ListViewItem> にイベント ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0c0e-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="a0c0e-107">次の例では、<xref:System.Windows.Controls.Control.MouseDoubleClick> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="a0c0e-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="a0c0e-108"><xref:System.Windows.Controls.ListView> をデータ ソースにバインドするのが最も一般的ですが、<xref:System.Windows.Controls.ListViewItem> を明示的に作成するかどうかにかかわらず、スタイルを使用することで、データ バインドされていない <xref:System.Windows.Controls.ListView> の各 <xref:System.Windows.Controls.ListViewItem> にイベント ハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a0c0e-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="a0c0e-109"><xref:System.Windows.Controls.ListViewItem> コントロールの明示的および暗黙的な作成の詳細については、<xref:System.Windows.Controls.ItemsControl> に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c0e-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c0e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0c0e-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="a0c0e-111">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="a0c0e-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a0c0e-112">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="a0c0e-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a0c0e-113">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="a0c0e-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="a0c0e-114">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="a0c0e-114">ListView Overview</span></span>](listview-overview.md)
