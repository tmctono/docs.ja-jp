---
title: '方法: キー フレームを使用してカメラの位置および方向をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 44464cc314d649516998338e36c1b523101ac4e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346081"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="bec58-102">方法: キー フレームを使用してカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="bec58-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="bec58-103">次の例では、<xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames>の位置をアニメーション化するために使用する<xref:System.Windows.Media.Media3D.PerspectiveCamera>3D シーンでします。</span><span class="sxs-lookup"><span data-stu-id="bec58-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="bec58-104">さらに、 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> 3D シーンでカメラが指す方向をアニメーション化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="bec58-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="bec58-105">どちらのアニメーションは、一連のアニメーション効果を作成するいくつかのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="bec58-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="bec58-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame>する滑らかな線形補間値の間での作成に使用します。</span><span class="sxs-lookup"><span data-stu-id="bec58-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="bec58-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame>値 (補間) の間で突然「ジャンプ」の作成に使用します。</span><span class="sxs-lookup"><span data-stu-id="bec58-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="bec58-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame>に応じて値の間に可変遷移を作成するために使用、<xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bec58-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="bec58-109">次の例では、アニメーションは低速と始まりますが、時間セグメントの末尾に向かって、急激に速くなります。</span><span class="sxs-lookup"><span data-stu-id="bec58-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bec58-110">例</span><span class="sxs-lookup"><span data-stu-id="bec58-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bec58-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="bec58-111">See also</span></span>

- [<span data-ttu-id="bec58-112">3D シーンでカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="bec58-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="bec58-113">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="bec58-113">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
