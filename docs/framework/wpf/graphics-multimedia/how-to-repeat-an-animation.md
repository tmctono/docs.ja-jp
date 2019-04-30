---
title: '方法: アニメーションを反復する'
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
ms.openlocfilehash: a80f72b0e67c13890d4befcbd5ab7c4a92a93fe7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942091"
---
# <a name="how-to-repeat-an-animation"></a><span data-ttu-id="76acf-102">方法: アニメーションを反復する</span><span class="sxs-lookup"><span data-stu-id="76acf-102">How to: Repeat an Animation</span></span>
<span data-ttu-id="76acf-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>のプロパティを<xref:System.Windows.Media.Animation.Timeline>アニメーションの繰り返し動作を制御するためにします。</span><span class="sxs-lookup"><span data-stu-id="76acf-103">This example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> in order to control the repeat behavior of an animation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76acf-104">例</span><span class="sxs-lookup"><span data-stu-id="76acf-104">Example</span></span>  
 <span data-ttu-id="76acf-105"><xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>のプロパティを<xref:System.Windows.Media.Animation.Timeline>アニメーションは、単純継続時間を繰り返す回数を制御します。</span><span class="sxs-lookup"><span data-stu-id="76acf-105">The <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> controls how many times an animation repeats its simple duration.</span></span> <span data-ttu-id="76acf-106">使用して<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>、ことを指定できる、<xref:System.Windows.Media.Animation.Timeline>回数だけ繰り返されます (反復カウント) か、指定された期間。</span><span class="sxs-lookup"><span data-stu-id="76acf-106">By using <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, you can specify that a <xref:System.Windows.Media.Animation.Timeline> repeats for a certain number of times (an iteration count) or for a specified time period.</span></span> <span data-ttu-id="76acf-107">いずれの場合も、アニメーションは、要求されたカウントまたは期間を入力するために必要な数の先頭まで実行します。</span><span class="sxs-lookup"><span data-stu-id="76acf-107">In either case, the animation goes through as many beginning-to-end runs that it needs in order to fill the requested count or duration.</span></span>  
  
 <span data-ttu-id="76acf-108">既定では、タイムラインは 1.0 では、1 回だけ再生して繰り返さない、つまりの繰り返し回数があります。</span><span class="sxs-lookup"><span data-stu-id="76acf-108">By default, timelines have a repeat count of 1.0, which means they play one time and do not repeat.</span></span> <span data-ttu-id="76acf-109">ただし、設定した場合、<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>のプロパティを<xref:System.Windows.Media.Animation.Timeline>に<xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>タイムラインを無限に繰り返します。</span><span class="sxs-lookup"><span data-stu-id="76acf-109">However, if you set the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> to <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, the timeline repeats indefinitely.</span></span>  
  
 <span data-ttu-id="76acf-110">次の例は、使用する方法を示します、<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>プロパティ アニメーションの繰り返し動作を制御するためです。</span><span class="sxs-lookup"><span data-stu-id="76acf-110">The following example shows how to use the <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> property to control the repeat behavior of an animation.</span></span> <span data-ttu-id="76acf-111">例では、アニメーション、<xref:System.Windows.FrameworkElement.Width%2A>繰り返し動作のさまざまな型を使用して各四角形を持つ 5 つの四角形のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="76acf-111">The example animates the <xref:System.Windows.FrameworkElement.Width%2A> property of five rectangles with each rectangle using a different type of repeat behavior.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 <span data-ttu-id="76acf-112">サンプル全体については、次を参照してください。[アニメーションのタイミング動作のサンプル](https://go.microsoft.com/fwlink/?LinkID=159970)します。</span><span class="sxs-lookup"><span data-stu-id="76acf-112">For the complete sample, see [Animation Timing Behavior Sample](https://go.microsoft.com/fwlink/?LinkID=159970).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76acf-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="76acf-113">See also</span></span>

- [<span data-ttu-id="76acf-114">反復サイクル中にアニメーション値を累積する</span><span class="sxs-lookup"><span data-stu-id="76acf-114">Accumulate Animation Values During Repeat Cycles</span></span>](how-to-accumulate-animation-values-during-repeat-cycles.md)
- [<span data-ttu-id="76acf-115">タイムラインを自動的に反転するかどうかを指定する</span><span class="sxs-lookup"><span data-stu-id="76acf-115">Specify Whether a Timeline Automatically Reverses</span></span>](how-to-specify-whether-a-timeline-automatically-reverses.md)
- [<span data-ttu-id="76acf-116">アニメーションとタイミングに関するトピック</span><span class="sxs-lookup"><span data-stu-id="76acf-116">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
- [<span data-ttu-id="76acf-117">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="76acf-117">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="76acf-118">アニメーションのタイミング動作のサンプル</span><span class="sxs-lookup"><span data-stu-id="76acf-118">Animation Timing Behavior Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159970)
