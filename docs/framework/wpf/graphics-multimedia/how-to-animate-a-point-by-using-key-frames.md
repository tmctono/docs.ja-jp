---
title: '方法: キー フレームを使用して点をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: b706568a0e8221aac737780592882f728f0f9e9c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328778"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a><span data-ttu-id="f48f6-102">方法: キー フレームを使用して点をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="f48f6-102">How to: Animate a Point by Using Key Frames</span></span>
<span data-ttu-id="f48f6-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Point>します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate a <xref:System.Windows.Point>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f48f6-104">例</span><span class="sxs-lookup"><span data-stu-id="f48f6-104">Example</span></span>  
 <span data-ttu-id="f48f6-105">次の例では、三角形のパスに沿って楕円を移動します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-105">The following example moves an ellipse along a triangular path.</span></span> <span data-ttu-id="f48f6-106">この例では、<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Media.EllipseGeometry.Center%2A>のプロパティ、<xref:System.Windows.Media.EllipseGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-106">The example uses the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property of an <xref:System.Windows.Media.EllipseGeometry>.</span></span> <span data-ttu-id="f48f6-107">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-107">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="f48f6-108">最初の 0.5 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.LinearPointKeyFrame>一定の速度で開始位置からパスに沿って楕円を移動するクラス。</span><span class="sxs-lookup"><span data-stu-id="f48f6-108">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearPointKeyFrame> class to move the ellipse along a path at a steady rate from its starting position.</span></span> <span data-ttu-id="f48f6-109">などの線形キーフレーム<xref:System.Windows.Media.Animation.LinearPointKeyFrame>滑らかな線形補間値を作成します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearPointKeyFrame> create a smooth linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="f48f6-110">インスタンスを使用して、[次へ] の末尾の 0.5 秒、<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>クラスに次の位置に突然パスに沿って楕円を移動します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-110">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> class to suddenly move the ellipse along the path to the next position.</span></span> <span data-ttu-id="f48f6-111">などの不連続のキーフレーム<xref:System.Windows.Media.Animation.DiscretePointKeyFrame>値の間に急なジャンプを作成します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> create sudden jumps between values.</span></span>  
  
3. <span data-ttu-id="f48f6-112">最後の 2 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.SplinePointKeyFrame>楕円を開始位置に移動するクラス。</span><span class="sxs-lookup"><span data-stu-id="f48f6-112">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame> class to move the ellipse back to its starting position.</span></span> <span data-ttu-id="f48f6-113">スプライン キー フレームのような<xref:System.Windows.Media.Animation.SplinePointKeyFrame>の値に基づいて値の間に可変遷移を作成、<xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f48f6-113">Spline key frames like <xref:System.Windows.Media.Animation.SplinePointKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="f48f6-114">この例では、アニメーションは最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="f48f6-114">In this example, the animation begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="f48f6-115">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f48f6-115">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="f48f6-116">この例のコードを使用して、他のアニメーション例と一貫性を保つのため、<xref:System.Windows.Media.Animation.Storyboard>を適用するオブジェクト、<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-116">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="f48f6-117">ただし、コード内で 1 つのアニメーションを適用する場合は使いやすく、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッドを使用してではなく、<xref:System.Windows.Media.Animation.Storyboard>します。</span><span class="sxs-lookup"><span data-stu-id="f48f6-117">However, when applying a single animation in code, it's simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="f48f6-118">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f48f6-118">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48f6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f48f6-119">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [<span data-ttu-id="f48f6-120">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="f48f6-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="f48f6-121">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="f48f6-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
