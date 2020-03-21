---
title: '方法 : キー フレームを使用して 3D 回転をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations [WPF], with key frames (Rotation3DAnimation)
- key frames [WPF], Rotation3DAnimation
- 3D translations [WPF], animating [WPF], with key frames (Rotation3DAnimation)
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
ms.openlocfilehash: 2b9059df079125c34c70237c0f600751020044c6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112311"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames"></a><span data-ttu-id="b8a83-102">方法 : キー フレームを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="b8a83-102">How to: Animate a 3D Rotation Using Key Frames</span></span>
<span data-ttu-id="b8a83-103">次の例では、3D<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>オブジェクトを回転させ、回転軸をアニメートして"ぐらつき"を生じさせます。</span><span class="sxs-lookup"><span data-stu-id="b8a83-103">In the following example, <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames> is used to make a 3D object rotate while its axis of rotation animates resulting in a "wobble".</span></span> <span data-ttu-id="b8a83-104">このアニメーションでは、次のキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8a83-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="b8a83-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>は、値間の滑らかな直線補間を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8a83-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="b8a83-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>は、値間に突然の「ジャンプ」を作成するために使用されます(補間なし)。</span><span class="sxs-lookup"><span data-stu-id="b8a83-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="b8a83-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>は、プロパティに応じて値間の変数遷移<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8a83-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="b8a83-108">次の例では、アニメーションのこの部分は低速から始まりますが、時間セグメントの終わりに向かって、指数関数的に高速化します。</span><span class="sxs-lookup"><span data-stu-id="b8a83-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a83-109">例</span><span class="sxs-lookup"><span data-stu-id="b8a83-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="b8a83-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8a83-110">See also</span></span>

- [<span data-ttu-id="b8a83-111">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="b8a83-111">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="b8a83-112">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="b8a83-112">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="b8a83-113">ストーリーボードを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="b8a83-113">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="b8a83-114">回転 3D アニメーションを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="b8a83-114">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="b8a83-115">四元数を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="b8a83-115">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="b8a83-116">キー フレームを使用して 3D 回転をアニメーション化する (クォータニオンアニメーションを使用してキーフレーム)</span><span class="sxs-lookup"><span data-stu-id="b8a83-116">Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>](animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)
