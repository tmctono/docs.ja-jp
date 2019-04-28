---
title: '方法: ListView の各項目の MouseDoubleClick イベントを処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 443e5c620ef5bf240d3e317f0234aac0b29b456f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770995"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="4d178-102">方法: ListView の各項目の MouseDoubleClick イベントを処理する</span><span class="sxs-lookup"><span data-stu-id="4d178-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="4d178-103">内の項目のイベントを処理するために、 <xref:System.Windows.Controls.ListView>、それぞれにイベント ハンドラーを追加する必要がある<xref:System.Windows.Controls.ListViewItem>します。</span><span class="sxs-lookup"><span data-stu-id="4d178-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="4d178-104">ときに、<xref:System.Windows.Controls.ListView>がバインドされているデータ ソースに明示的に作成しない、 <xref:System.Windows.Controls.ListViewItem>、追加することで各項目のイベントを処理することができますが、<xref:System.Windows.EventSetter>のスタイルを<xref:System.Windows.Controls.ListViewItem>します。</span><span class="sxs-lookup"><span data-stu-id="4d178-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d178-105">例</span><span class="sxs-lookup"><span data-stu-id="4d178-105">Example</span></span>  
 <span data-ttu-id="4d178-106">次の例は、データ バインドを作成します。<xref:System.Windows.Controls.ListView>を作成し、<xref:System.Windows.Style>各にイベント ハンドラーを追加する<xref:System.Windows.Controls.ListViewItem>します。</span><span class="sxs-lookup"><span data-stu-id="4d178-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="4d178-107">次の例のハンドル、<xref:System.Windows.Controls.Control.MouseDoubleClick>イベント。</span><span class="sxs-lookup"><span data-stu-id="4d178-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="4d178-108">バインドする最も一般的な<xref:System.Windows.Controls.ListView>各にイベント ハンドラーを追加するスタイルを使用するデータ ソースに<xref:System.Windows.Controls.ListViewItem>、非データ バインドで<xref:System.Windows.Controls.ListView>明示的に作成するかどうかに関係なく、<xref:System.Windows.Controls.ListViewItem>します。</span><span class="sxs-lookup"><span data-stu-id="4d178-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="4d178-109">明示的および暗黙的が作成の詳細については<xref:System.Windows.Controls.ListViewItem>コントロールを参照してください<xref:System.Windows.Controls.ItemsControl>します。</span><span class="sxs-lookup"><span data-stu-id="4d178-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d178-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d178-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="4d178-111">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="4d178-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="4d178-112">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="4d178-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="4d178-113">XMLDataProvider と XPath クエリを使用して XML データにバインドする</span><span class="sxs-lookup"><span data-stu-id="4d178-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="4d178-114">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="4d178-114">ListView Overview</span></span>](listview-overview.md)
