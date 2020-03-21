---
title: '方法 : アニメーションを反復する'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141550"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="c617b-102">方法 : アニメーションを反復する</span><span class="sxs-lookup"><span data-stu-id="c617b-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="c617b-103">この例では、アニメーションの繰<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>り返し<xref:System.Windows.Media.Animation.Timeline>動作を制御するために、プロパティを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c617b-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c617b-104">例</span><span class="sxs-lookup"><span data-stu-id="c617b-104">Example</span></span>  
 <span data-ttu-id="c617b-105">アニメーション<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>が単純な<xref:System.Windows.Media.Animation.Timeline>継続時間を繰り返す回数をコントロールするプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c617b-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="c617b-106">を使用<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>すると、特定の<xref:System.Windows.Media.Animation.Timeline>回数 (反復回数) または指定した期間の繰り返しを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c617b-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="c617b-107">どちらの場合も、アニメーションは要求されたカウントまたは継続時間を満たすために必要な数の開始から終了までの実行を実行します。</span><span class="sxs-lookup"><span data-stu-id="c617b-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="c617b-108">デフォルトでは、タイムラインの繰り返し回数は 1.0 で、1 回再生され、繰り返しは行いません。</span><span class="sxs-lookup"><span data-stu-id="c617b-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="c617b-109">ただし、 の<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A><xref:System.Windows.Media.Animation.Timeline>プロパティを<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>に設定すると、タイムラインは無期限に繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="c617b-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="c617b-110">プロパティを使用してアニメーションの<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>繰り返し動作を制御する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c617b-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="c617b-111">この例では、異なる<xref:System.Windows.FrameworkElement.Width%2A>種類の繰り返し動作を使用して、各四角形を使用して 5 つの四角形のプロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="c617b-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="c617b-112">完全なサンプルについては、「[アニメーションタイミング動作のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c617b-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c617b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c617b-113">See also</span></span>

- [<span data-ttu-id="c617b-114">反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="c617b-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="c617b-115">タイムラインを自動的に反転するかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="c617b-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="c617b-116">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="c617b-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="c617b-117">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="c617b-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="c617b-118">アニメーションのタイミング動作のサンプル</span><span class="sxs-lookup"><span data-stu-id="c617b-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
