---
title: '方法: Windows フォームに直線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: aab04b9236175cedd154b817db5a6f6450503105
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004160"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="61e7f-102">方法: Windows フォームに直線を描画する</span><span class="sxs-lookup"><span data-stu-id="61e7f-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="61e7f-103">この例では、フォームで線を描画します。</span><span class="sxs-lookup"><span data-stu-id="61e7f-103">This example draws a line on a form.</span></span> <span data-ttu-id="61e7f-104">通常は、フォームに描画するときに、フォームを処理<xref:System.Windows.Forms.Control.Paint>イベント、描画を使用して実行し、<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>のプロパティ、<xref:System.Windows.Forms.PaintEventArgs>この例で示すように、</span><span class="sxs-lookup"><span data-stu-id="61e7f-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="61e7f-105">例</span><span class="sxs-lookup"><span data-stu-id="61e7f-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61e7f-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="61e7f-106">Compiling the Code</span></span>  
 <span data-ttu-id="61e7f-107">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。</span><span class="sxs-lookup"><span data-stu-id="61e7f-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="61e7f-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="61e7f-108">Robust Programming</span></span>  
 <span data-ttu-id="61e7f-109">常に呼び出す必要があります<xref:System.IDisposable.Dispose%2A>などのシステム リソースを消費するすべてのオブジェクトに対する<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61e7f-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e7f-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="61e7f-110">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="61e7f-111">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="61e7f-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="61e7f-112">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="61e7f-112">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="61e7f-113">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="61e7f-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
