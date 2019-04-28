---
title: '方法: 楕円の円弧を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], elliptical arcs
- elliptical arcs [WPF], creating
- arcs [WPF], elliptical
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
ms.openlocfilehash: aae304b9963f3a8e5833b4d8ba0a54777a750225
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003367"
---
# <a name="how-to-create-an-elliptical-arc"></a><span data-ttu-id="04846-102">方法: 楕円の円弧を作成する</span><span class="sxs-lookup"><span data-stu-id="04846-102">How to: Create an Elliptical Arc</span></span>
<span data-ttu-id="04846-103">この例では、楕円の円弧を描画する方法を示します。楕円の円弧を作成するには、使用、 <xref:System.Windows.Media.PathGeometry>、 <xref:System.Windows.Media.PathFigure>、および<xref:System.Windows.Media.ArcSegment>クラス。</span><span class="sxs-lookup"><span data-stu-id="04846-103">This example shows how to draw an elliptical arc. To create an elliptical arc, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.ArcSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04846-104">例</span><span class="sxs-lookup"><span data-stu-id="04846-104">Example</span></span>  
 <span data-ttu-id="04846-105">次の例では、楕円の円弧は (200, 100) に (10,100) から描画されます。</span><span class="sxs-lookup"><span data-stu-id="04846-105">In the following examples, an elliptical arc is drawn from (10,100) to (200,100).</span></span> <span data-ttu-id="04846-106">円弧が、 <xref:System.Windows.Media.ArcSegment.Size%2A> 50 で 100 デバイス非依存のピクセルの<xref:System.Windows.Media.ArcSegment.RotationAngle%2A>、45 度の<xref:System.Windows.Media.ArcSegment.IsLargeArc%2A>の設定`true`、および<xref:System.Windows.Media.ArcSegment.SweepDirection%2A>の<xref:System.Windows.Media.SweepDirection.Counterclockwise>。</span><span class="sxs-lookup"><span data-stu-id="04846-106">The arc has a <xref:System.Windows.Media.ArcSegment.Size%2A> of 100 by 50 device-independent pixels, a <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> of 45 degrees, an <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> setting of `true`, and a <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> of <xref:System.Windows.Media.SweepDirection.Counterclockwise>.</span></span>  
  
 <span data-ttu-id="04846-107">[xaml]</span><span class="sxs-lookup"><span data-stu-id="04846-107">[xaml]</span></span>  
  
 <span data-ttu-id="04846-108">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]、属性構文を使用してパスを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="04846-108">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#56](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 <span data-ttu-id="04846-109">[xaml]</span><span class="sxs-lookup"><span data-stu-id="04846-109">[xaml]</span></span>  
  
 <span data-ttu-id="04846-110">(この属性の構文が実際に作成するメモを<xref:System.Windows.Media.StreamGeometry>の軽量バージョンを<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="04846-110">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="04846-111">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="04846-111">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="04846-112">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]、明示的にオブジェクトのタグを使用して、楕円の円弧を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="04846-112">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can also draw an elliptical arc by explicitly using object tags.</span></span> <span data-ttu-id="04846-113">次に、上記に相当[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]マークアップ。</span><span class="sxs-lookup"><span data-stu-id="04846-113">The following is equivalent to the preceding [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[GeometrySample#36](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 <span data-ttu-id="04846-114">この例は、さらに大きなサンプルの一部です。</span><span class="sxs-lookup"><span data-stu-id="04846-114">This example is part of a larger sample.</span></span> <span data-ttu-id="04846-115">サンプル全体については、次を参照してください。、[ジオメトリのサンプル](https://go.microsoft.com/fwlink/?LinkID=159989)します。</span><span class="sxs-lookup"><span data-stu-id="04846-115">For the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04846-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="04846-116">See also</span></span>

- [<span data-ttu-id="04846-117">2 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="04846-117">Create a Quadratic Bezier Curve</span></span>](how-to-create-a-quadratic-bezier-curve.md)
- [<span data-ttu-id="04846-118">3 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="04846-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
