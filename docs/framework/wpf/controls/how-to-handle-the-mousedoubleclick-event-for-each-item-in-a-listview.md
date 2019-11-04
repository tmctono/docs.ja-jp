---
title: '方法 : ListView の各項目の MouseDoubleClick イベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460223"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="9708c-102">方法 : ListView の各項目の MouseDoubleClick イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="9708c-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="9708c-103"><xref:System.Windows.Controls.ListView>内の項目のイベントを処理するには、各 <xref:System.Windows.Controls.ListViewItem>にイベントハンドラーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9708c-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="9708c-104"><xref:System.Windows.Controls.ListView> がデータソースにバインドされている場合は、明示的に <xref:System.Windows.Controls.ListViewItem>を作成する必要はありませんが、<xref:System.Windows.Controls.ListViewItem>のスタイルに <xref:System.Windows.EventSetter> を追加することで、各項目のイベントを処理できます。</span><span class="sxs-lookup"><span data-stu-id="9708c-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9708c-105">例</span><span class="sxs-lookup"><span data-stu-id="9708c-105">Example</span></span>  
 <span data-ttu-id="9708c-106">次の例では、データバインド <xref:System.Windows.Controls.ListView> を作成し、<xref:System.Windows.Style> を作成して、各 <xref:System.Windows.Controls.ListViewItem>にイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9708c-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="9708c-107">次の例では、<xref:System.Windows.Controls.Control.MouseDoubleClick> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="9708c-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="9708c-108"><xref:System.Windows.Controls.ListView> をデータソースにバインドするのが最も一般的ですが、<xref:System.Windows.Controls.ListViewItem>を明示的に作成するかどうかにかかわらず、データバインドされていない <xref:System.Windows.Controls.ListView> の各 <xref:System.Windows.Controls.ListViewItem> にイベントハンドラーを追加するには、スタイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9708c-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="9708c-109">明示的かつ暗黙的に作成された <xref:System.Windows.Controls.ListViewItem> コントロールの詳細については、「<xref:System.Windows.Controls.ItemsControl>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9708c-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9708c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9708c-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="9708c-111">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="9708c-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="9708c-112">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="9708c-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9708c-113">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="9708c-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="9708c-114">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="9708c-114">ListView Overview</span></span>](listview-overview.md)
