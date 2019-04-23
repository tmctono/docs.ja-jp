---
title: '方法: アニメーションの継続時間を設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
ms.openlocfilehash: bdae1689ffeb8c54d756b9debbd26d57a052892d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198791"
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="ca844-102">方法: アニメーションの継続時間を設定する</span><span class="sxs-lookup"><span data-stu-id="ca844-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="ca844-103">A<xref:System.Windows.Media.Animation.Timeline>表す時間のセグメントとそのセグメントの長さはタイムラインのによって決まります<xref:System.Windows.Duration>します。</span><span class="sxs-lookup"><span data-stu-id="ca844-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="ca844-104">ときに、<xref:System.Windows.Media.Animation.Timeline>が最後に達すると、その継続時間の再生を停止します。</span><span class="sxs-lookup"><span data-stu-id="ca844-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="ca844-105">場合、<xref:System.Windows.Media.Animation.Timeline>が子タイムラインも再生を停止します。</span><span class="sxs-lookup"><span data-stu-id="ca844-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="ca844-106">アニメーションの場合は、<xref:System.Windows.Duration>アニメーションにかかる時間の遷移の終了値をその開始値から指定します。</span><span class="sxs-lookup"><span data-stu-id="ca844-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="ca844-107">指定することができます、 <xref:System.Windows.Duration> 、有限の特定の時間または特殊な値を持つ<xref:System.Windows.Duration.Automatic%2A>または<xref:System.Windows.Duration.Forever%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ca844-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="ca844-108">アニメーションが定義されている、有限の長さを持つ必要がありますので、アニメーションの継続時間は、時刻の値をある常に必要があります、それ以外の場合、アニメーションには、ターゲット値の間に移行する方法が不明です。</span><span class="sxs-lookup"><span data-stu-id="ca844-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="ca844-109">コンテナー タイムライン (<xref:System.Windows.Media.Animation.TimelineGroup>オブジェクト) など<xref:System.Windows.Media.Animation.Storyboard>と<xref:System.Windows.Media.Animation.ParallelTimeline>の既定の時間が指定されて<xref:System.Windows.Duration.Automatic%2A>、つまり、これらは、最後の子が停止したときに自動的に終了します。</span><span class="sxs-lookup"><span data-stu-id="ca844-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="ca844-110">次の例、幅、高さ、および塗りつぶしの色で、<xref:System.Windows.Shapes.Rectangle>がアニメーション化されます。</span><span class="sxs-lookup"><span data-stu-id="ca844-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="ca844-111">期間は、結果として認識されるアニメーションの速度を制御して、コンテナー タイムラインの存続期間を持つ子タイムラインの期間のオーバーライドを含むアニメーション効果アニメーションとコンテナーのタイムラインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca844-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca844-112">例</span><span class="sxs-lookup"><span data-stu-id="ca844-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ca844-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca844-113">See also</span></span>

- <xref:System.Windows.Duration>
- [<span data-ttu-id="ca844-114">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="ca844-114">Animation Overview</span></span>](animation-overview.md)
