---
title: '方法: 結合したジオメトリを作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910095"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="42a6d-102">方法: 結合したジオメトリを作成する</span><span class="sxs-lookup"><span data-stu-id="42a6d-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="42a6d-103">この例は、ジオメトリを結合する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="42a6d-104">2 つのジオメトリを結合するには、<xref:System.Windows.Media.CombinedGeometry> オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="42a6d-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="42a6d-105">結合する 2 つのジオメトリでその <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> プロパティと <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> プロパティを設定します。また、ジオメトリの結合方法を決定する <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> プロパティを `Union`、`Intersect`、`Exclude`、または `Xor` に設定します。</span><span class="sxs-lookup"><span data-stu-id="42a6d-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="42a6d-106">2 つ以上のジオメトリから複合ジオメトリを作成するには、<xref:System.Windows.Media.GeometryGroup> を使用します。</span><span class="sxs-lookup"><span data-stu-id="42a6d-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42a6d-107">例</span><span class="sxs-lookup"><span data-stu-id="42a6d-107">Example</span></span>  
 <span data-ttu-id="42a6d-108">次の例では、<xref:System.Windows.Media.CombinedGeometry> が `Exclude` のジオメトリ結合モードで定義されています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="42a6d-109"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> と <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> は両方とも同じ半径の円として定義されますが、中心は 50 オフセットされています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="42a6d-110">![除外組み合わせモードの結果](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="42a6d-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="42a6d-111">結合したジオメトリの除外</span><span class="sxs-lookup"><span data-stu-id="42a6d-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="42a6d-112">次のマークアップでは、<xref:System.Windows.Media.CombinedGeometry> が `Intersect` の結合モードを指定して定義されています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="42a6d-113"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> と <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> は両方とも同じ半径の円として定義されますが、中心は 50 オフセットされています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="42a6d-114">![交差組み合わせモードの結果](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="42a6d-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="42a6d-115">結合したジオメトリの交差</span><span class="sxs-lookup"><span data-stu-id="42a6d-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="42a6d-116">次のマークアップでは、<xref:System.Windows.Media.CombinedGeometry> が `Union` の結合モードで定義されています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="42a6d-117"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> と <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> は両方とも同じ半径の円として定義されますが、中心は 50 オフセットされています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="42a6d-118">![和集合結合モードの結果](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="42a6d-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="42a6d-119">結合したジオメトリの和集合</span><span class="sxs-lookup"><span data-stu-id="42a6d-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="42a6d-120">次のマークアップでは、<xref:System.Windows.Media.CombinedGeometry> が `Xor` の結合モードで定義されています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="42a6d-121"><xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> と <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> は両方とも同じ半径の円として定義されますが、中心は 50 オフセットされています。</span><span class="sxs-lookup"><span data-stu-id="42a6d-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="42a6d-122">![Xor 結合モードの結果](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="42a6d-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="42a6d-123">結合したジオメトリの Xor</span><span class="sxs-lookup"><span data-stu-id="42a6d-123">Combined Geometry Xor</span></span>
