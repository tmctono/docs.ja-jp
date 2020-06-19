---
title: '方法: アニメーションを反復する'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: 1512c49a658c80f3ab6af652839c3562af3dd205
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141550"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="02c42-102">方法: アニメーションを反復する</span><span class="sxs-lookup"><span data-stu-id="02c42-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="02c42-103">この例では、<xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> プロパティを使用して、アニメーションの反復動作を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="02c42-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02c42-104">例</span><span class="sxs-lookup"><span data-stu-id="02c42-104">Example</span></span>  
 <span data-ttu-id="02c42-105"><xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> プロパティは、アニメーションがその単純継続時間を反復する回数を制御します。</span><span class="sxs-lookup"><span data-stu-id="02c42-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="02c42-106"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> を使用すると、特定の回数 (反復回数) または指定した期間、<xref:System.Windows.Media.Animation.Timeline> を繰り返すように指定できます。</span><span class="sxs-lookup"><span data-stu-id="02c42-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="02c42-107">いずれの場合も、アニメーションは、要求されたカウントまたは期間を満たすのに必要な回数だけ最初から最後までの実行を反復します。</span><span class="sxs-lookup"><span data-stu-id="02c42-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="02c42-108">既定では、タイムラインの反復回数は 1.0 です。これは、1 回だけ再生して繰り返さないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="02c42-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="02c42-109">ただし、<xref:System.Windows.Media.Animation.Timeline> の <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> プロパティを <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A> に設定すると、タイムラインは無期限に反復されます。</span><span class="sxs-lookup"><span data-stu-id="02c42-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="02c42-110">この例では、<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> プロパティを使用して、アニメーションの反復動作を制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="02c42-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="02c42-111">この例では、5 つの四角形の <xref:System.Windows.FrameworkElement.Width%2A> プロパティをアニメーション化し、それぞれの四角形では異なる種類の反復動作が使用されます。</span><span class="sxs-lookup"><span data-stu-id="02c42-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="02c42-112">サンプル全体については、「[アニメーションのタイミング動作のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02c42-112">For the complete sample, see [Animation Timing Behavior Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c42-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="02c42-113">See also</span></span>

- [<span data-ttu-id="02c42-114">反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="02c42-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="02c42-115">タイムラインを自動的に反転するかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="02c42-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="02c42-116">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="02c42-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="02c42-117">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="02c42-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="02c42-118">アニメーションのタイミング動作のサンプル</span><span class="sxs-lookup"><span data-stu-id="02c42-118">Animation Timing Behavior Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationTiming)
