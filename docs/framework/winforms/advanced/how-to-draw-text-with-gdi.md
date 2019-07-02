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
ms.openlocfilehash: 3d5b79e82185c044314ff8807b86835ef6a87c45
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505907"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="128fb-102">方法: GDI を使用してテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="128fb-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="128fb-103"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッドで、<xref:System.Windows.Forms.TextRenderer>クラス、フォームまたはコントロールにテキストを描画するための GDI 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="128fb-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access GDI functionality for drawing text on a form or control.</span></span> <span data-ttu-id="128fb-104">通常、GDI のテキストのレンダリングは、パフォーマンスが向上しより GDI + を測定するより正確なテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="128fb-104">GDI text rendering typically offers better performance and more accurate text measuring than GDI+.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="128fb-105"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>のメソッド、<xref:System.Windows.Forms.TextRenderer>クラスが印刷はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="128fb-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="128fb-106">印刷するときは常に使用して、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="128fb-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="128fb-107">例</span><span class="sxs-lookup"><span data-stu-id="128fb-107">Example</span></span>  
 <span data-ttu-id="128fb-108">次のコード例に示しますを使用して、四角形内の複数の行のテキストを描画する方法、<xref:System.Windows.Forms.TextRenderer.DrawText%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="128fb-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="128fb-109">テキストを表示するために、<xref:System.Windows.Forms.TextRenderer>必要がある、クラス、<xref:System.Drawing.IDeviceContext>などを<xref:System.Drawing.Graphics>と<xref:System.Drawing.Font>テキストをおよび描画必要がある色を描画する場所。</span><span class="sxs-lookup"><span data-stu-id="128fb-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="128fb-110">必要に応じて、テキストを使用して書式設定を指定できます、<xref:System.Windows.Forms.TextFormatFlags>列挙体。</span><span class="sxs-lookup"><span data-stu-id="128fb-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="128fb-111">取得の詳細については、<xref:System.Drawing.Graphics>を参照してください[方法。描画の Graphics オブジェクトを作成](how-to-create-graphics-objects-for-drawing.md)です。</span><span class="sxs-lookup"><span data-stu-id="128fb-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="128fb-112">構築の詳細については、<xref:System.Drawing.Font>を参照してください[方法。フォント ファミリとフォント作成](how-to-construct-font-families-and-fonts.md)です。</span><span class="sxs-lookup"><span data-stu-id="128fb-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="128fb-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="128fb-113">Compiling the Code</span></span>  
 <span data-ttu-id="128fb-114">上記のコード例が、Windows フォームで使用するために設計されており、必要があります、 <xref:System.Windows.Forms.PaintEventArgs> `e`はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="128fb-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="128fb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="128fb-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="128fb-116">フォントとテキストの使用</span><span class="sxs-lookup"><span data-stu-id="128fb-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
