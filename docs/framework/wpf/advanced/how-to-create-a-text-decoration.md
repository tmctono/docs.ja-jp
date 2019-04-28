---
title: '方法: 文字の装飾を作成する'
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
ms.openlocfilehash: d586eef8d1308070da38a0a54c63c3ba64d30c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776638"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="ff245-102">方法: 文字の装飾を作成する</span><span class="sxs-lookup"><span data-stu-id="ff245-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="ff245-103">A<xref:System.Windows.TextDecoration>オブジェクトがビジュアルの装飾をテキストに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="ff245-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="ff245-104">文字装飾の 4 つの種類があります。 ベースライン、下線、取り消し線、および上線。</span><span class="sxs-lookup"><span data-stu-id="ff245-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="ff245-105">次の例では、テキストに対する文字装飾の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="ff245-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![文字装飾の種類の図](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="ff245-107">テキストには、文字装飾を追加するには、作成、<xref:System.Windows.TextDecoration>オブジェクトし、そのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="ff245-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="ff245-108">使用して、<xref:System.Windows.TextDecoration.Location%2A>下線などの文字装飾を表示場所を指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ff245-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="ff245-109">使用して、<xref:System.Windows.TextDecoration.Pen%2A>塗りつぶしの純色のグラデーションなどの装飾の外観を指定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ff245-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="ff245-110">値を指定しない場合、<xref:System.Windows.TextDecoration.Pen%2A>プロパティ、文字装飾の既定値は、テキストと同じ色。</span><span class="sxs-lookup"><span data-stu-id="ff245-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="ff245-111">定義した後、<xref:System.Windows.TextDecoration>オブジェクトに追加してください。、<xref:System.Windows.TextDecorations>目的のテキスト オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ff245-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="ff245-112">次の例では、線状グラデーション ブラシと破線のペンによってスタイルが設定されている文字装飾を示します。</span><span class="sxs-lookup"><span data-stu-id="ff245-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![線形グラデーション下線を使用したテキスト装飾](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="ff245-114"><xref:System.Windows.Documents.Hyperlink>オブジェクトがインライン レベル フロー コンテンツ要素、フロー コンテンツ内のハイパーリンクをホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="ff245-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="ff245-115">既定では、<xref:System.Windows.Documents.Hyperlink>を使用して、<xref:System.Windows.TextDecoration>下線を表示するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff245-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="ff245-116"><xref:System.Windows.TextDecoration> 多数ある場合は特に、オブジェクトは処理を要するインスタンスを作成すると、パフォーマンスにできる<xref:System.Windows.Documents.Hyperlink>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ff245-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="ff245-117">広範に使用する場合<xref:System.Windows.Documents.Hyperlink>要素などのイベントをトリガーするときにのみ下線を表示するのにすることがあります、<xref:System.Windows.ContentElement.MouseEnter>イベント。</span><span class="sxs-lookup"><span data-stu-id="ff245-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="ff245-118">次の例では、"マイ MSN"リンクの下線が動的-にのみ表示されるときに、<xref:System.Windows.ContentElement.MouseEnter>イベントがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="ff245-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![TextDecorations を表示するハイパーリンク](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  
   
 <span data-ttu-id="ff245-120">詳細については、「[方法: ハイパーリンクに下線を引くかどうかを指定する](how-to-specify-whether-a-hyperlink-is-underlined.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff245-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff245-121">例</span><span class="sxs-lookup"><span data-stu-id="ff245-121">Example</span></span>  
 <span data-ttu-id="ff245-122">次のコード例では、下線文字の装飾は、既定のフォント値を使用します。</span><span class="sxs-lookup"><span data-stu-id="ff245-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="ff245-123">次のコード例では、ペンの純色ブラシを使用して下線の文字装飾が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ff245-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="ff245-124">次のコード例では、下線文字の装飾は破線のペンの線状グラデーション ブラシで作成されます。</span><span class="sxs-lookup"><span data-stu-id="ff245-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="ff245-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff245-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="ff245-126">ハイパーリンクに下線を引くかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="ff245-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
