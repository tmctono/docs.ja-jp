---
title: GDI+ での開いた曲線と閉じた曲線
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 33a8954296a7e63637ad5e210fb30fba1a3fdd53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641470"
---
# <a name="open-and-closed-curves-in-gdi"></a><span data-ttu-id="bb0bb-102">GDI+ での開いた曲線と閉じた曲線</span><span class="sxs-lookup"><span data-stu-id="bb0bb-102">Open and Closed Curves in GDI+</span></span>
<span data-ttu-id="bb0bb-103">次の図は、2 つの曲線を示しています。 1 つが開いて、もう 1 つの閉じられました。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-103">The following illustration shows two curves: one open and one closed.</span></span>  
  
 <span data-ttu-id="bb0bb-104">![開いた曲線と閉じた曲線](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span><span class="sxs-lookup"><span data-stu-id="bb0bb-104">![Open & Closed curves](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")</span></span>  
  
## <a name="managed-interface-for-curves"></a><span data-ttu-id="bb0bb-105">曲線の管理インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bb0bb-105">Managed Interface for Curves</span></span>  
 <span data-ttu-id="bb0bb-106">閉じた曲線は、内部があるし、ブラシを使用して入力することができます。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-106">Closed curves have an interior and therefore can be filled with a brush.</span></span> <span data-ttu-id="bb0bb-107"><xref:System.Drawing.Graphics>クラス[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]閉じた図形と曲線を塗りつぶすときの次のメソッドを提供します: <xref:System.Drawing.Graphics.FillRectangle%2A>、 <xref:System.Drawing.Graphics.FillEllipse%2A>、 <xref:System.Drawing.Graphics.FillPie%2A>、 <xref:System.Drawing.Graphics.FillPolygon%2A>、 <xref:System.Drawing.Graphics.FillClosedCurve%2A>、 <xref:System.Drawing.Graphics.FillPath%2A>、および<xref:System.Drawing.Graphics.FillRegion%2A>します。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-107">The <xref:System.Drawing.Graphics> class in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] provides the following methods for filling closed shapes and curves: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, and <xref:System.Drawing.Graphics.FillRegion%2A>.</span></span> <span data-ttu-id="bb0bb-108">これらのメソッドのいずれかを呼び出すたびに、特定のブラシの種類のいずれかを渡す必要があります (<xref:System.Drawing.SolidBrush>、 <xref:System.Drawing.Drawing2D.HatchBrush>、 <xref:System.Drawing.TextureBrush>、 <xref:System.Drawing.Drawing2D.LinearGradientBrush>、または<xref:System.Drawing.Drawing2D.PathGradientBrush>) を引数として。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-108">Whenever you call one of these methods, you must pass one of the specific brush types (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, or <xref:System.Drawing.Drawing2D.PathGradientBrush>) as an argument.</span></span>  
  
 <span data-ttu-id="bb0bb-109"><xref:System.Drawing.Graphics.FillPie%2A>メソッドは、対応する、<xref:System.Drawing.Graphics.DrawArc%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-109">The <xref:System.Drawing.Graphics.FillPie%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawArc%2A> method.</span></span> <span data-ttu-id="bb0bb-110">同様、<xref:System.Drawing.Graphics.DrawArc%2A>メソッドは、楕円のアウトラインの一部を描画、<xref:System.Drawing.Graphics.FillPie%2A>メソッドは、楕円の内部の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-110">Just as the <xref:System.Drawing.Graphics.DrawArc%2A> method draws a portion of the outline of an ellipse, the <xref:System.Drawing.Graphics.FillPie%2A> method fills a portion of the interior of an ellipse.</span></span> <span data-ttu-id="bb0bb-111">次の例では、円弧を描画し、楕円の内部の対応する部分を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-111">The following example draws an arc and fills the corresponding portion of the interior of the ellipse:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 <span data-ttu-id="bb0bb-112">次の図は、円弧と塗りつぶされた円グラフを示します。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-112">The following illustration shows the arc and the filled pie.</span></span>  
  
 <span data-ttu-id="bb0bb-113">![開いた曲線と閉じた曲線](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span><span class="sxs-lookup"><span data-stu-id="bb0bb-113">![Open & Closed curves](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")</span></span>  
  
 <span data-ttu-id="bb0bb-114"><xref:System.Drawing.Graphics.FillClosedCurve%2A>メソッドは、対応する、<xref:System.Drawing.Graphics.DrawClosedCurve%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-114">The <xref:System.Drawing.Graphics.FillClosedCurve%2A> method is a companion to the <xref:System.Drawing.Graphics.DrawClosedCurve%2A> method.</span></span> <span data-ttu-id="bb0bb-115">どちらの方法は、自動的に開始点、終点を接続することで、曲線を閉じます。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-115">Both methods automatically close the curve by connecting the ending point to the starting point.</span></span> <span data-ttu-id="bb0bb-116">次の例では、通過する曲線を描画します (0, 0)、(60, 20)、および (40、50)。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-116">The following example draws a curve that passes through (0, 0), (60, 20), and (40, 50).</span></span> <span data-ttu-id="bb0bb-117">接続することで、曲線が自動的に閉じられますし、(40、50) 開始点 (0, 0) と、内部が純色で塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-117">Then, the curve is automatically closed by connecting (40, 50) to the starting point (0, 0), and the interior is filled with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <span data-ttu-id="bb0bb-118"><xref:System.Drawing.Graphics.FillPath%2A>メソッドは、パスの別の部分の内部を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-118">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the interiors of the separate pieces of a path.</span></span> <span data-ttu-id="bb0bb-119">閉じた曲線や図形、パスの一部を形成しない場合、<xref:System.Drawing.Graphics.FillPath%2A>メソッドでは、入力する前に、パスの部分を自動的に閉じます。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-119">If a piece of a path doesn't form a closed curve or shape, the <xref:System.Drawing.Graphics.FillPath%2A> method automatically closes that piece of the path before filling it.</span></span> <span data-ttu-id="bb0bb-120">次の例では、描画し、円弧、カーディナル スプライン、文字列、および、円グラフで構成されるパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-120">The following example draws and fills a path that consists of an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 <span data-ttu-id="bb0bb-121">次の図では、塗りつぶしの純なしでパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-121">The following illustration shows the path with and without the solid fill.</span></span> <span data-ttu-id="bb0bb-122">文字列内のテキストが記載されているが入力されていない、によって、<xref:System.Drawing.Graphics.DrawPath%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-122">Note that the text in the string is outlined, but not filled, by the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="bb0bb-123"><xref:System.Drawing.Graphics.FillPath%2A>文字列内の文字の内部を描画するメソッド。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-123">It is the <xref:System.Drawing.Graphics.FillPath%2A> method that paints the interiors of the characters in the string.</span></span>  
  
 <span data-ttu-id="bb0bb-124">![パス文字列](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span><span class="sxs-lookup"><span data-stu-id="bb0bb-124">![String in a path](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb0bb-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb0bb-125">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="bb0bb-126">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="bb0bb-126">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="bb0bb-127">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb0bb-127">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="bb0bb-128">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="bb0bb-128">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
