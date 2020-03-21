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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186500"
---
# <a name="easing-functions"></a><span data-ttu-id="6cd82-102">イージング関数</span><span class="sxs-lookup"><span data-stu-id="6cd82-102">Easing Functions</span></span>
<span data-ttu-id="6cd82-103">イージング関数を使うと、独自の数式をアニメーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="6cd82-104">たとえば、オブジェクトをリアルにバウンドさせたり、バネに乗っているように動作させたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="6cd82-105">キー フレーム アニメーションや From/To/By アニメーションを使ってこれらの効果を近似することもできますが、大量の作業が必要であり、アニメーションは数式を使うほど正確ではありません。</span><span class="sxs-lookup"><span data-stu-id="6cd82-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="6cd82-106">継承<xref:System.Windows.Media.Animation.EasingFunctionBase>によって独自のカスタム イージング関数を作成する以外に、ランタイムによって提供される複数のイージング関数のいずれかを使用して、共通の効果を作成できます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
- <span data-ttu-id="6cd82-107"><xref:System.Windows.Media.Animation.BackEase>: アニメーションの動きを少し後退してから、指定されたパスでアニメーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
- <span data-ttu-id="6cd82-108"><xref:System.Windows.Media.Animation.BounceEase>: バウンス効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
- <span data-ttu-id="6cd82-109"><xref:System.Windows.Media.Animation.CircleEase>: 円形関数を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
- <span data-ttu-id="6cd82-110"><xref:System.Windows.Media.Animation.CubicEase>: *f*(*t*) = *t*<sup>3</sup>を使用して加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
- <span data-ttu-id="6cd82-111"><xref:System.Windows.Media.Animation.ElasticEase>: 休むまで前後に振動するばねのようなアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
- <span data-ttu-id="6cd82-112"><xref:System.Windows.Media.Animation.ExponentialEase>: 指数式を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
- <span data-ttu-id="6cd82-113"><xref:System.Windows.Media.Animation.PowerEase>: p がプロパティに等しい場合に式*f*(*t*) = *t*<sup>p</sup>を使用して<xref:System.Windows.Media.Animation.PowerEase.Power%2A>加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
- <span data-ttu-id="6cd82-114"><xref:System.Windows.Media.Animation.QuadraticEase>: *f*(*t*) = *t*<sup>2</sup>を使用して加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
- <span data-ttu-id="6cd82-115"><xref:System.Windows.Media.Animation.QuarticEase>: *f*(*t*) = *t*<sup>4</sup>を使用して加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
- <span data-ttu-id="6cd82-116"><xref:System.Windows.Media.Animation.QuinticEase>: *f*(*t*) = *t*<sup>5</sup>を使用して加速および減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
- <span data-ttu-id="6cd82-117"><xref:System.Windows.Media.Animation.SineEase>: sine 式を使用して加速または減速するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="6cd82-118">アニメーションにイージング関数を適用するには、アニメーションの`EasingFunction`プロパティを使用して、アニメーションに適用するイージング関数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-118">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="6cd82-119">次の例では、<xref:System.Windows.Media.Animation.BounceEase>イージング関数を<xref:System.Windows.Media.Animation.DoubleAnimation>に適用して、バウンス効果を作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-119">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="6cd82-120">前の例では、イージング関数を From/To/By アニメーションに適用しました。</span><span class="sxs-lookup"><span data-stu-id="6cd82-120">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="6cd82-121">キー フレーム アニメーションにこれらのイージング関数を適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-121">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="6cd82-122">次の例では、キー フレームとそれらに関連付けられたイージング関数を使って、四角形が上方に縮まり、遅くなり、下方に延び (落下するように)、停止するアニメーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-122">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="6cd82-123">このプロパティを<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>使用して、イージング関数の動作を変更したり、アニメーションの補間方法を変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-123">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="6cd82-124">次の 3 つの値を指定<xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>できます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-124">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
- <span data-ttu-id="6cd82-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: 補間はイージング関数に関連付けられた数式に従います。</span><span class="sxs-lookup"><span data-stu-id="6cd82-125"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="6cd82-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: 補間は、100% の補間からイージング関数に関連付けられた数式の出力を引いた値です。</span><span class="sxs-lookup"><span data-stu-id="6cd82-126"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
- <span data-ttu-id="6cd82-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: 補間は<xref:System.Windows.Media.Animation.EasingMode.EaseIn>、アニメーションの前半と<xref:System.Windows.Media.Animation.EasingMode.EaseOut>後半に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-127"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="6cd82-128">以下のグラフは *、f*( <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> *x*) がアニメーションの進行状況を表し *、t*が時間を表す場所の値を示しています。</span><span class="sxs-lookup"><span data-stu-id="6cd82-128">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="6cd82-129">![BackEase EasingMode のグラフ。](./media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-129">![BackEase EasingMode graphs.](./media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="6cd82-130">![BounceEase EasingMode のグラフ](./media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-130">![BounceEase EasingMode graphs.](./media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="6cd82-131">![CircleEase EasingMode のグラフ](./media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-131">![CircleEase EasingMode graphs.](./media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="6cd82-132">![CubicEase EasingMode のグラフ](./media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-132">![CubicEase EasingMode graphs.](./media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="6cd82-133">![異なる EasingMode の ElasticEase のグラフ](./media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-133">![ElasticEase with graphs of different easingmodes.](./media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="6cd82-134">![異なる EasingMode の ExponentialEase のグラフ。](./media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-134">![ExponentialEase graphs of different easingmodes.](./media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="6cd82-135">![異なる EasingMode の QuarticEase のグラフ](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-135">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="6cd82-136">![異なるイージングモードのグラフで二次的な動作](./media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-136">![QuadraticEase with graphs of different easingmodes](./media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="6cd82-137">![異なる EasingMode の QuarticEase のグラフ](./media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-137">![QuarticEase with graphs of different easingmodes.](./media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="6cd82-138">![異なる EasingMode の QuinticEase のグラフ](./media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-138">![QuinticEase with graphs of different easingmodes.](./media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="6cd82-139">![異なる EasingMode 値の SineEase](./media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="6cd82-139">![SineEase for different EasingMode values](./media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6cd82-140">プロパティを使用<xref:System.Windows.Media.Animation.PowerEase>して<xref:System.Windows.Media.Animation.CubicEase>、 、 <xref:System.Windows.Media.Animation.QuadraticEase>、および<xref:System.Windows.Media.Animation.QuarticEase>と<xref:System.Windows.Media.Animation.QuinticEase>同じ動作を<xref:System.Windows.Media.Animation.PowerEase.Power%2A>作成できます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-140">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="6cd82-141">たとえば、<xref:System.Windows.Media.Animation.PowerEase><xref:System.Windows.Media.Animation.CubicEase>を使用して を置換する場合は、値<xref:System.Windows.Media.Animation.PowerEase.Power%2A>3 を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-141">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="6cd82-142">ランタイムに含まれるイージング関数を使用するだけでなく、 から<xref:System.Windows.Media.Animation.EasingFunctionBase>継承して独自のカスタム イージング関数を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-142">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="6cd82-143">次の例では、簡単なカスタム イージング関数を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6cd82-143">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="6cd82-144">メソッドをオーバーライドすることで、イージング関数の動作に関する独自の数学ロジックを<xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A>追加できます。</span><span class="sxs-lookup"><span data-stu-id="6cd82-144">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
