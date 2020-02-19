---
title: '方法 : 複合図形を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452098"
---
# <a name="how-to-create-a-composite-shape"></a><span data-ttu-id="6c105-102">方法 : 複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="6c105-102">How to: Create a Composite Shape</span></span>
<span data-ttu-id="6c105-103">この例では、<xref:System.Windows.Media.Geometry> オブジェクトを使用して複合図形を作成し、<xref:System.Windows.Shapes.Path> 要素を使用してその図形を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c105-103">This example shows how to create composite shapes using <xref:System.Windows.Media.Geometry> objects and display them using a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="6c105-104">次の例では、複合図形を作成するために、<xref:System.Windows.Media.LineGeometry>、<xref:System.Windows.Media.EllipseGeometry>、および <xref:System.Windows.Media.RectangleGeometry> を <xref:System.Windows.Media.GeometryGroup> と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="6c105-104">In the following example, a <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>, and a <xref:System.Windows.Media.RectangleGeometry> are used with a <xref:System.Windows.Media.GeometryGroup> to create a composite shape.</span></span> <span data-ttu-id="6c105-105">次に、<xref:System.Windows.Shapes.Path> 要素を使用してジオメトリが描画されます。</span><span class="sxs-lookup"><span data-stu-id="6c105-105">The geometries are then drawn using a <xref:System.Windows.Shapes.Path> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c105-106">例</span><span class="sxs-lookup"><span data-stu-id="6c105-106">Example</span></span>  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 <span data-ttu-id="6c105-107">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6c105-107">The following illustration shows the shape created in the previous example.</span></span>  
  
 <span data-ttu-id="6c105-108">![System.windows.media.geometrygroup> を使用して作成された複合ジオメトリ](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span><span class="sxs-lookup"><span data-stu-id="6c105-108">![A composite geometry created using a GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")</span></span>  
<span data-ttu-id="6c105-109">複合ジオメトリ</span><span class="sxs-lookup"><span data-stu-id="6c105-109">Composite Geometry</span></span>  
  
 <span data-ttu-id="6c105-110">多角形や曲線セグメントを持つ図形など、より複雑な図形は、<xref:System.Windows.Media.PathGeometry>を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="6c105-110">More complex shapes, such as polygons and shapes with curved segments, may be created using a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="6c105-111"><xref:System.Windows.Media.PathGeometry>を使用して図形を作成する方法を示す例については、「 [PathGeometry を使用](how-to-create-a-shape-by-using-a-pathgeometry.md)して図形を作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c105-111">For an example showing how to create a shape using a <xref:System.Windows.Media.PathGeometry>, see [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  <span data-ttu-id="6c105-112">この例では、<xref:System.Windows.Shapes.Path> 要素を使用して図形を画面に表示しますが、<xref:System.Windows.Media.Geometry> オブジェクトを使用して <xref:System.Windows.Media.GeometryDrawing> または <xref:System.Windows.Media.DrawingContext>の内容を記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c105-112">Although this example renders a shape to the screen using a <xref:System.Windows.Shapes.Path> element, <xref:System.Windows.Media.Geometry> objects may also be used to describe the contents of a <xref:System.Windows.Media.GeometryDrawing> or a <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="6c105-113">また、クリッピングやヒットテストに使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c105-113">They may also be used for clipping and hit-testing.</span></span>  
  
 <span data-ttu-id="6c105-114">この例は、より大きなサンプルの一部です。完全なサンプルについては、「[ジオメトリのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c105-114">This example is part of larger sample; for the complete sample, see the [Geometries Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).</span></span>
