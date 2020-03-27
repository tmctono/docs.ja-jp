---
title: '方法 : キー フレームを使用して色をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344749"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="6d45f-102">方法 : キー フレームを使用して色をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="6d45f-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="6d45f-103">この例では、キー フレームを使用<xref:System.Windows.Media.SolidColorBrush.Color%2A>して<xref:System.Windows.Media.SolidColorBrush>a の をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d45f-104">例</span><span class="sxs-lookup"><span data-stu-id="6d45f-104">Example</span></span>  
 <span data-ttu-id="6d45f-105">次の例では、<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>クラスを使用して、<xref:System.Windows.Media.SolidColorBrush.Color%2A>のプロパティを<xref:System.Windows.Media.SolidColorBrush>アニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="6d45f-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="6d45f-107">最初の 2 秒間に、クラスのインスタンス<xref:System.Windows.Media.Animation.LinearColorKeyFrame>を使用して、色を徐々に緑から赤に変更します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="6d45f-108">線形キー フレーム<xref:System.Windows.Media.Animation.LinearColorKeyFrame>のような値間のスムーズな直線遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="6d45f-109">次の半分の秒の終わりの間に、<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>クラスのインスタンスを使用して、色を赤から黄色に素早く変更します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="6d45f-110">値の間に<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>突然の変化を作成するような不連続なキー フレーム、つまりアニメーションのこの部分の色の変化は、すぐに発生し、微妙ではありません。</span><span class="sxs-lookup"><span data-stu-id="6d45f-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="6d45f-111">最後の 2 秒間に、クラスのインスタンス<xref:System.Windows.Media.Animation.SplineColorKeyFrame>を使用して、もう一度色を変更します(今度は黄色から緑に戻ります)。</span><span class="sxs-lookup"><span data-stu-id="6d45f-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="6d45f-112">スプライン キー<xref:System.Windows.Media.Animation.SplineColorKeyFrame>フレームのような値の間に、プロパティの値に従<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>った可変的な遷移を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d45f-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="6d45f-113">この例では、色の変化は最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="6d45f-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="6d45f-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d45f-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d45f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d45f-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="6d45f-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="6d45f-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="6d45f-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="6d45f-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
