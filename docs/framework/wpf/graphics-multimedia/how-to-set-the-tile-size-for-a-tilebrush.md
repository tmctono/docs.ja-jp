---
title: '方法 : TileBrush のタイル サイズを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186836"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a><span data-ttu-id="60d8a-102">方法 : TileBrush のタイル サイズを設定する</span><span class="sxs-lookup"><span data-stu-id="60d8a-102">How to: Set the Tile Size for a TileBrush</span></span>

<span data-ttu-id="60d8a-103">この例では、 のタイル サイズを設定<xref:System.Windows.Media.TileBrush>する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-103">This example shows how to set the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="60d8a-104">既定では、<xref:System.Windows.Media.TileBrush>は、ペイントする領域全体を完全に塗りつぶす単一のタイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-104">By default, a <xref:System.Windows.Media.TileBrush> produces a single tile that completely fills the area that you are painting.</span></span> <span data-ttu-id="60d8a-105">この動作は、 プロパティと<xref:System.Windows.Media.TileBrush.Viewport%2A>プロパティ<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>を設定することでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="60d8a-105">You can override this behavior by setting the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties.</span></span>

<span data-ttu-id="60d8a-106">プロパティ<xref:System.Windows.Media.TileBrush.Viewport%2A>は、 のタイル サイズ<xref:System.Windows.Media.TileBrush>を指定します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-106">The <xref:System.Windows.Media.TileBrush.Viewport%2A> property specifies the tile size for a <xref:System.Windows.Media.TileBrush>.</span></span> <span data-ttu-id="60d8a-107">デフォルトでは、プロパティの<xref:System.Windows.Media.TileBrush.Viewport%2A>値は、ペイントされる領域のサイズに対する相対的な値です。</span><span class="sxs-lookup"><span data-stu-id="60d8a-107">By default, the value of the <xref:System.Windows.Media.TileBrush.Viewport%2A> property is relative to the size of the area being painted.</span></span> <span data-ttu-id="60d8a-108">プロパティに<xref:System.Windows.Media.TileBrush.Viewport%2A>絶対タイル サイズを指定するには、プロパティを<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>に<xref:System.Windows.Media.BrushMappingMode.Absolute>設定します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-108">To make the <xref:System.Windows.Media.TileBrush.Viewport%2A> property specify an absolute tile size, set the <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> property to <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span>

## <a name="example"></a><span data-ttu-id="60d8a-109">例</span><span class="sxs-lookup"><span data-stu-id="60d8a-109">Example</span></span>

<span data-ttu-id="60d8a-110">次の例では<xref:System.Windows.Media.ImageBrush>、の種類<xref:System.Windows.Media.TileBrush>を使用して、タイルを持つ四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-110">The following example uses an <xref:System.Windows.Media.ImageBrush>, a type of <xref:System.Windows.Media.TileBrush>, to paint a rectangle with tiles.</span></span> <span data-ttu-id="60d8a-111">この例では、各タイルを出力領域 (四角形) の 50 % から 50% に設定します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-111">The example sets each tile to 50 percent by 50 percent of the output area (the rectangle).</span></span> <span data-ttu-id="60d8a-112">その結果、四角形は、イメージの 4 つの投影で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="60d8a-112">As a result, the rectangle is painted with four projections of the image.</span></span>

<span data-ttu-id="60d8a-113">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="60d8a-113">The following illustration shows the output that the example produces:</span></span>

![イメージ ブラシでタイリングを示す 4 つのサクランボを持つ四角形。](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

<span data-ttu-id="60d8a-115">次<xref:System.Windows.Media.ImageBrush>の例では、 を作成<xref:System.Windows.Media.TileBrush.Viewport%2A>し`0,0,25,25`、その<xref:System.Windows.Media.TileBrush.ViewportUnits%2A><xref:System.Windows.Media.BrushMappingMode.Absolute>を に設定し、それを使用して別の四角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-115">The next example creates an <xref:System.Windows.Media.ImageBrush>, sets its <xref:System.Windows.Media.TileBrush.Viewport%2A> to `0,0,25,25` and its <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> to <xref:System.Windows.Media.BrushMappingMode.Absolute>, and uses it to paint another rectangle.</span></span> <span data-ttu-id="60d8a-116">その結果、ブラシは、幅が 25 ピクセル、高さが 25 ピクセルのタイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-116">As a result, the brush produces tiles that have a width of 25  pixels and a height of 25 pixels .</span></span>

<span data-ttu-id="60d8a-117">次の図は、この例で生成される出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="60d8a-117">The following illustration shows the output that the example produces:</span></span>

![ビューポート付きタイル ブラシを示す 48 個のサクランボを持つ四角形。](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

<span data-ttu-id="60d8a-119">上記の例は、大規模なサンプルの一部です。</span><span class="sxs-lookup"><span data-stu-id="60d8a-119">The preceding examples are part of a larger sample.</span></span> <span data-ttu-id="60d8a-120">完全なサンプルについては、「[イメージブラシのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60d8a-120">For the complete sample, see [ImageBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).</span></span>

<span data-ttu-id="60d8a-121">この例ではクラスを<xref:System.Windows.Media.ImageBrush>使用していますが、 <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>プロパティと プロパティは他<xref:System.Windows.Media.TileBrush>のオブジェクト (for<xref:System.Windows.Media.DrawingBrush>および<xref:System.Windows.Media.VisualBrush>for) とで同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="60d8a-121">Although this example uses the <xref:System.Windows.Media.ImageBrush> class, the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> properties behave identically for the other <xref:System.Windows.Media.TileBrush> objects, that is, for <xref:System.Windows.Media.DrawingBrush> and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="60d8a-122">その他<xref:System.Windows.Media.TileBrush>のオブジェクト<xref:System.Windows.Media.ImageBrush>の詳細については、「[イメージ、描画、およびビジュアルを使用したペイント](painting-with-images-drawings-and-visuals.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60d8a-122">For more information about <xref:System.Windows.Media.ImageBrush> and the other <xref:System.Windows.Media.TileBrush> objects, see [Painting with Images, Drawings, and Visuals](painting-with-images-drawings-and-visuals.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60d8a-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="60d8a-123">See also</span></span>

- <xref:System.Windows.Media.TileBrush>
- [<span data-ttu-id="60d8a-124">イメージ、描画、およびビジュアルによる塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="60d8a-124">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="60d8a-125">TileBrush を使用してさまざまなタイル パターンを作成する</span><span class="sxs-lookup"><span data-stu-id="60d8a-125">Create Different Tile Patterns with a TileBrush</span></span>](how-to-create-different-tile-patterns-with-a-tilebrush.md)
