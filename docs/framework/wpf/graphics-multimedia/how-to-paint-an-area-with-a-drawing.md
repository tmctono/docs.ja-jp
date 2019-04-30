---
title: '方法: 描画を使用して領域を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with drawings
- painting [WPF], with drawings
- drawings [WPF], painting with
ms.assetid: c10dc4b1-09b1-41e8-ad14-456b5fb377df
ms.openlocfilehash: 6b204ae631912181333e2559ebadcdc37e7693b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010075"
---
# <a name="how-to-paint-an-area-with-a-drawing"></a><span data-ttu-id="1d3e9-102">方法: 描画を使用して領域を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="1d3e9-102">How to: Paint an Area with a Drawing</span></span>
<span data-ttu-id="1d3e9-103">この例では、描画を使用して領域を塗りつぶす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-103">This example shows how to paint an area with a drawing.</span></span> <span data-ttu-id="1d3e9-104">使用する描画を使用して領域を描画する、<xref:System.Windows.Media.DrawingBrush>と 1 つ以上<xref:System.Windows.Media.Drawing>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-104">To paint an area with a drawing, you use a <xref:System.Windows.Media.DrawingBrush> and one or more <xref:System.Windows.Media.Drawing> objects.</span></span>   <span data-ttu-id="1d3e9-105">次の例では、<xref:System.Windows.Media.DrawingBrush>の 2 つの楕円の描画を使用してオブジェクトを描画します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-105">The following example uses a <xref:System.Windows.Media.DrawingBrush> to paint an object with a drawing of two ellipses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d3e9-106">例</span><span class="sxs-lookup"><span data-stu-id="1d3e9-106">Example</span></span>  
 [!code-xaml[drawingbrush_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/DrawingBrushExample.xaml#drawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/DrawingBrushExample.cs#drawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#DrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/DrawingBrushExample.vb#drawingbrushexamplewholepage)]  
  
 <span data-ttu-id="1d3e9-107">この例の出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-107">The following illustration shows the example's output.</span></span>  
  
 <span data-ttu-id="1d3e9-108">![DrawingBrush からの出力](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span><span class="sxs-lookup"><span data-stu-id="1d3e9-108">![Output from a DrawingBrush](./media/graphicsmm-drawingbrush-simple.png "graphicsmm_drawingbrush_simple")</span></span>  
  
 <span data-ttu-id="1d3e9-109">(で説明した理由から、図形の中心が白い[複合図形の塗りつぶしを制御](how-to-control-the-fill-of-a-composite-shape.md))。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-109">(The center of the shape is white for reasons described in     [Control the Fill of a Composite Shape](how-to-control-the-fill-of-a-composite-shape.md).)</span></span>  
  
 <span data-ttu-id="1d3e9-110">設定して、<xref:System.Windows.Media.DrawingBrush>オブジェクトの<xref:System.Windows.Media.TileBrush.Viewport%2A>と<xref:System.Windows.Media.TileBrush.TileMode%2A>プロパティ、繰り返しパターンを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-110">By setting a <xref:System.Windows.Media.DrawingBrush> object's <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties, you can create a repeating pattern.</span></span> <span data-ttu-id="1d3e9-111">2 つの楕円の描画から作成されるパターンで、オブジェクトを塗りつぶす例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-111">The following example paints an object with a pattern created from a drawing of two ellipses.</span></span>  
  
 [!code-xaml[drawingbrush_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_snip/CS/TiledDrawingBrushExample.xaml#tileddrawingbrushexamplewholepage)]  
  
 [!code-csharp[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/drawingbrush_procedural_snip/CSharp/TiledDrawingBrushExample.cs#tileddrawingbrushexamplewholepage)]
 [!code-vb[drawingbrush_procedural_snip#TiledDrawingBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/drawingbrush_procedural_snip/VisualBasic/TiledDrawingBrushExample.vb#tileddrawingbrushexamplewholepage)]  
  
 <span data-ttu-id="1d3e9-112">次の図は、並べて表示された<xref:System.Windows.Media.DrawingBrush>出力します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-112">The following illustration shows the tiled <xref:System.Windows.Media.DrawingBrush> output.</span></span>  
  
 <span data-ttu-id="1d3e9-113">![並べて表示された DrawingBrush の出力](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span><span class="sxs-lookup"><span data-stu-id="1d3e9-113">![Tiled output from a DrawingBrush](./media/graphicsmm-drawingbrush-tiled.png "graphicsmm_drawingbrush_tiled")</span></span>  
  
 <span data-ttu-id="1d3e9-114">描画ブラシの詳細については、次を参照してください。[イメージ、描画、およびビジュアル](painting-with-images-drawings-and-visuals.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-114">For more information about drawing brushes, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span> <span data-ttu-id="1d3e9-115">詳細については<xref:System.Windows.Media.Drawing>、オブジェクトを参照してください、 [Drawing オブジェクトの概要](drawing-objects-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="1d3e9-115">For more information about <xref:System.Windows.Media.Drawing> objects, see the [Drawing Objects Overview](drawing-objects-overview.md).</span></span>
