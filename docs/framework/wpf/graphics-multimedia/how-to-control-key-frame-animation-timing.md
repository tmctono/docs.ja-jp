---
title: '方法 : キー フレーム アニメーションのタイミングを制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344736"
---
# <a name="how-to-control-key-frame-animation-timing"></a><span data-ttu-id="d86a5-102">方法 : キー フレーム アニメーションのタイミングを制御する</span><span class="sxs-lookup"><span data-stu-id="d86a5-102">How to: Control Key-Frame Animation Timing</span></span>

<span data-ttu-id="d86a5-103">この例では、キー フレーム アニメーション内のキー フレームのタイミングを制御する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d86a5-103">This example shows how to control the timing of key frames within a key-frame animation.</span></span> <span data-ttu-id="d86a5-104">他のアニメーションと同様に、キー フレーム アニメーション<xref:System.Windows.Media.Animation.Timeline.Duration%2A>にもプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d86a5-104">Like other animations, key-frame animations have a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property.</span></span> <span data-ttu-id="d86a5-105">アニメーションの継続時間を指定するだけでなく、その期間の各キーフレームに割り当てる部分を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d86a5-105">In addition to specifying the duration of an animation, you need to specify what part of that duration is allotted to each of its key frames.</span></span> <span data-ttu-id="d86a5-106">時間を割り当てるには、アニメーション<xref:System.Windows.Media.Animation.KeyTime>の各キー フレームに 対して を指定します。</span><span class="sxs-lookup"><span data-stu-id="d86a5-106">To allot the time, you specify a <xref:System.Windows.Media.Animation.KeyTime> for each key frame in the animation.</span></span>

<span data-ttu-id="d86a5-107">各<xref:System.Windows.Media.Animation.KeyTime>キー フレームのキー フレームは、いつキー フレームが終了するかを指定します (キー フレームが再生される時間の長さは指定しません)。</span><span class="sxs-lookup"><span data-stu-id="d86a5-107">The <xref:System.Windows.Media.Animation.KeyTime> for each key frame specifies when a key frame ends (it does not specify the length of time a key frame plays).</span></span> <span data-ttu-id="d86a5-108">値<xref:System.Windows.Media.Animation.KeyTime>、<xref:System.TimeSpan>パーセント、または<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A><xref:System.Windows.Media.Animation.KeyTime.Paced%2A>特殊値として指定できます。</span><span class="sxs-lookup"><span data-stu-id="d86a5-108">You can specify a <xref:System.Windows.Media.Animation.KeyTime> as a <xref:System.TimeSpan> value, as a percentage, or as the <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> or <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> special value.</span></span>

## <a name="example"></a><span data-ttu-id="d86a5-109">例</span><span class="sxs-lookup"><span data-stu-id="d86a5-109">Example</span></span>

<span data-ttu-id="d86a5-110">次の例では、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>を使用して、画面上の四角形をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="d86a5-110">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> to animate a rectangle across the screen.</span></span> <span data-ttu-id="d86a5-111">キー フレームのキータイムは値で<xref:System.TimeSpan>設定されます。</span><span class="sxs-lookup"><span data-stu-id="d86a5-111">The key frames' key times are set with <xref:System.TimeSpan> values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

<span data-ttu-id="d86a5-112">次の図は、各キー フレームの値に達したときを示しています。</span><span class="sxs-lookup"><span data-stu-id="d86a5-112">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d86a5-113">![キー値は 3 秒、4 秒、および 10 秒です](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span><span class="sxs-lookup"><span data-stu-id="d86a5-113">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")</span></span>

<span data-ttu-id="d86a5-114">次の例では、キー フレームのキータイムがパーセンテージ値で設定される点を除いて、同一のアニメーションを示します。</span><span class="sxs-lookup"><span data-stu-id="d86a5-114">The next example shows an animation that is identical, except that the key frames' key times are set with percentage values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

<span data-ttu-id="d86a5-115">次の図は、各キー フレームの値に達したときを示しています。</span><span class="sxs-lookup"><span data-stu-id="d86a5-115">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d86a5-116">![キー値は 3 秒、4 秒、および 10 秒です](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span><span class="sxs-lookup"><span data-stu-id="d86a5-116">![Key values are reached at 3, 4, and 10 seconds](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")</span></span>

<span data-ttu-id="d86a5-117">次の例では<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>、キー時間値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d86a5-117">The next example uses <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

<span data-ttu-id="d86a5-118">次の図は、各キー フレームの値に達したときを示しています。</span><span class="sxs-lookup"><span data-stu-id="d86a5-118">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d86a5-119">![キー値は 3.3 秒、6.6 秒、および 9.9 秒です](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span><span class="sxs-lookup"><span data-stu-id="d86a5-119">![Key values are reached at 3.3,6.6, and 9.9 seconds](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")</span></span>

<span data-ttu-id="d86a5-120">最後の例では<xref:System.Windows.Media.Animation.KeyTime.Paced%2A>、キー時間値を使用します。</span><span class="sxs-lookup"><span data-stu-id="d86a5-120">The final example uses <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> key time values.</span></span>

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

<span data-ttu-id="d86a5-121">次の図は、各キー フレームの値に達したときを示しています。</span><span class="sxs-lookup"><span data-stu-id="d86a5-121">The following illustration shows when the value of each key frame is reached.</span></span>

<span data-ttu-id="d86a5-122">![キー値は 0 秒、5 秒、および 10 秒です](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span><span class="sxs-lookup"><span data-stu-id="d86a5-122">![Key values are reached at 0, 5, and 10 seconds](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")</span></span>

<span data-ttu-id="d86a5-123">わかりやすくするために、この例のコード バージョンでは、1 つのプロパティに適用されるアニメーションは 1 つだけであるため、ストーリーボードではなくローカル アニメーションが使用されますが、代わりにストーリーボードを使用するように変更できます。</span><span class="sxs-lookup"><span data-stu-id="d86a5-123">For simplicity, the code versions of this example use local animations, not storyboards, because only a single animation is being applied to a single property, but the examples may be modified to use storyboards instead.</span></span> <span data-ttu-id="d86a5-124">コードでストーリーボードを宣言する方法の例については、「[ストーリーボードを使用してプロパティをアニメーション化](how-to-animate-a-property-by-using-a-storyboard.md)する 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a5-124">For an example showing how to declare a storyboard in code, see [Animate a Property by Using a Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).</span></span>

<span data-ttu-id="d86a5-125">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a5-125">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span> <span data-ttu-id="d86a5-126">キー フレーム アニメーションの詳細については、「 キー フレーム[アニメーションの概要](key-frame-animations-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d86a5-126">For more information about key frame animations, see the [Key-Frame Animations Overview](key-frame-animations-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d86a5-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="d86a5-127">See also</span></span>

- [<span data-ttu-id="d86a5-128">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="d86a5-128">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d86a5-129">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="d86a5-129">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d86a5-130">方法のトピック</span><span class="sxs-lookup"><span data-stu-id="d86a5-130">How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
