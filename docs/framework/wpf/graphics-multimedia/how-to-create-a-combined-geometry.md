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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910095"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="b8352-102">方法: 結合したジオメトリを作成する</span><span class="sxs-lookup"><span data-stu-id="b8352-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="b8352-103">この例では、ジオメトリを結合する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8352-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="b8352-104">2 つのジオメトリを結合するを使用して、<xref:System.Windows.Media.CombinedGeometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="b8352-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="b8352-105">設定の<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>と<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>結合、および設定する 2 つのジオメトリとプロパティ、 <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> 、ジオメトリをまとめて結合が方法を決定するプロパティを`Union`、 `Intersect`、 `Exclude`、または`Xor`.</span><span class="sxs-lookup"><span data-stu-id="b8352-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="b8352-106">2 つ以上のジオメトリから複合ジオメトリを作成するには、使用、<xref:System.Windows.Media.GeometryGroup>します。</span><span class="sxs-lookup"><span data-stu-id="b8352-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8352-107">例</span><span class="sxs-lookup"><span data-stu-id="b8352-107">Example</span></span>  
 <span data-ttu-id="b8352-108">次の例では、<xref:System.Windows.Media.CombinedGeometry>のジオメトリの結合モードで定義されて`Exclude`します。</span><span class="sxs-lookup"><span data-stu-id="b8352-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="b8352-109">と<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> は<xref:System.Windows.Media.CombinedGeometry.Geometry2%2A>両方とも同じ半径の円として定義されていますが、中心が50でオフセットされています。</span><span class="sxs-lookup"><span data-stu-id="b8352-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="b8352-110">![結果を除外組み合わせモード](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="b8352-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="b8352-111">結合したジオメトリの除外</span><span class="sxs-lookup"><span data-stu-id="b8352-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="b8352-112">次のマークアップで、<xref:System.Windows.Media.CombinedGeometry>の結合モードで定義されて`Intersect`します。</span><span class="sxs-lookup"><span data-stu-id="b8352-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="b8352-113">両方<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>、 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 と <xref:system.windows.media.combinedgeometry.geometry2%2a> が、同じ半径の円として定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8352-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="b8352-114">![交差の結果の結合モード](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="b8352-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="b8352-115">結合したジオメトリを交差します。</span><span class="sxs-lookup"><span data-stu-id="b8352-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="b8352-116">次のマークアップで、<xref:System.Windows.Media.CombinedGeometry>の結合モードで定義されて`Union`します。</span><span class="sxs-lookup"><span data-stu-id="b8352-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="b8352-117">両方<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>、 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 と <xref:system.windows.media.combinedgeometry.geometry2%2a> が、同じ半径の円として定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8352-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="b8352-118">![和集合結合モードの結果](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="b8352-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="b8352-119">結合された Geometry の和集合</span><span class="sxs-lookup"><span data-stu-id="b8352-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="b8352-120">次のマークアップで、<xref:System.Windows.Media.CombinedGeometry>の結合モードで定義されて`Xor`します。</span><span class="sxs-lookup"><span data-stu-id="b8352-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="b8352-121">両方<xref:System.Windows.Media.CombinedGeometry.Geometry1%2A>、 <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> 50 と <xref:system.windows.media.combinedgeometry.geometry2%2a> が、同じ半径の円として定義されます。</span><span class="sxs-lookup"><span data-stu-id="b8352-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="b8352-122">![Xor 結合モードの結果](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="b8352-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="b8352-123">結合したジオメトリの Xor</span><span class="sxs-lookup"><span data-stu-id="b8352-123">Combined Geometry Xor</span></span>
