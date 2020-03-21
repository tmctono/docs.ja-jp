---
title: '方法 : キー フレームを使用してカメラの位置および方向をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera direction with key frames
- key frames [WPF], animating camera direction
- animation [WPF], camera position with key frames
- camera position [WPF], animating with key frames
- key frames [WPF], animating camera position
- camera direction [WPF], animating with key frames
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
ms.openlocfilehash: 28471f9b42140a6c75b043d33939503528b63194
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112168"
---
# <a name="how-to-animate-camera-position-and-direction-using-key-frames"></a><span data-ttu-id="c7694-102">方法 : キー フレームを使用してカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="c7694-102">How to: Animate Camera Position and Direction Using Key Frames</span></span>
<span data-ttu-id="c7694-103">次の例では、3D<xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames>シーンでの a の<xref:System.Windows.Media.Media3D.PerspectiveCamera>位置をアニメートするために使用します。</span><span class="sxs-lookup"><span data-stu-id="c7694-103">In the following example, <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames> is used to animate the position of a <xref:System.Windows.Media.Media3D.PerspectiveCamera> in a 3D scene.</span></span> <span data-ttu-id="c7694-104">さらに、<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>カメラが 3D シーンで向いている方向をアニメートするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7694-104">In addition, <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames> is used to animate the direction the camera is pointing in the 3D scene.</span></span> <span data-ttu-id="c7694-105">これらのアニメーションはどちらも、一連のアニメーション効果を作成するいくつかのキー フレームを使用します。</span><span class="sxs-lookup"><span data-stu-id="c7694-105">Both of these animations use several key frames which create a series of animation effects:</span></span>  
  
1. <span data-ttu-id="c7694-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame>値<xref:System.Windows.Media.Animation.LinearVector3DKeyFrame>間の滑らかな直線補間を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7694-106"><xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> and <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame> are used to create a smooth, linear interpolation between values.</span></span>  
  
2. <span data-ttu-id="c7694-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame>値<xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame>間に突然の「ジャンプ」を作成するために使用されます(補間なし)。</span><span class="sxs-lookup"><span data-stu-id="c7694-107"><xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame> are used to create sudden "jumps" between values (no interpolation).</span></span>  
  
3. <span data-ttu-id="c7694-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame>プロパティ<xref:System.Windows.Media.Animation.SplineVector3DKeyFrame>に応じて値間の変数遷移を<xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A>作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c7694-108"><xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> and <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame> are used to create a variable transition between values depending on the <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="c7694-109">次の例では、アニメーションは低速から開始しますが、時間セグメントの終わりに向かって、指数関数的に高速化します。</span><span class="sxs-lookup"><span data-stu-id="c7694-109">In the example below, the animation starts off slow but toward the end of the time segment, speeds up exponentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7694-110">例</span><span class="sxs-lookup"><span data-stu-id="c7694-110">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c7694-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7694-111">See also</span></span>

- [<span data-ttu-id="c7694-112">3D シーンでカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="c7694-112">Animate Camera Position and Direction in a 3D Scene</span></span>](how-to-animate-camera-position-and-direction-in-a-3d-scene.md)
- [<span data-ttu-id="c7694-113">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="c7694-113">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
