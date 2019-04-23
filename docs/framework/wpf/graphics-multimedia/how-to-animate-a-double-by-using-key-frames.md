---
title: '方法: キー フレームを使用して Double 値をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 73cbeab8aee566313bad8e8a18a5500374287de0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305586"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="4f0e7-102">方法: キー フレームを使用して Double 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="4f0e7-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="4f0e7-103">この例を受け取るプロパティの値をアニメーション化する方法を示しています、<xref:System.Double>キー フレームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f0e7-104">例</span><span class="sxs-lookup"><span data-stu-id="4f0e7-104">Example</span></span>  
 <span data-ttu-id="4f0e7-105">次の例では、画面を横切るように四角形を移動します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="4f0e7-106">この例では、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Media.TranslateTransform.X%2A>のプロパティを<xref:System.Windows.Media.TranslateTransform>に適用される、 <xref:System.Windows.Shapes.Rectangle>。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="4f0e7-107">無期限に繰り返すこのアニメーションでは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="4f0e7-108">最初の 3 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>クラス パスに沿った四角形の開始位置からの一定の速度で 500 の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="4f0e7-109">などの線形キーフレーム<xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>値の間の滑らかな線形トランジションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="4f0e7-110">4 番目の 2 つ目の末尾にはのインスタンスを使用して、<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>クラスに次の位置に突然四角形を移動します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="4f0e7-111">などの不連続のキーフレーム<xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>値の間に急なジャンプを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="4f0e7-112">この例では、開始位置にあった四角形が突然 500 の位置に出現します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3. <span data-ttu-id="4f0e7-113">最後の 2 秒では、インスタンスを使用して、<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>クラスに四角形を開始位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="4f0e7-114">スプライン キー フレームのような<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>の値に基づいて値の間に可変遷移を作成、<xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="4f0e7-115">この例では、四角形の動きは最初はゆっくりしていますが、時間セグメントの終点に向かった急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="4f0e7-116">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-116">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="4f0e7-117">この例のコードを使用して、他のアニメーション例と一貫性を保つのため、<xref:System.Windows.Media.Animation.Storyboard>を適用するオブジェクト、<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="4f0e7-118">または、コード内で 1 つのアニメーションを適用する場合は簡単に使用、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッドを使用してではなく、<xref:System.Windows.Media.Animation.Storyboard>します。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="4f0e7-119">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f0e7-119">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0e7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f0e7-120">See also</span></span>

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [<span data-ttu-id="4f0e7-121">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="4f0e7-121">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="4f0e7-122">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="4f0e7-122">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
