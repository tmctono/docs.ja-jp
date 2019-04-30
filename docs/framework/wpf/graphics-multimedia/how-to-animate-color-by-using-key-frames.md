---
title: '方法: キー フレームを使用して色をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: e579c4beb757ccf58eb1b9ca1f3852a5b96cac1a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010028"
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="e8abc-102">方法: キー フレームを使用して色をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="e8abc-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="e8abc-103">この例は、アニメーション化する方法を示しています、<xref:System.Windows.Media.SolidColorBrush.Color%2A>の<xref:System.Windows.Media.SolidColorBrush>キー フレームを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e8abc-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8abc-104">例</span><span class="sxs-lookup"><span data-stu-id="e8abc-104">Example</span></span>  
 <span data-ttu-id="e8abc-105">次の例では、<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>をアニメーション化するクラス、<xref:System.Windows.Media.SolidColorBrush.Color%2A>のプロパティを<xref:System.Windows.Media.SolidColorBrush>します。</span><span class="sxs-lookup"><span data-stu-id="e8abc-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="e8abc-106">このアニメーションは、次の方法で 3 つのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8abc-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="e8abc-107">最初の 2 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.LinearColorKeyFrame>緑から赤に色を徐々 に変化するクラス。</span><span class="sxs-lookup"><span data-stu-id="e8abc-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="e8abc-108">などの線形キーフレーム<xref:System.Windows.Media.Animation.LinearColorKeyFrame>値の間の滑らかな線形トランジションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8abc-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2. <span data-ttu-id="e8abc-109">インスタンスを使用して、[次へ] の末尾の 0.5 秒、<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>クラスをすばやく色を赤から黄色に変更します。</span><span class="sxs-lookup"><span data-stu-id="e8abc-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="e8abc-110">などの不連続のキーフレーム<xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>、つまり値の間での急激な変化を作成、アニメーションのこの部分で色の変更は、短時間で発生しはありません。</span><span class="sxs-lookup"><span data-stu-id="e8abc-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3. <span data-ttu-id="e8abc-111">最後の 2 秒のインスタンスを使用して、<xref:System.Windows.Media.Animation.SplineColorKeyFrame>クラスをもう一度、色を変更する — 現時点黄色から緑色にします。</span><span class="sxs-lookup"><span data-stu-id="e8abc-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="e8abc-112">スプライン キー フレームのような<xref:System.Windows.Media.Animation.SplineColorKeyFrame>の値に基づいて値の間に可変遷移を作成、<xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e8abc-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="e8abc-113">この例では、色の変化は最初はゆっくりしていますが、時間セグメントの終点に向かって急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="e8abc-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e8abc-114">サンプル全体については、「[キーフレーム アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160012)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8abc-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8abc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8abc-115">See also</span></span>

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [<span data-ttu-id="e8abc-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="e8abc-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="e8abc-117">キー フレームに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="e8abc-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
