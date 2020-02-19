---
title: '方法 : 放射状グラデーションを使用して領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452754"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="a8bc9-102">方法 : 放射状グラデーションを使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="a8bc9-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="a8bc9-103">この例では、<xref:System.Windows.Media.RadialGradientBrush> クラスを使用して、放射状グラデーションで領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8bc9-104">例</span><span class="sxs-lookup"><span data-stu-id="a8bc9-104">Example</span></span>  
 <span data-ttu-id="a8bc9-105">次の例では、<xref:System.Windows.Media.RadialGradientBrush> を使用して、黄色から赤、青から緑に変化する放射状グラデーションで四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="a8bc9-106">次の図は、前の例のグラデーションを示しています。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="a8bc9-107">グラデーションの分岐点が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="a8bc9-108">![放射状グラデーションでのグラデーションの分岐点](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="a8bc9-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8bc9-109">このトピックの例では、コントロールポイントを設定するための既定の座標系を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="a8bc9-110">既定の座標系は境界ボックスに対して相対的です。0は境界ボックスの0% を示し、1は境界ボックスの100% を示します。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="a8bc9-111">この座標系を変更するには、[<xref:System.Windows.Media.GradientBrush.MappingMode%2A>] プロパティを <xref:System.Windows.Media.BrushMappingMode.Absolute>の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="a8bc9-112">絶対座標系は、境界ボックスに相対しません。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="a8bc9-113">値は、ローカル空間に直接変換されます。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="a8bc9-114">その他の <xref:System.Windows.Media.RadialGradientBrush> 例については、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="a8bc9-115">グラデーションとその他の種類のブラシの詳細については、「[純色およびグラデーションによる塗りつぶしの概要](painting-with-solid-colors-and-gradients-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8bc9-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
