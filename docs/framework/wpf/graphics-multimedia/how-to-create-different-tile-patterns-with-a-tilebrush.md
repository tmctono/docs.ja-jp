---
title: '方法: TileBrush を使用してさまざまなタイル パターンを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: c1051b234961eee9ae740af2abac3d64c523656c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227406"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a><span data-ttu-id="28c06-102">方法: TileBrush を使用してさまざまなタイル パターンを作成する</span><span class="sxs-lookup"><span data-stu-id="28c06-102">How to: Create Different Tile Patterns with a TileBrush</span></span>
<span data-ttu-id="28c06-103">この例は、使用する方法を示します、<xref:System.Windows.Media.TileBrush.TileMode%2A>のプロパティを<xref:System.Windows.Media.TileBrush>パターンを作成します。</span><span class="sxs-lookup"><span data-stu-id="28c06-103">This example shows how to use the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.TileBrush> to create a pattern.</span></span>  
  
 <span data-ttu-id="28c06-104"><xref:System.Windows.Media.TileBrush.TileMode%2A>プロパティを使用すると、指定する方法のコンテンツを<xref:System.Windows.Media.TileBrush>が繰り返されますが、出力領域を埋めるに並べて表示。</span><span class="sxs-lookup"><span data-stu-id="28c06-104">The <xref:System.Windows.Media.TileBrush.TileMode%2A> property enables you to specify how the content of a <xref:System.Windows.Media.TileBrush> is repeated, that is, tiled to fill an output area.</span></span> <span data-ttu-id="28c06-105">パターンを作成するに設定する、<xref:System.Windows.Media.TileBrush.TileMode%2A>に<xref:System.Windows.Media.TileMode.Tile>、 <xref:System.Windows.Media.TileMode.FlipX>、 <xref:System.Windows.Media.TileMode.FlipY>、または<xref:System.Windows.Media.TileMode.FlipXY>します。</span><span class="sxs-lookup"><span data-stu-id="28c06-105">To create a pattern, you set the <xref:System.Windows.Media.TileBrush.TileMode%2A> to <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, or <xref:System.Windows.Media.TileMode.FlipXY>.</span></span> <span data-ttu-id="28c06-106">設定する必要があります、<xref:System.Windows.Media.TileBrush.Viewport%2A>の<xref:System.Windows.Media.TileBrush>; 描画している領域よりも小さくなるようにそれ以外の場合、タイルが 1 つだけに関係なく、生成されたこの<xref:System.Windows.Media.TileBrush.TileMode%2A>設定を使用しています。</span><span class="sxs-lookup"><span data-stu-id="28c06-106">You must also set the <xref:System.Windows.Media.TileBrush.Viewport%2A> of the <xref:System.Windows.Media.TileBrush> so that it is smaller than the area that you are painting; otherwise, only a single tile is produced, regardless which <xref:System.Windows.Media.TileBrush.TileMode%2A> setting you use.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28c06-107">例</span><span class="sxs-lookup"><span data-stu-id="28c06-107">Example</span></span>  
 <span data-ttu-id="28c06-108">次の例では、5 で作成します<xref:System.Windows.Media.DrawingBrush>オブジェクトはそれぞれ異なる<xref:System.Windows.Media.TileBrush.TileMode%2A>を設定して、それらを 5 つの四角形の描画に使用します。</span><span class="sxs-lookup"><span data-stu-id="28c06-108">The following example creates five <xref:System.Windows.Media.DrawingBrush> objects, gives them each a different <xref:System.Windows.Media.TileBrush.TileMode%2A> setting, and uses them to paint five rectangles.</span></span> <span data-ttu-id="28c06-109">この例では、<xref:System.Windows.Media.DrawingBrush>クラスを示すために<xref:System.Windows.Media.TileBrush.TileMode%2A>の動作、<xref:System.Windows.Media.TileBrush.TileMode%2A>プロパティのすべての動作と同様、<xref:System.Windows.Media.TileBrush>オブジェクト、つまりの<xref:System.Windows.Media.ImageBrush>、<xref:System.Windows.Media.VisualBrush>と<xref:System.Windows.Media.DrawingBrush>します。</span><span class="sxs-lookup"><span data-stu-id="28c06-109">Although this example uses the <xref:System.Windows.Media.DrawingBrush> class to demonstrate <xref:System.Windows.Media.TileBrush.TileMode%2A> behavior, the <xref:System.Windows.Media.TileBrush.TileMode%2A> property works identically for all the <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, and <xref:System.Windows.Media.DrawingBrush>.</span></span>  
  
 <span data-ttu-id="28c06-110">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="28c06-110">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="28c06-111">![出力例を並べて表示する TileBrush](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span><span class="sxs-lookup"><span data-stu-id="28c06-111">![TileBrush tiling example output](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")</span></span>  
<span data-ttu-id="28c06-112">TileMode プロパティを使用して作成されたタイル パターン</span><span class="sxs-lookup"><span data-stu-id="28c06-112">Tile patterns created with the TileMode property</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="28c06-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="28c06-113">See also</span></span>

- [<span data-ttu-id="28c06-114">TileBrush のタイル サイズを設定する</span><span class="sxs-lookup"><span data-stu-id="28c06-114">Set the Tile Size for a TileBrush</span></span>](how-to-set-the-tile-size-for-a-tilebrush.md)
- [<span data-ttu-id="28c06-115">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="28c06-115">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
