---
title: ベクター グラフィックスの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inclusive-inclusive endpoints
- coordinate systems
- graphics [Windows Forms], vector graphics
ms.assetid: 0195df81-66be-452d-bb53-5a582ebfdc09
ms.openlocfilehash: 64bec47a186b08298a49c6f188795d1b51d234eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505242"
---
# <a name="vector-graphics-overview"></a><span data-ttu-id="becbe-102">ベクター グラフィックスの概要</span><span class="sxs-lookup"><span data-stu-id="becbe-102">Vector Graphics Overview</span></span>
<span data-ttu-id="becbe-103">GDI +、座標系の線、四角形、およびその他の図形を描画します。</span><span class="sxs-lookup"><span data-stu-id="becbe-103">GDI+ draws lines, rectangles, and other shapes on a coordinate system.</span></span> <span data-ttu-id="becbe-104">さまざまな座標系から選択できますが、既定の座標系では、左上隅の原点が、x 軸が右と下向きの y 軸を参照します。</span><span class="sxs-lookup"><span data-stu-id="becbe-104">You can choose from a variety of coordinate systems, but the default coordinate system has the origin in the upper-left corner with the x-axis pointing to the right and the y-axis pointing down.</span></span> <span data-ttu-id="becbe-105">既定の座標系内のメジャーの単位は、ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="becbe-105">The unit of measure in the default coordinate system is the pixel.</span></span>  
  
