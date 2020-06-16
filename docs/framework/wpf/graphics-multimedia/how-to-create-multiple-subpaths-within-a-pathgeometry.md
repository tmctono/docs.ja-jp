---
title: '方法: PathGeometry 内に複数のサブパスを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 286075448cd6a343f8a7b15b2b5005f840f68e1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904723"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="f8150-102">方法: PathGeometry 内に複数のサブパスを作成する</span><span class="sxs-lookup"><span data-stu-id="f8150-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="f8150-103">この例では、<xref:System.Windows.Media.PathGeometry> に複数のサブパスを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8150-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f8150-104">サブパスを複数作成するには、サブパスごとに <xref:System.Windows.Media.PathFigure> を作成します。</span><span class="sxs-lookup"><span data-stu-id="f8150-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8150-105">例</span><span class="sxs-lookup"><span data-stu-id="f8150-105">Example</span></span>  
 <span data-ttu-id="f8150-106">次の例では、それぞれが三角形である 2 つのサブパスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f8150-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="f8150-107">次の例では、<xref:System.Windows.Shapes.Path> と [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の属性構文を使用して、サブパスを複数作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8150-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="f8150-108">各 `M` では、新しいサブパスが作成されるので、この例では、それぞれが三角形を描画する 2 つのサブパスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f8150-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="f8150-109">(この属性構文では、実際には <xref:System.Windows.Media.PathGeometry> の軽量バージョンである <xref:System.Windows.Media.StreamGeometry> が作成されます。)</span><span class="sxs-lookup"><span data-stu-id="f8150-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f8150-110">詳細については、「[パス マークアップ構文](path-markup-syntax.md)」のページを参照してください。)</span><span class="sxs-lookup"><span data-stu-id="f8150-110">For more information, see the [Path Markup Syntax](path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8150-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8150-111">See also</span></span>

- [<span data-ttu-id="f8150-112">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="f8150-112">Geometry Overview</span></span>](geometry-overview.md)
