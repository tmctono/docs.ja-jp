---
title: '方法: 垂直方向のテキストを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 8398b3f18b764743bac19022b69e7f6fac0f7d57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625993"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="5f988-102">方法: 垂直方向のテキストを作成する</span><span class="sxs-lookup"><span data-stu-id="5f988-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="5f988-103">使用することができます、<xref:System.Drawing.StringFormat>水平方向にではなく縦方向にテキストを描画することを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5f988-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f988-104">例</span><span class="sxs-lookup"><span data-stu-id="5f988-104">Example</span></span>  
 <span data-ttu-id="5f988-105">次の例には、値が割り当てられます。<xref:System.Drawing.StringFormatFlags.DirectionVertical>を、<xref:System.Drawing.StringFormat.FormatFlags%2A>のプロパティを<xref:System.Drawing.StringFormat>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5f988-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="5f988-106">ある<xref:System.Drawing.StringFormat>にオブジェクトが渡される、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="5f988-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="5f988-107">値<xref:System.Drawing.StringFormatFlags.DirectionVertical>のメンバーである、<xref:System.Drawing.StringFormatFlags>列挙体。</span><span class="sxs-lookup"><span data-stu-id="5f988-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="5f988-108">次の図は、垂直方向のテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="5f988-108">The following illustration shows the vertical text:</span></span> 
  
 ![縦書きフォントのテキストを示すグラフィック。](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5f988-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5f988-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="5f988-111">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e` 、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="5f988-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f988-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f988-112">See also</span></span>

- [<span data-ttu-id="5f988-113">方法: GDI を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="5f988-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
