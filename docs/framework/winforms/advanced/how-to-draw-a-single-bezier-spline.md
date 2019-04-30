---
title: '方法: 1 つの B を描画&#233;ベジエ スプライン'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines [Windows Forms], drawing
- drawing [Windows Forms], Bezier splines
ms.assetid: f4f3fe30-f0a6-4743-ac91-11310cebea9f
ms.openlocfilehash: ebb53e7df979a553ed4a44deba34345c9ecac772
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004238"
---
# <a name="how-to-draw-a-single-b233zier-spline"></a><span data-ttu-id="14af8-102">方法: 1 つの B を描画&#233;ベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="14af8-102">How to: Draw a Single B&#233;zier Spline</span></span>
<span data-ttu-id="14af8-103">ベジエ スプラインは、4 つの点によって定義されます。 開始点、2 つの制御点、およびエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="14af8-103">A Bézier spline is defined by four points: a start point, two control points, and an endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14af8-104">例</span><span class="sxs-lookup"><span data-stu-id="14af8-104">Example</span></span>  
 <span data-ttu-id="14af8-105">次の例では、(10, 100) の開始点と終点 (200, 100) を持つベジエ スプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="14af8-105">The following example draws a Bézier spline with start point (10, 100) and endpoint (200, 100).</span></span> <span data-ttu-id="14af8-106">コントロールは (100, 10) と (150, 150) をポイントします。</span><span class="sxs-lookup"><span data-stu-id="14af8-106">The control points are (100, 10) and (150, 150).</span></span>  
  
 <span data-ttu-id="14af8-107">次の図は、その開始点、コントロール ポイント、およびエンドポイントと共に結果として得られる本のベジエ スプラインを示します。</span><span class="sxs-lookup"><span data-stu-id="14af8-107">The following illustration shows the resulting Bézier spline along with its start point, control points, and endpoint.</span></span> <span data-ttu-id="14af8-108">図には、4 つの点を直線で接続することで形成される多角形は、スプラインの凸包も示します。</span><span class="sxs-lookup"><span data-stu-id="14af8-108">The illustration also shows the spline's convex hull, which is a polygon formed by connecting the four points with straight lines.</span></span>  
  
 ![ベジエ スプラインの図。](./media/how-to-draw-a-single-bezier-spline/bezier-spline-illustration.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ConstructingDrawingCurves#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingCurves/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14af8-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="14af8-110">Compiling the Code</span></span>  
 <span data-ttu-id="14af8-111">前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.Control.Paint> イベント ハンドラーのパラメーターである <xref:System.Windows.Forms.PaintEventArgs> `e` を必要とします。</span><span class="sxs-lookup"><span data-stu-id="14af8-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14af8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="14af8-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawBezier%2A>
- [<span data-ttu-id="14af8-113">GDI+ でのベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="14af8-113">Bézier Splines in GDI+</span></span>](bezier-splines-in-gdi.md)
- [<span data-ttu-id="14af8-114">方法: 一連のベジエ スプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="14af8-114">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)
