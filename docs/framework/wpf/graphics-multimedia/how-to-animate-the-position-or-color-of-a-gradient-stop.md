---
title: '方法: グラデーション ストップの位置または色をアニメーション化する'
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
ms.openlocfilehash: eeaea4732855155bf711912644f2f5b3f5a4f8d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651364"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a><span data-ttu-id="c0ea2-102">方法: グラデーション ストップの位置または色をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="c0ea2-102">How to: Animate the Position or Color of a Gradient Stop</span></span>
<span data-ttu-id="c0ea2-103">この例は、アニメーション化する方法を示しています、<xref:System.Windows.Media.GradientStop.Color%2A>と<xref:System.Windows.Media.GradientStop.Offset%2A>の<xref:System.Windows.Media.GradientStop>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-103">This example shows how to animate the <xref:System.Windows.Media.GradientStop.Color%2A> and <xref:System.Windows.Media.GradientStop.Offset%2A> of <xref:System.Windows.Media.GradientStop> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0ea2-104">例</span><span class="sxs-lookup"><span data-stu-id="c0ea2-104">Example</span></span>  
 <span data-ttu-id="c0ea2-105">次の例では、アニメーション内の 3 つのグラデーションの分岐点を<xref:System.Windows.Media.LinearGradientBrush>します。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-105">The following example animates three gradient stops inside a <xref:System.Windows.Media.LinearGradientBrush>.</span></span> <span data-ttu-id="c0ea2-106">例では、さまざまなグラデーションの分岐点をアニメーション化の 3 つのアニメーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-106">The example uses three animations, each of which animates a different gradient stop:</span></span>  
  
- <span data-ttu-id="c0ea2-107">最初のアニメーションを<xref:System.Windows.Media.Animation.DoubleAnimation>、アニメーションの最初のグラデーションの<xref:System.Windows.Media.GradientStop.Offset%2A>0.0 ~ 1.0 0.0 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-107">The first animation, a <xref:System.Windows.Media.Animation.DoubleAnimation>, animates the first gradient stop's <xref:System.Windows.Media.GradientStop.Offset%2A> from 0.0 to 1.0 and then back to 0.0.</span></span> <span data-ttu-id="c0ea2-108">その結果、最初の色の四角形の右側にあるを左側にあるグラデーション シフトで、左側に戻ります。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-108">As a result, the first color in the gradient shifts from the left side to the right side of the rectangle and then back to the left side.</span></span>  
  
- <span data-ttu-id="c0ea2-109">2 番目のアニメーションを<xref:System.Windows.Media.Animation.ColorAnimation>、2 番目のグラデーションのアニメーション化<xref:System.Windows.Media.GradientStop.Color%2A>から<xref:System.Windows.Media.Colors.Purple%2A>に<xref:System.Windows.Media.Colors.Yellow%2A>に再び<xref:System.Windows.Media.Colors.Purple%2A>します。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-109">The second animation, a <xref:System.Windows.Media.Animation.ColorAnimation>, animates the second gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> from <xref:System.Windows.Media.Colors.Purple%2A> to <xref:System.Windows.Media.Colors.Yellow%2A> and then back to <xref:System.Windows.Media.Colors.Purple%2A>.</span></span> <span data-ttu-id="c0ea2-110">その結果、黄色および紫へ、グラデーションの中間色を表すは紫から変更します。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-110">As a result, the middle color in the gradient changes from purple to yellow and back to purple.</span></span>  
  
- <span data-ttu-id="c0ea2-111">3 番目のアニメーションでは、もう 1 つ<xref:System.Windows.Media.Animation.ColorAnimation>、3 番目のグラデーション ストップの不透明度をアニメーション化<xref:System.Windows.Media.GradientStop.Color%2A>-1 で戻ります。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-111">The third animation, another <xref:System.Windows.Media.Animation.ColorAnimation>, animates the opacity of the third gradient stop's <xref:System.Windows.Media.GradientStop.Color%2A> by -1 and then back.</span></span> <span data-ttu-id="c0ea2-112">その結果、3 番目の色、グラデーションはフェードアウトし、し、再び不透明になります。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-112">As a result, the third color in the gradient fades away and then becomes opaque again.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 <span data-ttu-id="c0ea2-113">この例では、 <xref:System.Windows.Media.LinearGradientBrush>、プロセスは、アニメーション化するため同じ<xref:System.Windows.Media.GradientStop>内でオブジェクトを<xref:System.Windows.Media.RadialGradientBrush>します。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-113">Although this example uses a <xref:System.Windows.Media.LinearGradientBrush>, the process is the same for animating <xref:System.Windows.Media.GradientStop> objects inside a <xref:System.Windows.Media.RadialGradientBrush>.</span></span>  
  
 <span data-ttu-id="c0ea2-114">その他の例では、次を参照してください。、[ブラシのサンプル](https://go.microsoft.com/fwlink/?LinkID=159973)します。</span><span class="sxs-lookup"><span data-stu-id="c0ea2-114">For additional examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ea2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0ea2-115">See also</span></span>

- <xref:System.Windows.Media.GradientStop>
- [<span data-ttu-id="c0ea2-116">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="c0ea2-116">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c0ea2-117">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="c0ea2-117">Storyboards Overview</span></span>](storyboards-overview.md)
