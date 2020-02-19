---
title: '方法 : ポリライン要素を使用してポリラインを描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 6698141bcaa3b0fd5f5b9cf66bcab1be1f4ea2f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452962"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a><span data-ttu-id="8c264-102">方法 : ポリライン要素を使用してポリラインを描画する</span><span class="sxs-lookup"><span data-stu-id="8c264-102">How to: Draw a Polyline by Using the Polyline Element</span></span>
<span data-ttu-id="8c264-103">この例では、<xref:System.Windows.Shapes.Polyline> 要素を使用して、接続された一連の線であるポリラインを描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c264-103">This example shows how to draw a polyline, which is a series of connected lines, by using the <xref:System.Windows.Shapes.Polyline> element.</span></span>  
  
 <span data-ttu-id="8c264-104">ポリラインを描画するには、<xref:System.Windows.Shapes.Polyline> 要素を作成し、その <xref:System.Windows.Shapes.Polyline.Points%2A> プロパティを使用して図形の頂点を指定します。</span><span class="sxs-lookup"><span data-stu-id="8c264-104">To draw a polyline, create a <xref:System.Windows.Shapes.Polyline> element and use its <xref:System.Windows.Shapes.Polyline.Points%2A> property to specify the shape vertices.</span></span> <span data-ttu-id="8c264-105">最後に、<xref:System.Windows.Shapes.Shape.Stroke%2A> と <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> のプロパティを使用して、ストロークの輪郭を記述します。これは、ストロークのない線が非表示になっているためです。</span><span class="sxs-lookup"><span data-stu-id="8c264-105">Finally, use the <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> properties to describe the polyline outline because a line without a stroke is invisible.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c264-106"><xref:System.Windows.Shapes.Polyline> 要素は閉じた図形ではないため、図形のアウトラインを意図的に閉じた場合でも、<xref:System.Windows.Shapes.Shape.Fill%2A> プロパティは効果がありません。</span><span class="sxs-lookup"><span data-stu-id="8c264-106">Because the <xref:System.Windows.Shapes.Polyline> element is not a closed shape, the <xref:System.Windows.Shapes.Shape.Fill%2A> property has no effect, even if you deliberately close the shape outline.</span></span> <span data-ttu-id="8c264-107"><xref:System.Windows.Shapes.Shape.Fill%2A>を持つ閉じた図形を作成するには、<xref:System.Windows.Shapes.Polygon> 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c264-107">To create a closed shape with a <xref:System.Windows.Shapes.Shape.Fill%2A>, use a <xref:System.Windows.Shapes.Polygon> element.</span></span>  
  
 <span data-ttu-id="8c264-108">次の例では、<xref:System.Windows.Controls.Canvas>内に2つの <xref:System.Windows.Shapes.Polyline> 要素を描画します。</span><span class="sxs-lookup"><span data-stu-id="8c264-108">The following example draws two <xref:System.Windows.Shapes.Polyline> elements inside a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c264-109">例</span><span class="sxs-lookup"><span data-stu-id="8c264-109">Example</span></span>  
 <span data-ttu-id="8c264-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]では、ポイントの有効な構文は、コンマで区切られた x 座標と y 座標のペアのスペース区切りのリストです。</span><span class="sxs-lookup"><span data-stu-id="8c264-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], valid syntax for points is a space-delimited list of comma-separated x- and y-coordinate pairs.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 <span data-ttu-id="8c264-111">この例では、<xref:System.Windows.Controls.Canvas> を使用して、ポリラインを格納しますが、テキスト以外のコンテンツをサポートする <xref:System.Windows.Controls.Panel> または <xref:System.Windows.Controls.Control> では、ポリライン要素 (およびその他のすべての図形要素) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8c264-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the polylines, you can use polyline elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="8c264-112">この例は、大規模なサンプルに含まれています。完全なサンプルについては、「 [Shape Elements sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c264-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c264-113">参照</span><span class="sxs-lookup"><span data-stu-id="8c264-113">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="8c264-114">図形要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="8c264-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [<span data-ttu-id="8c264-115">WPF での図形と基本描画の概要</span><span class="sxs-lookup"><span data-stu-id="8c264-115">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
