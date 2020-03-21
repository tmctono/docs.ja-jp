---
title: '方法 : 中抜きの文字列を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186858"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="63c73-102">方法 : 中抜きの文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="63c73-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="63c73-103">ほとんどの場合、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]アプリケーションでテキスト文字列に装飾を追加する場合、テキストを使用して、個別の文字またはグリフのコレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="63c73-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="63c73-104">たとえば、線形グラデーション ブラシを作成し、<xref:System.Windows.Controls.Control.Foreground%2A><xref:System.Windows.Controls.TextBox>オブジェクトのプロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="63c73-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="63c73-105">テキスト ボックスを表示または編集すると、テキスト文字列の現在の文字セットに線形グラデーション ブラシが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="63c73-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![線形グラデーション ブラシで表示されるテキスト](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="63c73-107">ただし、テキストをオブジェクトに<xref:System.Windows.Media.Geometry>変換して、他の種類の視覚的なリッチ テキストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="63c73-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="63c73-108">たとえば、テキスト文字列のアウトラインに<xref:System.Windows.Media.Geometry>基づいてオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="63c73-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![線形グラデーション ブラシを使用するテキスト アウトライン](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="63c73-110">テキストを<xref:System.Windows.Media.Geometry>オブジェクトに変換すると、文字のコレクションではなく、テキスト文字列の文字を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="63c73-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="63c73-111">ただし、変換されたテキストのストロークおよび塗りつぶしのプロパティを変更することで、テキストの外観を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="63c73-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="63c73-112">ストロークは、変換したテキストのアウトラインを参照します。塗りつぶしは、変換したテキストのアウトラインの内側の領域を参照します。</span><span class="sxs-lookup"><span data-stu-id="63c73-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="63c73-113">次の例は、変換されたテキストのストロークと塗りつぶしを変更することによって視覚効果を作成するいくつかの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63c73-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![塗りつぶしとストロークに別の色を使用するテキスト](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![ストロークに適用されるイメージ ブラシを含むテキスト](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="63c73-116">変換されたテキストの外接ボックスの四角形またはハイライトを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="63c73-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="63c73-117">次の例は、変換されたテキストのストロークと強調表示を変更して視覚効果を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63c73-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![イメージ ブラシがストロークとハイライトに適用されたテキスト](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="63c73-119">例</span><span class="sxs-lookup"><span data-stu-id="63c73-119">Example</span></span>  
 <span data-ttu-id="63c73-120">テキストを<xref:System.Windows.Media.Geometry>オブジェクトに変換するキーは、オブジェクトを<xref:System.Windows.Media.FormattedText>使用することです。</span><span class="sxs-lookup"><span data-stu-id="63c73-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="63c73-121">このオブジェクトを作成したら、<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>メソッドと メソッド<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>を使用してテキストをオブジェクトに<xref:System.Windows.Media.Geometry>変換できます。</span><span class="sxs-lookup"><span data-stu-id="63c73-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="63c73-122">最初のメソッドは、書式設定されたテキストのジオメトリを返します。2 番目のメソッドは、書式設定されたテキストの境界ボックスのジオメトリを返します。</span><span class="sxs-lookup"><span data-stu-id="63c73-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="63c73-123"><xref:System.Windows.Media.FormattedText>次のコード例は、オブジェクトを作成し、書式設定されたテキストとその境界ボックスのジオメトリを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="63c73-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="63c73-124">取得した<xref:System.Windows.Media.Geometry>オブジェクトを表示するには、変換されたテキストを表示しているオブジェクト<xref:System.Windows.Media.DrawingContext>にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="63c73-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="63c73-125">これらのコード例では、ユーザー定義のレンダリングをサポートするクラスから派生したカスタム コントロール オブジェクトを作成することによって、この処理を行います。</span><span class="sxs-lookup"><span data-stu-id="63c73-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="63c73-126">カスタム<xref:System.Windows.Media.Geometry>コントロール内のオブジェクトを表示するには、メソッドのオーバーライド<xref:System.Windows.UIElement.OnRender%2A>を指定します。</span><span class="sxs-lookup"><span data-stu-id="63c73-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="63c73-127">オーバーライドしたメソッドは、オブジェクトを<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>描画するメソッドを<xref:System.Windows.Media.Geometry>使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63c73-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="63c73-128">カスタム ユーザー コントロール オブジェクトの例のソースについては[、「C# のOutlineTextControl.cs](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs)と[Visual Basic のアウトライン テキスト コントロール.vb](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63c73-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63c73-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="63c73-129">See also</span></span>

- [<span data-ttu-id="63c73-130">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="63c73-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
