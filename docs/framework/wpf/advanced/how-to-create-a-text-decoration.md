---
title: '方法 : 文字の装飾を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185924"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="325e5-102">方法 : 文字の装飾を作成する</span><span class="sxs-lookup"><span data-stu-id="325e5-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="325e5-103">オブジェクト<xref:System.Windows.TextDecoration>は、テキストに追加できる視覚的な装飾です。</span><span class="sxs-lookup"><span data-stu-id="325e5-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="325e5-104">文字装飾には、下線、ベースライン、取り消し線、上線の 4 種類があります。</span><span class="sxs-lookup"><span data-stu-id="325e5-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="325e5-105">次の例は、テキストに関連する文字装飾の位置を示しています。</span><span class="sxs-lookup"><span data-stu-id="325e5-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![文字装飾タイプの図](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="325e5-107">テキストに文字装飾を追加するには、オブジェクトを<xref:System.Windows.TextDecoration>作成し、そのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="325e5-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="325e5-108"><xref:System.Windows.TextDecoration.Location%2A>下線などの文字装飾の表示場所を指定するには、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="325e5-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="325e5-109">塗りつぶし<xref:System.Windows.TextDecoration.Pen%2A>やグラデーションの色など、文字装飾の外観を指定するには、このプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="325e5-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="325e5-110"><xref:System.Windows.TextDecoration.Pen%2A>プロパティの値を指定しない場合、装飾は既定でテキストと同じ色になります。</span><span class="sxs-lookup"><span data-stu-id="325e5-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="325e5-111">オブジェクトを<xref:System.Windows.TextDecoration>定義したら、目的のテキスト オブジェクトの<xref:System.Windows.TextDecorations>コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="325e5-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="325e5-112">線形グラデーション ブラシと破線のペンでスタイル設定された文字装飾の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="325e5-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![線形グラデーション下線を使用したテキスト装飾](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="325e5-114">オブジェクト<xref:System.Windows.Documents.Hyperlink>はインラインレベルのフローコンテンツ要素で、フローコンテンツ内でハイパーリンクをホストできます。</span><span class="sxs-lookup"><span data-stu-id="325e5-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="325e5-115">既定では、<xref:System.Windows.Documents.Hyperlink>オブジェクトを<xref:System.Windows.TextDecoration>使用して下線を表示します。</span><span class="sxs-lookup"><span data-stu-id="325e5-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="325e5-116"><xref:System.Windows.TextDecoration>オブジェクトのインスタンス化に対して、特に多数<xref:System.Windows.Documents.Hyperlink>のオブジェクトがある場合は、オブジェクトのインスタンス化に多くのパフォーマンスを要する場合があります。</span><span class="sxs-lookup"><span data-stu-id="325e5-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="325e5-117">要素を広範囲に<xref:System.Windows.Documents.Hyperlink>使用する場合は、イベントなどのイベントをトリガするときにのみ下線を表示することを検討してください。 <xref:System.Windows.ContentElement.MouseEnter></span><span class="sxs-lookup"><span data-stu-id="325e5-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="325e5-118">次の例では、[マイ MSN] リンクの下線は動的で、<xref:System.Windows.ContentElement.MouseEnter>イベントがトリガーされたときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="325e5-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![TextDecorations を表示するハイパーリンク](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="325e5-120">詳細については、「[方法: ハイパーリンクに下線を引くかどうかを指定する](how-to-specify-whether-a-hyperlink-is-underlined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="325e5-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="325e5-121">例</span><span class="sxs-lookup"><span data-stu-id="325e5-121">Example</span></span>  
 <span data-ttu-id="325e5-122">次のコード例では、下線付きの文字装飾で既定のフォント値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="325e5-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="325e5-123">次のコード例では、ペンの単色ブラシを使用して下線付きの文字装飾を作成しています。</span><span class="sxs-lookup"><span data-stu-id="325e5-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="325e5-124">次のコード例では、点線付きのペンに線形グラデーション ブラシを使用して下線付きの文字装飾を作成します。</span><span class="sxs-lookup"><span data-stu-id="325e5-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="325e5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="325e5-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="325e5-126">ハイパーリンクに下線を引くかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="325e5-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
