---
title: '方法 : キー フレームを使用して 3D 回転をアニメーション化する (クォータニオンアニメーションを使用するキーフレーム)'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D translations [WPF], animating [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
- key frames [WPF], QuaternionAnimationUsingKeyFrames
- animation [WPF], 3D translations [WPF], with key frames (QuaternionAnimationUsingKeyFrames)
ms.assetid: 09e5707b-7523-4a08-9aa7-bb13cbedccdf
ms.openlocfilehash: 5273183aaa49a743cc401dec0b4b16bae09e3129
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112298"
---
# <a name="how-to-animate-a-3d-rotation-using-key-frames-quaternionanimationusingkeyframes"></a><span data-ttu-id="dbd7b-102">方法 : キー フレームを使用して 3D 回転をアニメーション化する (クォータニオンアニメーションを使用するキーフレーム)</span><span class="sxs-lookup"><span data-stu-id="dbd7b-102">How to: Animate a 3D Rotation Using Key Frames (QuaternionAnimationUsingKeyFrames)</span></span>
<span data-ttu-id="dbd7b-103">次の例では、3D<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>オブジェクトを回転させるために使用します。</span><span class="sxs-lookup"><span data-stu-id="dbd7b-103">In the following example, <xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames> is used to make a 3D object rotate.</span></span> <span data-ttu-id="dbd7b-104">このアニメーションでは、次のキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbd7b-104">This animation uses the following key frames:</span></span>  
  
1. <span data-ttu-id="dbd7b-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>は、値間の滑らかな直線補間を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbd7b-105"><xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame> is used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="dbd7b-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>は、値間に突然の「ジャンプ」を作成するために使用されます(補間なし)。</span><span class="sxs-lookup"><span data-stu-id="dbd7b-106"><xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame> is used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="dbd7b-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>は、プロパティに応じて値間の変数遷移<xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A>を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbd7b-107"><xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame> is used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="dbd7b-108">次の例では、アニメーションのこの部分は低速から始まりますが、時間セグメントの終わりに向かって、指数関数的に高速化します。</span><span class="sxs-lookup"><span data-stu-id="dbd7b-108">In the example below, this part of the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbd7b-109">例</span><span class="sxs-lookup"><span data-stu-id="dbd7b-109">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationUsingKeyFramesExample.xaml#quaternionanimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="dbd7b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbd7b-110">See also</span></span>

- [<span data-ttu-id="dbd7b-111">ストーリーボードを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="dbd7b-111">Animate a 3D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="dbd7b-112">回転 3D アニメーションを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="dbd7b-112">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="dbd7b-113">四元数を使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="dbd7b-113">Animate a 3D Rotation Using Quaternions</span></span>](how-to-animate-a-3-d-rotation-using-quaternions.md)
- [<span data-ttu-id="dbd7b-114">キー フレームを使用して 3D 回転をアニメーション化する (回転 3D アニメーションを使用してキー フレーム)</span><span class="sxs-lookup"><span data-stu-id="dbd7b-114">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="dbd7b-115">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="dbd7b-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="dbd7b-116">キー フレーム アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="dbd7b-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
