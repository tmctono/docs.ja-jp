---
title: '方法 : キー フレームを使用して四角形のジオメトリをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344679"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="40424-102">方法 : キー フレームを使用して四角形のジオメトリをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="40424-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="40424-103">この例では、キー フレームを使用<xref:System.Windows.Media.RectangleGeometry.Rect%2A>して a<xref:System.Windows.Media.RectangleGeometry>のプロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="40424-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40424-104">例</span><span class="sxs-lookup"><span data-stu-id="40424-104">Example</span></span>  
 <span data-ttu-id="40424-105">次の例では、<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>クラスを使用して、<xref:System.Windows.Media.RectangleGeometry.Rect%2A>のプロパティを<xref:System.Windows.Media.RectangleGeometry>アニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="40424-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="40424-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="40424-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="40424-107">最初の 2 秒間に、クラスのインスタンス<xref:System.Windows.Media.Animation.LinearRectKeyFrame>を使用して、四角形の位置、幅、および高さの段階的な変化をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="40424-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="40424-108">線形キー フレーム<xref:System.Windows.Media.Animation.LinearRectKeyFrame>のような値間のスムーズな直線遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="40424-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="40424-109">次の半分の秒の終わりの間に、クラスの<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>インスタンスを使用して、突然四角形の高さを減少させます。</span><span class="sxs-lookup"><span data-stu-id="40424-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="40424-110">値の間に<xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>急激な変化を生じるなどの不連続なキー フレーム、つまり高さの低下はすばやく発生し、微妙ではありません。</span><span class="sxs-lookup"><span data-stu-id="40424-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="40424-111">最後の 2 秒間に、クラスのインスタンス<xref:System.Windows.Media.Animation.SplineRectKeyFrame>を使用して、四角形を元のサイズと位置に戻します。</span><span class="sxs-lookup"><span data-stu-id="40424-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="40424-112">スプライン キー<xref:System.Windows.Media.Animation.SplineRectKeyFrame>フレームのような値の間に、プロパティの値に従<xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A>った可変的な遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="40424-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="40424-113">この例では、変化は最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="40424-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="40424-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40424-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40424-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="40424-115">See also</span></span>

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [<span data-ttu-id="40424-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="40424-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="40424-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="40424-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
