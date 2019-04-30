---
title: '方法: 複合図形の塗りつぶしを制御する'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 0ba07d8979a2910ce4ec775493e38c714240f642
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61997171"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a><span data-ttu-id="2ceed-102">方法: 複合図形の塗りつぶしを制御する</span><span class="sxs-lookup"><span data-stu-id="2ceed-102">How to: Control the Fill of a Composite Shape</span></span>
<span data-ttu-id="2ceed-103"><xref:System.Windows.Media.GeometryGroup.FillRule%2A>のプロパティを<xref:System.Windows.Media.GeometryGroup>または<xref:System.Windows.Media.PathGeometry>、複合図形を使用して、指定された点がジオメトリの一部であるかどうかを確認する「規則」を指定します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-103">The <xref:System.Windows.Media.GeometryGroup.FillRule%2A> property of a <xref:System.Windows.Media.GeometryGroup> or a <xref:System.Windows.Media.PathGeometry>, specifies a "rule" which the composite shape uses to determine whether a given point is part of the geometry.</span></span> <span data-ttu-id="2ceed-104">2 つの値がある<xref:System.Windows.Media.FillRule>:<xref:System.Windows.Media.FillRule.EvenOdd>と<xref:System.Windows.Media.FillRule.Nonzero>します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-104">There are two possible values for <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> and <xref:System.Windows.Media.FillRule.Nonzero>.</span></span> <span data-ttu-id="2ceed-105">以下のセクションでは、これら 2 つの規則の使用方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-105">The following sections will describe how to use these two rules.</span></span>  
  
 <span data-ttu-id="2ceed-106">**EvenOdd:** このルールは、その時点から任意の方向に無限に伸びる射線を描画し、その光線が交差する特定の図形のパス セグメントの数をカウントして、ポイントが塗りつぶし領域内がかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-106">**EvenOdd:** This rule determines whether a point is in the fill region by drawing a ray from that point to infinity in any direction and counting the number of path segments within the given shape that the ray crosses.</span></span> <span data-ttu-id="2ceed-107">この数値が偶数の場合は、ポイントは内側にあります。偶数の場合は、ポイントは外側にあります。</span><span class="sxs-lookup"><span data-stu-id="2ceed-107">If this number is odd, the point is inside; if even, the point is outside.</span></span>  
  
 <span data-ttu-id="2ceed-108">たとえば、次の XAML での一連の同心リング (ターゲット) から成る複合図形を作成します.、<xref:System.Windows.Media.GeometryGroup.FillRule%2A>設定<xref:System.Windows.Media.FillRule.EvenOdd>します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-108">For example, the XAML below creates a composite shape made up of a series of concentric rings (target) with a <xref:System.Windows.Media.GeometryGroup.FillRule%2A> set to <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 <span data-ttu-id="2ceed-109">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-109">The following illustration shows the shape created in the previous example.</span></span>  
  
 ![色を交互に一連の同心リングから成る円です。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-property.png)  
  
 <span data-ttu-id="2ceed-111">前の図では、中央と 3 番目のリングが塗りつぶされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2ceed-111">In the previous illustration, notice that the center and third ring are not filled.</span></span> <span data-ttu-id="2ceed-112">これは、これら 2 つのリングの任意の点から描画された射線が、偶数個のセグメントを通過するためです。</span><span class="sxs-lookup"><span data-stu-id="2ceed-112">This is because a ray drawn from any point within either of those two rings passes through an even number of segments.</span></span> <span data-ttu-id="2ceed-113">次の図を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2ceed-113">See the following illustration:</span></span>  
  
 ![円の中で描画 EvenOdd 光線を示す図。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-evenodd-rays.png)  
  
 <span data-ttu-id="2ceed-115">**0 以外の場合。** このルールは、その時点から任意の方向に無限に伸びる射線を描画し、図形のセグメントが光線と交差する場所を調べることによって、ポイントが、パスの塗りつぶし領域内がかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-115">**NonZero:** This rule determines whether a point is in the fill region of the path by drawing a ray from that point to infinity in any direction and then examining the places where a segment of the shape crosses the ray.</span></span> <span data-ttu-id="2ceed-116">0 からカウントを開始し、パス セグメントが左から右に射線と交わるたびに 1 を加算し、パス セグメントが右から左に射線と交わるたびに 1 を減算します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-116">Starting with a count of zero, add one each time a Segment crosses the ray from left to right and subtract one each time a path segment crosses the ray from right to left.</span></span> <span data-ttu-id="2ceed-117">交差のカウント後、結果が 0 の場合は、ポイントは、パスの外側にあります。</span><span class="sxs-lookup"><span data-stu-id="2ceed-117">After counting the crossings, if the result is zero then the point is outside the path.</span></span> <span data-ttu-id="2ceed-118">それ以外の場合は、内側にあります。</span><span class="sxs-lookup"><span data-stu-id="2ceed-118">Otherwise, it is inside.</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 <span data-ttu-id="2ceed-119">前の例の値を使用して<xref:System.Windows.Media.FillRule.Nonzero>の<xref:System.Windows.Media.GeometryGroup.FillRule%2A>結果として、次の図を示します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-119">Using the previous example, a value of <xref:System.Windows.Media.FillRule.Nonzero> for <xref:System.Windows.Media.GeometryGroup.FillRule%2A> gives the following illustration as a result:</span></span>  
  
 ![構成のシリーズ同心リングすべて同じ色で塗りつぶされた円です。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-nonzero.png)  
  
 <span data-ttu-id="2ceed-121">上の図からわかるように、すべてのリングが塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="2ceed-121">As you can see, all the rings are filled.</span></span> <span data-ttu-id="2ceed-122">これは、すべてのセグメントが同じ方向で、任意の点から描画された射線は 1 つ以上のセグメントと交わり、交差の合計が 0 にならないためです。</span><span class="sxs-lookup"><span data-stu-id="2ceed-122">This is because all the segments are running in the same direction and so a ray drawn from any point will cross one or more segments and the sum of the crossings will not equal zero.</span></span> <span data-ttu-id="2ceed-123">たとえば、次の図に赤の矢印はセグメントが描画される方向を表すし、白い矢印は、最も内側のリング内のポイントから任意の射線を表します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-123">For example, in the following illustration, the red arrows represent the direction the segments are drawn and the white arrow represents an arbitrary ray running from a point in the innermost ring.</span></span> <span data-ttu-id="2ceed-124">値 0 から開始し、セグメントは左から右に射線と交わるため、射線が交わるセグメントごとに値 1 が加算されます。</span><span class="sxs-lookup"><span data-stu-id="2ceed-124">Starting with a value of zero, for each segment that the ray crosses, a value of one is added because the segment crosses the ray from left to right.</span></span>  
  
 ![0 以外と等しい FillRule プロパティ値を示す図。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-value-equal-nonzero.png)  
  
 <span data-ttu-id="2ceed-126">動作をわかりやすく示すために<xref:System.Windows.Media.FillRule.Nonzero>規則セグメントがさまざまな方向で実行されているより複雑な図形が必要です。</span><span class="sxs-lookup"><span data-stu-id="2ceed-126">To better demonstrate the behavior of <xref:System.Windows.Media.FillRule.Nonzero> rule a more complex shape with segments running in different directions is required.</span></span> <span data-ttu-id="2ceed-127">次の XAML コードで作成する点を除いて前の例と類似した図形を作成、<xref:System.Windows.Media.PathGeometry>ではなく、<xref:System.Windows.Media.EllipseGeometry>同心円を完全に終了ではなく 4 つの同心の円弧を作成します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-127">The XAML code below creates a similar shape as the previous example except that it is created with a <xref:System.Windows.Media.PathGeometry> rather then a <xref:System.Windows.Media.EllipseGeometry> which creates four concentric arcs rather then fully closed concentric circles.</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 <span data-ttu-id="2ceed-128">前の例で作成した図を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2ceed-128">The following illustration shows the shape created in the previous example.</span></span>  
  
 ![3 番目の円弧が塗りつぶされていないと色を交互に一連の同心リングから成る円です。](./media/how-to-control-the-fill-of-a-composite-shape/pathgeometry-concentric-arcs.png)  
  
 <span data-ttu-id="2ceed-130">中央から 3 番目の円弧が塗りつぶされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2ceed-130">Notice that the third arc from the center is not filled.</span></span> <span data-ttu-id="2ceed-131">次の図は、これが理由を示しています。</span><span class="sxs-lookup"><span data-stu-id="2ceed-131">The following illustration shows why this is.</span></span> <span data-ttu-id="2ceed-132">この図で、赤い矢印はセグメントが描画されている方向を表しています。</span><span class="sxs-lookup"><span data-stu-id="2ceed-132">In the illustration, the red arrows represent the direction the segments are drawn.</span></span> <span data-ttu-id="2ceed-133">2 つの白い矢印は、"塗りつぶされていない" 領域内の点から外に向かって伸びる、2 本の任意の射線を表しています。</span><span class="sxs-lookup"><span data-stu-id="2ceed-133">The two white arrows represent two arbitrary rays that move out from a point in the "non-filled" region.</span></span> <span data-ttu-id="2ceed-134">この図からわかるように、指定された射線がパス内でセグメントと交わることによる値の合計は 0 です。</span><span class="sxs-lookup"><span data-stu-id="2ceed-134">As can be seen from the illustration, the sum of the values from a given ray crossing the segments in its path is zero.</span></span> <span data-ttu-id="2ceed-135">前に定義したように、合計が 0 となるのは、その点がジオメトリの一部でない (塗りつぶしに含まれない) ことを意味し、合計が 0 で*ない*場合 (負の値を含む) は、その点がジオメトリの一部であることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="2ceed-135">As defined above, a sum of zero means that the point is not part of the geometry (not part of the fill) while a sum that is *not* zero, including a negative value, is part of the geometry.</span></span>  
  
 ![任意の光線交差セグメントを示す図。](./media/how-to-control-the-fill-of-a-composite-shape/arbitrary-ray-cross-segment.png)  
  
 <span data-ttu-id="2ceed-137">**注:** 目的で<xref:System.Windows.Media.FillRule>、すべての図形が終了と見なされます。</span><span class="sxs-lookup"><span data-stu-id="2ceed-137">**Note:** For the purposes of <xref:System.Windows.Media.FillRule>, all shapes are considered closed.</span></span> <span data-ttu-id="2ceed-138">セグメントにすき間がある場合は、架空の線を描画して、そのすき間を閉じます。</span><span class="sxs-lookup"><span data-stu-id="2ceed-138">If there is a gap in a segment, draw an imaginary line to close it.</span></span> <span data-ttu-id="2ceed-139">上の例では、リングに小さなすき間があります。</span><span class="sxs-lookup"><span data-stu-id="2ceed-139">In the example above, there are small gaps in the rings.</span></span> <span data-ttu-id="2ceed-140">この場合、このすき間を通る射線は、別の方向に伸びる射線とは異なる結果を生じると思えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="2ceed-140">Given this, one might expect a ray that runs through the gap to give a different result then a ray running in another direction.</span></span> <span data-ttu-id="2ceed-141">このようなギャップと「架空のセグメント」のいずれかを拡大した図を次に示します (適用するために描画されるセグメント、 <xref:System.Windows.Media.FillRule>) そのすき間を閉じる。</span><span class="sxs-lookup"><span data-stu-id="2ceed-141">Below is an enlarged illustration of one of these gaps and the "imaginary segment" (segment that is drawn for purposes of applying the <xref:System.Windows.Media.FillRule>) that closes it.</span></span>  
  
 ![常に閉じている FillRule セグメントを示す図。](./media/how-to-control-the-fill-of-a-composite-shape/fillrule-closed-segments.png)  
  
## <a name="example"></a><span data-ttu-id="2ceed-143">例</span><span class="sxs-lookup"><span data-stu-id="2ceed-143">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ceed-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ceed-144">See also</span></span>

- [<span data-ttu-id="2ceed-145">複合図形を作成する</span><span class="sxs-lookup"><span data-stu-id="2ceed-145">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="2ceed-146">ジオメトリの概要</span><span class="sxs-lookup"><span data-stu-id="2ceed-146">Geometry Overview</span></span>](geometry-overview.md)
