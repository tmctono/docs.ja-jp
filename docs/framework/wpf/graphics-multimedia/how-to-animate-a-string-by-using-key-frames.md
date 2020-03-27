---
title: '方法 : キー フレームを使用して文字列をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344670"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="ba0cb-102">方法 : キー フレームを使用して文字列をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="ba0cb-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="ba0cb-103">この例では、キー フレームを使用して、コントロールの<xref:System.Windows.Controls.ContentControl.Content%2A>プロパティである文字列を<xref:System.Windows.Controls.Button>アニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ba0cb-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba0cb-104">例</span><span class="sxs-lookup"><span data-stu-id="ba0cb-104">Example</span></span>  
 <span data-ttu-id="ba0cb-105">次の例では、<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>クラスを使用して、<xref:System.Windows.Controls.ContentControl.Content%2A>のプロパティを<xref:System.Windows.Controls.Button>アニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="ba0cb-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="ba0cb-106">この例のすべてのキー フレームは<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>、キー フレームを使用して作成される文字列アニメーションは個別のキー フレームしか使用できないため、クラスのインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba0cb-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="ba0cb-107">値の間に<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>突然ジャンプを作成するような離散的なキー フレーム、つまりアニメーションの変更はすばやく発生し、微妙ではありません。</span><span class="sxs-lookup"><span data-stu-id="ba0cb-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="ba0cb-108">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba0cb-108">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba0cb-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba0cb-109">See also</span></span>

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [<span data-ttu-id="ba0cb-110">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="ba0cb-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="ba0cb-111">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="ba0cb-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
