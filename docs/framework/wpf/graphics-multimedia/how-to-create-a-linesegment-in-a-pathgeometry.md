---
title: '方法: PathGeometry で LineSegment を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- line segments [WPF], creating
- graphics [WPF], line segments
ms.assetid: 0155ed47-a20d-49a7-a306-186d8e07fbc4
ms.openlocfilehash: fc7fbad1e534988a36d85c55c1b6a8249692ad67
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452085"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="946f0-102">方法: PathGeometry で LineSegment を作成する</span><span class="sxs-lookup"><span data-stu-id="946f0-102">How to: Create a LineSegment in a PathGeometry</span></span>

<span data-ttu-id="946f0-103">この例では、線分を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="946f0-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="946f0-104">線分を作成するには、<xref:System.Windows.Media.PathGeometry>、<xref:System.Windows.Media.PathFigure>、および <xref:System.Windows.Media.LineSegment> の各クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="946f0-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>

## <a name="example"></a><span data-ttu-id="946f0-105">例</span><span class="sxs-lookup"><span data-stu-id="946f0-105">Example</span></span>

<span data-ttu-id="946f0-106">次の例では、(10, 50) から (200, 70) までの <xref:System.Windows.Media.LineSegment> を描画します。</span><span class="sxs-lookup"><span data-stu-id="946f0-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="946f0-107">結果として得られる <xref:System.Windows.Media.LineSegment> を次の図に示します。座標を示すために、グリッド背景を追加しています。</span><span class="sxs-lookup"><span data-stu-id="946f0-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>

<span data-ttu-id="946f0-108">![PathFigure 内の LineSegment](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") (10,50) から (200,70) まで描画された LineSegment</span><span class="sxs-lookup"><span data-stu-id="946f0-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment") A LineSegment drawn from (10,50) to (200,70)</span></span>

<span data-ttu-id="946f0-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="946f0-109">[xaml]</span></span>

<span data-ttu-id="946f0-110">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] では、属性構文を使用してパスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="946f0-110">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1"
  Data="M 10,50 L 200,70" />
```

<span data-ttu-id="946f0-111">[xaml]</span><span class="sxs-lookup"><span data-stu-id="946f0-111">[xaml]</span></span>

<span data-ttu-id="946f0-112">(この属性構文では、実際には <xref:System.Windows.Media.PathGeometry> の軽量バージョンである <xref:System.Windows.Media.StreamGeometry> が作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="946f0-112">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="946f0-113">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="946f0-113">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>

<span data-ttu-id="946f0-114">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] では、オブジェクト要素構文を使用して線分を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="946f0-114">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="946f0-115">次の例は、前の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="946f0-115">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>

```xaml
<Path Stroke="Black" StrokeThickness="1">
  <Path.Data>
    <PathGeometry>
      <PathFigure StartPoint="10,50">
        <LineSegment Point="200,70" />
      </PathFigure>
    </PathGeometry>
  </Path.Data>
</Path>
```

```csharp
PathFigure myPathFigure = new PathFigure();
myPathFigure.StartPoint = new Point(10, 50);

LineSegment myLineSegment = new LineSegment();
myLineSegment.Point = new Point(200, 70);

PathSegmentCollection myPathSegmentCollection = new PathSegmentCollection();
myPathSegmentCollection.Add(myLineSegment);

myPathFigure.Segments = myPathSegmentCollection;

PathFigureCollection myPathFigureCollection = new PathFigureCollection();
myPathFigureCollection.Add(myPathFigure);

PathGeometry myPathGeometry = new PathGeometry();
myPathGeometry.Figures = myPathFigureCollection;

Path myPath = new Path();
myPath.Stroke = Brushes.Black;
myPath.StrokeThickness = 1;
myPath.Data = myPathGeometry;
```

```vb
Dim myPathFigure As New PathFigure()
myPathFigure.StartPoint = New Point(10, 50)

Dim myLineSegment As New LineSegment()
myLineSegment.Point = New Point(200, 70)

Dim myPathSegmentCollection As New PathSegmentCollection()
myPathSegmentCollection.Add(myLineSegment)

myPathFigure.Segments = myPathSegmentCollection

Dim myPathFigureCollection As New PathFigureCollection()
myPathFigureCollection.Add(myPathFigure)

Dim myPathGeometry As New PathGeometry()
myPathGeometry.Figures = myPathFigureCollection

Dim myPath As New Path()
myPath.Stroke = Brushes.Black
myPath.StrokeThickness = 1
myPath.Data = myPathGeometry
```

<span data-ttu-id="946f0-116">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="946f0-116">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>

## <a name="see-also"></a><span data-ttu-id="946f0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="946f0-117">See also</span></span>

- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="946f0-118">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="946f0-118">Geometry Overview</span></span>](geometry-overview.md)
