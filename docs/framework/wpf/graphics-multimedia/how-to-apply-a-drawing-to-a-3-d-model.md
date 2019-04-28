---
title: '方法: 3-D モデルに描画を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: a20b89a7359fc85d9790ac02dd2b173452df8c22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699111"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="2034f-102">方法: 3-D モデルに描画を適用する</span><span class="sxs-lookup"><span data-stu-id="2034f-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="2034f-103">この例は、使用する方法を示します、<xref:System.Windows.Media.DrawingBrush>として、<xref:System.Windows.Media.Media3D.Material>に適用される、[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]モデル。</span><span class="sxs-lookup"><span data-stu-id="2034f-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="2034f-104">次のコード定義を<xref:System.Windows.Media.DrawingGroup>の内容として、<xref:System.Windows.Media.DrawingBrush>します。</span><span class="sxs-lookup"><span data-stu-id="2034f-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="2034f-105"><xref:System.Windows.Media.DrawingBrush>として設定されて、<xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>のプロパティ、<xref:System.Windows.Media.Media3D.DiffuseMaterial>に適用される、[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)]平面。</span><span class="sxs-lookup"><span data-stu-id="2034f-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="2034f-106">**注:** 多くの場合、複雑なオブジェクトと次の図のような値を再利用できるし、コードを簡略化するリソースとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2034f-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="2034f-107">参照してください[XAML リソース](../advanced/xaml-resources.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="2034f-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="2034f-108">例</span><span class="sxs-lookup"><span data-stu-id="2034f-108">Example</span></span>  
 <span data-ttu-id="2034f-109">次のコードでは、全体のサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="2034f-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2034f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="2034f-110">See also</span></span>

- [<span data-ttu-id="2034f-111">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="2034f-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="2034f-112">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="2034f-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="2034f-113">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="2034f-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="2034f-114">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="2034f-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
