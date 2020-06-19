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
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278926"
---
# <a name="how-to-create-outlined-text"></a><span data-ttu-id="008f4-102">方法: 中抜きの文字列を作成する</span><span class="sxs-lookup"><span data-stu-id="008f4-102">How to: Create outlined text</span></span>

<span data-ttu-id="008f4-103">ほとんどの場合、[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] アプリケーションでテキスト文字列に装飾を追加するときは、不連続の文字またはグリフのコレクションという観点でテキストを使用します。</span><span class="sxs-lookup"><span data-stu-id="008f4-103">In most cases, when you're adding ornamentation to text strings in your [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application, you are using text in terms of a collection of discrete characters, or glyphs.</span></span> <span data-ttu-id="008f4-104">たとえば、線状グラデーション ブラシを作成し、<xref:System.Windows.Controls.TextBox> オブジェクトの <xref:System.Windows.Controls.Control.Foreground%2A> プロパティにそれを適用します。</span><span class="sxs-lookup"><span data-stu-id="008f4-104">For example, you could create a linear gradient brush and apply it to the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.TextBox> object.</span></span> <span data-ttu-id="008f4-105">テキスト ボックスを表示または編集すると、テキスト文字列内の現在の文字セットに線状グラデーション ブラシが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="008f4-105">When you display or edit the text box, the linear gradient brush is automatically applied to the current set of characters in the text string.</span></span>  
  
 ![線形グラデーション ブラシで表示されるテキスト](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 <span data-ttu-id="008f4-107">しかし、テキストを <xref:System.Windows.Media.Geometry> オブジェクトに変換し、他の種類の見た目がリッチなテキストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="008f4-107">However, you can also convert text into <xref:System.Windows.Media.Geometry> objects, allowing you to create other types of visually rich text.</span></span> <span data-ttu-id="008f4-108">たとえば、テキスト文字列のアウトラインに基づいて <xref:System.Windows.Media.Geometry> オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="008f4-108">For example, you could create a <xref:System.Windows.Media.Geometry> object based on the outline of a text string.</span></span>  
  
 ![線形グラデーション ブラシを使用するテキスト アウトライン](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 <span data-ttu-id="008f4-110">テキストを <xref:System.Windows.Media.Geometry> オブジェクトに変換すると、テキストは文字の集まりではなくなります。つまり、文字列内の文字を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="008f4-110">When text is converted to a <xref:System.Windows.Media.Geometry> object, it is no longer a collection of characters—you cannot modify the characters in the text string.</span></span> <span data-ttu-id="008f4-111">ただし、変換されたテキストのストロークおよび塗りつぶしのプロパティを変更することで、テキストの外観を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="008f4-111">However, you can affect the appearance of the converted text by modifying its stroke and fill properties.</span></span> <span data-ttu-id="008f4-112">ストロークは、変換したテキストのアウトラインを参照します。塗りつぶしは、変換したテキストのアウトラインの内側の領域を参照します。</span><span class="sxs-lookup"><span data-stu-id="008f4-112">The stroke refers to the outline of the converted text; the fill refers to the area inside the outline of the converted text.</span></span>  
  
 <span data-ttu-id="008f4-113">変換されたテキストのストロークと塗りつぶしを変更することで、視覚効果を作成するいくつかの方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="008f4-113">The following examples illustrate several ways of creating visual effects by modifying the stroke and fill of converted text.</span></span>  
  
 ![塗りつぶしとストロークに別の色を使用するテキスト](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![ストロークに適用されるイメージ ブラシを含むテキスト](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 <span data-ttu-id="008f4-116">また、変換されたテキストの境界ボックスの四角形 (強調表示) を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="008f4-116">It is also possible to modify the bounding box rectangle, or highlight, of the converted text.</span></span> <span data-ttu-id="008f4-117">変換されたテキストのストロークと強調表示を変更することで、視覚効果を作成する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="008f4-117">The following example illustrates a way to create visual effects by modifying the stroke and highlight of converted text.</span></span>  
  
 ![ストロークと強調表示に適用されるイメージ ブラシを含むテキスト](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a><span data-ttu-id="008f4-119">例</span><span class="sxs-lookup"><span data-stu-id="008f4-119">Example</span></span>  
 <span data-ttu-id="008f4-120">テキストを <xref:System.Windows.Media.Geometry> オブジェクトに変換するときに重要なのは、<xref:System.Windows.Media.FormattedText> オブジェクトを使用することです。</span><span class="sxs-lookup"><span data-stu-id="008f4-120">The key to converting text to a <xref:System.Windows.Media.Geometry> object is to use the <xref:System.Windows.Media.FormattedText> object.</span></span> <span data-ttu-id="008f4-121">このオブジェクトを作成したら、<xref:System.Windows.Media.FormattedText.BuildGeometry%2A> メソッドと <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> メソッドを使用して、テキストを <xref:System.Windows.Media.Geometry> オブジェクトに変換できます。</span><span class="sxs-lookup"><span data-stu-id="008f4-121">Once you have created this object, you can use the <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> and <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> methods to convert the text to <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="008f4-122">最初のメソッドでは、書式設定されたテキストのジオメトリが返されます。2 番目のメソッドでは、書式設定されたテキストの境界ボックスのジオメトリが返されます。</span><span class="sxs-lookup"><span data-stu-id="008f4-122">The first method returns the geometry of the formatted text; the second method returns the geometry of the formatted text's bounding box.</span></span> <span data-ttu-id="008f4-123">次のコード例では、<xref:System.Windows.Media.FormattedText> オブジェクトを作成し、書式設定されたテキストとその境界ボックスのジオメトリを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="008f4-123">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and to retrieve the geometries of the formatted text and its bounding box.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 <span data-ttu-id="008f4-124">取得した <xref:System.Windows.Media.Geometry> オブジェクトを表示するには、変換されたテキストを表示するオブジェクトの <xref:System.Windows.Media.DrawingContext> にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="008f4-124">In order to display the retrieved the <xref:System.Windows.Media.Geometry> objects, you need to access the <xref:System.Windows.Media.DrawingContext> of the object that's displaying the converted text.</span></span> <span data-ttu-id="008f4-125">これらのコード例では、ユーザー定義のレンダリングをサポートするクラスから派生したカスタム コントロール オブジェクトを作成することによって、このアクセスを実現しています。</span><span class="sxs-lookup"><span data-stu-id="008f4-125">In these code examples, this access is achieved by creating a custom control object that's derived from a class that supports user-defined rendering.</span></span>  
  
 <span data-ttu-id="008f4-126">カスタム コントロールで <xref:System.Windows.Media.Geometry> オブジェクトを表示するには、<xref:System.Windows.UIElement.OnRender%2A> メソッドのオーバーライドを指定します。</span><span class="sxs-lookup"><span data-stu-id="008f4-126">To display <xref:System.Windows.Media.Geometry> objects in the custom control, provide an override for the <xref:System.Windows.UIElement.OnRender%2A> method.</span></span> <span data-ttu-id="008f4-127">オーバーライドされたメソッドでは、<xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> メソッドを使用して、<xref:System.Windows.Media.Geometry> オブジェクトを描画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="008f4-127">Your overridden method should use the <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> method to draw the <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  <span data-ttu-id="008f4-128">カスタム ユーザー コントロール オブジェクトの例のソースについては、[C# の場合は OutlineTextControl.cs](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) を、[Visual Basic の場合は OutlineTextControl.vb](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="008f4-128">For the source of the example custom user control object, see [OutlineTextControl.cs for C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) and [OutlineTextControl.vb for Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="008f4-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="008f4-129">See also</span></span>

- [<span data-ttu-id="008f4-130">書式設定されたテキストの描画</span><span class="sxs-lookup"><span data-stu-id="008f4-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
