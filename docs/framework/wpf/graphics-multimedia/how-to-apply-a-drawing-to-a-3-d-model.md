---
title: '方法: 3-D モデルに描画を適用する'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855875"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="5a948-102">方法: 3-D モデルに描画を適用する</span><span class="sxs-lookup"><span data-stu-id="5a948-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="5a948-103">この例では、を<xref:System.Windows.Media.DrawingBrush> 3-d モデルに適用された<xref:System.Windows.Media.Media3D.Material>として使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5a948-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="5a948-104">次のコードでは<xref:System.Windows.Media.DrawingGroup> 、を<xref:System.Windows.Media.DrawingBrush>のコンテンツとして定義しています。</span><span class="sxs-lookup"><span data-stu-id="5a948-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="5a948-105">は、3-d 平面に<xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial>適用されるのプロパティとして設定されます。<xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="5a948-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="5a948-106">多くの場合、次の図のような複雑なオブジェクトと値をリソースとして定義することをお勧めします。これは、コードを再利用し、簡略化することができます。</span><span class="sxs-lookup"><span data-stu-id="5a948-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="5a948-107">詳細については、「 [XAML リソース](../advanced/xaml-resources.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a948-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="5a948-108">例</span><span class="sxs-lookup"><span data-stu-id="5a948-108">Example</span></span>

<span data-ttu-id="5a948-109">次のコードは、サンプル全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a948-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="5a948-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a948-110">See also</span></span>

- [<span data-ttu-id="5a948-111">XAML リソース</span><span class="sxs-lookup"><span data-stu-id="5a948-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="5a948-112">3-D シーンを作成する</span><span class="sxs-lookup"><span data-stu-id="5a948-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="5a948-113">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="5a948-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="5a948-114">3-D グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="5a948-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
