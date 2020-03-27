---
title: '方法 : キー フレームを使用して Double 値をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344929"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="67258-102">方法 : キー フレームを使用して Double 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="67258-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="67258-103">この例では、キー フレームを使用<xref:System.Double>して を取得するプロパティの値をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="67258-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67258-104">例</span><span class="sxs-lookup"><span data-stu-id="67258-104">Example</span></span>  
 <span data-ttu-id="67258-105">次の例では、画面を横切るように四角形を移動します。</span><span class="sxs-lookup"><span data-stu-id="67258-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="67258-106">この例では、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>このクラスを使用して、<xref:System.Windows.Media.TranslateTransform.X%2A>に適用<xref:System.Windows.Media.TranslateTransform>される プロパティ<xref:System.Windows.Shapes.Rectangle>をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="67258-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="67258-107">無期限に繰り返すこのアニメーションでは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="67258-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="67258-108">最初の 3 秒間に、クラスのインスタンス<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>を使用して、開始位置から 500 の位置に、パスに沿って四角形を安定した速度で移動します。</span><span class="sxs-lookup"><span data-stu-id="67258-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="67258-109">線形キー フレーム<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>のような値間のスムーズな直線遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="67258-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="67258-110">4 秒目の終わりには、クラスのインスタンスを<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>使用して、突然四角形を次の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="67258-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="67258-111">値の間に<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>突然ジャンプを作成するような離散的なキー フレーム。</span><span class="sxs-lookup"><span data-stu-id="67258-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="67258-112">この例では、開始位置にあった四角形が突然 500 の位置に出現します。</span><span class="sxs-lookup"><span data-stu-id="67258-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3. <span data-ttu-id="67258-113">最後の 2 秒で、クラスのインスタンス<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>を使用して、四角形を開始位置に戻します。</span><span class="sxs-lookup"><span data-stu-id="67258-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="67258-114">スプライン キー<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>フレームのような値の間に、プロパティの値に従<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>った可変的な遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="67258-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="67258-115">この例では、四角形の動きは最初はゆっくりしていますが、時間セグメントの終点に向かった急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="67258-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="67258-116">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67258-116">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
 <span data-ttu-id="67258-117">他のアニメーションの例との一貫性を保つために、この例<xref:System.Windows.Media.Animation.Storyboard>のコード バージョン<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>ではオブジェクトを使用して を適用します。</span><span class="sxs-lookup"><span data-stu-id="67258-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="67258-118">または、コード内で単一のアニメーションを適用する場合は、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A><xref:System.Windows.Media.Animation.Storyboard>メソッドを使用する代わりに、より簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="67258-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="67258-119">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67258-119">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67258-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="67258-120">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [<span data-ttu-id="67258-121">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="67258-121">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="67258-122">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="67258-122">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
