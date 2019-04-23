---
title: '方法: テクスチャを使用して塗りつぶした直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: c0f90c298f48aeb96893bb09241faddc08d8a49d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186908"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="70ab3-102">方法: テクスチャを使用して塗りつぶした直線を描画する</span><span class="sxs-lookup"><span data-stu-id="70ab3-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="70ab3-103">純色で直線を描画するには、代わりに、テクスチャを使用して線を描画できます。</span><span class="sxs-lookup"><span data-stu-id="70ab3-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="70ab3-104">直線とテクスチャを使用して曲線を描画するには、作成、<xref:System.Drawing.TextureBrush>オブジェクト、および渡す<xref:System.Drawing.TextureBrush>オブジェクトを<xref:System.Drawing.Pen.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="70ab3-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="70ab3-105">テクスチャ ブラシに関連付けられたビットマップは、平面のタイルを (表示) を使用し、ペンのストロークが特定のピクセルのタイルのテクスチャを得るため、ペンでは、直線または曲線を描画、ときにします。</span><span class="sxs-lookup"><span data-stu-id="70ab3-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70ab3-106">例</span><span class="sxs-lookup"><span data-stu-id="70ab3-106">Example</span></span>  
 <span data-ttu-id="70ab3-107">次の例では、作成、<xref:System.Drawing.Bitmap>ファイルからオブジェクト`Texture1.jpg`します。</span><span class="sxs-lookup"><span data-stu-id="70ab3-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="70ab3-108">そのビットマップが構築に使用される、<xref:System.Drawing.TextureBrush>オブジェクト、および<xref:System.Drawing.TextureBrush>オブジェクトが構築するために使用、<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="70ab3-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="70ab3-109">呼び出し<xref:System.Drawing.Graphics.DrawImage%2A>でその左上隅のビットマップを描画します (0, 0)。</span><span class="sxs-lookup"><span data-stu-id="70ab3-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="70ab3-110">呼び出し<xref:System.Drawing.Graphics.DrawEllipse%2A>を使用して、<xref:System.Drawing.Pen>テクスチャ楕円を描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="70ab3-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="70ab3-111">次の図は、ビットマップ、テクスチャの楕円を示します。</span><span class="sxs-lookup"><span data-stu-id="70ab3-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![ビットマップ、およびテクスチャの楕円を示すスクリーン ショット。](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="70ab3-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="70ab3-113">Compiling the Code</span></span>  
 <span data-ttu-id="70ab3-114">Windows フォームを作成し、フォームの処理<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="70ab3-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="70ab3-115">上記のコードを貼り付け、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="70ab3-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="70ab3-116">置換`Texture.jpg`イメージ システム上で有効にします。</span><span class="sxs-lookup"><span data-stu-id="70ab3-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ab3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="70ab3-117">See also</span></span>

- [<span data-ttu-id="70ab3-118">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="70ab3-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="70ab3-119">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="70ab3-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
