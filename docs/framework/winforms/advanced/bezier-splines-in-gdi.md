---
title: B&#233;ベジエ スプラインを GDI + で
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Bezier splines
- splines [Windows Forms], Bezier
- GDI+, Bezier splines
ms.assetid: 5774ce1e-87d4-4bc7-88c4-4862052781b8
ms.openlocfilehash: ff4e9eb18610b70c88e057d3d44020321bbb9f4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779277"
---
# <a name="b233zier-splines-in-gdi"></a><span data-ttu-id="6bed8-102">B&#233;ベジエ スプラインを GDI + で</span><span class="sxs-lookup"><span data-stu-id="6bed8-102">B&#233;zier Splines in GDI+</span></span>
<span data-ttu-id="6bed8-103">ベジエ スプラインは、4 つのポイントで指定された曲線: 2 つの終点 (p1 および p2) と 2 つの制御点 (c1 と c2)。</span><span class="sxs-lookup"><span data-stu-id="6bed8-103">A Bézier spline is a curve specified by four points: two end points (p1 and p2) and two control points (c1 and c2).</span></span> <span data-ttu-id="6bed8-104">曲線が p1 で始まり p2 で終了します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-104">The curve begins at p1 and ends at p2.</span></span> <span data-ttu-id="6bed8-105">曲線が制御点を通過しませんが、制御点は磁石、特定の方向に曲線を取得し、湾曲方法に影響を与えてとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-105">The curve does not pass through the control points, but the control points act as magnets, pulling the curve in certain directions and influencing the way the curve bends.</span></span> <span data-ttu-id="6bed8-106">次の図は、そのエンドポイントの制御点とベジエ曲線を示します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-106">The following illustration shows a Bézier curve along with its endpoints and control points.</span></span>  
  
 <span data-ttu-id="6bed8-107">![ベジエ スプライン](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span><span class="sxs-lookup"><span data-stu-id="6bed8-107">![Bezier Splines](./media/aboutgdip02-art11a.gif "Aboutgdip02_art11a")</span></span>  
  
 <span data-ttu-id="6bed8-108">曲線は、p1 で開始し、制御ポイント c1 に向かって移動します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-108">The curve starts at p1 and moves toward the control point c1.</span></span> <span data-ttu-id="6bed8-109">P1 に曲線の接線は、c1 を p1 から描画される直線です。</span><span class="sxs-lookup"><span data-stu-id="6bed8-109">The tangent line to the curve at p1 is the line drawn from p1 to c1.</span></span> <span data-ttu-id="6bed8-110">エンドポイント p2 の接線は、c2 から p2 に描画される直線です。</span><span class="sxs-lookup"><span data-stu-id="6bed8-110">The tangent line at the endpoint p2 is the line drawn from c2 to p2.</span></span>  
  
## <a name="drawing-bzier-splines"></a><span data-ttu-id="6bed8-111">ベジエ スプラインを描画</span><span class="sxs-lookup"><span data-stu-id="6bed8-111">Drawing Bézier Splines</span></span>  
 <span data-ttu-id="6bed8-112">インスタンスが必要な本のベジエ スプラインを描画するために、<xref:System.Drawing.Graphics>クラスと<xref:System.Drawing.Pen>します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-112">To draw a Bézier spline, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Pen>.</span></span> <span data-ttu-id="6bed8-113">インスタンス、<xref:System.Drawing.Graphics>クラスを提供、<xref:System.Drawing.Graphics.DrawBezier%2A>メソッド、および<xref:System.Drawing.Pen>曲線を表示するために使用する線の色、幅などの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-113">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawBezier%2A> method, and the <xref:System.Drawing.Pen> stores attributes, such as width and color, of the line used to render the curve.</span></span> <span data-ttu-id="6bed8-114"><xref:System.Drawing.Pen>への引数の 1 つとして渡される、<xref:System.Drawing.Graphics.DrawBezier%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="6bed8-114">The <xref:System.Drawing.Pen> is passed as one of the arguments to the <xref:System.Drawing.Graphics.DrawBezier%2A> method.</span></span> <span data-ttu-id="6bed8-115">残りの引数が渡される、<xref:System.Drawing.Graphics.DrawBezier%2A>メソッドは、エンドポイントとの制御点。</span><span class="sxs-lookup"><span data-stu-id="6bed8-115">The remaining arguments passed to the <xref:System.Drawing.Graphics.DrawBezier%2A> method are the endpoints and the control points.</span></span> <span data-ttu-id="6bed8-116">次の例では、開始位置 (0, 0) のベジエ スプラインを描画するポイント (40, 20) と (80, 150) を制御し、終了位置 (100, 10)。</span><span class="sxs-lookup"><span data-stu-id="6bed8-116">The following example draws a Bézier spline with starting point (0, 0), control points (40, 20) and (80, 150), and ending point (100, 10):</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#71](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#71)]
 [!code-vb[LinesCurvesAndShapes#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#71)]  
  
 <span data-ttu-id="6bed8-117">次の図は、曲線、コントロール ポイント、および 2 つの接線を示します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-117">The following illustration shows the curve, the control points, and two tangent lines.</span></span>  
  
 <span data-ttu-id="6bed8-118">![ベジエ スプライン](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span><span class="sxs-lookup"><span data-stu-id="6bed8-118">![Bezier Splines](./media/aboutgdip02-art12.gif "Aboutgdip02_art12")</span></span>  
  
 <span data-ttu-id="6bed8-119">ベジエ スプラインは、自動車業界での設計向けもともとサンピエール ベジエによって開発されました。</span><span class="sxs-lookup"><span data-stu-id="6bed8-119">Bézier splines were originally developed by Pierre Bézier for design in the automotive industry.</span></span> <span data-ttu-id="6bed8-120">さまざまな種類のコンピューター支援設計で利用できることがわかっていますので、フォントの輪郭の定義にも使用します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-120">They have since proven to be useful in many types of computer-aided design and are also used to define the outlines of fonts.</span></span> <span data-ttu-id="6bed8-121">ベジエ スプラインは、さまざまな図形の一部は、次の図に示しますを生成できます。</span><span class="sxs-lookup"><span data-stu-id="6bed8-121">Bézier splines can yield a wide variety of shapes, some of which are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="6bed8-122">![パス](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span><span class="sxs-lookup"><span data-stu-id="6bed8-122">![Paths](./media/aboutgdip02-art13.gif "Aboutgdip02_art13")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bed8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bed8-123">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [<span data-ttu-id="6bed8-124">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="6bed8-124">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="6bed8-125">曲線の作成と描画</span><span class="sxs-lookup"><span data-stu-id="6bed8-125">Constructing and Drawing Curves</span></span>](constructing-and-drawing-curves.md)
- [<span data-ttu-id="6bed8-126">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-126">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="6bed8-127">方法: ペンを作成します。</span><span class="sxs-lookup"><span data-stu-id="6bed8-127">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
