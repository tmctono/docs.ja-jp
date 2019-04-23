---
title: '方法: GeometryDrawing を作成する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179791"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="60400-102">方法: GeometryDrawing を作成する</span><span class="sxs-lookup"><span data-stu-id="60400-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="60400-103">この例は、作成および表示する方法を示しています、<xref:System.Windows.Media.GeometryDrawing>します。</span><span class="sxs-lookup"><span data-stu-id="60400-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="60400-104">A<xref:System.Windows.Media.GeometryDrawing>塗りつぶしをアウトラインと関連付けることによって図形を作成することができます、<xref:System.Windows.Media.Pen>と<xref:System.Windows.Media.Brush>で、<xref:System.Windows.Media.Geometry>します。</span><span class="sxs-lookup"><span data-stu-id="60400-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="60400-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A>図形の構造体について説明します、<xref:System.Windows.Media.GeometryDrawing.Brush%2A>図形の塗りつぶし、について説明しますと、<xref:System.Windows.Media.GeometryDrawing.Pen%2A>図形のアウトラインをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="60400-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60400-106">例</span><span class="sxs-lookup"><span data-stu-id="60400-106">Example</span></span>  
 <span data-ttu-id="60400-107">次の例では、<xref:System.Windows.Media.GeometryDrawing>図形を表示するためにします。</span><span class="sxs-lookup"><span data-stu-id="60400-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="60400-108">図形は、<xref:System.Windows.Media.GeometryGroup>と 2 つ<xref:System.Windows.Media.EllipseGeometry>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="60400-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="60400-109">図形の内部を塗りつぶす、<xref:System.Windows.Media.LinearGradientBrush>アウトラインの描画に使用して、 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>します。</span><span class="sxs-lookup"><span data-stu-id="60400-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="60400-110"><xref:System.Windows.Media.GeometryDrawing>を使用して表示される、<xref:System.Windows.Media.ImageDrawing>と<xref:System.Windows.Controls.Image>要素。</span><span class="sxs-lookup"><span data-stu-id="60400-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="60400-111">次の図は、その結果<xref:System.Windows.Media.GeometryDrawing>します。</span><span class="sxs-lookup"><span data-stu-id="60400-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="60400-112">![2 つの楕円の GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="60400-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="60400-113">複雑な図面を作成するには、1 つの複合描画を使用してに複数の描画オブジェクトを結合できます、<xref:System.Windows.Media.DrawingGroup>します。</span><span class="sxs-lookup"><span data-stu-id="60400-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60400-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="60400-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="60400-115">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="60400-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="60400-116">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="60400-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="60400-117">複合描画を作成する</span><span class="sxs-lookup"><span data-stu-id="60400-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
