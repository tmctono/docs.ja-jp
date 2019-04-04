---
title: '方法: パスに沿ってオブジェクトをアニメーション化する (ポイント アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: 13cf583277b4e105da01c5ab56111123cf03038c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351619"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="7a9a7-102">方法: パスに沿ってオブジェクトをアニメーション化する (ポイント アニメーション)</span><span class="sxs-lookup"><span data-stu-id="7a9a7-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="7a9a7-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.PointAnimationUsingPath>アニメーション化するオブジェクト、<xref:System.Windows.Point>曲線のパスに沿ってします。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a9a7-104">例</span><span class="sxs-lookup"><span data-stu-id="7a9a7-104">Example</span></span>  
 <span data-ttu-id="7a9a7-105">次の例では、移動、<xref:System.Windows.Media.EllipseGeometry>によって定義されたパスに沿って、<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="7a9a7-106">楕円ジオメトリの<xref:System.Windows.Media.EllipseGeometry.Center%2A>プロパティを<xref:System.Windows.Point>値をアニメーション化する、楕円ジオメトリを移動する位置を指定します、<xref:System.Windows.Media.EllipseGeometry.Center%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="7a9a7-107">この例では、<xref:System.Windows.Media.Animation.PointAnimationUsingPath>をアニメーション化する、<xref:System.Windows.Media.EllipseGeometry>オブジェクトの<xref:System.Windows.Media.EllipseGeometry.Center%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="7a9a7-108">サンプル全体については、[パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-108">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="7a9a7-109">使用前の例のコードのバージョン、<xref:System.Windows.Media.Animation.Storyboard>をアニメーション化する、 <xref:System.Windows.Media.EllipseGeometry>1 つだけのアニメーションが適用された場合でも、します。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="7a9a7-110">A<xref:System.Windows.Media.Animation.Storyboard>同じこれらのアニメーションを制御できるため、複数のアニメーションを適用する最も簡単な方法は、多くの場合、<xref:System.Windows.Media.Animation.Storyboard>します。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="7a9a7-111">しかし、コードを使用する場合は、1 つのアニメーションをプロパティに適用する簡単な方法は、使用する、<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="7a9a7-112">例については、「[ストーリーボードを使用せずにプロパティをアニメーション化する](how-to-animate-a-property-without-using-a-storyboard.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a9a7-112">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9a7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a9a7-113">See also</span></span>
- [<span data-ttu-id="7a9a7-114">パス アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="7a9a7-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="7a9a7-115">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="7a9a7-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7a9a7-116">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="7a9a7-116">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
