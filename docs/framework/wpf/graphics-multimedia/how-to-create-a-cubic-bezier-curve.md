---
title: '方法 : 3 次ベジエ曲線を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- curves [WPF], cubic Bezier
- Bezier curves [WPF], cubic
- graphics [WPF], cubic Bezier curves
- cubic Bezier curves [WPF]
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
ms.openlocfilehash: c12bd84fcebb3acebb80bef5f4479ad535fd6691
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452111"
---
# <a name="how-to-create-a-cubic-bezier-curve"></a><span data-ttu-id="57001-102">方法 : 3 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="57001-102">How to: Create a Cubic Bezier Curve</span></span>
<span data-ttu-id="57001-103">この例では、3次ベジエ曲線を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57001-103">This example shows how to create a cubic Bezier curve.</span></span> <span data-ttu-id="57001-104">3次ベジエ曲線を作成するには、<xref:System.Windows.Media.PathGeometry>、<xref:System.Windows.Media.PathFigure>、および <xref:System.Windows.Media.BezierSegment> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="57001-104">To create a cubic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.BezierSegment> classes.</span></span>  <span data-ttu-id="57001-105">結果として得られるジオメトリを表示するには、<xref:System.Windows.Shapes.Path> 要素を使用するか、<xref:System.Windows.Media.GeometryDrawing> または <xref:System.Windows.Media.DrawingContext>と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="57001-105">To display the resulting geometry, use a <xref:System.Windows.Shapes.Path> element, or use it with a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="57001-106">次の例では、3次ベジエ曲線が (10, 100) から (300, 100) に描画されます。</span><span class="sxs-lookup"><span data-stu-id="57001-106">In the following examples, a cubic Bezier curve is drawn from (10, 100) to (300, 100).</span></span> <span data-ttu-id="57001-107">曲線には、(100, 0) と (200, 200) の制御点があります。</span><span class="sxs-lookup"><span data-stu-id="57001-107">The curve has control points of (100, 0) and (200, 200).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57001-108">例</span><span class="sxs-lookup"><span data-stu-id="57001-108">Example</span></span>  
 <span data-ttu-id="57001-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="57001-109">[xaml]</span></span>  
  
 <span data-ttu-id="57001-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]では、省略したマークアップ構文を使用してパスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="57001-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use abbreviated markup syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 <span data-ttu-id="57001-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="57001-111">[xaml]</span></span>  
  
 <span data-ttu-id="57001-112">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]では、オブジェクトタグを使用して3次ベジエ曲線を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="57001-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw a cubic Bezier curve using object tags.</span></span> <span data-ttu-id="57001-113">次の例は、前の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="57001-113">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#33](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 <span data-ttu-id="57001-114">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57001-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57001-115">参照</span><span class="sxs-lookup"><span data-stu-id="57001-115">See also</span></span>

- [<span data-ttu-id="57001-116">楕円の円弧を作成する</span><span class="sxs-lookup"><span data-stu-id="57001-116">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="57001-117">PathGeometry で LineSegment を作成する</span><span class="sxs-lookup"><span data-stu-id="57001-117">Create a LineSegment in a PathGeometry</span></span>](how-to-create-a-linesegment-in-a-pathgeometry.md)
- [<span data-ttu-id="57001-118">3 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="57001-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
- [<span data-ttu-id="57001-119">2 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="57001-119">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
