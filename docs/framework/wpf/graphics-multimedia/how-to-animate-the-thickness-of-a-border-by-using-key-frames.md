---
title: '方法: キー フレームを使用して境界線の太さをアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 101fd077bf125faadbd9a0186c2282e4b20ee78f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699033"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="eb2a0-102">方法: キー フレームを使用して境界線の太さをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="eb2a0-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="eb2a0-103">この例は、アニメーション化する方法を示しています、<xref:System.Windows.Controls.Control.BorderThickness%2A>のプロパティを<xref:System.Windows.Controls.Border>します。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb2a0-104">例</span><span class="sxs-lookup"><span data-stu-id="eb2a0-104">Example</span></span>  
 <span data-ttu-id="eb2a0-105">次の例では、<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Controls.Control.BorderThickness%2A>のプロパティを<xref:System.Windows.Controls.Border>します。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="eb2a0-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="eb2a0-107">最初の 0.5 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>の境界線の太さを徐々 に増加するクラス。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="eb2a0-108">この例では<xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>値の間の滑らかな線形増加を作成します。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="eb2a0-109">インスタンスを使用している 0.5 秒は、次の最後に、<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>クラスを境界線の太さを突然太きます。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="eb2a0-110">派生したもののような不連続キーフレーム<xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>されている値の間に急なジャンプを作成、アニメーションの動きはぎくしゃくします。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="eb2a0-111">最後の 2 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>の境界線の太さを小さくクラス。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="eb2a0-112">派生したもののようなスプライン キーフレーム<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>の値に基づいて値の間に可変遷移を作成、<xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="eb2a0-113">このキー フレームでは、アニメーションはゆっくりと始まりますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="eb2a0-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb2a0-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb2a0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb2a0-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="eb2a0-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="eb2a0-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="eb2a0-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="eb2a0-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="eb2a0-118">BorderThickness 値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="eb2a0-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
