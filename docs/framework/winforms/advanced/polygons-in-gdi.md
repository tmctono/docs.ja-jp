---
title: GDI+ での多角形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641308"
---
# <a name="polygons-in-gdi"></a><span data-ttu-id="ed3e0-102">GDI+ での多角形</span><span class="sxs-lookup"><span data-stu-id="ed3e0-102">Polygons in GDI+</span></span>
<span data-ttu-id="ed3e0-103">多角形は、次の 3 つまたは複数の辺を持つ閉じた図形です。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-103">A polygon is a closed shape with three or more straight sides.</span></span> <span data-ttu-id="ed3e0-104">たとえば、三角形は、次の 3 つの辺の多角形、四角形は、4 辺の多角形および五角形は、5 つの辺の多角形です。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-104">For example, a triangle is a polygon with three sides, a rectangle is a polygon with four sides, and a pentagon is a polygon with five sides.</span></span> <span data-ttu-id="ed3e0-105">次の図は、いくつかの多角形を示します。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-105">The following illustration shows several polygons.</span></span>  
  
 <span data-ttu-id="ed3e0-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span><span class="sxs-lookup"><span data-stu-id="ed3e0-106">![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")</span></span>  
  
## <a name="drawing-a-polygon"></a><span data-ttu-id="ed3e0-107">多角形の描画</span><span class="sxs-lookup"><span data-stu-id="ed3e0-107">Drawing a Polygon</span></span>  
 <span data-ttu-id="ed3e0-108">多角形を描画する必要があります、<xref:System.Drawing.Graphics>オブジェクト、<xref:System.Drawing.Pen>オブジェクト、および配列の<xref:System.Drawing.Point>(または<xref:System.Drawing.PointF>) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-108">To draw a polygon, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and an array of <xref:System.Drawing.Point> (or <xref:System.Drawing.PointF>) objects.</span></span> <span data-ttu-id="ed3e0-109"><xref:System.Drawing.Graphics>オブジェクトは、提供、<xref:System.Drawing.Graphics.DrawPolygon%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-109">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="ed3e0-110"><xref:System.Drawing.Pen>オブジェクトは、多角形、およびの配列を表示するために使用する線の色、幅などの属性を格納<xref:System.Drawing.Point>オブジェクトが直線で接続するポイントを格納します。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-110">The <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the polygon, and the array of <xref:System.Drawing.Point> objects stores the points to be connected by straight lines.</span></span> <span data-ttu-id="ed3e0-111"><xref:System.Drawing.Pen>オブジェクトの配列および<xref:System.Drawing.Point>オブジェクトへの引数として渡される、<xref:System.Drawing.Graphics.DrawPolygon%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-111">The <xref:System.Drawing.Pen> object and the array of <xref:System.Drawing.Point> objects are passed as arguments to the <xref:System.Drawing.Graphics.DrawPolygon%2A> method.</span></span> <span data-ttu-id="ed3e0-112">次の例では、3 つの辺の多角形を描画します。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-112">The following example draws a three-sided polygon.</span></span> <span data-ttu-id="ed3e0-113">内の 3 つだけのポイントがあることに注意してください`myPointArray`:。(0, 0)、(50, 30) と (30, 60)。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-113">Note that there are only three points in `myPointArray`: (0, 0), (50, 30), and (30, 60).</span></span> <span data-ttu-id="ed3e0-114"><xref:System.Drawing.Graphics.DrawPolygon%2A>メソッドから行を描画することで、多角形を自動的に閉じます (30, 60) 開始ポイント (0, 0) に戻ります。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-114">The <xref:System.Drawing.Graphics.DrawPolygon%2A> method automatically closes the polygon by drawing a line from (30, 60) back to the starting point (0, 0).</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 <span data-ttu-id="ed3e0-115">次の図は、多角形を示します。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-115">The following illustration shows the polygon.</span></span>  
  
 <span data-ttu-id="ed3e0-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span><span class="sxs-lookup"><span data-stu-id="ed3e0-116">![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3e0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed3e0-117">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="ed3e0-118">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="ed3e0-118">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="ed3e0-119">方法: ペンを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed3e0-119">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
