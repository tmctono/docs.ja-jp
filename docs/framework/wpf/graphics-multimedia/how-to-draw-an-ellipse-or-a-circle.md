---
title: '方法 : 楕円または円を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: 5f17615da4907cba6e25b68f2f934602c2f8a390
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452923"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a><span data-ttu-id="aea19-102">方法 : 楕円または円を描画する</span><span class="sxs-lookup"><span data-stu-id="aea19-102">How to: Draw an Ellipse or a Circle</span></span>
<span data-ttu-id="aea19-103">この例では、<xref:System.Windows.Shapes.Ellipse> 要素を使用して、楕円と円を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aea19-103">This example shows how to draw ellipses and circles by using the <xref:System.Windows.Shapes.Ellipse> element.</span></span> <span data-ttu-id="aea19-104">楕円を描画するには、<xref:System.Windows.Shapes.Ellipse> 要素を作成し、その <xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A>を指定します。</span><span class="sxs-lookup"><span data-stu-id="aea19-104">To draw an ellipse, create an <xref:System.Windows.Shapes.Ellipse> element and specify its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="aea19-105"><xref:System.Windows.Shapes.Shape.Fill%2A> プロパティを使用して、楕円の内部を描画するために使用される <xref:System.Windows.Media.Brush> を指定します。</span><span class="sxs-lookup"><span data-stu-id="aea19-105">Use its <xref:System.Windows.Shapes.Shape.Fill%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the interior of the ellipse.</span></span> <span data-ttu-id="aea19-106"><xref:System.Windows.Shapes.Shape.Stroke%2A> プロパティを使用して、楕円の輪郭の描画に使用する <xref:System.Windows.Media.Brush> を指定します。</span><span class="sxs-lookup"><span data-stu-id="aea19-106">Use its <xref:System.Windows.Shapes.Shape.Stroke%2A> property to specify the <xref:System.Windows.Media.Brush> that is used to paint the outline of the ellipse.</span></span> <span data-ttu-id="aea19-107"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A> プロパティは、楕円の輪郭の太さを指定します。</span><span class="sxs-lookup"><span data-stu-id="aea19-107">The <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> property specifies the thickness of the ellipse outline.</span></span>  
  
 <span data-ttu-id="aea19-108">円を描画するには、<xref:System.Windows.Shapes.Ellipse> 要素の <xref:System.Windows.FrameworkElement.Width%2A> と <xref:System.Windows.FrameworkElement.Height%2A> を互いに等しくするようにします。</span><span class="sxs-lookup"><span data-stu-id="aea19-108">To draw a circle, make the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> of the <xref:System.Windows.Shapes.Ellipse> element equal to each other.</span></span>  
  
 <span data-ttu-id="aea19-109">次の例では、<xref:System.Windows.Controls.Canvas>内に4つの <xref:System.Windows.Shapes.Ellipse> 要素を描画します。</span><span class="sxs-lookup"><span data-stu-id="aea19-109">The following example draws four <xref:System.Windows.Shapes.Ellipse> elements within a <xref:System.Windows.Controls.Canvas>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aea19-110">例</span><span class="sxs-lookup"><span data-stu-id="aea19-110">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 <span data-ttu-id="aea19-111">この例では、<xref:System.Windows.Controls.Canvas> を使用して省略記号を格納していますが、テキスト以外のコンテンツをサポートする <xref:System.Windows.Controls.Panel> または <xref:System.Windows.Controls.Control> を持つ楕円要素 (およびその他のすべての図形要素) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aea19-111">Although this example uses a <xref:System.Windows.Controls.Canvas> to contain the ellipses, you can use ellipse elements (and all the other shape elements) with any <xref:System.Windows.Controls.Panel> or <xref:System.Windows.Controls.Control> that supports non-text content.</span></span>  
  
 <span data-ttu-id="aea19-112">この例は、大規模なサンプルに含まれています。完全なサンプルについては、「 [Shape Elements sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea19-112">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea19-113">参照</span><span class="sxs-lookup"><span data-stu-id="aea19-113">See also</span></span>

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [<span data-ttu-id="aea19-114">図形要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="aea19-114">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
