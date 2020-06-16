---
title: '方法: PointAnimation を使用してオブジェクトの位置をアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 1ef3f77e551affaa7e61d2aabf95f10c29275417
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651351"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="e69df-102">方法: PointAnimation を使用してオブジェクトの位置をアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="e69df-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="e69df-103">この例は、<xref:System.Windows.Media.Animation.PointAnimation> クラスを使用して、<xref:System.Windows.Shapes.Path> に沿ってオブジェクトをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e69df-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e69df-104">例</span><span class="sxs-lookup"><span data-stu-id="e69df-104">Example</span></span>  
 <span data-ttu-id="e69df-105">次の例は、画面上のある点から別の点まで、<xref:System.Windows.Shapes.Path> に沿って楕円が移動しています。</span><span class="sxs-lookup"><span data-stu-id="e69df-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="e69df-106">この例では、<xref:System.Windows.Media.Animation.PointAnimation> を使用して <xref:System.Windows.Media.EllipseGeometry.Center%2A> プロパティをアニメーション化することによって、<xref:System.Windows.Media.EllipseGeometry> の位置をアニメーション化しています。</span><span class="sxs-lookup"><span data-stu-id="e69df-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e69df-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="e69df-107">See also</span></span>

- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [<span data-ttu-id="e69df-108">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="e69df-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="e69df-109">グラフィックスとマルチメディア</span><span class="sxs-lookup"><span data-stu-id="e69df-109">Graphics and Multimedia</span></span>](index.md)
- [<span data-ttu-id="e69df-110">グラフィックスに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="e69df-110">Graphics How-to Topics</span></span>](graphics-how-to-topics.md)
- [<span data-ttu-id="e69df-111">アニメーションおよびタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="e69df-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
