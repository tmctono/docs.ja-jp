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
ms.openlocfilehash: a6862ab02c288f9cfd1fac4a8c22079b0cf91016
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356183"
---
# <a name="how-to-create-a-linesegment-in-a-pathgeometry"></a><span data-ttu-id="326c6-102">方法: PathGeometry で LineSegment を作成する</span><span class="sxs-lookup"><span data-stu-id="326c6-102">How to: Create a LineSegment in a PathGeometry</span></span>
<span data-ttu-id="326c6-103">この例では、線分を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="326c6-103">This example shows how to create a line segment.</span></span> <span data-ttu-id="326c6-104">直線セグメントを作成するには、使用、 <xref:System.Windows.Media.PathGeometry>、 <xref:System.Windows.Media.PathFigure>、および<xref:System.Windows.Media.LineSegment>クラス。</span><span class="sxs-lookup"><span data-stu-id="326c6-104">To create a line segment, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.LineSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="326c6-105">例</span><span class="sxs-lookup"><span data-stu-id="326c6-105">Example</span></span>  
 <span data-ttu-id="326c6-106">次の例では、描画、<xref:System.Windows.Media.LineSegment>から (10, 50) を (200, 70)。</span><span class="sxs-lookup"><span data-stu-id="326c6-106">The following examples draw a <xref:System.Windows.Media.LineSegment> from (10, 50) to (200, 70).</span></span> <span data-ttu-id="326c6-107">次の図は、その結果<xref:System.Windows.Media.LineSegment>; 座標系を表示するグリッドの背景色が追加されました。</span><span class="sxs-lookup"><span data-stu-id="326c6-107">The following illustration shows the resulting <xref:System.Windows.Media.LineSegment>; a grid background was added to show the coordinate system.</span></span>  
  
 <span data-ttu-id="326c6-108">![PathFigure 内の LineSegment](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span><span class="sxs-lookup"><span data-stu-id="326c6-108">![A LineSegment in a PathFigure](./media/graphicsmm-pathgeometrylinesegment.png "graphicsmm_pathgeometrylinesegment")</span></span>  
<span data-ttu-id="326c6-109">(10,50) から (200,70) まで描画された LineSegment</span><span class="sxs-lookup"><span data-stu-id="326c6-109">A LineSegment drawn from (10,50) to (200,70)</span></span>  
  
 <span data-ttu-id="326c6-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="326c6-110">[xaml]</span></span>  
  
 <span data-ttu-id="326c6-111">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] では、属性構文を使用してパスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="326c6-111">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may use attribute syntax to describe a path.</span></span>  
  
```xaml  
<Path Stroke="Black" StrokeThickness="1"    
  Data="M 10,50 L 200,70" />  
```  
  
 <span data-ttu-id="326c6-112">[xaml]</span><span class="sxs-lookup"><span data-stu-id="326c6-112">[xaml]</span></span>  
  
 <span data-ttu-id="326c6-113">(この属性の構文が実際に作成するメモを<xref:System.Windows.Media.StreamGeometry>の軽量バージョンを<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="326c6-113">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="326c6-114">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="326c6-114">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="326c6-115">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] では、オブジェクト要素構文を使用して線分を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="326c6-115">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a line segment by using object element syntax.</span></span> <span data-ttu-id="326c6-116">次の例は、前の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="326c6-116">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
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
  
 <span data-ttu-id="326c6-117">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://go.microsoft.com/fwlink/?LinkID=159989)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="326c6-117">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="326c6-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="326c6-118">See also</span></span>
- <xref:System.Windows.Media.PathFigure>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.GeometryDrawing>
- <xref:System.Windows.Shapes.Path>
- [<span data-ttu-id="326c6-119">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="326c6-119">Geometry Overview</span></span>](geometry-overview.md)
