---
title: '方法 : 3-D モデルに描画を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459371"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="0bcae-102">方法 : 3-D モデルに描画を適用する</span><span class="sxs-lookup"><span data-stu-id="0bcae-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="0bcae-103">この例では、<xref:System.Windows.Media.DrawingBrush> を3-d モデルに適用する <xref:System.Windows.Media.Media3D.Material> として使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0bcae-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="0bcae-104">次のコードは、<xref:System.Windows.Media.DrawingBrush>のコンテンツとして <xref:System.Windows.Media.DrawingGroup> を定義します。</span><span class="sxs-lookup"><span data-stu-id="0bcae-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="0bcae-105"><xref:System.Windows.Media.DrawingBrush> は、3-d 平面に適用される <xref:System.Windows.Media.Media3D.DiffuseMaterial> の <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> プロパティとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="0bcae-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="0bcae-106">多くの場合、次の図のような複雑なオブジェクトと値をリソースとして定義することをお勧めします。これは、コードを再利用し、簡略化することができます。</span><span class="sxs-lookup"><span data-stu-id="0bcae-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="0bcae-107">詳細については、「 [XAML リソース](../../../desktop-wpf/fundamentals/xaml-resources-define.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bcae-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="0bcae-108">例</span><span class="sxs-lookup"><span data-stu-id="0bcae-108">Example</span></span>

<span data-ttu-id="0bcae-109">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="0bcae-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="0bcae-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0bcae-110">See also</span></span>

- [<span data-ttu-id="0bcae-111">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="0bcae-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="0bcae-112">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="0bcae-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="0bcae-113">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="0bcae-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="0bcae-114">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="0bcae-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
