---
title: '方法: パスに沿ってオブジェクトをアニメーション化する (行列アニメーション)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 3c90d20cac60004aa9876d9fe8d213d33c5a6883
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651436"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="7b8c6-102">方法: パスに沿ってオブジェクトをアニメーション化する (行列アニメーション)</span><span class="sxs-lookup"><span data-stu-id="7b8c6-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="7b8c6-103">この例は、使用する方法を示します、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>で定義されているパスに沿ってオブジェクトをアニメーション化するクラス、<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b8c6-104">例</span><span class="sxs-lookup"><span data-stu-id="7b8c6-104">Example</span></span>  
 <span data-ttu-id="7b8c6-105">次の例では、以下の処理を実行し、パスに沿ってオブジェクトをアニメーション化します。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="7b8c6-106">適用対象を<xref:System.Windows.Media.MatrixTransform>移動するには、オブジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="7b8c6-107">使用してパスを定義、<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="7b8c6-108">作成、<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>をアニメーション化するために使用して、<xref:System.Windows.Media.Matrix>のプロパティ、<xref:System.Windows.Media.MatrixTransform>します。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="7b8c6-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>は、<xref:System.Windows.Media.PathGeometry>しを使用して生成<xref:System.Windows.Media.Matrix>値。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="7b8c6-110">サンプル全体については、次を参照してください。[パス アニメーションのサンプル](https://go.microsoft.com/fwlink/?LinkID=160028)します。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-110">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span> <span data-ttu-id="7b8c6-111">ジオメトリック パスの詳細については、次を参照してください。、[ジオメトリの概要](geometry-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8c6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b8c6-112">See also</span></span>

- [<span data-ttu-id="7b8c6-113">アニメーションの概要</span><span class="sxs-lookup"><span data-stu-id="7b8c6-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="7b8c6-114">パス アニメーションのサンプル</span><span class="sxs-lookup"><span data-stu-id="7b8c6-114">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="7b8c6-115">パス アニメーションに関する「方法」トピック</span><span class="sxs-lookup"><span data-stu-id="7b8c6-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
