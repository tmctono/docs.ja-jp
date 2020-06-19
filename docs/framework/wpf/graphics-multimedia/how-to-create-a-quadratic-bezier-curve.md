---
title: '方法: 2 次ベジエ曲線を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452072"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="78c22-102">方法: 2 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="78c22-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="78c22-103">この例では、2 次ベジエ曲線を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="78c22-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="78c22-104">2 次ベジエ曲線を作成するには、<xref:System.Windows.Media.PathGeometry>、<xref:System.Windows.Media.PathFigure>、<xref:System.Windows.Media.QuadraticBezierSegment> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="78c22-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78c22-105">例</span><span class="sxs-lookup"><span data-stu-id="78c22-105">Example</span></span>  
 <span data-ttu-id="78c22-106">次の例では、(10,100) から (300,100) の 2 次ベジエ曲線が描画されます。</span><span class="sxs-lookup"><span data-stu-id="78c22-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="78c22-107">この曲線には、(200,200) の制御点があります。</span><span class="sxs-lookup"><span data-stu-id="78c22-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="78c22-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="78c22-108">[xaml]</span></span>  
  
 <span data-ttu-id="78c22-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] では、属性構文を使用してパスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="78c22-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="78c22-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="78c22-110">[xaml]</span></span>  
  
 <span data-ttu-id="78c22-111">(この属性構文では、実際には <xref:System.Windows.Media.PathGeometry> の軽量バージョンである <xref:System.Windows.Media.StreamGeometry> が作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="78c22-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="78c22-112">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="78c22-112">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="78c22-113">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] では、オブジェクト要素構文を使用して 2 次ベジエ曲線を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="78c22-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="78c22-114">次の例は、前の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="78c22-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="78c22-115">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78c22-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c22-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="78c22-116">See also</span></span>

- [<span data-ttu-id="78c22-117">楕円の円弧を作成する</span><span class="sxs-lookup"><span data-stu-id="78c22-117">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="78c22-118">3 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="78c22-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
