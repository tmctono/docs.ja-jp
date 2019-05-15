---
title: '方法: ペンを使用して四角形を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: cd5d965f8b92d15cdeb3049330d9b3cc0de893b2
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590229"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="9a1de-102">方法: ペンを使用して四角形を描画する</span><span class="sxs-lookup"><span data-stu-id="9a1de-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="9a1de-103">四角形を描画するためにする必要があります、<xref:System.Drawing.Graphics>オブジェクトと<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9a1de-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="9a1de-104"><xref:System.Drawing.Graphics>オブジェクトを提供、<xref:System.Drawing.Graphics.DrawRectangle%2A>メソッド、および<xref:System.Drawing.Pen>オブジェクトは、線、色や幅などの機能を格納します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a1de-105">例</span><span class="sxs-lookup"><span data-stu-id="9a1de-105">Example</span></span>  
 <span data-ttu-id="9a1de-106">次の例で、左上隅を四角形を描画します (10, 10)。</span><span class="sxs-lookup"><span data-stu-id="9a1de-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="9a1de-107">四角形は、100 の幅と高さを 50 があります。</span><span class="sxs-lookup"><span data-stu-id="9a1de-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="9a1de-108">渡される 2 番目の引数、<xref:System.Drawing.Pen.%23ctor%2A>コンス トラクターの場合、ペンの幅が 5 ピクセルであることを示します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="9a1de-109">四角形が描画されるときに、四角形の境界のペンが中央に配置します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="9a1de-110">四角形の辺が 5 ピクセルの描画には、ペンの幅が 5 であるため、その 1 ピクセルの描画など、さまざまには、境界の 2 ピクセルの描画し、2 つのピクセルの外側に描画します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="9a1de-111">ペンの配置の詳細については、次を参照してください。[方法。ペンの幅と配置を設定](how-to-set-pen-width-and-alignment.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="9a1de-112">次の図は、結果として得られる四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="9a1de-113">位置四角形が描画される場合は、ペンの幅が 1 つのピクセルになっていた点線表示します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="9a1de-114">四角形の左上隅を拡大表示では、シック黒い線はそれらの点線中心を示します。</span><span class="sxs-lookup"><span data-stu-id="9a1de-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![黒と点線で描画された四角形を示すスクリーン ショット。](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a1de-116">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9a1de-116">Compiling the Code</span></span>  
 <span data-ttu-id="9a1de-117">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="9a1de-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1de-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a1de-118">See also</span></span>

- [<span data-ttu-id="9a1de-119">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="9a1de-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