## <a name="the-building-blocks-of-gdi"></a><span data-ttu-id="becbe-106">GDI + の構成要素</span><span class="sxs-lookup"><span data-stu-id="becbe-106">The Building Blocks of GDI+</span></span>  
 <span data-ttu-id="becbe-107">![ベクター グラフィックス](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span><span class="sxs-lookup"><span data-stu-id="becbe-107">![Vector graphic](./media/aboutgdip02-art01.gif "AboutGdip02_Art01")</span></span>  
  
 <span data-ttu-id="becbe-108">コンピューター モニターでは、図の要素 (ピクセル) と呼ばれる点の四角形の配列での表示を作成します。</span><span class="sxs-lookup"><span data-stu-id="becbe-108">A computer monitor creates its display on a rectangular array of dots called picture elements or pixels.</span></span> <span data-ttu-id="becbe-109">1 つのモニターの画面に表示されるピクセルの数が異なり、ユーザーが、個々 のモニターに表示されるピクセルの数をある程度の構成することができます通常します。</span><span class="sxs-lookup"><span data-stu-id="becbe-109">The number of pixels that appear on the screen varies from one monitor to the next, and the number of pixels that appear on an individual monitor can usually be configured to some extent by the user.</span></span>  
  
 <span data-ttu-id="becbe-110">![ベクター グラフィックス](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span><span class="sxs-lookup"><span data-stu-id="becbe-110">![Vector graphic](./media/aboutgdip02-art02.gif "AboutGdip02_Art02")</span></span>  
  
 <span data-ttu-id="becbe-111">を使用する GDI + 線、四角形、または曲線を描画するときに、描画される項目に関する特定のキー情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="becbe-111">When you use GDI+ to draw a line, rectangle, or curve, you provide certain key information about the item to be drawn.</span></span> <span data-ttu-id="becbe-112">たとえば、2 つのポイントを提供することで、行を指定することができ、ポイントを高さ、幅を提供し、四角形を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="becbe-112">For example, you can specify a line by providing two points, and you can specify a rectangle by providing a point, a height, and a width.</span></span> <span data-ttu-id="becbe-113">GDI + ディスプレイ ドライバー ソフトウェアは、線、四角形、または曲線の表示にするピクセルをオンにするかを判断すると連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="becbe-113">GDI+ works in conjunction with the display driver software to determine which pixels must be turned on to show the line, rectangle, or curve.</span></span> <span data-ttu-id="becbe-114">次の図は、点 (12, 8) (4, 2) のポイントから行を表示するのになっている (ピクセル) を示します。</span><span class="sxs-lookup"><span data-stu-id="becbe-114">The following illustration shows the pixels that are turned on to display a line from the point (4, 2) to the point (12, 8).</span></span>  
  
 <span data-ttu-id="becbe-115">![ベクター グラフィックス](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span><span class="sxs-lookup"><span data-stu-id="becbe-115">![Vector graphic](./media/aboutgdip02-art03.gif "AboutGdip02_Art03")</span></span>  
  
 <span data-ttu-id="becbe-116">時間の経過と共に一部の基本的な構成要素が最も便利な 2 次元の画像を作成するために実績のあります。</span><span class="sxs-lookup"><span data-stu-id="becbe-116">Over time, certain basic building blocks have proven to be the most useful for creating two-dimensional pictures.</span></span> <span data-ttu-id="becbe-117">GDI + ですべてサポートされていますが、これらのビルディング ブロックは、次の一覧で与えられます。</span><span class="sxs-lookup"><span data-stu-id="becbe-117">These building blocks, which are all supported by GDI+, are given in the following list:</span></span>  
  
- <span data-ttu-id="becbe-118">線</span><span class="sxs-lookup"><span data-stu-id="becbe-118">Lines</span></span>  
  
- <span data-ttu-id="becbe-119">四角形</span><span class="sxs-lookup"><span data-stu-id="becbe-119">Rectangles</span></span>  
  
- <span data-ttu-id="becbe-120">省略記号</span><span class="sxs-lookup"><span data-stu-id="becbe-120">Ellipses</span></span>  
  
- <span data-ttu-id="becbe-121">円弧</span><span class="sxs-lookup"><span data-stu-id="becbe-121">Arcs</span></span>  
  
- <span data-ttu-id="becbe-122">多角形</span><span class="sxs-lookup"><span data-stu-id="becbe-122">Polygons</span></span>  
  
- <span data-ttu-id="becbe-123">カーディナル スプライン</span><span class="sxs-lookup"><span data-stu-id="becbe-123">Cardinal splines</span></span>  
  
- <span data-ttu-id="becbe-124">ベジエ スプライン</span><span class="sxs-lookup"><span data-stu-id="becbe-124">Bezier splines</span></span>  
  
## <a name="methods-for-drawing-with-a-graphics-object"></a><span data-ttu-id="becbe-125">グラフィックス オブジェクトを使用した描画メソッド</span><span class="sxs-lookup"><span data-stu-id="becbe-125">Methods For Drawing with a Graphics Object</span></span>  
 <span data-ttu-id="becbe-126"><xref:System.Drawing.Graphics> GDI + でクラスには前の一覧に項目を描画するための次のメソッド: <xref:System.Drawing.Graphics.DrawLine%2A>、 <xref:System.Drawing.Graphics.DrawRectangle%2A>、 <xref:System.Drawing.Graphics.DrawEllipse%2A>、 <xref:System.Drawing.Graphics.DrawPolygon%2A>、 <xref:System.Drawing.Graphics.DrawArc%2A>、 <xref:System.Drawing.Graphics.DrawCurve%2A> (のカーディナル スプライン)、および<xref:System.Drawing.Graphics.DrawBezier%2A>.</span><span class="sxs-lookup"><span data-stu-id="becbe-126">The <xref:System.Drawing.Graphics> class in GDI+ provides the following methods for drawing the items in the previous list: <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawRectangle%2A>, <xref:System.Drawing.Graphics.DrawEllipse%2A>, <xref:System.Drawing.Graphics.DrawPolygon%2A>, <xref:System.Drawing.Graphics.DrawArc%2A>, <xref:System.Drawing.Graphics.DrawCurve%2A> (for cardinal splines), and <xref:System.Drawing.Graphics.DrawBezier%2A>.</span></span> <span data-ttu-id="becbe-127">これらの各メソッドはオーバー ロードされます。つまり、各メソッドは、さまざまなパラメーター リストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="becbe-127">Each of these methods is overloaded; that is, each method supports several different parameter lists.</span></span> <span data-ttu-id="becbe-128">例では、1 つのバリエーション、<xref:System.Drawing.Graphics.DrawLine%2A>メソッドは受信、<xref:System.Drawing.Pen>オブジェクトと別のバリエーションの中に、4 つの整数、<xref:System.Drawing.Graphics.DrawLine%2A>メソッドは受信、<xref:System.Drawing.Pen>オブジェクトと 2 つ<xref:System.Drawing.Point>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="becbe-128">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers, while another variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and two <xref:System.Drawing.Point> objects.</span></span>  
  
 <span data-ttu-id="becbe-129">線、四角形、およびベジエ スプラインを描画するためのメソッドがある 1 回の呼び出しで複数の項目を描画する複数形のコンパニオン メソッド: <xref:System.Drawing.Graphics.DrawLines%2A>、 <xref:System.Drawing.Graphics.DrawRectangles%2A>、および<xref:System.Drawing.Graphics.DrawBeziers%2A>します。</span><span class="sxs-lookup"><span data-stu-id="becbe-129">The methods for drawing lines, rectangles, and Bézier splines have plural companion methods that draw several items in a single call: <xref:System.Drawing.Graphics.DrawLines%2A>, <xref:System.Drawing.Graphics.DrawRectangles%2A>, and <xref:System.Drawing.Graphics.DrawBeziers%2A>.</span></span> <span data-ttu-id="becbe-130">また、<xref:System.Drawing.Graphics.DrawCurve%2A>メソッドには、コンパニオン メソッド<xref:System.Drawing.Graphics.DrawClosedCurve%2A>終了、開始する曲線の終了点を接続することで曲線をポイントします。</span><span class="sxs-lookup"><span data-stu-id="becbe-130">Also, the <xref:System.Drawing.Graphics.DrawCurve%2A> method has a companion method, <xref:System.Drawing.Graphics.DrawClosedCurve%2A>, that closes a curve by connecting the ending point of the curve to the starting point.</span></span>  
  
 <span data-ttu-id="becbe-131">すべての描画メソッドの<xref:System.Drawing.Graphics>クラスと連携して動作を<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="becbe-131">All of the drawing methods of the <xref:System.Drawing.Graphics> class work in conjunction with a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="becbe-132">を何も描画するには、少なくとも 2 つのオブジェクトを作成する必要があります:、<xref:System.Drawing.Graphics>オブジェクトと<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="becbe-132">To draw anything, you must create at least two objects: a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="becbe-133"><xref:System.Drawing.Pen>オブジェクトが描画される項目の色、線の幅などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="becbe-133">The <xref:System.Drawing.Pen> object stores attributes, such as line width and color, of the item to be drawn.</span></span> <span data-ttu-id="becbe-134"><xref:System.Drawing.Pen>オブジェクトが引数の 1 つとして描画メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="becbe-134">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the drawing method.</span></span> <span data-ttu-id="becbe-135">例では、1 つのバリエーション、<xref:System.Drawing.Graphics.DrawLine%2A>メソッドは受信、<xref:System.Drawing.Pen>オブジェクトと、幅が 100、高さを 50 との左上隅を四角形を描画する次の例で示すように 4 つの整数 (20, 10)。</span><span class="sxs-lookup"><span data-stu-id="becbe-135">For example, one variation of the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object and four integers as shown in the following example, which draws a rectangle with a width of 100, a height of 50 and an upper-left corner of (20, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#11](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#11)]
 [!code-vb[LinesCurvesAndShapes#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="becbe-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="becbe-136">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="becbe-137">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="becbe-137">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="becbe-138">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="becbe-138">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
