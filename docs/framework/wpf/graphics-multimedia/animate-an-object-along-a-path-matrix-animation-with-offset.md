---
title: '方法: パスに沿ってオブジェクトをアニメーション化する (オフセット累積による行列アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 3e7b892e2a2215d26512850477844d71bce7fe09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207371"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="a10cd-102">方法: パスに沿ってオブジェクトをアニメーション化する (オフセット累積による行列アニメーション)</span><span class="sxs-lookup"><span data-stu-id="a10cd-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="a10cd-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>クラス パスに沿ってオブジェクトをアニメーション化して、そのオフセットを蓄積するアニメーションを繰り返すたびの値します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a10cd-104">例</span><span class="sxs-lookup"><span data-stu-id="a10cd-104">Example</span></span>  
 <span data-ttu-id="a10cd-105">次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>アニメーション化するオブジェクト、<xref:System.Windows.Media.MatrixTransform.Matrix%2A>のプロパティを<xref:System.Windows.Media.MatrixTransform>ボタンに適用します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="a10cd-106">その結果、ボタンは曲線状のパスに沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="a10cd-107">さらに、例では、設定、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>プロパティを`true`、蓄積、アニメーションを繰り返すたびにアニメーション化された行列のオフセットします。</span><span class="sxs-lookup"><span data-stu-id="a10cd-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="a10cd-108">オフセットが累積されるので、アニメーションが繰り返されたとき、ボタンは開始位置にリセットされるのではなく、画面を横切ってさらに移動します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="a10cd-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A>プロパティを繰り返しで累積する値をオフセットすると、累積する回転の値が原因です。</span><span class="sxs-lookup"><span data-stu-id="a10cd-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="a10cd-110">回転値を累積するために、設定、アニメーションの<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>と<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A>プロパティ`true`します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="a10cd-111">サンプル全体については、次を参照してください。[パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-111">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="a10cd-112">アニメーション化する方法を示す例については、<xref:System.Windows.Media.Matrix>値のオフセットを蓄積せず、パスに沿ってを参照してください[、オブジェクト パスに沿って (行列アニメーション) をアニメーション化する](how-to-animate-an-object-along-a-path-matrix-animation.md)します。</span><span class="sxs-lookup"><span data-stu-id="a10cd-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10cd-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a10cd-113">See also</span></span>

- [<span data-ttu-id="a10cd-114">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="a10cd-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="a10cd-115">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="a10cd-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
