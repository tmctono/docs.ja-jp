---
title: '方法 : ArcSegment のサイズをアニメーション化する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], ArcSegment size
- ArcSegment [WPF], animating size
ms.assetid: f93a1065-b00a-4d7e-9d4b-37023f98186a
ms.openlocfilehash: d1b9db72c9d1ea47f3c1bc6476a3b579bc03eae2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452871"
---
# <a name="how-to-animate-the-size-of-an-arcsegment"></a><span data-ttu-id="587cd-102">方法 : ArcSegment のサイズをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="587cd-102">How to: Animate the Size of an ArcSegment</span></span>
<span data-ttu-id="587cd-103">この例では、<xref:System.Windows.Media.ArcSegment>の <xref:System.Windows.Media.ArcSegment.Size%2A> プロパティをアニメーション化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="587cd-103">This example shows how to animate the <xref:System.Windows.Media.ArcSegment.Size%2A> property of an <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="587cd-104">例</span><span class="sxs-lookup"><span data-stu-id="587cd-104">Example</span></span>  
 <span data-ttu-id="587cd-105">次の例では、画面に読み込むときに <xref:System.Windows.Media.ArcSegment.Size%2A> をアニメーション化する <xref:System.Windows.Media.ArcSegment> を作成します。</span><span class="sxs-lookup"><span data-stu-id="587cd-105">The following example creates an <xref:System.Windows.Media.ArcSegment> that animates its <xref:System.Windows.Media.ArcSegment.Size%2A> when it loads on the screen.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/SizeAnimationExample.cs#sizeanimationwholepage)]
 [!code-vb[BasicAnimations_snip#SizeAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/SizeAnimationExample.vb#sizeanimationwholepage)]  
  
 <span data-ttu-id="587cd-106">その他のジオメトリとアニメーションのサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="587cd-106">For additional geometry and animation samples, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="587cd-107">参照</span><span class="sxs-lookup"><span data-stu-id="587cd-107">See also</span></span>

- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- [<span data-ttu-id="587cd-108">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="587cd-108">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="587cd-109">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="587cd-109">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="587cd-110">ジオメトリに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="587cd-110">Geometries How-to Topics</span></span>](geometries-how-to-topics.md)
- [<span data-ttu-id="587cd-111">アニメーションとタイミングに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="587cd-111">Animation and Timing How-to Topics</span></span>](animation-and-timing-how-to-topics.md)
