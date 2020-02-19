---
title: '方法 : グラデーション ストップの位置または色をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452845"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="692aa-102">方法 : グラデーション ストップの位置または色をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="692aa-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="692aa-103">この例では、<xref:System.Windows.Media.GradientStop> オブジェクトの <xref:System.Windows.Media.GradientStop.Color%2A> と <xref:System.Windows.Media.GradientStop.Offset%2A> をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="692aa-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="692aa-104">例</span><span class="sxs-lookup"><span data-stu-id="692aa-104">Example</span></span>  
 <span data-ttu-id="692aa-105">次の例では、<xref:System.Windows.Media.LinearGradientBrush>内の3つのグラデーションの分岐点をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="692aa-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="692aa-106">この例では、3つのアニメーションを使用して、それぞれ異なるグラデーションの分岐点をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="692aa-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="692aa-107">最初のアニメーション (<xref:System.Windows.Media.Animation.DoubleAnimation>) では、最初のグラデーションの分岐点の <xref:System.Windows.Media.GradientStop.Offset%2A> を0.0 から1.0 に、次に0.0 に戻します。</span><span class="sxs-lookup"><span data-stu-id="692aa-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="692aa-108">その結果、グラデーションの最初の色が四角形の左側から右側に移動し、次に左側に戻ります。</span><span class="sxs-lookup"><span data-stu-id="692aa-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="692aa-109">2番目のアニメーション (<xref:System.Windows.Media.Animation.ColorAnimation>) では、2番目のグラデーション分岐点の <xref:System.Windows.Media.GradientStop.Color%2A> を <xref:System.Windows.Media.Colors.Purple%2A> から <xref:System.Windows.Media.Colors.Yellow%2A>、<xref:System.Windows.Media.Colors.Purple%2A>に戻します。</span><span class="sxs-lookup"><span data-stu-id="692aa-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="692aa-110">その結果、グラデーションの中間色は紫色から黄色に変わり、紫色に戻ります。</span><span class="sxs-lookup"><span data-stu-id="692aa-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="692aa-111">3番目のアニメーション (もう1つの <xref:System.Windows.Media.Animation.ColorAnimation>) は、3番目のグラデーション分岐点の不透明度を-1 で <xref:System.Windows.Media.GradientStop.Color%2A> し、次に戻るようにアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="692aa-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="692aa-112">その結果、グラデーションの3番目の色が消え、もう一度不透明になります。</span><span class="sxs-lookup"><span data-stu-id="692aa-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="692aa-113">この例では <xref:System.Windows.Media.LinearGradientBrush>を使用しますが、プロセスは <xref:System.Windows.Media.RadialGradientBrush>内の <xref:System.Windows.Media.GradientStop> オブジェクトをアニメーション化する場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="692aa-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="692aa-114">その他の例については、「[ブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="692aa-114">For additional examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="692aa-115">参照</span><span class="sxs-lookup"><span data-stu-id="692aa-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="692aa-116">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="692aa-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="692aa-117">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="692aa-117">Storyboards Overview</span></span>](storyboards-overview.md)
