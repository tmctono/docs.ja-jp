---
title: '方法: テクスチャを使用して塗りつぶした直線を描画します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
ms.openlocfilehash: 82fc553e2a2fc9d1e8161c0f0dfef9190668e48c
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653757"
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="ac63b-102">方法: テクスチャを使用して塗りつぶした直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="ac63b-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="ac63b-103">純色で直線を描画するには、代わりに、テクスチャを使用して線を描画できます。</span><span class="sxs-lookup"><span data-stu-id="ac63b-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="ac63b-104">直線とテクスチャを使用して曲線を描画するには、作成、<xref:System.Drawing.TextureBrush>オブジェクト、および渡す<xref:System.Drawing.TextureBrush>オブジェクトを<xref:System.Drawing.Pen.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="ac63b-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="ac63b-105">テクスチャ ブラシに関連付けられたビットマップは、平面のタイルを (表示) を使用し、ペンのストロークが特定のピクセルのタイルのテクスチャを得るため、ペンでは、直線または曲線を描画、ときにします。</span><span class="sxs-lookup"><span data-stu-id="ac63b-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac63b-106">例</span><span class="sxs-lookup"><span data-stu-id="ac63b-106">Example</span></span>  
 <span data-ttu-id="ac63b-107">次の例では、作成、<xref:System.Drawing.Bitmap>ファイルからオブジェクト`Texture1.jpg`します。</span><span class="sxs-lookup"><span data-stu-id="ac63b-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="ac63b-108">そのビットマップが構築に使用される、<xref:System.Drawing.TextureBrush>オブジェクト、および<xref:System.Drawing.TextureBrush>オブジェクトが構築するために使用、<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ac63b-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="ac63b-109">呼び出し<xref:System.Drawing.Graphics.DrawImage%2A>でその左上隅のビットマップを描画します (0, 0)。</span><span class="sxs-lookup"><span data-stu-id="ac63b-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="ac63b-110">呼び出し<xref:System.Drawing.Graphics.DrawEllipse%2A>を使用して、<xref:System.Drawing.Pen>テクスチャ楕円を描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ac63b-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="ac63b-111">次の図は、ビットマップ、テクスチャの楕円を示します。</span><span class="sxs-lookup"><span data-stu-id="ac63b-111">The following illustration shows the bitmap and the textured ellipse:</span></span>  
  
 ![ビットマップ、およびテクスチャの楕円を示すスクリーン ショット。](./media/how-to-draw-a-line-filled-with-a-texture/bitmap-textured-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingAPen#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ac63b-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ac63b-113">Compiling the Code</span></span>  
 <span data-ttu-id="ac63b-114">Windows フォームを作成し、フォームの処理<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="ac63b-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="ac63b-115">上記のコードを貼り付け、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="ac63b-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ac63b-116">置換`Texture.jpg`イメージ システム上で有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac63b-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac63b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac63b-117">See also</span></span>
- [<span data-ttu-id="ac63b-118">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="ac63b-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="ac63b-119">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="ac63b-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
