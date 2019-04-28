---
title: '方法: 中抜きの文字列を作成する'
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
ms.openlocfilehash: 237bdc097cd2a3fbfff6dd79bce401c2d091e211
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776739"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="d7903-102">方法: 中抜きの文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="d7903-102">How to: Create Outlined Text</span></span>
<span data-ttu-id="d7903-103">ほとんどの場合、テキスト文字列内に装飾を追加するときに、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]アプリケーションでは、一連の個別の文字とグリフの観点からテキストを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d7903-103">In most cases, when you are adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="d7903-104">たとえば、線状グラデーション ブラシを作成してに適用、<xref:System.Windows.Controls.Control.Foreground%2A>のプロパティを<xref:System.Windows.Controls.TextBox>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7903-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="d7903-105">表示またはテキスト ボックスを編集すると、線状グラデーション ブラシがテキスト文字列内の文字の現在のセットに自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="d7903-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![線形グラデーション ブラシで表示されるテキスト](./media/how-to-create-outlined-text/text-linear-gradient.jpg)    
  
 <span data-ttu-id="d7903-107">ただし、テキストに変換も<xref:System.Windows.Media.Geometry>オブジェクトを視覚的にリッチ テキストの他の種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="d7903-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="d7903-108">たとえば、作成する、<xref:System.Windows.Media.Geometry>のテキスト文字列のアウトラインに基づいてオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7903-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![線形グラデーション ブラシを使用するテキスト アウトライン](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="d7903-110">テキストを変換するときに、<xref:System.Windows.Media.Geometry>文字のコレクションでは不要になったオブジェクト-テキスト文字列内の文字を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7903-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="d7903-111">ただし、変換されたテキストのストロークおよび塗りつぶしのプロパティを変更することで、テキストの外観を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="d7903-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="d7903-112">ストロークは、変換したテキストのアウトラインを参照します。塗りつぶしは、変換したテキストのアウトラインの内側の領域を参照します。</span><span class="sxs-lookup"><span data-stu-id="d7903-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="d7903-113">次の例では、変換されたテキストの塗りつぶし、ストロークを変更して視覚効果を作成するいくつかの方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d7903-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![塗りつぶしとストロークに別の色を使用するテキスト](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![ストロークに適用されるイメージ ブラシを含むテキスト](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="d7903-116">境界ボックスの四角形、または変換後のテキストの強調表示を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7903-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="d7903-117">次の例では、ストロークと変換されたテキストの強調表示を変更することで視覚効果を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d7903-117">The following example illustrates a way to creating visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![ストロークし、強調表示に適用されるイメージ ブラシを含むテキスト](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="d7903-119">例</span><span class="sxs-lookup"><span data-stu-id="d7903-119">Example</span></span>  
 <span data-ttu-id="d7903-120">テキストを変換するキー、<xref:System.Windows.Media.Geometry>オブジェクトは、使用する、<xref:System.Windows.Media.FormattedText>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7903-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="d7903-121">使用することがこのオブジェクトを作成すると、<xref:System.Windows.Media.FormattedText.BuildGeometry%2A>と<xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A>にテキストを変換するメソッドを<xref:System.Windows.Media.Geometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7903-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="d7903-122">最初のメソッドが書式設定されたテキストのジオメトリを返します2 番目のメソッドの境界ボックスの書式設定されたテキストのジオメトリを返します。</span><span class="sxs-lookup"><span data-stu-id="d7903-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="d7903-123">次のコード例を作成する方法を示しています、<xref:System.Windows.Media.FormattedText>オブジェクトと書式設定されたテキストとその境界ボックスのジオメトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="d7903-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="d7903-124">取得して、表示するために、<xref:System.Windows.Media.Geometry>オブジェクトにアクセスする必要がある、<xref:System.Windows.Media.DrawingContext>の変換後のテキストが表示されているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7903-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that is displaying the converted text.</span></span> <span data-ttu-id="d7903-125">これらのコード例では、ユーザー定義のレンダリングをサポートするクラスから派生したカスタム コントロール オブジェクトを作成してこれは、します。</span><span class="sxs-lookup"><span data-stu-id="d7903-125">In these code examples, this is done by creating a custom control object that is derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="d7903-126">表示する<xref:System.Windows.Media.Geometry>、カスタム コントロール内のオブジェクトのオーバーライドを提供する、<xref:System.Windows.UIElement.OnRender%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="d7903-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="d7903-127">オーバーライドされたメソッドを使用する必要があります、<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A>を描画するメソッド、<xref:System.Windows.Media.Geometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d7903-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="d7903-128">カスタム ユーザー コントロール オブジェクトの例のソースを参照してください。[の OutlineTextControl.cs C# ](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs)と[Visual basic の OutlineTextControl.vb](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)します。</span><span class="sxs-lookup"><span data-stu-id="d7903-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7903-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7903-129">See also</span></span>

- [<span data-ttu-id="d7903-130">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="d7903-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
