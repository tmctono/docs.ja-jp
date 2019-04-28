---
title: GDI+ でのペン、直線、および四角形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines
- GDI+, lines
- drawing [Windows Forms], rectangles
- rectangles
- drawing [Windows Forms], lines
- GDI+, pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- GDI+, rectangles
- examples [Windows Forms], GDI+
- lines [Windows Forms], dashed
ms.assetid: 30b25aae-e3eb-4479-bdb8-187cf651fc84
ms.openlocfilehash: 84752773c0b56d9684dc31620d463d4ddccf9dad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641392"
---
# <a name="pens-lines-and-rectangles-in-gdi"></a><span data-ttu-id="72145-102">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="72145-102">Pens, Lines, and Rectangles in GDI+</span></span>
<span data-ttu-id="72145-103">使用して線を描画するために[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]を作成する必要がある、<xref:System.Drawing.Graphics>オブジェクトと<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72145-103">To draw lines with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you need to create a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="72145-104"><xref:System.Drawing.Graphics>オブジェクトが実際には、描画を実行するメソッドを提供し、<xref:System.Drawing.Pen>オブジェクトが線の色、幅、およびスタイルなどの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="72145-104">The <xref:System.Drawing.Graphics> object provides the methods that actually do the drawing, and the <xref:System.Drawing.Pen> object stores attributes, such as line color, width, and style.</span></span>  
  
