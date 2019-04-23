---
title: '方法: 四元数を使用して 3-D 回転をアニメーション化する'
ms.date: 03/30/2017
helpviewer_keywords:
- quaternions [WPF]
- animation [WPF], 3-D translations [WPF], with quaternions
- 3-D translations [WPF], animating [WPF], with quaternions
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
ms.openlocfilehash: d994ac2ae67fd366f27f123d5bd15f14d5ac7abe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183223"
---
# <a name="how-to-animate-a-3-d-rotation-using-quaternions"></a><span data-ttu-id="2b364-102">方法: 四元数を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="2b364-102">How to: Animate a 3-D Rotation Using Quaternions</span></span>
<span data-ttu-id="2b364-103">この例では、四元数を使用して 3-D オブジェクトの回転をアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2b364-103">This example shows how to animate a rotation of a 3-D object using quaternions.</span></span>  
  
 <span data-ttu-id="2b364-104">次のコードを<xref:System.Windows.Media.Media3D.QuaternionRotation3D>の値として使用される、<xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A>のプロパティを<xref:System.Windows.Media.Media3D.RotateTransform3D>します。</span><span class="sxs-lookup"><span data-stu-id="2b364-104">The code below shows a <xref:System.Windows.Media.Media3D.QuaternionRotation3D> used as the value for the <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> property of a <xref:System.Windows.Media.Media3D.RotateTransform3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 <span data-ttu-id="2b364-105">これは、<xref:System.Windows.Media.Media3D.QuaternionRotation3D>をアニメーション化は、<xref:System.Windows.Media.Animation.QuaternionAnimation>内で、<xref:System.Windows.Media.Animation.Storyboard>次のコードを使用して。</span><span class="sxs-lookup"><span data-stu-id="2b364-105">This <xref:System.Windows.Media.Media3D.QuaternionRotation3D> is animated with a <xref:System.Windows.Media.Animation.QuaternionAnimation> within a <xref:System.Windows.Media.Animation.Storyboard> using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="2b364-106">例</span><span class="sxs-lookup"><span data-stu-id="2b364-106">Example</span></span>  
 <span data-ttu-id="2b364-107">次のコードでは、全体のサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="2b364-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2b364-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b364-108">See also</span></span>

- [<span data-ttu-id="2b364-109">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="2b364-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2b364-110">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="2b364-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="2b364-111">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="2b364-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2b364-112">変換の概要</span><span class="sxs-lookup"><span data-stu-id="2b364-112">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="2b364-113">ストーリーボードを使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="2b364-113">Animate a 3-D Rotation Using Storyboards</span></span>](how-to-animate-a-3-d-rotation-using-storyboards.md)
- [<span data-ttu-id="2b364-114">Rotation3DAnimation を使用して 3-D 回転をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="2b364-114">Animate a 3-D Rotation Using Rotation3DAnimation</span></span>](how-to-animate-a-3-d-rotation-using-rotation3danimation.md)
