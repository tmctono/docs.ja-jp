---
title: '方法 : 2 次ベジエ曲線を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- Bezier curves [WPF], creating
- quadratic Bezier curves [WPF], creating
- graphics [WPF], quadratic Bezier curves
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
ms.openlocfilehash: caaf967b7cb5447d86dd031beeb16195413b0393
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452072"
---
# <a name="how-to-create-a-quadratic-bezier-curve"></a><span data-ttu-id="f1df4-102">方法 : 2 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="f1df4-102">How to: Create a Quadratic Bezier Curve</span></span>
<span data-ttu-id="f1df4-103">次の例では、2次ベジエ曲線を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f1df4-103">This example shows how to create a quadratic Bezier curve.</span></span>  <span data-ttu-id="f1df4-104">2次ベジエ曲線を作成するには、<xref:System.Windows.Media.PathGeometry>、<xref:System.Windows.Media.PathFigure>、および <xref:System.Windows.Media.QuadraticBezierSegment> クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1df4-104">To create a quadratic Bezier curve, use the <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure>, and <xref:System.Windows.Media.QuadraticBezierSegment> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1df4-105">例</span><span class="sxs-lookup"><span data-stu-id="f1df4-105">Example</span></span>  
 <span data-ttu-id="f1df4-106">次の例では、2次ベジエ曲線を (10100) から (300100) に描画しています。</span><span class="sxs-lookup"><span data-stu-id="f1df4-106">In the following examples, a quadratic Bezier curve is drawn from (10,100) to (300,100).</span></span> <span data-ttu-id="f1df4-107">曲線の制御点は (200200) です。</span><span class="sxs-lookup"><span data-stu-id="f1df4-107">The curve has a control point of (200,200).</span></span>  
  
 <span data-ttu-id="f1df4-108">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f1df4-108">[xaml]</span></span>  
  
 <span data-ttu-id="f1df4-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]では、属性構文を使用してパスを記述できます。</span><span class="sxs-lookup"><span data-stu-id="f1df4-109">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you can use attribute syntax to describe a path.</span></span>  
  
 [!code-xaml[GeometrySample#54](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 <span data-ttu-id="f1df4-110">[xaml]</span><span class="sxs-lookup"><span data-stu-id="f1df4-110">[xaml]</span></span>  
  
 <span data-ttu-id="f1df4-111">(この属性構文では、実際には <xref:System.Windows.Media.PathGeometry>の軽量バージョンである <xref:System.Windows.Media.StreamGeometry>が作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1df4-111">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f1df4-112">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="f1df4-112">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
 <span data-ttu-id="f1df4-113">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]では、オブジェクト要素構文を使用して2次ベジエ曲線を描画することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1df4-113">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you may also draw a quadratic Bezier curve using object element syntax.</span></span> <span data-ttu-id="f1df4-114">次の例は、前の [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の例と同じです。</span><span class="sxs-lookup"><span data-stu-id="f1df4-114">The following is equivalent to the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example.</span></span>  
  
 [!code-xaml[GeometrySample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="f1df4-115">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1df4-115">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1df4-116">参照</span><span class="sxs-lookup"><span data-stu-id="f1df4-116">See also</span></span>

- [<span data-ttu-id="f1df4-117">楕円の円弧を作成する</span><span class="sxs-lookup"><span data-stu-id="f1df4-117">Create an Elliptical Arc</span></span>](how-to-create-an-elliptical-arc.md)
- [<span data-ttu-id="f1df4-118">3 次ベジエ曲線を作成する</span><span class="sxs-lookup"><span data-stu-id="f1df4-118">Create a Cubic Bezier Curve</span></span>](how-to-create-a-cubic-bezier-curve.md)
