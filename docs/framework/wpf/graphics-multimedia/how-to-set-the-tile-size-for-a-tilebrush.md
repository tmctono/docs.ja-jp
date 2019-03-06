---
title: '方法: TileBrush のタイル サイズを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 2b603345e00ae3067c4be860b6aad1cf7b9883c5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354454"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="ae7c5-102">方法: TileBrush のタイル サイズを設定する</span><span class="sxs-lookup"><span data-stu-id="ae7c5-102">How to: Set the Tile Size for a TileBrush</span></span>
<span data-ttu-id="ae7c5-103">この例のタイル サイズを設定する方法を示しています、<xref:System.Windows.Media.TileBrush>します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="ae7c5-104">既定で、<xref:System.Windows.Media.TileBrush>描画している領域を完全に塗りつぶす 1 つのタイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="ae7c5-105">この動作をオーバーライドするには、設定、<xref:System.Windows.Media.TileBrush.Viewport%2A>と<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>  
  
 <span data-ttu-id="ae7c5-106"><xref:System.Windows.Media.TileBrush.Viewport%2A>プロパティのタイル サイズを指定します、<xref:System.Windows.Media.TileBrush>します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="ae7c5-107">既定の値で、<xref:System.Windows.Media.TileBrush.Viewport%2A>プロパティは、塗りつぶされる領域のサイズを基準とします。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="ae7c5-108">させる、<xref:System.Windows.Media.TileBrush.Viewport%2A>プロパティを絶対タイル サイズを指定する設定、<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>プロパティを<xref:System.Windows.Media.BrushMappingMode.Absolute>します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae7c5-109">例</span><span class="sxs-lookup"><span data-stu-id="ae7c5-109">Example</span></span>  
 <span data-ttu-id="ae7c5-110">次の例では、 <xref:System.Windows.Media.ImageBrush>、一種の<xref:System.Windows.Media.TileBrush>タイルを含む四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="ae7c5-111">例では、各タイルを出力領域 (四角形) の 50% x 50% に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-111">The example sets each tile to  50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="ae7c5-112">その結果、四角形は、イメージの 4 つの投影で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-112">As a result, the rectangle is painted with four projections of the image.</span></span>  
  
 <span data-ttu-id="ae7c5-113">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-113">The following illustration shows the output that the example produces.</span></span>
  
 <span data-ttu-id="ae7c5-114">![イメージ ブラシを並べて表示する例](./media/0.png "0")</span><span class="sxs-lookup"><span data-stu-id="ae7c5-114">![Example of tiling with an image brush](./media/0.png "0")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 <span data-ttu-id="ae7c5-115">次の例では、作成、 <xref:System.Windows.Media.ImageBrush>、設定、<xref:System.Windows.Media.TileBrush.Viewport%2A>に`0,0,25,25`とその<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>に<xref:System.Windows.Media.BrushMappingMode.Absolute>、され別の四角形を描画するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="ae7c5-116">その結果、ブラシは、幅が 25 ピクセル、高さが 25 ピクセルのタイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>  
  
 <span data-ttu-id="ae7c5-117">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-117">The following illustration shows the output that the example produces.</span></span>  
  
 <span data-ttu-id="ae7c5-118">![0,0,0.25,0.25 の Viewport を使用したタイル表示の TileBrush](./media/25x25viewport.png "25x25viewport")</span><span class="sxs-lookup"><span data-stu-id="ae7c5-118">![A tiled TileBrush with a Viewport of 0,0,0.25,0.25](./media/25x25viewport.png "25x25viewport")</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 <span data-ttu-id="ae7c5-119">上記の例は、大規模なサンプルの一部です。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="ae7c5-120">サンプル全体については、次を参照してください。 [ImageBrush のサンプル](https://go.microsoft.com/fwlink/?LinkID=160005)します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-120">For the complete sample, see [ImageBrush Sample](https://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
 <span data-ttu-id="ae7c5-121">この例では、<xref:System.Windows.Media.ImageBrush>クラス、<xref:System.Windows.Media.TileBrush.Viewport%2A>と<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>プロパティの他の動作は同じ<xref:System.Windows.Media.TileBrush>オブジェクト、つまりの<xref:System.Windows.Media.DrawingBrush>と<xref:System.Windows.Media.VisualBrush>します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="ae7c5-122">詳細については<xref:System.Windows.Media.ImageBrush>およびその他、 <xref:System.Windows.Media.TileBrush> 、オブジェクトを参照してください[イメージ、描画、およびビジュアル](painting-with-images-drawings-and-visuals.md)します。</span><span class="sxs-lookup"><span data-stu-id="ae7c5-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7c5-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae7c5-123">See also</span></span>
- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="ae7c5-124">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="ae7c5-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="ae7c5-125">TileBrush を使用してさまざまなタイル パターンを作成する</span><span class="sxs-lookup"><span data-stu-id="ae7c5-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
