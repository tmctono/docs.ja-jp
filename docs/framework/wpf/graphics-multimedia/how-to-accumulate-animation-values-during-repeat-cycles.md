---
title: '方法: 反復サイクル中にアニメーション値を累積する'
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: bccdc9b7bf2d5a0ea476e39e8d54107854db7ae3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591468"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a><span data-ttu-id="1352b-102">方法: 反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="1352b-102">How to: Accumulate Animation Values During Repeat Cycles</span></span>
<span data-ttu-id="1352b-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティを反復サイクル中にアニメーション値を累積します。</span><span class="sxs-lookup"><span data-stu-id="1352b-103">This example shows how to use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate animation values across repeating cycles.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1352b-104">例</span><span class="sxs-lookup"><span data-stu-id="1352b-104">Example</span></span>  
 <span data-ttu-id="1352b-105">使用して、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>反復サイクル中、アニメーションの底の値を累積するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1352b-105">Use the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to accumulate base values of an animation across repeating cycles.</span></span> <span data-ttu-id="1352b-106">9 回繰り返すアニメーションを設定する場合など (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> ="9 x") 10 から 15 までアニメーション化するプロパティを設定して (から 10 を = = 15)、プロパティは、15 ~ 20 2 つ目のサイクル中に、最初のサイクル中に 10 から 15 までアニメーション化、20 ~ 25 と 3 番目のサイクル中にから。</span><span class="sxs-lookup"><span data-stu-id="1352b-106">For example, if you set an animation to repeat 9 times (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = "9x") and you set the property to animate between 10 and 15 (From = 10 To = 15), the property animates from 10 to 15 during the first cycle, from 15 to 20 during the second cycle, from 20 to 25 during the third cycle, and so on.</span></span> <span data-ttu-id="1352b-107">そのため、各アニメーション サイクルは、その基本値として前のアニメーション サイクルからの終了値を使用します。</span><span class="sxs-lookup"><span data-stu-id="1352b-107">Hence, each animation cycle uses the ending animation value from the previous animation cycle as its base value.</span></span>  
  
 <span data-ttu-id="1352b-108">使用することができます、`IsCumulative`最も基本的なアニメーションとほとんどのキー フレーム アニメーションのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="1352b-108">You can use the `IsCumulative` property with most basic animations and most key frame animations.</span></span> <span data-ttu-id="1352b-109">詳細については、次を参照してください。[アニメーションの概要](animation-overview.md)と[キー フレーム アニメーションの概要](key-frame-animations-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1352b-109">For more information, see [Animation Overview](animation-overview.md) and [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="1352b-110">次の例では、次の 4 つの四角形の幅をアニメーション化してこの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="1352b-110">The following example shows this behavior by animating the width of four rectangles.</span></span> <span data-ttu-id="1352b-111">例:</span><span class="sxs-lookup"><span data-stu-id="1352b-111">The example:</span></span>  
  
- <span data-ttu-id="1352b-112">最初の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimation>設定と、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="1352b-112">Animates the first rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="1352b-113">2 番目の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimation>設定と、<xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A>プロパティの既定値を`false`します。</span><span class="sxs-lookup"><span data-stu-id="1352b-113">Animates the second rectangle with <xref:System.Windows.Media.Animation.DoubleAnimation> and sets the <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> property to the default value of `false`.</span></span>  
  
- <span data-ttu-id="1352b-114">含む 3 番目の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>設定と、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="1352b-114">Animates the third rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `true`.</span></span>  
  
- <span data-ttu-id="1352b-115">含む最後の四角形をアニメーション化<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>設定と、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A>プロパティを`false`します。</span><span class="sxs-lookup"><span data-stu-id="1352b-115">Animates the last rectangle with <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> and sets the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> property to `false`.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1352b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1352b-116">See also</span></span>

- [<span data-ttu-id="1352b-117">アニメーションの出力値をアニメーションの開始値に追加する</span><span class="sxs-lookup"><span data-stu-id="1352b-117">Add an Animation Output Value to an Animation Starting Value</span></span>](how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [<span data-ttu-id="1352b-118">アニメーションを反復する</span><span class="sxs-lookup"><span data-stu-id="1352b-118">Repeat an Animation</span></span>](how-to-repeat-an-animation.md)
- [<span data-ttu-id="1352b-119">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="1352b-119">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="1352b-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="1352b-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="1352b-121">方法トピック</span><span class="sxs-lookup"><span data-stu-id="1352b-121">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
