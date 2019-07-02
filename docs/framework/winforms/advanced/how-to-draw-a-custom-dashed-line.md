---
title: '方法: カスタム破線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: d2184a8d7d7f24b8f631818608ab4bcdb89857c7
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506039"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="d4031-102">方法: カスタム破線を描画する</span><span class="sxs-lookup"><span data-stu-id="d4031-102">How to: Draw a Custom Dashed Line</span></span>
<span data-ttu-id="d4031-103">GDI + に記載されているいくつかの破線スタイルを提供する、<xref:System.Drawing.Drawing2D.DashStyle>列挙体。</span><span class="sxs-lookup"><span data-stu-id="d4031-103">GDI+ provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="d4031-104">これらの標準の破線スタイルがニーズに合わないしない場合は、カスタムの破線パターンを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d4031-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4031-105">例</span><span class="sxs-lookup"><span data-stu-id="d4031-105">Example</span></span>  
 <span data-ttu-id="d4031-106">カスタム破線を描画するために、配列にダッシュと空白の長さを格納し、配列の値として割り当てます、<xref:System.Drawing.Pen.DashPattern%2A>のプロパティを<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d4031-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="d4031-107">次の例では、配列に基づくカスタム破線を描画する`{5, 2, 15, 4}`します。</span><span class="sxs-lookup"><span data-stu-id="d4031-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="d4031-108">取得する場合は 5 のペンの幅によって、配列の要素を乗算する`{25, 10, 75, 20}`します。</span><span class="sxs-lookup"><span data-stu-id="d4031-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="d4031-109">長さ 25 75 の間で交互に表示されるダッシュと長さが 10 と 20 の間で交互に、スペースです。</span><span class="sxs-lookup"><span data-stu-id="d4031-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="d4031-110">次の図は、結果として得られる、破線を示します。</span><span class="sxs-lookup"><span data-stu-id="d4031-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="d4031-111">最終的なダッシュ ボードがで行を終了するようにに 25 よりも短くする必要があるに注意してください (405, 5)。</span><span class="sxs-lookup"><span data-stu-id="d4031-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="d4031-112">![破線を示す図。](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="d4031-112">![Illustration that shows a dashed line.](./media/how-to-draw-a-custom-dashed-line/dashed-line-illustration.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d4031-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d4031-113">Compiling the Code</span></span>  
 <span data-ttu-id="d4031-114">Windows フォームを作成し、フォームの処理<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="d4031-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="d4031-115">上記のコードを貼り付け、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="d4031-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4031-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4031-116">See also</span></span>

- [<span data-ttu-id="d4031-117">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="d4031-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
