---
title: '方法 : 線を描画する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452949"
---
# <a name="how-to-draw-a-line"></a><span data-ttu-id="d33f2-102">方法 : 線を描画する</span><span class="sxs-lookup"><span data-stu-id="d33f2-102">How to: Draw a Line</span></span>
<span data-ttu-id="d33f2-103">この例では、<xref:System.Windows.Shapes.Line> 要素を使用して線を描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d33f2-103">This example shows you how to draw lines by using the <xref:System.Windows.Shapes.Line> element.</span></span>  
  
 <span data-ttu-id="d33f2-104">線を描画するには、<xref:System.Windows.Shapes.Line> 要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="d33f2-104">To draw a line, create a <xref:System.Windows.Shapes.Line> element.</span></span> <span data-ttu-id="d33f2-105">その <xref:System.Windows.Shapes.Line.X1%2A> と <xref:System.Windows.Shapes.Line.Y1%2A> プロパティを使用して、開始点を設定します。とは、その <xref:System.Windows.Shapes.Line.X2%2A> と <xref:System.Windows.Shapes.Line.Y2%2A> プロパティを使用してエンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="d33f2-105">Use its <xref:System.Windows.Shapes.Line.X1%2A> and <xref:System.Windows.Shapes.Line.Y1%2A> properties to set its start point; and use its <xref:System.Windows.Shapes.Line.X2%2A> and <xref:System.Windows.Shapes.Line.Y2%2A> properties to set its end point.</span></span> <span data-ttu-id="d33f2-106">最後に、ストロークのない線が非表示になっているため、<xref:System.Windows.Shapes.Shape.Stroke%2A> と <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> を設定します。</span><span class="sxs-lookup"><span data-stu-id="d33f2-106">Finally, set its <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> because a line without a stroke is invisible.</span></span>  
  
 <span data-ttu-id="d33f2-107">線に内部がないため、行の <xref:System.Windows.Shapes.Shape.Fill%2A> 要素を設定しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="d33f2-107">Setting the <xref:System.Windows.Shapes.Shape.Fill%2A> element for a line has no effect, because a line has no interior.</span></span>  
  
 <span data-ttu-id="d33f2-108">次の例では、<xref:System.Windows.Controls.Canvas> 要素内に3つの直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="d33f2-108">The following example draws three lines inside a <xref:System.Windows.Controls.Canvas> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d33f2-109">例</span><span class="sxs-lookup"><span data-stu-id="d33f2-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 <span data-ttu-id="d33f2-110">この例は、大規模なサンプルに含まれています。完全なサンプルについては、「 [Shape Elements sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d33f2-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d33f2-111">参照</span><span class="sxs-lookup"><span data-stu-id="d33f2-111">See also</span></span>

- <xref:System.Windows.Shapes.Line>
- [<span data-ttu-id="d33f2-112">図形要素のサンプル</span><span class="sxs-lookup"><span data-stu-id="d33f2-112">Shape Elements Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
