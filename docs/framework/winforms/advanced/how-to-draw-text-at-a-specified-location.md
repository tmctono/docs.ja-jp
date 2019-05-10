---
title: '方法: テキストを指定の位置に描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 0c36b00e4f6f71f0ecf8042853bb8e99e57854da
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2019
ms.locfileid: "64912425"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="22c3c-102">方法: テキストを指定の位置に描画する</span><span class="sxs-lookup"><span data-stu-id="22c3c-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="22c3c-103">カスタム描画を実行するときに、指定された位置から始まる 1 つの水平方向にテキストを描画できます。</span><span class="sxs-lookup"><span data-stu-id="22c3c-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="22c3c-104">使用して、この方法でテキストを描画することができます、<xref:System.Drawing.Graphics.DrawString%2A>のメソッドをオーバー ロード、<xref:System.Drawing.Graphics>を受け取るクラス、<xref:System.Drawing.Point>または<xref:System.Drawing.PointF>パラメーター。</span><span class="sxs-lookup"><span data-stu-id="22c3c-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="22c3c-105"><xref:System.Drawing.Graphics.DrawString%2A>メソッドも必要になります、<xref:System.Drawing.Brush>と <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="22c3c-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="22c3c-106">使用することも、<xref:System.Windows.Forms.TextRenderer.DrawText%2A>のメソッドをオーバー ロード、<xref:System.Windows.Forms.TextRenderer>を受け取る、<xref:System.Drawing.Point>します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="22c3c-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> 必要です、<xref:System.Drawing.Color>と<xref:System.Drawing.Font>します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="22c3c-108">次の図は、使用すると、特定の時点で描画されるテキストの出力、<xref:System.Drawing.Graphics.DrawString%2A>オーバー ロードされたメソッド。</span><span class="sxs-lookup"><span data-stu-id="22c3c-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![指定した時点でのテキストの出力を示すスクリーン ショット。](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="22c3c-110">GDI + でのテキストの線を描画するには</span><span class="sxs-lookup"><span data-stu-id="22c3c-110">To draw a line of text with GDI+</span></span>  
  
1. <span data-ttu-id="22c3c-111">使用して、 <xref:System.Drawing.Graphics.DrawString%2A> 、テキストを渡すメソッド<xref:System.Drawing.Point>または<xref:System.Drawing.PointF>、 <xref:System.Drawing.Font>、および<xref:System.Drawing.Brush>します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="22c3c-112">GDI を使用してテキストの線を描画するには</span><span class="sxs-lookup"><span data-stu-id="22c3c-112">To draw a line of text with GDI</span></span>  
  
1. <span data-ttu-id="22c3c-113">使用して、 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 、テキストを渡すメソッド<xref:System.Drawing.Point>、 <xref:System.Drawing.Font>、および<xref:System.Drawing.Color>します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22c3c-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="22c3c-114">Compiling the Code</span></span>  
 <span data-ttu-id="22c3c-115">前の例が必要です。</span><span class="sxs-lookup"><span data-stu-id="22c3c-115">The previous examples require:</span></span>  
  
- <span data-ttu-id="22c3c-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`でのパラメーターである<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c3c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="22c3c-117">See also</span></span>

- [<span data-ttu-id="22c3c-118">方法: GDI を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="22c3c-119">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="22c3c-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="22c3c-120">方法: フォント ファミリとフォントを作成します。</span><span class="sxs-lookup"><span data-stu-id="22c3c-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="22c3c-121">方法: 四角形内にテキストを折り返して描画</span><span class="sxs-lookup"><span data-stu-id="22c3c-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
