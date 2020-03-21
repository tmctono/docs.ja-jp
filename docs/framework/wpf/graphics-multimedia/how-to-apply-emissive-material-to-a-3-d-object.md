---
title: '方法: 3D オブジェクトにエミセッシブ マテリアルを適用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112155"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a><span data-ttu-id="9aa48-102">方法: 3D オブジェクトにエミセッシブ マテリアルを適用する</span><span class="sxs-lookup"><span data-stu-id="9aa48-102">How to: Apply Emissive Material to a 3D Object</span></span>
<span data-ttu-id="9aa48-103">次の例は、既存の<xref:System.Windows.Media.Media3D.EmissiveMaterial>マテリアルに、EmissiveMaterial のブラシの色と等しい色を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9aa48-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="9aa48-104">次のコードは<xref:System.Windows.Media.Media3D.DiffuseMaterial>、DiffuseMaterial の外観に青を追加するために、組み合わせて表示され<xref:System.Windows.Media.Media3D.EmissiveMaterial>、適用されています。</span><span class="sxs-lookup"><span data-stu-id="9aa48-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="9aa48-105">手続き型コード:</span><span class="sxs-lookup"><span data-stu-id="9aa48-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="9aa48-106">例</span><span class="sxs-lookup"><span data-stu-id="9aa48-106">Example</span></span>  
 <span data-ttu-id="9aa48-107">次のコードは、XAML のサンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="9aa48-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="9aa48-108">例</span><span class="sxs-lookup"><span data-stu-id="9aa48-108">Example</span></span>  
 <span data-ttu-id="9aa48-109">以下は、手続き型コードのサンプル全体です。</span><span class="sxs-lookup"><span data-stu-id="9aa48-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9aa48-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="9aa48-110">See also</span></span>

- [<span data-ttu-id="9aa48-111">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="9aa48-111">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="9aa48-112">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="9aa48-112">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="9aa48-113">3D シーンでのマテリアル プロパティのアニメーション化</span><span class="sxs-lookup"><span data-stu-id="9aa48-113">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="9aa48-114">3D オブジェクトの前面と背面にマテリアルを適用する</span><span class="sxs-lookup"><span data-stu-id="9aa48-114">Apply Material to the Front and Back of a 3D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
