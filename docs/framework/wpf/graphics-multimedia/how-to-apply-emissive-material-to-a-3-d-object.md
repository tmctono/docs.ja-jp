---
title: '方法: 3-D モデルに発色マテリアルを適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: b898148fa07950e3ad1eddcaf9206f7d6a837241
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698981"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="e184c-102">方法: 3-D モデルに発色マテリアルを適用する</span><span class="sxs-lookup"><span data-stu-id="e184c-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="e184c-103">次の例は、使用する方法を示します<xref:System.Windows.Media.Media3D.EmissiveMaterial>EmissiveMaterial のブラシの色に等しい既存の材料に色を追加します。</span><span class="sxs-lookup"><span data-stu-id="e184c-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="e184c-104">次のコード<xref:System.Windows.Media.Media3D.DiffuseMaterial>と<xref:System.Windows.Media.Media3D.EmissiveMaterial>DiffuseMaterial の外観に青色を追加するための組み合わせに適用します。</span><span class="sxs-lookup"><span data-stu-id="e184c-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="e184c-105">手続き型コード。</span><span class="sxs-lookup"><span data-stu-id="e184c-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="e184c-106">例</span><span class="sxs-lookup"><span data-stu-id="e184c-106">Example</span></span>  
 <span data-ttu-id="e184c-107">次のコードでは、XAML でサンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="e184c-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e184c-108">例</span><span class="sxs-lookup"><span data-stu-id="e184c-108">Example</span></span>  
 <span data-ttu-id="e184c-109">以下の手続き型コード全体のサンプルに示します。</span><span class="sxs-lookup"><span data-stu-id="e184c-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e184c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e184c-110">See also</span></span>

- [<span data-ttu-id="e184c-111">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="e184c-111">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="e184c-112">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="e184c-112">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="e184c-113">3-D シーンで素材プロパティをアニメーション化する</span><span class="sxs-lookup"><span data-stu-id="e184c-113">Animate Material Properties in a 3-D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="e184c-114">3-D オブジェクトの前面および背面に素材を適用する</span><span class="sxs-lookup"><span data-stu-id="e184c-114">Apply Material to the Front and Back of a 3-D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
