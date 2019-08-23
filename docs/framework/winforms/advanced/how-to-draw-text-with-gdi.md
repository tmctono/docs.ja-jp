---
title: '方法: GDI を使用してテキストを描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956541"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="24e48-102">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="24e48-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="24e48-103"><xref:System.Windows.Forms.TextRenderer>クラスの<xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッドを使用すると、フォームまたはコントロールにテキストを描画するための GDI 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="24e48-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="24e48-104">GDI テキストレンダリングでは、通常、GDI + よりもパフォーマンスが向上し、より正確なテキスト測定が提供されます。</span><span class="sxs-lookup"><span data-stu-id="24e48-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24e48-105">クラスのメソッドは印刷がサポートされていません。 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <xref:System.Windows.Forms.TextRenderer></span><span class="sxs-lookup"><span data-stu-id="24e48-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="24e48-106">印刷時には、常<xref:System.Drawing.Graphics.DrawString%2A>に<xref:System.Drawing.Graphics>クラスのメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="24e48-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24e48-107">例</span><span class="sxs-lookup"><span data-stu-id="24e48-107">Example</span></span>  
 <span data-ttu-id="24e48-108">次のコード例は、 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッドを使用して、四角形内の複数の行にテキストを描画する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="24e48-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="24e48-109"><xref:System.Windows.Forms.TextRenderer>クラスを使用してテキストを表示するに<xref:System.Drawing.IDeviceContext>は、 <xref:System.Drawing.Graphics>と<xref:System.Drawing.Font>などの、テキストを描画する場所、および描画する色を必要とします。</span><span class="sxs-lookup"><span data-stu-id="24e48-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="24e48-110">必要に応じて、 <xref:System.Windows.Forms.TextFormatFlags>列挙を使用してテキストの書式を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="24e48-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="24e48-111">の<xref:System.Drawing.Graphics>取得の詳細については[、「方法:描画](how-to-create-graphics-objects-for-drawing.md)用のグラフィックスオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="24e48-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="24e48-112">の<xref:System.Drawing.Font>構築の詳細については[、「」を参照してください。フォントファミリとフォントを](how-to-construct-font-families-and-fonts.md)構築します。</span><span class="sxs-lookup"><span data-stu-id="24e48-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24e48-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="24e48-113">Compiling the Code</span></span>  
 <span data-ttu-id="24e48-114">上記のコード例は、Windows フォームで使用するように設計され<xref:System.Windows.Forms.PaintEventArgs>ており、の<xref:System.Windows.Forms.PaintEventHandler>パラメーターである`e`を必要とします。</span><span class="sxs-lookup"><span data-stu-id="24e48-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e48-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="24e48-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="24e48-116">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="24e48-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
