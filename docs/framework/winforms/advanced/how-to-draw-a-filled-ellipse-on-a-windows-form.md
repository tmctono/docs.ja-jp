---
title: '方法: Windows フォームに塗りつぶした楕円を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 2e7be3f2c4c710bb24568dd2e70f6f5cc4706c63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171009"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="e4dc1-102">方法: Windows フォームに塗りつぶした楕円を描画する</span><span class="sxs-lookup"><span data-stu-id="e4dc1-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="e4dc1-103">この例では、フォームに塗りつぶした楕円を描画します。</span><span class="sxs-lookup"><span data-stu-id="e4dc1-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4dc1-104">例</span><span class="sxs-lookup"><span data-stu-id="e4dc1-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e4dc1-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e4dc1-105">Compiling the Code</span></span>  
 <span data-ttu-id="e4dc1-106">このメソッドを呼び出すことはできません、<xref:System.Windows.Forms.Form.Load>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="e4dc1-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="e4dc1-107">フォームのサイズを変更または別の形式によって隠されている場合、描画のコンテンツを再描画されませんされます。</span><span class="sxs-lookup"><span data-stu-id="e4dc1-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="e4dc1-108">コンテンツを自動的に再描画するために、オーバーライドする必要があります、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="e4dc1-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e4dc1-109">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="e4dc1-109">Robust Programming</span></span>  
 <span data-ttu-id="e4dc1-110">常に呼び出す必要があります<xref:System.IDisposable.Dispose%2A>などのシステム リソースを消費するすべてのオブジェクトに対する<xref:System.Drawing.Brush>と<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="e4dc1-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4dc1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4dc1-111">See also</span></span>

- [<span data-ttu-id="e4dc1-112">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="e4dc1-112">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e4dc1-113">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="e4dc1-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e4dc1-114">アルファ ブレンドの直線と塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="e4dc1-114">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="e4dc1-115">ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="e4dc1-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
