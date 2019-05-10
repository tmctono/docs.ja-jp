---
title: '方法: イメージを並べたパターンによって図形を塗りつぶす'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
ms.openlocfilehash: a906db44a548361df2822efa24d1dd1849cb5a24
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063734"
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="d46a5-102">方法: イメージを並べたパターンによって図形を塗りつぶす</span><span class="sxs-lookup"><span data-stu-id="d46a5-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="d46a5-103">フロアをカバーする他の横にあるタイルを配置すると同様、(タイル) 図形の塗りつぶし、四角形のイメージを互いの横にある配置できます。</span><span class="sxs-lookup"><span data-stu-id="d46a5-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="d46a5-104">形状の内部を並べて表示するには、テクスチャ ブラシを使用します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="d46a5-105">構築する際に、<xref:System.Drawing.TextureBrush>オブジェクトのコンス トラクターに渡す引数の 1 つは、<xref:System.Drawing.Image>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d46a5-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="d46a5-106">テクスチャ ブラシを使用して、図形の内部を描画するときにこのイメージのコピーを繰り返し、図形が入力されます。</span><span class="sxs-lookup"><span data-stu-id="d46a5-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="d46a5-107">ラップ モード プロパティ、<xref:System.Drawing.TextureBrush>方法、画像には、四角形グリッドでこれが繰り返されるオブジェクトを決定します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="d46a5-108">行うことができます、グリッド内のタイルがすべて同じ方向、または反転させる 1 つのグリッド位置から、次に、イメージを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d46a5-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="d46a5-109">反転は、水平、垂直、またはその両方です。</span><span class="sxs-lookup"><span data-stu-id="d46a5-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="d46a5-110">次の例では、さまざまな種類の反転を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="d46a5-111">イメージを並べて表示</span><span class="sxs-lookup"><span data-stu-id="d46a5-111">To tile an image</span></span>  
  
- <span data-ttu-id="d46a5-112">この例では、次の 75 × 75 イメージを使用して、200 × 200 四角形を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 ![赤い家とツリーを表示するタイルの画像。](./media/how-to-tile-a-shape-with-an-image/rectangle-tile-200x200.gif)  
  
- <span data-ttu-id="d46a5-114">次の図は、四角形がイメージに並べて表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="d46a5-115">すべてのタイルが同じ方向; があることに注意してください。反転はありません。</span><span class="sxs-lookup"><span data-stu-id="d46a5-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 ![すべてのタイルの方向を使用してイメージを並べて表示された四角形。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-no-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="d46a5-117">水平方向に並べて表示するときにイメージを反転するには</span><span class="sxs-lookup"><span data-stu-id="d46a5-117">To flip an image horizontally while tiling</span></span>  
  
- <span data-ttu-id="d46a5-118">この例では、同じ 75 × 75 イメージを使用して、200 × 200 四角形を入力します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="d46a5-119">ラップ モードは、イメージを水平方向に反転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d46a5-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="d46a5-120">次の図は、四角形がイメージに並べて表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="d46a5-121">次の特定の行に 1 つのタイルから移動すると、イメージ水平方向に反転に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d46a5-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 ![イメージを並べて表示された四角形を水平方向に反転します。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="d46a5-123">垂直方向に並べて表示するときにイメージを反転するには</span><span class="sxs-lookup"><span data-stu-id="d46a5-123">To flip an image vertically while tiling</span></span>  
  
- <span data-ttu-id="d46a5-124">この例では、同じ 75 × 75 イメージを使用して、200 × 200 四角形を入力します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="d46a5-125">ラップ モードは、イメージを垂直方向に反転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d46a5-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="d46a5-126">並べて表示するとき、イメージを水平および垂直方向に反転するには</span><span class="sxs-lookup"><span data-stu-id="d46a5-126">To flip an image horizontally and vertically while tiling</span></span>  
  
- <span data-ttu-id="d46a5-127">この例では、同じ 75 × 75 イメージを使用して、200 × 200 四角形を並べて表示します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="d46a5-128">ラップ モードは、イメージを水平および垂直方向に反転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d46a5-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="d46a5-129">次の図は、四角形がイメージと、並べて表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d46a5-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="d46a5-130">次の特定の行に 1 つのタイルから移動する、イメージは水平方向に反転させる、イメージが垂直方向に反転させるように、特定の列に 1 つのタイルから移動するに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d46a5-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 ![イメージを並べて表示された四角形は、水平および垂直方向に反転します。](./media/how-to-tile-a-shape-with-an-image/rectangle-tiled-image-horizontal-vertical-flip.gif)  
  
 [!code-csharp[System.Drawing.UsingABrush#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="d46a5-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d46a5-132">See also</span></span>

- [<span data-ttu-id="d46a5-133">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="d46a5-133">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
