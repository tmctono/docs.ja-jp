---
title: '方法 : 四角形を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452936"
---
# <a name="how-to-draw-a-rectangle"></a><span data-ttu-id="6b2b7-102">方法 : 四角形を描画する</span><span class="sxs-lookup"><span data-stu-id="6b2b7-102">How to: Draw a Rectangle</span></span>
<span data-ttu-id="6b2b7-103">この例では、<xref:System.Windows.Shapes.Rectangle> 要素を使用して四角形を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-103">This example shows how to draw a rectangle by using the <xref:System.Windows.Shapes.Rectangle> element.</span></span>  
  
 <span data-ttu-id="6b2b7-104">四角形を描画するには、<xref:System.Windows.Shapes.Rectangle> 要素を作成し、その <xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A>を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-104">To draw a rectangle, create a <xref:System.Windows.Shapes.Rectangle> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="6b2b7-105">四角形の内部を描画するには、その <xref:System.Windows.Shapes.Shape.Fill%2A>を設定します。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-105">To paint the inside of the rectangle, set its <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="6b2b7-106">四角形に輪郭を付けるには、その <xref:System.Windows.Shapes.Shape.Stroke%2A> と <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-106">To give the rectangle an outline, use its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties.</span></span>  
  
 <span data-ttu-id="6b2b7-107">四角形の角を丸くするには、オプションの <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-107">To give the rectangle rounded corners, specify the optional <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties.</span></span> <span data-ttu-id="6b2b7-108"><xref:System.Windows.Shapes.Rectangle.RadiusX%2A> と <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> のプロパティは、四角形の角を丸めるために使用される楕円の x 軸と y 軸の半径を設定します。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-108">The <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> and <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> properties set the x-axis and y-axis radii of the ellipse that is used to round the corners of the rectangle.</span></span>  
  
 <span data-ttu-id="6b2b7-109">次の例では、2つの <xref:System.Windows.Shapes.Rectangle> 要素が <xref:System.Windows.Controls.Canvas>で描画されます。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-109">In the following example, two <xref:System.Windows.Shapes.Rectangle> elements are drawn in a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="6b2b7-110">最初の四角形には <xref:System.Windows.Media.Brushes.Blue%2A> 内部があります。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-110">The first rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior.</span></span> <span data-ttu-id="6b2b7-111">2番目の四角形には、<xref:System.Windows.Media.Brushes.Blue%2A> 内部、<xref:System.Windows.Media.Brushes.Black%2A> アウトライン、および角の丸みがあります。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-111">The second rectangle has a <xref:System.Windows.Media.Brushes.Blue%2A> interior, a <xref:System.Windows.Media.Brushes.Black%2A> outline, and rounded corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b2b7-112">例</span><span class="sxs-lookup"><span data-stu-id="6b2b7-112">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 <span data-ttu-id="6b2b7-113">この例では、<xref:System.Windows.Controls.Canvas> を使用して四角形を格納しますが、テキスト以外のコンテンツをサポートする <xref:System.Windows.Controls.Panel> または <xref:System.Windows.Controls.Control> で四角形要素 (およびその他のすべての図形要素) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-113">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the rectangles, you can use rectangle elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span> <span data-ttu-id="6b2b7-114">実際、四角形は、<xref:System.Windows.Controls.Grid> パネルの一部の背景を提供する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-114">In fact, rectangles are particularly useful for providing backgrounds for portions of <xref:System.Windows.Controls.Grid> panels.</span></span> <span data-ttu-id="6b2b7-115">例については、[テーブルの概要](../advanced/table-overview.md)に関するトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-115">For an example, see the [Table Overview](../advanced/table-overview.md).</span></span>  
  
 <span data-ttu-id="6b2b7-116">この例は、大規模なサンプルに含まれています。完全なサンプルについては、「 [Shape Elements sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b2b7-116">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2b7-117">参照</span><span class="sxs-lookup"><span data-stu-id="6b2b7-117">See also</span></span>

- <xref:System.Windows.Shapes.Rectangle>
- [<span data-ttu-id="6b2b7-118">図形要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="6b2b7-118">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="6b2b7-119">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="6b2b7-119">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="6b2b7-120">テーブルの概要</span><span class="sxs-lookup"><span data-stu-id="6b2b7-120">Table Overview</span></span>](../advanced/table-overview.md)
