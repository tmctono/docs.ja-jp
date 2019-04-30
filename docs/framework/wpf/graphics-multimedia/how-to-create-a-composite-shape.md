---
title: '方法: 複合図形を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: de9f7972c7a51ea623c3630fe62bb48f6109317e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052899"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="abe60-102">方法: 複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="abe60-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="abe60-103">この例を使用して複合図形を作成する方法を示しています。<xref:System.Windows.Media.Geometry>オブジェクトとそれらを表示を使用して、<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="abe60-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="abe60-104">次の例では、 <xref:System.Windows.Media.LineGeometry>、<xref:System.Windows.Media.EllipseGeometry>と<xref:System.Windows.Media.RectangleGeometry>を併用、<xref:System.Windows.Media.GeometryGroup>複合図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="abe60-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="abe60-105">ジオメトリを使用して描画し、<xref:System.Windows.Shapes.Path>要素。</span><span class="sxs-lookup"><span data-stu-id="abe60-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abe60-106">例</span><span class="sxs-lookup"><span data-stu-id="abe60-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="abe60-107">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="abe60-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="abe60-108">![GeometryGroup を使用して作成された複合ジオメトリ](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="abe60-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="abe60-109">複合ジオメトリ</span><span class="sxs-lookup"><span data-stu-id="abe60-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="abe60-110">使用して多角形と曲線のセグメントを持つ図形などのより複雑な図形を作成することがあります、<xref:System.Windows.Media.PathGeometry>します。</span><span class="sxs-lookup"><span data-stu-id="abe60-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="abe60-111">使用して図形を作成する方法を示す例については、<xref:System.Windows.Media.PathGeometry>を参照してください[PathGeometry を使用して図形を作成](how-to-create-a-shape-by-using-a-pathgeometry.md)です。</span><span class="sxs-lookup"><span data-stu-id="abe60-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="abe60-112">この例を使用して、画面に図形をレンダリングしますが、<xref:System.Windows.Shapes.Path>要素、<xref:System.Windows.Media.Geometry>オブジェクトがの内容を記述することも可能性があります、<xref:System.Windows.Media.GeometryDrawing>または<xref:System.Windows.Media.DrawingContext>します。</span><span class="sxs-lookup"><span data-stu-id="abe60-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="abe60-113">また、クリップのヒット テストも使用可能性があります。</span><span class="sxs-lookup"><span data-stu-id="abe60-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="abe60-114">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://go.microsoft.com/fwlink/?LinkID=159989)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abe60-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://go.microsoft.com/fwlink/?LinkID=159989).</span></span>
