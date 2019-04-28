---
title: GDI+ でのグラフィックス パス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], paths
- GDI+, drawing paths
- paths [Windows Forms], drawing
- drawing [Windows Forms], paths
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
ms.openlocfilehash: c9a43065210f5ef0fffcae01cc7eb88349696b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938170"
---
# <a name="graphics-paths-in-gdi"></a><span data-ttu-id="52179-102">GDI+ でのグラフィックス パス</span><span class="sxs-lookup"><span data-stu-id="52179-102">Graphics Paths in GDI+</span></span>
<span data-ttu-id="52179-103">パスは、線、四角形、および単純な曲線を組み合わせることで形成されます。</span><span class="sxs-lookup"><span data-stu-id="52179-103">Paths are formed by combining lines, rectangles, and simple curves.</span></span> <span data-ttu-id="52179-104">メッセージの取り消し、[ベクター グラフィックスの概要](vector-graphics-overview.md)基本ビルディング ブロックを次に図を描画するために最も便利なことがわかっています。</span><span class="sxs-lookup"><span data-stu-id="52179-104">Recall from the [Vector Graphics Overview](vector-graphics-overview.md) that the following basic building blocks have proven to be the most useful for drawing pictures:</span></span>  
  
- <span data-ttu-id="52179-105">線</span><span class="sxs-lookup"><span data-stu-id="52179-105">Lines</span></span>  
  
- <span data-ttu-id="52179-106">四角形</span><span class="sxs-lookup"><span data-stu-id="52179-106">Rectangles</span></span>  
  
- <span data-ttu-id="52179-107">省略記号</span><span class="sxs-lookup"><span data-stu-id="52179-107">Ellipses</span></span>  
  
- <span data-ttu-id="52179-108">円弧</span><span class="sxs-lookup"><span data-stu-id="52179-108">Arcs</span></span>  
  
- <span data-ttu-id="52179-109">多角形</span><span class="sxs-lookup"><span data-stu-id="52179-109">Polygons</span></span>  
  
- <span data-ttu-id="52179-110">カーディナル スプライン</span><span class="sxs-lookup"><span data-stu-id="52179-110">Cardinal splines</span></span>  
  