## <a name="drawing-a-line"></a><span data-ttu-id="72145-105">直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="72145-105">Drawing a Line</span></span>  
 <span data-ttu-id="72145-106">線を描画するために呼び出す、<xref:System.Drawing.Graphics.DrawLine%2A>のメソッド、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72145-106">To draw a line, call the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="72145-107"><xref:System.Drawing.Pen>オブジェクトが渡される引数の 1 つとして、<xref:System.Drawing.Graphics.DrawLine%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="72145-107">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method.</span></span> <span data-ttu-id="72145-108">次の例は、点 (12, 6) (4, 2) のポイントから線を描画します。</span><span class="sxs-lookup"><span data-stu-id="72145-108">The following example draws a line from the point (4, 2) to the point (12, 6):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#41](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#41)]
 [!code-vb[LinesCurvesAndShapes#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#41)]  
  
 <span data-ttu-id="72145-109"><xref:System.Drawing.Graphics.DrawLine%2A> オーバー ロードされたメソッド、<xref:System.Drawing.Graphics>クラスの引数を指定することがいくつかの方法があるようにします。</span><span class="sxs-lookup"><span data-stu-id="72145-109"><xref:System.Drawing.Graphics.DrawLine%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="72145-110">2 つの構築など<xref:System.Drawing.Point>オブジェクトとパス、<xref:System.Drawing.Point>オブジェクトへの引数として、<xref:System.Drawing.Graphics.DrawLine%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="72145-110">For example, you can construct two <xref:System.Drawing.Point> objects and pass the <xref:System.Drawing.Point> objects as arguments to the <xref:System.Drawing.Graphics.DrawLine%2A> method:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#42](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#42)]
 [!code-vb[LinesCurvesAndShapes#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#42)]  
  
## <a name="constructing-a-pen"></a><span data-ttu-id="72145-111">ペンを作成</span><span class="sxs-lookup"><span data-stu-id="72145-111">Constructing a Pen</span></span>  
 <span data-ttu-id="72145-112">特定の属性を指定するには、構築するときに、<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72145-112">You can specify certain attributes when you construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="72145-113">たとえば、1 つ`Pen`コンス トラクターでは、色と幅を指定できます。</span><span class="sxs-lookup"><span data-stu-id="72145-113">For example, one `Pen` constructor allows you to specify color and width.</span></span> <span data-ttu-id="72145-114">次の例では、幅が 2 から青い線を描画します (0, 0) に (60, 30)。</span><span class="sxs-lookup"><span data-stu-id="72145-114">The following example draws a blue line of width 2 from (0, 0) to (60, 30):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#43](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#43)]
 [!code-vb[LinesCurvesAndShapes#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#43)]  
  
## <a name="dashed-lines-and-line-caps"></a><span data-ttu-id="72145-115">破線とライン キャップ</span><span class="sxs-lookup"><span data-stu-id="72145-115">Dashed Lines and Line Caps</span></span>  
 <span data-ttu-id="72145-116"><xref:System.Drawing.Pen>オブジェクトのプロパティをなど、公開も<xref:System.Drawing.Pen.DashStyle%2A>行の機能の指定を行えます。</span><span class="sxs-lookup"><span data-stu-id="72145-116">The <xref:System.Drawing.Pen> object also exposes properties, such as <xref:System.Drawing.Pen.DashStyle%2A>, that you can use to specify features of the line.</span></span> <span data-ttu-id="72145-117">次の例から破線を描画します (100, 50) に (300, 80)。</span><span class="sxs-lookup"><span data-stu-id="72145-117">The following example draws a dashed line from (100, 50) to (300, 80):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#44](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#44)]
 [!code-vb[LinesCurvesAndShapes#44](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#44)]  
  
 <span data-ttu-id="72145-118">プロパティを使用することができます、<xref:System.Drawing.Pen>行の多くの属性を設定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72145-118">You can use the properties of the <xref:System.Drawing.Pen> object to set many more attributes of the line.</span></span> <span data-ttu-id="72145-119"><xref:System.Drawing.Pen.StartCap%2A>と<xref:System.Drawing.Pen.EndCap%2A>プロパティは、線の端の外観を指定。 end は、フラット、正方形、丸められた、三角形、またはカスタムの形状。</span><span class="sxs-lookup"><span data-stu-id="72145-119">The <xref:System.Drawing.Pen.StartCap%2A> and <xref:System.Drawing.Pen.EndCap%2A> properties specify the appearance of the ends of the line; the ends can be flat, square, rounded, triangular, or a custom shape.</span></span> <span data-ttu-id="72145-120"><xref:System.Drawing.Pen.LineJoin%2A>プロパティかどうか接続されている行はマイター (鋭い角の結合)、傾斜、丸め、またはクリップを指定できます。</span><span class="sxs-lookup"><span data-stu-id="72145-120">The <xref:System.Drawing.Pen.LineJoin%2A> property lets you specify whether connected lines are mitered (joined with sharp corners), beveled, rounded, or clipped.</span></span> <span data-ttu-id="72145-121">次の図は、さまざまな上限と結合スタイルを使用して行を示します。</span><span class="sxs-lookup"><span data-stu-id="72145-121">The following illustration shows lines with various cap and join styles.</span></span>  
  
 <span data-ttu-id="72145-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span><span class="sxs-lookup"><span data-stu-id="72145-122">![Lines](./media/aboutgdip02-art04.gif "Aboutgdip02_art04")</span></span>  
  
## <a name="drawing-a-rectangle"></a><span data-ttu-id="72145-123">四角形の描画</span><span class="sxs-lookup"><span data-stu-id="72145-123">Drawing a Rectangle</span></span>  
 <span data-ttu-id="72145-124">四角形を描画[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]線を描画に似ています。</span><span class="sxs-lookup"><span data-stu-id="72145-124">Drawing rectangles with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is similar to drawing lines.</span></span> <span data-ttu-id="72145-125">四角形を描画する必要があります、<xref:System.Drawing.Graphics>オブジェクトと<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="72145-125">To draw a rectangle, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="72145-126"><xref:System.Drawing.Graphics>オブジェクトを提供、<xref:System.Drawing.Graphics.DrawRectangle%2A>メソッド、および<xref:System.Drawing.Pen>オブジェクトが線の幅と色などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="72145-126">The <xref:System.Drawing.Graphics> object provides a <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores attributes, such as line width and color.</span></span> <span data-ttu-id="72145-127"><xref:System.Drawing.Pen>オブジェクトが渡される引数の 1 つとして、<xref:System.Drawing.Graphics.DrawRectangle%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="72145-127">The <xref:System.Drawing.Pen> object is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method.</span></span> <span data-ttu-id="72145-128">次の例で、左上隅を四角形を描画します (100, 50)、80、幅と高さ 40。</span><span class="sxs-lookup"><span data-stu-id="72145-128">The following example draws a rectangle with its upper-left corner at (100, 50), a width of 80, and a height of 40:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#45](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#45)]
 [!code-vb[LinesCurvesAndShapes#45](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#45)]  
  
 <span data-ttu-id="72145-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> オーバー ロードされたメソッド、<xref:System.Drawing.Graphics>クラスの引数を指定することがいくつかの方法があるようにします。</span><span class="sxs-lookup"><span data-stu-id="72145-129"><xref:System.Drawing.Graphics.DrawRectangle%2A> is an overloaded method of the <xref:System.Drawing.Graphics> class, so there are several ways you can supply it with arguments.</span></span> <span data-ttu-id="72145-130">たとえば、構築、<xref:System.Drawing.Rectangle>オブジェクトを渡します、<xref:System.Drawing.Rectangle>オブジェクトを<xref:System.Drawing.Graphics.DrawRectangle%2A>を引数としてメソッド。</span><span class="sxs-lookup"><span data-stu-id="72145-130">For example, you can construct a <xref:System.Drawing.Rectangle> object and pass the <xref:System.Drawing.Rectangle> object to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method as an argument:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#46](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#46)]
 [!code-vb[LinesCurvesAndShapes#46](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#46)]  
  
 <span data-ttu-id="72145-131">A<xref:System.Drawing.Rectangle>オブジェクトがメソッドとプロパティを操作すると、四角形に関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="72145-131">A <xref:System.Drawing.Rectangle> object has methods and properties for manipulating and gathering information about the rectangle.</span></span> <span data-ttu-id="72145-132">たとえば、<xref:System.Drawing.Rectangle.Inflate%2A>と<xref:System.Drawing.Rectangle.Offset%2A>メソッドは、四角形の位置とサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="72145-132">For example, the <xref:System.Drawing.Rectangle.Inflate%2A> and <xref:System.Drawing.Rectangle.Offset%2A> methods change the size and position of the rectangle.</span></span> <span data-ttu-id="72145-133"><xref:System.Drawing.Rectangle.IntersectsWith%2A>メソッドに指示するかどうか、四角形と交差する別の四角形を指定し、<xref:System.Drawing.Rectangle.Contains%2A>メソッドは、指定された点が四角形の内側がかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="72145-133">The <xref:System.Drawing.Rectangle.IntersectsWith%2A> method tells you whether the rectangle intersects another given rectangle, and the <xref:System.Drawing.Rectangle.Contains%2A> method tells you whether a given point is inside the rectangle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72145-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="72145-134">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- [<span data-ttu-id="72145-135">方法: ペンを作成します。</span><span class="sxs-lookup"><span data-stu-id="72145-135">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="72145-136">方法: Windows フォームに直線を描画します。</span><span class="sxs-lookup"><span data-stu-id="72145-136">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)
- [<span data-ttu-id="72145-137">方法: 形状のアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="72145-137">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)
