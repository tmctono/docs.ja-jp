---
title: '方法: キー フレームを使用して 3-D 回転をアニメーション化します。'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3-D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2316282a39190e86b0e2f0ec67ccc743a45d55e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213182"
---
# <a name="how-to-animate-a-3-d-rotation-using-key-frames"></a><span data-ttu-id="3d6b4-102">方法: キー フレームを使用して 3-D 回転をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-102">How to: Animate a 3-D Rotation Using Key Frames</span></span>
<span data-ttu-id="3d6b4-103">次の例では、 <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> 「補助」の結果としてその軸の回転をアニメーション化中に回転 3D オブジェクトを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="3d6b4-104">このアニメーションは、次のキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-104">This animation uses the following key frames:</span></span>  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> <span data-ttu-id="3d6b4-105">作成する滑らかな線形補間値の間に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-105">is used to create a smooth, linear interpolation between values.</span></span>  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> <span data-ttu-id="3d6b4-106">(補間) の値の間で突然「ジャンプ」の作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-106">is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> <span data-ttu-id="3d6b4-107">によって値の間に可変遷移を作成するために使用、<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-107">is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="3d6b4-108">次の例で、アニメーションのこの部分は低速と始まりますが、時間セグメントの末尾に向かって、急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="3d6b4-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d6b4-109">例</span><span class="sxs-lookup"><span data-stu-id="3d6b4-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3d6b4-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d6b4-110">See also</span></span>

- [<span data-ttu-id="3d6b4-111">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="3d6b4-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="3d6b4-112">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="3d6b4-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="3d6b4-113">ストーリーボードを使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3d6b4-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="3d6b4-114">Rotation3DAnimation を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3d6b4-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="3d6b4-115">四元数を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3d6b4-115">Animate a 3-D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="3d6b4-116">キー フレーム (QuaternionAnimationUsingKeyFrames) を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="3d6b4-116">Animate a 3-D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
