---
title: '方法: ライン キャップを持つ行を描画します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: 05c678b25563eb7a4e2e5ce0e49138b5445b4764
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707600"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="3d436-102">方法: ライン キャップを持つ行を描画します。</span><span class="sxs-lookup"><span data-stu-id="3d436-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="3d436-103">ライン キャップと呼ばれるいくつかの図形のいずれかでは、先頭または末尾の行を描画できます。</span><span class="sxs-lookup"><span data-stu-id="3d436-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3d436-104">round、正方形、ひし形、および矢印などのいくつかのライン キャップをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3d436-104">supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d436-105">例</span><span class="sxs-lookup"><span data-stu-id="3d436-105">Example</span></span>  
 <span data-ttu-id="3d436-106">ライン キャップ (start cap) の行、行 (end cap) の末尾または破線 (ダッシュ cap) のダッシュの開始を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="3d436-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="3d436-107">次の例では、線を一端にある矢印、もう一方の end ラウンド線端を描画します。</span><span class="sxs-lookup"><span data-stu-id="3d436-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="3d436-108">図は、その結果、行を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d436-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="3d436-109">![ペン](./media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="3d436-109">![Pens](./media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d436-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3d436-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="3d436-111">Windows フォームを作成し、フォームの処理<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="3d436-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="3d436-112">例のコードを<xref:System.Windows.Forms.Control.Paint>イベント ハンドラーを渡す`e`として<xref:System.Windows.Forms.PaintEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="3d436-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d436-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d436-113">See also</span></span>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="3d436-114">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="3d436-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="3d436-115">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="3d436-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
