---
title: イージング関数
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: 72118711dfd40ad8c665157e09f01c60085db903
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965732"
---
# <a name="easing-functions"></a><span data-ttu-id="70842-102">イージング関数</span><span class="sxs-lookup"><span data-stu-id="70842-102">Easing Functions</span></span>
<span data-ttu-id="70842-103">イージング関数を使うと、独自の数式をアニメーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="70842-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="70842-104">たとえば、オブジェクトをリアルにバウンドさせたり、バネに乗っているように動作させたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="70842-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="70842-105">キー フレーム アニメーションや From/To/By アニメーションを使ってこれらの効果を近似することもできますが、大量の作業が必要であり、アニメーションは数式を使うほど正確ではありません。</span><span class="sxs-lookup"><span data-stu-id="70842-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="70842-106">から<xref:System.Windows.Media.Animation.EasingFunctionBase>継承することによって独自のカスタムイージング関数を作成するだけでなく、ランタイムによって提供されるいくつかのイージング関数の1つを使用して、一般的な効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="70842-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="70842-107"><xref:System.Windows.Media.Animation.BackEase> :指定されたパスでアニメーション化を開始する前に、アニメーションのモーションを少し取り消します。</span><span class="sxs-lookup"><span data-stu-id="70842-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="70842-108"><xref:System.Windows.Media.Animation.BounceEase>:バウンス効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="70842-109"><xref:System.Windows.Media.Animation.CircleEase> :循環関数を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="70842-110"><xref:System.Windows.Media.Animation.CubicEase> :数式*f*(*t*) = *t*<sup>3</sup>を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="70842-111"><xref:System.Windows.Media.Animation.ElasticEase>:残りの部分に戻るまで、スプリングの不安定さに似たアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="70842-112"><xref:System.Windows.Media.Animation.ExponentialEase> :指数式を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="70842-113"><xref:System.Windows.Media.Animation.PowerEase> :式*f*(*t*) = *t*<sup>p</sup> (p が<xref:System.Windows.Media.Animation.PowerEase.Power%2A>プロパティと等しい) を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="70842-114"><xref:System.Windows.Media.Animation.QuadraticEase>:数式*f*(*t*) = *t*<sup>2</sup>を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="70842-115"><xref:System.Windows.Media.Animation.QuarticEase>:数式*f*(*t*) = *t*<sup>4</sup>を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="70842-116"><xref:System.Windows.Media.Animation.QuinticEase>:数式*f*(*t*) = *t*<sup>5</sup>を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="70842-117"><xref:System.Windows.Media.Animation.SineEase>:サイン式を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="70842-118">イージング関数をアニメーションに適用するには、アニメーション`EasingFunction`のプロパティを使用して、アニメーションに適用するイージング関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="70842-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="70842-119">次の例では<xref:System.Windows.Media.Animation.BounceEase> 、にイージング関数<xref:System.Windows.Media.Animation.DoubleAnimation>を適用して、バウンス効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="70842-120">前の例では、イージング関数を From/To/By アニメーションに適用しました。</span><span class="sxs-lookup"><span data-stu-id="70842-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="70842-121">キー フレーム アニメーションにこれらのイージング関数を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="70842-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="70842-122">次の例では、キー フレームとそれらに関連付けられたイージング関数を使って、四角形が上方に縮まり、遅くなり、下方に延び (落下するように)、停止するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70842-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="70842-123"><xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>プロパティを使用して、イージング関数の動作方法を変更したり、アニメーションの補間方法を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="70842-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="70842-124">次の3つの値を<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>指定できます。</span><span class="sxs-lookup"><span data-stu-id="70842-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="70842-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>:補間は、イージング関数に関連付けられている数式に従います。</span><span class="sxs-lookup"><span data-stu-id="70842-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="70842-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>:補間は、イージング関数に関連付けられた数式の出力を差し引いた 100% 補間に従います。</span><span class="sxs-lookup"><span data-stu-id="70842-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="70842-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>:補間<xref:System.Windows.Media.Animation.EasingMode.EaseIn>は、アニメーションの最初の半分と<xref:System.Windows.Media.Animation.EasingMode.EaseOut> 2 番目の半分に使用されます。</span><span class="sxs-lookup"><span data-stu-id="70842-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="70842-128">次<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>のグラフでは、 *f*(*x*) がアニメーションの進行状況を表し、 *t*が時間を表すという異なる値を示しています。</span><span class="sxs-lookup"><span data-stu-id="70842-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="70842-129">![BackEase EasingMode のグラフ。](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="70842-130">![BounceEase EasingMode のグラフ。](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="70842-131">![CircleEase EasingMode のグラフ。](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="70842-132">![CubicEase EasingMode のグラフ。](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="70842-133">![異なる EasingMode の ElasticEase のグラフ。](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="70842-134">![異なる EasingMode の ExponentialEase のグラフ。](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="70842-135">![異なる EasingMode の QuarticEase のグラフ。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="70842-136">![異なる EasingMode の QuadraticEase のグラフ。](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="70842-137">![異なる EasingMode の QuarticEase のグラフ。](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="70842-138">![異なる EasingMode の QuinticEase のグラフ。](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="70842-139">![異なる EasingMode 値の SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="70842-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70842-140">を使用<xref:System.Windows.Media.Animation.PowerEase>すると<xref:System.Windows.Media.Animation.QuadraticEase> <xref:System.Windows.Media.Animation.QuinticEase> 、プロパティを<xref:System.Windows.Media.Animation.PowerEase.Power%2A>使用して、、、およびと同じ動作を作成できます。 <xref:System.Windows.Media.Animation.QuarticEase> <xref:System.Windows.Media.Animation.CubicEase></span><span class="sxs-lookup"><span data-stu-id="70842-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="70842-141">たとえば、を使用しての<xref:System.Windows.Media.Animation.PowerEase> <xref:System.Windows.Media.Animation.CubicEase>代わりにを使用する場合は<xref:System.Windows.Media.Animation.PowerEase.Power%2A> 、値を3に指定します。</span><span class="sxs-lookup"><span data-stu-id="70842-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="70842-142">ランタイムに含まれるイージング関数を使用するだけでなく、から継承することで、独自の<xref:System.Windows.Media.Animation.EasingFunctionBase>カスタムイージング関数を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="70842-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="70842-143">次の例では、簡単なカスタム イージング関数を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="70842-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="70842-144"><xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>メソッドをオーバーライドすることにより、イージング関数の動作について独自の数学的ロジックを追加できます。</span><span class="sxs-lookup"><span data-stu-id="70842-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
