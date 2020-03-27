---
title: '方法 : キー フレームを使用してブール値をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344935"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="293d0-102">方法 : キー フレームを使用してブール値をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="293d0-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="293d0-103">この例では、キー フレームを使用してコントロールの Boolean<xref:System.Windows.Controls.Button>プロパティ値をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="293d0-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="293d0-104">例</span><span class="sxs-lookup"><span data-stu-id="293d0-104">Example</span></span>  
 <span data-ttu-id="293d0-105">次の例では、<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>クラスを使用してコントロールの<xref:System.Windows.UIElement.IsEnabled%2A>プロパティをアニメーション<xref:System.Windows.Controls.Button>化します。</span><span class="sxs-lookup"><span data-stu-id="293d0-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="293d0-106">この例のすべてのキー フレームでは、クラスのインスタンスを<xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>使用します。</span><span class="sxs-lookup"><span data-stu-id="293d0-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="293d0-107">値の間に<xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame>突然ジャンプを作成するような離散的なキー フレーム、つまりアニメーションの動きがぎくしゃくします。</span><span class="sxs-lookup"><span data-stu-id="293d0-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="293d0-108">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="293d0-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="293d0-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="293d0-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="293d0-110">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="293d0-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="293d0-111">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="293d0-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
