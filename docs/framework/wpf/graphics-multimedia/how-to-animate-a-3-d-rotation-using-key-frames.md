---
title: '方法: キー フレームを使用して 3-D 回転をアニメーション化します。'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: e72ec94f830f0f5001a77e7492aa1326a47b309d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762151"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="60c04-102">方法: キー フレームを使用して 3-D 回転をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="60c04-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="60c04-103">次の例では、 <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> 「補助」の結果としてその軸の回転をアニメーション化中に回転 3D オブジェクトを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="60c04-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="60c04-104">このアニメーションは、次のキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="60c04-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="60c04-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> 作成する滑らかな線形補間値の間に使用されます。</span><span class="sxs-lookup"><span data-stu-id="60c04-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="60c04-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> (補間) の値の間で突然「ジャンプ」の作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="60c04-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="60c04-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> によって値の間に可変遷移を作成するために使用、<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="60c04-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="60c04-108">次の例で、アニメーションのこの部分は低速と始まりますが、時間セグメントの末尾に向かって、急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="60c04-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60c04-109">例</span><span class="sxs-lookup"><span data-stu-id="60c04-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="60c04-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="60c04-110">See also</span></span>

- [<span data-ttu-id="60c04-111">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="60c04-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="60c04-112">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="60c04-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="60c04-113">ストーリーボードを使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="60c04-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="60c04-114">Rotation3DAnimation を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="60c04-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="60c04-115">四元数を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="60c04-115">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="60c04-116">キー フレーム (QuaternionAnimationUsingKeyFrames) を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="60c04-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
