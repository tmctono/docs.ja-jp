---
title: '方法: ピクセルをコピーしてちらつきを軽減する'
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
ms.openlocfilehash: 299041e7038d5bd5b9824d668b3f47d842030ac7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746487"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="ab923-102">方法 :ピクセルをコピーして Windows フォームのちらつきを低減する</span><span class="sxs-lookup"><span data-stu-id="ab923-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="ab923-103">単純なグラフィックをアニメーション化すると、ユーザーがちらつきやその他の望ましくない視覚効果を発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="ab923-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="ab923-104">この問題を制限する1つの方法は、グラフィックで "bitblt" プロセスを使用することです。</span><span class="sxs-lookup"><span data-stu-id="ab923-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="ab923-105">Bitblt は、原点の四角形からピクセルの移動先の四角形までのカラーデータの "ビットブロック転送" です。</span><span class="sxs-lookup"><span data-stu-id="ab923-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="ab923-106">Windows フォームでは、bitblt は <xref:System.Drawing.Graphics> クラスの <xref:System.Drawing.Graphics.CopyFromScreen%2A> メソッドを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="ab923-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="ab923-107">メソッドのパラメーターでは、ソースとターゲット (ポイント)、コピーする領域のサイズ、および新しい図形の描画に使用するグラフィックスオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab923-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="ab923-108">次の例では、図形が <xref:System.Windows.Forms.Control.Paint> イベントハンドラーのフォームに描画されます。</span><span class="sxs-lookup"><span data-stu-id="ab923-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ab923-109">次に、<xref:System.Drawing.Graphics.CopyFromScreen%2A> メソッドを使用して図形を複製します。</span><span class="sxs-lookup"><span data-stu-id="ab923-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab923-110">フォームの <xref:System.Windows.Forms.Control.DoubleBuffered%2A> プロパティを `true` に設定すると、<xref:System.Windows.Forms.Control.Paint> イベント内のグラフィックスベースのコードがダブルバッファリングされます。</span><span class="sxs-lookup"><span data-stu-id="ab923-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="ab923-111">以下のコードを使用すると、これによって認識できないパフォーマンスが向上することはありませんが、より複雑なグラフィックス操作コードを使用する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab923-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab923-112">例</span><span class="sxs-lookup"><span data-stu-id="ab923-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab923-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ab923-113">Compiling the Code</span></span>  
 <span data-ttu-id="ab923-114">上記のコードはフォームの <xref:System.Windows.Forms.Control.Paint> イベントハンドラーで実行されるので、フォームが再描画されるときにグラフィックスが保持されます。</span><span class="sxs-lookup"><span data-stu-id="ab923-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="ab923-115">そのため、<xref:System.Windows.Forms.Form.Load> イベントハンドラーでは、フォームのサイズが変更されたり、別の形式によって隠されたりした場合に描画コンテンツが再描画されないため、グラフィックス関連のメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="ab923-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab923-116">参照</span><span class="sxs-lookup"><span data-stu-id="ab923-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ab923-117">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="ab923-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="ab923-118">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="ab923-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
