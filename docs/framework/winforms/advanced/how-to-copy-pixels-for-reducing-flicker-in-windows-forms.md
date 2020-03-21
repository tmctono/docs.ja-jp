---
title: '方法: フリッカを減らすためにピクセルをコピーする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitblt
- graphics [Windows Forms], copying
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing flicker
- pixels [Windows Forms], copying
- flicker
- bit-block transfer
ms.assetid: 33b76910-13a3-4521-be98-5c097341ae3b
ms.openlocfilehash: a25295532d7123d92bcacc6828d3e8cfcc839d6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182583"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="9ecfb-102">方法 :ピクセルをコピーして Windows フォームのちらつきを低減する</span><span class="sxs-lookup"><span data-stu-id="9ecfb-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="9ecfb-103">単純なグラフィックをアニメーション化すると、ユーザーがちらつきやその他の望ましくない視覚効果を見つめてしまうことがあります。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="9ecfb-104">この問題を制限する 1 つの方法は、グラフィック上で "bitblt" プロセスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="9ecfb-105">Bitblt は、ピクセルの元の四角形からピクセルのターゲット矩形へのカラーデータの「ビットブロック転送」です。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="9ecfb-106">Windows フォームでは、クラスのメソッドを<xref:System.Drawing.Graphics.CopyFromScreen%2A>使用して bitblt が実行されます。 <xref:System.Drawing.Graphics></span><span class="sxs-lookup"><span data-stu-id="9ecfb-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="9ecfb-107">メソッドのパラメータでは、ソースとコピー先 (ポイント)、コピーする領域のサイズ、および新しい図形の描画に使用するグラフィックス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="9ecfb-108">次の例では、フォーム上のイベント ハンドラーで図形が<xref:System.Windows.Forms.Control.Paint>描画されます。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="9ecfb-109">次に、<xref:System.Drawing.Graphics.CopyFromScreen%2A>このメソッドを使用して図形を複製します。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ecfb-110">フォームの<xref:System.Windows.Forms.Control.DoubleBuffered%2A>プロパティを設定すると`true`、イベント内のグラフィックス ベースの<xref:System.Windows.Forms.Control.Paint>コードがダブル バッファリングされます。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="9ecfb-111">以下のコードを使用する場合、この方法でパフォーマンスが向上するわけではありませんが、より複雑なグラフィックス操作コードを使用する場合は、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ecfb-112">例</span><span class="sxs-lookup"><span data-stu-id="9ecfb-112">Example</span></span>  
  
```vb  
Private Sub Form1_Paint(ByVal sender As Object, ByVal e As _  
    System.Windows.Forms.PaintEventArgs) Handles MyBase.Paint  
    ' Draw a circle with a bar on top.  
        e.Graphics.FillEllipse(Brushes.DarkBlue, New Rectangle _  
             (10, 10, 60, 60))  
        e.Graphics.FillRectangle(Brushes.Khaki, New Rectangle _  
             (20, 30, 60, 10))  
    ' Copy the graphic to a new location.  
        e.Graphics.CopyFromScreen(New Point(10, 10), New Point _  
             (100, 100), New Size(70, 70))  
End Sub  
```  
  
```csharp  
private void Form1_Paint(System.Object sender,  
    System.Windows.Forms.PaintEventArgs e)  
        {  
        e.Graphics.FillEllipse(Brushes.DarkBlue, new  
            Rectangle(10,10,60,60));  
        e.Graphics.FillRectangle(Brushes.Khaki, new  
            Rectangle(20,30,60,10));  
        e.Graphics.CopyFromScreen(new Point(10, 10), new Point(100, 100),
            new Size(70, 70));  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ecfb-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="9ecfb-113">Compiling the Code</span></span>  
 <span data-ttu-id="9ecfb-114">上記のコードはフォームの<xref:System.Windows.Forms.Control.Paint>イベント ハンドラで実行されるため、フォームが再描画されたときにグラフィックスが保持されます。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="9ecfb-115">そのため、フォームのサイズが変更されたり、別のフォーム<xref:System.Windows.Forms.Form.Load>によって隠されたりしても描画されたコンテンツは再描画されないため、イベント ハンドラでグラフィックス関連のメソッドを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="9ecfb-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecfb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ecfb-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9ecfb-117">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="9ecfb-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="9ecfb-118">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="9ecfb-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
