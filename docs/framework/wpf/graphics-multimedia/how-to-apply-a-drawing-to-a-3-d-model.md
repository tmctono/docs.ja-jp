---
title: '方法: 3-D モデルに描画を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 8ac24fdf8d7e407e10764c17fcc12121aa5f51d7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662809"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="feb77-102">方法: 3-D モデルに描画を適用する</span><span class="sxs-lookup"><span data-stu-id="feb77-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="feb77-103">この例は、使用する方法を示します、<xref:System.Windows.Media.DrawingBrush>として、 <xref:System.Windows.Media.Media3D.Material> 3-D モデルに適用します。</span><span class="sxs-lookup"><span data-stu-id="feb77-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>  
  
 <span data-ttu-id="feb77-104">次のコード定義を<xref:System.Windows.Media.DrawingGroup>の内容として、<xref:System.Windows.Media.DrawingBrush>します。</span><span class="sxs-lookup"><span data-stu-id="feb77-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="feb77-105"><xref:System.Windows.Media.DrawingBrush>として設定されて、<xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>のプロパティ、 <xref:System.Windows.Media.Media3D.DiffuseMaterial> 3-D 平面に適用します。</span><span class="sxs-lookup"><span data-stu-id="feb77-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>  
  
 <span data-ttu-id="feb77-106">**注:** 多くの場合、複雑なオブジェクトと次の図のような値を再利用できるし、コードを簡略化するリソースとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feb77-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="feb77-107">参照してください[XAML リソース](../advanced/xaml-resources.md)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="feb77-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="feb77-108">例</span><span class="sxs-lookup"><span data-stu-id="feb77-108">Example</span></span>  
 <span data-ttu-id="feb77-109">次のコードでは、全体のサンプルを示します。</span><span class="sxs-lookup"><span data-stu-id="feb77-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="feb77-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="feb77-110">See also</span></span>

- [<span data-ttu-id="feb77-111">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="feb77-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="feb77-112">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="feb77-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="feb77-113">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="feb77-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="feb77-114">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="feb77-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
