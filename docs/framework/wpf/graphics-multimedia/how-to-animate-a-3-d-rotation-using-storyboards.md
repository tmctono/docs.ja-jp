---
title: '方法: ストーリーボードを使用して 3D 回転をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF]
- 3D translations [WPF], animating [WPF], with Storyboards
- animation [WPF], 3D translations [WPF], with Storyboards
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
ms.openlocfilehash: 088f1a33cfc73a706ffed55ffff6494adaf8fca4
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112216"
---
# <a name="how-to-animate-a-3d-rotation-using-storyboards"></a><span data-ttu-id="5cec3-102">方法: ストーリーボードを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="5cec3-102">How to: Animate a 3D Rotation Using Storyboards</span></span>
<span data-ttu-id="5cec3-103">次の例は、オブジェクトのプロパティと<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A><xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>プロパティをアニメーション化して、3D オブジェクトを回転させながら、オブジェクトを 「<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>ぐらつく」 方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5cec3-103">The following example shows how to make a 3D object rotate while it "wobbles" by animating the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> and <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> properties of an <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object.</span></span> <span data-ttu-id="5cec3-104">この<xref:System.Windows.Media.Media3D.AxisAngleRotation3D>オブジェクトは 3D オブジェクトの回転変換を指定するため、そのプロパティをアニメートすると、欲望の回転効果が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5cec3-104">This <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> object specifies the rotation transform of the 3D object and so animating its properties creates the desire rotation effect.</span></span> <span data-ttu-id="5cec3-105">ストーリーボード内では、<xref:System.Windows.Media.Animation.DoubleAnimation><xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A>プロパティをアニメーション化するために使用され、プロパティ<xref:System.Windows.Media.Animation.Vector3DAnimation>はアニメーション化に使用されます<xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A>。</span><span class="sxs-lookup"><span data-stu-id="5cec3-105">Within the Storyboard, <xref:System.Windows.Media.Animation.DoubleAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> property while <xref:System.Windows.Media.Animation.Vector3DAnimation> is used to animate the <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cec3-106">例</span><span class="sxs-lookup"><span data-stu-id="5cec3-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5cec3-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="5cec3-107">See also</span></span>

- [<span data-ttu-id="5cec3-108">回転 3D アニメーションを使用して 3D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="5cec3-108">Animate a 3D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
- [<span data-ttu-id="5cec3-109">キー フレームを使用して 3D 回転をアニメーション化する (回転 3D アニメーションを使用してキー フレーム)</span><span class="sxs-lookup"><span data-stu-id="5cec3-109">Animate a 3D Rotation Using Key Frames (Rotation3DAnimationUsingKeyFrames)</span></span>](how-to-animate-a-3-d-rotation-using-key-frames.md)
- [<span data-ttu-id="5cec3-110">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="5cec3-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="5cec3-111">ストーリーボードの概要</span><span class="sxs-lookup"><span data-stu-id="5cec3-111">Storyboards Overview</span></span>](storyboards-overview.md)
