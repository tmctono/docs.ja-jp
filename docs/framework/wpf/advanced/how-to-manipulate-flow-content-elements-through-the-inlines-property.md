---
title: '方法: Inlines プロパティを介してフロー コンテンツ要素を操作する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
ms.openlocfilehash: 92f23fbf44464eb7658f3382f873f3db63f7cb26
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64614577"
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="3b69e-102">方法: Inlines プロパティを介してフロー コンテンツ要素を操作する</span><span class="sxs-lookup"><span data-stu-id="3b69e-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="3b69e-103">この例では、**Inlines** プロパティを介して、インライン フロー コンテンツ要素 (および <xref:System.Windows.Controls.TextBlock> などの、そのような要素のコンテナー) に対して実行できる一般的な操作をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="3b69e-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="3b69e-104">このプロパティは、<xref:System.Windows.Documents.InlineCollection> の項目を追加および削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b69e-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="3b69e-105">**Inlines** プロパティを使用するフロー コンテンツ要素には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3b69e-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
- <xref:System.Windows.Documents.Bold>  
  
- <xref:System.Windows.Documents.Hyperlink>  
  
- <xref:System.Windows.Documents.Italic>  
  
- <xref:System.Windows.Documents.Paragraph>  
  
- <xref:System.Windows.Documents.Span>  
  
- <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="3b69e-106">この例では、フロー コンテンツ要素として <xref:System.Windows.Documents.Span> が使用されることがありますが、これらの手法は、<xref:System.Windows.Documents.InlineCollection> コレクションをホストするすべての要素またはコントロールに適用できます。</span><span class="sxs-lookup"><span data-stu-id="3b69e-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b69e-107">例</span><span class="sxs-lookup"><span data-stu-id="3b69e-107">Example</span></span>  
 <span data-ttu-id="3b69e-108">次の例では、新しい <xref:System.Windows.Documents.Span> オブジェクトを作成し、**Add** メソッドを使用して、<xref:System.Windows.Documents.Span> のコンテンツの子として 2 つのテキスト実行を追加します。</span><span class="sxs-lookup"><span data-stu-id="3b69e-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="3b69e-109">例</span><span class="sxs-lookup"><span data-stu-id="3b69e-109">Example</span></span>  
 <span data-ttu-id="3b69e-110">次の例では、新しい <xref:System.Windows.Documents.Run> 要素を作成し、それを <xref:System.Windows.Documents.Span> の先頭に挿入します。</span><span class="sxs-lookup"><span data-stu-id="3b69e-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="3b69e-111">例</span><span class="sxs-lookup"><span data-stu-id="3b69e-111">Example</span></span>  
 <span data-ttu-id="3b69e-112">次の例では、<xref:System.Windows.Documents.Span> に含まれる最上位レベルの <xref:System.Windows.Documents.Inline> 要素の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="3b69e-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="3b69e-113">例</span><span class="sxs-lookup"><span data-stu-id="3b69e-113">Example</span></span>  
 <span data-ttu-id="3b69e-114">次の例では、<xref:System.Windows.Documents.Span> 内の最後の <xref:System.Windows.Documents.Inline> 要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="3b69e-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="3b69e-115">例</span><span class="sxs-lookup"><span data-stu-id="3b69e-115">Example</span></span>  
 <span data-ttu-id="3b69e-116">次の例では、<xref:System.Windows.Documents.Span> からすべてのコンテンツ (<xref:System.Windows.Documents.Inline> 要素) をクリアします。</span><span class="sxs-lookup"><span data-stu-id="3b69e-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](~/samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="3b69e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b69e-117">See also</span></span>

- <xref:System.Windows.Documents.BlockCollection>
- <xref:System.Windows.Documents.InlineCollection>
- <xref:System.Windows.Documents.ListItemCollection>
- [<span data-ttu-id="3b69e-118">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="3b69e-118">Flow Document Overview</span></span>](flow-document-overview.md)
- [<span data-ttu-id="3b69e-119">Blocks プロパティを介して FlowDocument を操作する</span><span class="sxs-lookup"><span data-stu-id="3b69e-119">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="3b69e-120">Columns プロパティによってテーブルの列を操作する</span><span class="sxs-lookup"><span data-stu-id="3b69e-120">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
- [<span data-ttu-id="3b69e-121">RowGroups プロパティを介してテーブルの行グループを操作する</span><span class="sxs-lookup"><span data-stu-id="3b69e-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
