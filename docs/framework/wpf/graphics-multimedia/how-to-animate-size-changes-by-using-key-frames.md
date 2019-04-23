---
title: '方法: キー フレームを使用してサイズの変更をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0629b6600444bd172af451fd7e970bff894d8047
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342369"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a><span data-ttu-id="289ea-102">方法: キー フレームを使用してサイズの変更をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="289ea-102">How to: Animate Size Changes by Using Key Frames</span></span>
<span data-ttu-id="289ea-103">この例では、キー フレームを使用してサイズの変更をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="289ea-103">This example shows how to animate size changes by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="289ea-104">例</span><span class="sxs-lookup"><span data-stu-id="289ea-104">Example</span></span>  
 <span data-ttu-id="289ea-105">次の例では、<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Media.ArcSegment.Size%2A>のプロパティ、<xref:System.Windows.Media.ArcSegment>します。</span><span class="sxs-lookup"><span data-stu-id="289ea-105">The following example uses the <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span> <span data-ttu-id="289ea-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="289ea-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="289ea-107">インスタンスを使用して、アニメーションの最初の 0.5 秒、<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>クラスは、円弧のサイズを徐々 に増やします。などの線形キーフレーム<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>値の間の滑らかな線形トランジションを作成します。</span><span class="sxs-lookup"><span data-stu-id="289ea-107">During the first half second of the animation, uses an instance of the <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> class to gradually increase the size of the arc. Linear key frames like <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="289ea-108">インスタンスを使用している 0.5 秒は、次の最後に、<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>クラスを突然、円弧のサイズを大ききます。などの不連続のキーフレーム<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>されている値の間に急なジャンプを作成、サイズの変更が突然発生してはなく。</span><span class="sxs-lookup"><span data-stu-id="289ea-108">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> class to suddenly increase the size of the arc. Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> create sudden jumps between values, that is, the size changes occur suddenly and are not subtle.</span></span>  
  
3. <span data-ttu-id="289ea-109">インスタンスが使用する最後の 2 秒、<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>円弧のサイズを大きくクラス。スプライン キー フレームのような<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>の値に基づいて値の間に可変遷移を作成、<xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="289ea-109">Over the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> class to increase the size of the arc. Spline key frames like <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="289ea-110">この例では、円弧のサイズは最初はゆっくり大きくなりますが、時間セグメントの終点に向かって急激に大きくなります。</span><span class="sxs-lookup"><span data-stu-id="289ea-110">In this example, the size of the arc increases slowly at first and then increases exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="289ea-111">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="289ea-111">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="289ea-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="289ea-112">See also</span></span>

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [<span data-ttu-id="289ea-113">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="289ea-113">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="289ea-114">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="289ea-114">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
