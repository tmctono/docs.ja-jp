---
title: '方法 : アクティブな期間の末尾に到達したタイムラインの FillBehavior を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
ms.openlocfilehash: 1f54f2c1bb49bb7a0301f112a109194ab1a8658e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141174"
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="64e52-102">方法 : アクティブな期間の末尾に到達したタイムラインの FillBehavior を指定する</span><span class="sxs-lookup"><span data-stu-id="64e52-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="64e52-103">次の<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>例は、アニメーション化されたプロパティの非<xref:System.Windows.Media.Animation.Timeline>アクティブの を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64e52-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64e52-104">例</span><span class="sxs-lookup"><span data-stu-id="64e52-104">Example</span></span>  
 <span data-ttu-id="64e52-105">a<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A><xref:System.Windows.Media.Animation.Timeline>のプロパティは、アニメーション化されていない場合、つまり、アニメーション化されていない場合、つまり、アクティブでないが親<xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.Timeline>がアクティブまたは保持期間内にある場合に、アニメーション化されたプロパティの値に対して何が起こるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="64e52-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="64e52-106">たとえば、アニメーションプロパティは、アニメーションの終了後も終了値に留まるのか、アニメーションが開始される前の値に戻るのか。</span><span class="sxs-lookup"><span data-stu-id="64e52-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="64e52-107">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimation>を使用して<xref:System.Windows.FrameworkElement.Width%2A>2 つの四角形のアニメーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="64e52-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="64e52-108">各四角形は、<xref:System.Windows.Media.Animation.Timeline>異なるオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="64e52-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="64e52-109">1 つは<xref:System.Windows.Media.Animation.Timeline><xref:System.Windows.Media.Animation.FillBehavior.Stop>に設定されており、終了すると、四角形の幅がアニメーション化されていない値に戻ります<xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A></span><span class="sxs-lookup"><span data-stu-id="64e52-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="64e52-110">もう<xref:System.Windows.Media.Animation.Timeline>1<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>つは<xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>、 のが含まれており、終了すると幅は終了値<xref:System.Windows.Media.Animation.Timeline>に留まる。</span><span class="sxs-lookup"><span data-stu-id="64e52-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="64e52-111">完全なサンプルについては、「[アニメーションの例ギャラリー](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64e52-111">For the complete sample, see [Animation Example Gallery](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e52-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="64e52-112">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimation>
- <xref:System.Windows.FrameworkElement.Width%2A>
- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>
- <xref:System.Windows.Media.Animation.FillBehavior.Stop>
- <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>
- [<span data-ttu-id="64e52-113">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="64e52-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="64e52-114">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="64e52-114">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
