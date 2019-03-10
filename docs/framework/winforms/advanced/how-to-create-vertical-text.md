---
title: '方法: 垂直方向のテキストを作成します。'
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
ms.openlocfilehash: b2c26ab220fc9b796c8f8ababdef144847d52698
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710408"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="56eda-102">方法: 垂直方向のテキストを作成します。</span><span class="sxs-lookup"><span data-stu-id="56eda-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="56eda-103">使用することができます、<xref:System.Drawing.StringFormat>水平方向にではなく縦方向にテキストを描画することを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56eda-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56eda-104">例</span><span class="sxs-lookup"><span data-stu-id="56eda-104">Example</span></span>  
 <span data-ttu-id="56eda-105">次の例には、値が割り当てられます。<xref:System.Drawing.StringFormatFlags.DirectionVertical>を、<xref:System.Drawing.StringFormat.FormatFlags%2A>のプロパティを<xref:System.Drawing.StringFormat>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="56eda-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="56eda-106">ある<xref:System.Drawing.StringFormat>にオブジェクトが渡される、<xref:System.Drawing.Graphics.DrawString%2A>のメソッド、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="56eda-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="56eda-107">値<xref:System.Drawing.StringFormatFlags.DirectionVertical>のメンバーである、<xref:System.Drawing.StringFormatFlags>列挙体。</span><span class="sxs-lookup"><span data-stu-id="56eda-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="56eda-108">次の図は、垂直方向のテキストを示します。</span><span class="sxs-lookup"><span data-stu-id="56eda-108">The following illustration shows the vertical text.</span></span>  
  
 <span data-ttu-id="56eda-109">![フォント テキスト](./media/csfontstext5.png "csfontstext5")</span><span class="sxs-lookup"><span data-stu-id="56eda-109">![Fonts Text](./media/csfontstext5.png "csfontstext5")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56eda-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="56eda-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="56eda-111">前の例は、Windows フォームで使用するために設計されています。 また必要が<xref:System.Windows.Forms.PaintEventArgs> `e` 、はのパラメーター<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="56eda-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56eda-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="56eda-112">See also</span></span>
- [<span data-ttu-id="56eda-113">方法: GDI を使用してテキストを描画します。</span><span class="sxs-lookup"><span data-stu-id="56eda-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
