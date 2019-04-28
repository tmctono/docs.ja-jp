---
title: '方法: ピクセルをコピーして Windows フォームのちらつきを低減する'
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
ms.openlocfilehash: e3d1c2b681e98dc7c45467683924dd4022eb377e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937749"
---
# <a name="how-to-copy-pixels-for-reducing-flicker-in-windows-forms"></a><span data-ttu-id="2ed73-102">方法: ピクセルをコピーして Windows フォームのちらつきを低減する</span><span class="sxs-lookup"><span data-stu-id="2ed73-102">How to: Copy Pixels for Reducing Flicker in Windows Forms</span></span>
<span data-ttu-id="2ed73-103">単純なグラフィックをアニメーション化するとユーザーことができます、ちらつき、またはその他の望ましくない視覚効果発生場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ed73-103">When you animate a simple graphic, users can sometimes encounter flicker or other undesirable visual effects.</span></span> <span data-ttu-id="2ed73-104">この問題を制限する方法の 1 つでは、グラフィック"bitblt"プロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2ed73-104">One way to limit this problem is to use a "bitblt" process on the graphic.</span></span> <span data-ttu-id="2ed73-105">Bitblt 関数は、「ビット ブロック転送」カラー データのピクセルの四角形を配信元からのピクセルの四角形に。</span><span class="sxs-lookup"><span data-stu-id="2ed73-105">Bitblt is the "bit-block transfer" of the color data from an origin rectangle of pixels to a destination rectangle of pixels.</span></span>  
  
 <span data-ttu-id="2ed73-106">使用して Windows フォーム、bitblt 関数が実行は、<xref:System.Drawing.Graphics.CopyFromScreen%2A>のメソッド、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="2ed73-106">With Windows Forms, bitblt is accomplished using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="2ed73-107">メソッドのパラメーターでは、ソースと宛先 (ポイント単位) として、コピーされる領域のサイズに新しい図形を描画するために使用するグラフィックス オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2ed73-107">In the parameters of the method, you specify the source and destination (as points), the size of the area to be copied, and the graphics object used to draw the new shape.</span></span>  
  
 <span data-ttu-id="2ed73-108">次の例でのフォームの形状を描画、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="2ed73-108">In the example below, a shape is drawn on the form in its <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="2ed73-109">次に、<xref:System.Drawing.Graphics.CopyFromScreen%2A>メソッドを使用して、図形が重複しています。</span><span class="sxs-lookup"><span data-stu-id="2ed73-109">Then, the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method is used to duplicate the shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ed73-110">フォームの設定<xref:System.Windows.Forms.Control.DoubleBuffered%2A>プロパティを`true`でグラフィックス ベースのコードになります、<xref:System.Windows.Forms.Control.Paint>ダブル バッファーされたイベントがあります。</span><span class="sxs-lookup"><span data-stu-id="2ed73-110">Setting the form's <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true` will make graphics-based code in the <xref:System.Windows.Forms.Control.Paint> event be double-buffered.</span></span> <span data-ttu-id="2ed73-111">認識できるようなパフォーマンス上のメリットは、次のコードを使用するときにこれがないより複雑なグラフィックス操作のコードを使用する場合に留意すべきことです。</span><span class="sxs-lookup"><span data-stu-id="2ed73-111">While this will not have any discernible performance gains when using the code below, it is something to keep in mind when working with more complex graphics-manipulation code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ed73-112">例</span><span class="sxs-lookup"><span data-stu-id="2ed73-112">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ed73-113">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2ed73-113">Compiling the Code</span></span>  
 <span data-ttu-id="2ed73-114">上記のコードは、フォームの実行は<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー、フォームが再描画されるときに、グラフィックスが持続するようにします。</span><span class="sxs-lookup"><span data-stu-id="2ed73-114">The code above is run in the form's <xref:System.Windows.Forms.Control.Paint> event handler so that the graphics persist when the form is redrawn.</span></span> <span data-ttu-id="2ed73-115">そのため、呼び出さないでくださいグラフィックに関連するメソッド、<xref:System.Windows.Forms.Form.Load>イベント ハンドラーでは、フォームのサイズを変更または別の形式によって隠されている場合、描画のコンテンツは描画しないためです。</span><span class="sxs-lookup"><span data-stu-id="2ed73-115">As such, do not call graphics-related methods in the <xref:System.Windows.Forms.Form.Load> event handler, because the drawn content will not be redrawn if the form is resized or obscured by another form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed73-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ed73-116">See also</span></span>

- <xref:System.Drawing.CopyPixelOperation>
- <xref:System.Drawing.Graphics.FillRectangle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.OnPaint%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2ed73-117">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="2ed73-117">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2ed73-118">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="2ed73-118">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