- <span data-ttu-id="52179-111">ベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="52179-111">Bézier splines</span></span>  
  
 <span data-ttu-id="52179-112">GDI + で、<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトでは、これらの構成要素のシーケンスを 1 つの単位に収集できます。</span><span class="sxs-lookup"><span data-stu-id="52179-112">In GDI+, the <xref:System.Drawing.Drawing2D.GraphicsPath> object allows you to collect a sequence of these building blocks into a single unit.</span></span> <span data-ttu-id="52179-113">1 回の呼び出しで線、四角形、多角形、および曲線のシーケンス全体を描画することができますし、<xref:System.Drawing.Graphics.DrawPath%2A>のメソッド、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="52179-113">The entire sequence of lines, rectangles, polygons, and curves can then be drawn with one call to the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="52179-114">次の図には、行、円弧、本のベジエ スプライン、カーディナル スプラインを組み合わせることにより作成されたパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52179-114">The following illustration shows a path created by combining a line, an arc, a Bézier spline, and a cardinal spline.</span></span>  
  
 <span data-ttu-id="52179-115">![パス](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span><span class="sxs-lookup"><span data-stu-id="52179-115">![Path](./media/aboutgdip02-art14.gif "Aboutgdip02_art14")</span></span>  
  
## <a name="using-a-path"></a><span data-ttu-id="52179-116">パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="52179-116">Using a Path</span></span>  
 <span data-ttu-id="52179-117"><xref:System.Drawing.Drawing2D.GraphicsPath>クラスが描画される項目のシーケンスを作成するために、次のメソッドを提供します: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (のカーディナル スプライン)、および<xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>します。</span><span class="sxs-lookup"><span data-stu-id="52179-117">The <xref:System.Drawing.Drawing2D.GraphicsPath> class provides the following methods for creating a sequence of items to be drawn: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> (for cardinal splines), and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A>.</span></span> <span data-ttu-id="52179-118">これらの各メソッドはオーバー ロードされます。つまり、各メソッドは、さまざまなパラメーター リストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="52179-118">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="52179-119">例では、1 つのバリエーション、<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>メソッドは、4 つの整数と別のバリエーションを受け取る、<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>メソッドが受け取る 2 つ<xref:System.Drawing.Point>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="52179-119">For example, one variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives four integers, and another variation of the <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> method receives two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="52179-120">線、四角形、およびベジエ スプラインをパスに追加するためのメソッドを 1 つの呼び出しパスに複数の項目を追加する複数形のコンパニオン メソッドがある: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>、 <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>、および<xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>します。</span><span class="sxs-lookup"><span data-stu-id="52179-120">The methods for adding lines, rectangles, and Bézier splines to a path have plural companion methods that add several items to the path in a single call: <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A>, and <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A>.</span></span> <span data-ttu-id="52179-121">また、<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>と<xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>メソッド コンパニオンのメソッドがある<xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A>と<xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>パスに閉じた曲線または円を追加します。</span><span class="sxs-lookup"><span data-stu-id="52179-121">Also, the <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> methods have companion methods, <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A>, that add a closed curve or pie to the path.</span></span>  
  
 <span data-ttu-id="52179-122">パスを描画するためにする必要があります、<xref:System.Drawing.Graphics>オブジェクト、<xref:System.Drawing.Pen>オブジェクト、および<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="52179-122">To draw a path, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Pen> object, and a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="52179-123"><xref:System.Drawing.Graphics>オブジェクトを提供、<xref:System.Drawing.Graphics.DrawPath%2A>メソッド、および<xref:System.Drawing.Pen>オブジェクトは、パスを表示するために使用する線の色、幅などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="52179-123">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawPath%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as width and color, of the line used to render the path.</span></span> <span data-ttu-id="52179-124"><xref:System.Drawing.Drawing2D.GraphicsPath>の直線と曲線のパスを構成するシーケンスを格納するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="52179-124">The <xref:System.Drawing.Drawing2D.GraphicsPath> object stores the sequence of lines and curves that make up the path.</span></span> <span data-ttu-id="52179-125"><xref:System.Drawing.Pen>オブジェクトと<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトが引数として渡される、<xref:System.Drawing.Graphics.DrawPath%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="52179-125">The <xref:System.Drawing.Pen> object and the <xref:System.Drawing.Drawing2D.GraphicsPath> object are passed as arguments to the <xref:System.Drawing.Graphics.DrawPath%2A> method.</span></span> <span data-ttu-id="52179-126">次の例では、パスは、行、楕円、および本のベジエ スプラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="52179-126">The following example draws a path that consists of a line, an ellipse, and a Bézier spline:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#101](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 <span data-ttu-id="52179-127">次の図には、パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52179-127">The following illustration shows the path.</span></span>  
  
 <span data-ttu-id="52179-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span><span class="sxs-lookup"><span data-stu-id="52179-128">![Path](./media/aboutgdip02-art15.gif "Aboutgdip02_art15")</span></span>  
  
 <span data-ttu-id="52179-129">パスに線、四角形、および曲線を追加するだけでは、パスにパスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="52179-129">In addition to adding lines, rectangles, and curves to a path, you can add paths to a path.</span></span> <span data-ttu-id="52179-130">これにより、大規模で複雑なパスを形成する既存のパスを結合することができます。</span><span class="sxs-lookup"><span data-stu-id="52179-130">This allows you to combine existing paths to form large, complex paths.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#102](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 <span data-ttu-id="52179-131">パスに追加できるその他の 2 つの項目がある: 文字列と円グラフ。</span><span class="sxs-lookup"><span data-stu-id="52179-131">There are two other items you can add to a path: strings and pies.</span></span> <span data-ttu-id="52179-132">円、楕円の内部の一部です。</span><span class="sxs-lookup"><span data-stu-id="52179-132">A pie is a portion of the interior of an ellipse.</span></span> <span data-ttu-id="52179-133">次の例では、円弧、カーディナル スプライン、文字列、および円からパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="52179-133">The following example creates a path from an arc, a cardinal spline, a string, and a pie:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#103](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 <span data-ttu-id="52179-134">次の図には、パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="52179-134">The following illustration shows the path.</span></span> <span data-ttu-id="52179-135">パスに接続されている; がないことに注意してください。円弧をカーディナル スプラインを文字列、および円グラフは区切られます。</span><span class="sxs-lookup"><span data-stu-id="52179-135">Note that a path does not have to be connected; the arc, cardinal spline, string, and pie are separated.</span></span>  
  
 <span data-ttu-id="52179-136">![パス](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span><span class="sxs-lookup"><span data-stu-id="52179-136">![Paths](./media/aboutgdip02-art16.gif "Aboutgdip02_Art16")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52179-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="52179-137">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [<span data-ttu-id="52179-138">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="52179-138">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="52179-139">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="52179-139">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="52179-140">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="52179-140">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
