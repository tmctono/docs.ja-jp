---
title: '方法 : パスに沿ってオブジェクトをアニメーション化する (オフセット累積による行列アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
ms.openlocfilehash: 8b3975ef5031b50381dfa9baf7f34a58fc05ab4e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453105"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a><span data-ttu-id="daa26-102">方法 : パスに沿ってオブジェクトをアニメーション化する (オフセット累積による行列アニメーション)</span><span class="sxs-lookup"><span data-stu-id="daa26-102">How to: Animate an Object Along a Path (Matrix Animation with Offset Accumulation)</span></span>
<span data-ttu-id="daa26-103">この例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> クラスを使用して、パスに沿ってオブジェクトをアニメーション化する方法を示します。また、アニメーションの再生時に、そのアニメーションのオフセット値が累積されます。</span><span class="sxs-lookup"><span data-stu-id="daa26-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path and have that animation accumulate its offset values as it repeats.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daa26-104">例</span><span class="sxs-lookup"><span data-stu-id="daa26-104">Example</span></span>  
 <span data-ttu-id="daa26-105">次の例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> オブジェクトを使用して、ボタンに適用されている <xref:System.Windows.Media.MatrixTransform> の <xref:System.Windows.Media.MatrixTransform.Matrix%2A> プロパティをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="daa26-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform> applied to a button.</span></span> <span data-ttu-id="daa26-106">その結果、ボタンは曲線状のパスに沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="daa26-106">As a result, a button moves along a curved path.</span></span>  
  
 <span data-ttu-id="daa26-107">また、この例では、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> プロパティを `true`に設定しています。これにより、アニメーションの繰り返しに応じて、アニメーション化された行列のオフセットが累積されます。</span><span class="sxs-lookup"><span data-stu-id="daa26-107">In addition, the example sets the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property to `true`, which causes the offset of the animated matrix to accumulate as the animation repeats.</span></span> <span data-ttu-id="daa26-108">オフセットが累積されるので、アニメーションが繰り返されたとき、ボタンは開始位置にリセットされるのではなく、画面を横切ってさらに移動します。</span><span class="sxs-lookup"><span data-stu-id="daa26-108">Because the offset accumulates, the button moves farther across the screen when the animation repeats, rather than resetting to the starting position.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 <span data-ttu-id="daa26-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> プロパティを指定するとオフセット値が繰り返しで累積されますが、回転値が累積されることはないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="daa26-109">Note that, although the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> property causes offset values to accumulate over repetitions, it doesn't cause rotation values to accumulate.</span></span> <span data-ttu-id="daa26-110">回転値を累積させるには、アニメーションの <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> と <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="daa26-110">To make rotation values accumulate, set the animation's <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> and <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> properties to `true`.</span></span>  
  
 <span data-ttu-id="daa26-111">完全なサンプルについては、「[パスアニメーションのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa26-111">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="daa26-112">オフセットを累積せずにパスに沿って <xref:System.Windows.Media.Matrix> 値をアニメーション化する方法を示す例については、「[パスに沿ってオブジェクトをアニメーション化する (行列アニメーション)](how-to-animate-an-object-along-a-path-matrix-animation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="daa26-112">For an example showing how to animate a <xref:System.Windows.Media.Matrix> value along a path without offset accumulation, see [Animate an Object Along a Path (Matrix Animation)](how-to-animate-an-object-along-a-path-matrix-animation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa26-113">参照</span><span class="sxs-lookup"><span data-stu-id="daa26-113">See also</span></span>

- [<span data-ttu-id="daa26-114">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="daa26-114">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="daa26-115">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="daa26-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
