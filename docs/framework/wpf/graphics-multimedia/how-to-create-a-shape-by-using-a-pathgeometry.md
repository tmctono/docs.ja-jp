---
title: '方法: PathGeometry を使用して図形を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: b0ab703596612524881ab892a1095b0f49cd1551
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904315"
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a><span data-ttu-id="efdbd-102">方法: PathGeometry を使用して図形を作成する</span><span class="sxs-lookup"><span data-stu-id="efdbd-102">How to: Create a Shape by Using a PathGeometry</span></span>
<span data-ttu-id="efdbd-103">この例を使用して図形を作成する方法を示しています、<xref:System.Windows.Media.PathGeometry>クラス。</span><span class="sxs-lookup"><span data-stu-id="efdbd-103">This example shows how to create a shape using the <xref:System.Windows.Media.PathGeometry> class.</span></span> <span data-ttu-id="efdbd-104"><xref:System.Windows.Media.PathGeometry> オブジェクトが 1 つまたは複数で構成される<xref:System.Windows.Media.PathFigure>オブジェクト。 各<xref:System.Windows.Media.PathFigure>異なる"図"または図形を表します。</span><span class="sxs-lookup"><span data-stu-id="efdbd-104"><xref:System.Windows.Media.PathGeometry> objects are composed of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="efdbd-105">各<xref:System.Windows.Media.PathFigure>自体は 1 つ以上ので構成されます<xref:System.Windows.Media.PathSegment>それぞれ図や図形の接続されている部分を表すオブジェクトします。</span><span class="sxs-lookup"><span data-stu-id="efdbd-105">Each <xref:System.Windows.Media.PathFigure> is itself composed of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="efdbd-106">セグメントの種類<xref:System.Windows.Media.LineSegment>、 <xref:System.Windows.Media.ArcSegment>、および<xref:System.Windows.Media.BezierSegment>します。</span><span class="sxs-lookup"><span data-stu-id="efdbd-106">Segment types include <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, and <xref:System.Windows.Media.BezierSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efdbd-107">例</span><span class="sxs-lookup"><span data-stu-id="efdbd-107">Example</span></span>  
 <span data-ttu-id="efdbd-108">次の例では、<xref:System.Windows.Media.PathGeometry>三角形が作成されます。</span><span class="sxs-lookup"><span data-stu-id="efdbd-108">The following example uses a <xref:System.Windows.Media.PathGeometry> to create a triangle.</span></span> <span data-ttu-id="efdbd-109"><xref:System.Windows.Media.PathGeometry>を使用して表示される、<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="efdbd-109">The  <xref:System.Windows.Media.PathGeometry> is displayed using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 [!code-xaml[GeometrySample#49](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 <span data-ttu-id="efdbd-110">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="efdbd-110">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="efdbd-111">![PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span><span class="sxs-lookup"><span data-stu-id="efdbd-111">![A PathGeometry](./media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")</span></span>  
<span data-ttu-id="efdbd-112">PathGeometry で作成された三角形</span><span class="sxs-lookup"><span data-stu-id="efdbd-112">A triangle created with a PathGeometry</span></span>  
  
 <span data-ttu-id="efdbd-113">前の例では、比較的単純な図形、三角形を作成する方法を示しました。</span><span class="sxs-lookup"><span data-stu-id="efdbd-113">The previous example showed how to create a relatively simple shape, a triangle.</span></span> <span data-ttu-id="efdbd-114">A<xref:System.Windows.Media.PathGeometry>円弧、曲線などのより複雑な図形を作成できます。</span><span class="sxs-lookup"><span data-stu-id="efdbd-114">A <xref:System.Windows.Media.PathGeometry> can also be used to create more complex shapes, including arcs and curves.</span></span> <span data-ttu-id="efdbd-115">例については、次を参照してください。[楕円の円弧を作成する](how-to-create-an-elliptical-arc.md)、 [3 次ベジエ曲線を作成](how-to-create-a-cubic-bezier-curve.md)、および[2 次ベジエ曲線を作成する](how-to-create-a-quadratic-bezier-curve.md)します。</span><span class="sxs-lookup"><span data-stu-id="efdbd-115">For examples, see [Create an Elliptical Arc](how-to-create-an-elliptical-arc.md), [Create a Cubic Bezier Curve](how-to-create-a-cubic-bezier-curve.md), and [Create a Quadratic Bezier Curve](how-to-create-a-quadratic-bezier-curve.md).</span></span>  
  
 <span data-ttu-id="efdbd-116">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://go.microsoft.com/fwlink/?LinkID=159989)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efdbd-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdbd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="efdbd-117">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.GeometryDrawing>
- [<span data-ttu-id="efdbd-118">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="efdbd-118">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="efdbd-119">ジオメトリのサンプル</span><span class="sxs-lookup"><span data-stu-id="efdbd-119">Geometries Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159989)
