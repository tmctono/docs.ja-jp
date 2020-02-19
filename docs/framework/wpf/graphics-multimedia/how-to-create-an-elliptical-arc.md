---
title: '方法 : 楕円の円弧を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: d0fffbb25f3c5aaceb2cd80af4f1093e44111200
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453066"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="8b98e-102">方法 : 楕円の円弧を作成する</span><span class="sxs-lookup"><span data-stu-id="8b98e-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="8b98e-103">この例では、楕円の円弧を描画する方法を示します。楕円の円弧を作成するには、<xref:System.Windows.Media.PathGeometry>、<xref:System.Windows.Media.PathFigure>、および <xref:System.Windows.Media.ArcSegment> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b98e-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b98e-104">例</span><span class="sxs-lookup"><span data-stu-id="8b98e-104">Example</span></span>  
 <span data-ttu-id="8b98e-105">次の例では、楕円弧が (10100) から (200100) に描画されます。</span><span class="sxs-lookup"><span data-stu-id="8b98e-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="8b98e-106">弧には、100の <xref:System.Windows.Media.ArcSegment.Size%2A> が50デバイスに依存しないピクセル、<xref:System.Windows.Media.ArcSegment.RotationAngle%2A> 45 度、`true`の <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 設定、<xref:System.Windows.Media.ArcSegment.SweepDirection%2A> の <xref:System.Windows.Media.SweepDirection.Counterclockwise>があります。</span><span class="sxs-lookup"><span data-stu-id="8b98e-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="8b98e-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="8b98e-107">[xaml]</span></span>  
  
 <span data-ttu-id="8b98e-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]では、属性構文を使用してパスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="8b98e-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="8b98e-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="8b98e-109">[xaml]</span></span>  
  
 <span data-ttu-id="8b98e-110">(この属性構文では、実際には <xref:System.Windows.Media.PathGeometry>の軽量バージョンである <xref:System.Windows.Media.StreamGeometry>が作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b98e-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="8b98e-111">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="8b98e-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="8b98e-112">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]では、オブジェクトタグを明示的に使用して楕円の円弧を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b98e-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="8b98e-113">次に示すのは、前の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] マークアップに相当します。</span><span class="sxs-lookup"><span data-stu-id="8b98e-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="8b98e-114">この例は、さらに大きなサンプルの一部です。</span><span class="sxs-lookup"><span data-stu-id="8b98e-114">This example is part of a larger sample.</span></span> <span data-ttu-id="8b98e-115">完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b98e-115">For the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b98e-116">参照</span><span class="sxs-lookup"><span data-stu-id="8b98e-116">See also</span></span>

- [<span data-ttu-id="8b98e-117">2 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="8b98e-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="8b98e-118">3 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="8b98e-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
