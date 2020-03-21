---
title: '方法 : ジオメトリック パスを使用してオブジェクトを回転させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186876"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="9c4a7-102">方法 : ジオメトリック パスを使用してオブジェクトを回転させる</span><span class="sxs-lookup"><span data-stu-id="9c4a7-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="9c4a7-103">この例では、オブジェクトによって定義されたジオメトリパスに沿ってオブジェクトを回転 (ピボット)<xref:System.Windows.Media.PathGeometry>する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c4a7-104">例</span><span class="sxs-lookup"><span data-stu-id="9c4a7-104">Example</span></span>  
 <span data-ttu-id="9c4a7-105">次の例では、3 つの<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>オブジェクトを使用して、四角形をジオメトリパスに沿って移動します。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="9c4a7-106">最初<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>のアニメーション<xref:System.Windows.Media.RotateTransform>は、四角形に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="9c4a7-107">アニメーションは、角度の値を生成します。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-107">The animation generates angle values.</span></span> <span data-ttu-id="9c4a7-108">これにより、四角形がパスの輪郭に沿って回転 (ピボット) します。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="9c4a7-109">他の 2 つのオブジェクトは<xref:System.Windows.Media.TranslateTransform.X%2A>、<xref:System.Windows.Media.TranslateTransform.Y%2A>四角形に<xref:System.Windows.Media.TranslateTransform>適用される の と の値をアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="9c4a7-110">これにより、四角形が、パスに沿って水平方向と垂直方向に移動します。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="9c4a7-111">ジオメトリパスを使用してオブジェクトを回転するもう 1 つの方法<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>は、オブジェクトを<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A>使用して`true`そのプロパティを に設定することです。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="9c4a7-112">詳細と例については、「[ジオメトリック パスを使用してオブジェクトを回転する (行列アニメーション)」](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="9c4a7-113">完全なサンプルについては、「[パス アニメーションのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c4a7-113">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c4a7-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c4a7-114">See also</span></span>

- [<span data-ttu-id="9c4a7-115">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="9c4a7-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="9c4a7-116">パス アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="9c4a7-116">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="9c4a7-117">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="9c4a7-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
