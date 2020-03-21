---
title: '方法: 3D モデルに図面を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112181"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="e219b-102">方法: 3D モデルに図面を適用する</span><span class="sxs-lookup"><span data-stu-id="e219b-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="e219b-103">この例では、3D<xref:System.Windows.Media.DrawingBrush>モデルに<xref:System.Windows.Media.Media3D.Material>適用された a を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e219b-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="e219b-104">次のコードでは、<xref:System.Windows.Media.DrawingGroup>の内容として<xref:System.Windows.Media.DrawingBrush>を定義します。</span><span class="sxs-lookup"><span data-stu-id="e219b-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="e219b-105"><xref:System.Windows.Media.DrawingBrush>は、3D<xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A>平面に適用<xref:System.Windows.Media.Media3D.DiffuseMaterial>されるプロパティとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="e219b-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="e219b-106">多くの場合、以下の図のような複雑なオブジェクトや値を、再利用してコードを単純化できるリソースとして定義することが望ましい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e219b-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="e219b-107">詳細については[、「XAML リソース](../../../desktop-wpf/fundamentals/xaml-resources-define.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e219b-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="e219b-108">例</span><span class="sxs-lookup"><span data-stu-id="e219b-108">Example</span></span>

<span data-ttu-id="e219b-109">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="e219b-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="e219b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e219b-110">See also</span></span>

- [<span data-ttu-id="e219b-111">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="e219b-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="e219b-112">3D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="e219b-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="e219b-113">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="e219b-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="e219b-114">3D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="e219b-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
