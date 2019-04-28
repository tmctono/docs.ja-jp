---
title: '方法: 3D シーンでカメラの位置および方向をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: b64263a495ffe845a76317aad8f5b4a14e11b31e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651377"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="d730d-102">方法: 3D シーンでカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="d730d-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="d730d-103">次の例では、カメラの位置をアニメーション化してが、3 D シーンで向いている方向をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d730d-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="d730d-104">使用してこれは、<xref:System.Windows.Media.Animation.Point3DAnimation>と<xref:System.Windows.Media.Animation.Vector3DAnimation>をアニメーション化する、<xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A>と<xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A>それぞれのプロパティ、<xref:System.Windows.Media.Media3D.PerspectiveCamera>します。</span><span class="sxs-lookup"><span data-stu-id="d730d-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="d730d-105">このようなアニメーションを使用すると、イベントへの応答でのシーンの観察者のビューを変更するのに可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d730d-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d730d-106">例</span><span class="sxs-lookup"><span data-stu-id="d730d-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d730d-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="d730d-107">See also</span></span>

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [<span data-ttu-id="d730d-108">キー フレームを使用してカメラの位置および方向をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="d730d-108">Animate Camera Position and Direction Using Key Frames</span></span>](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [<span data-ttu-id="d730d-109">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="d730d-109">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
