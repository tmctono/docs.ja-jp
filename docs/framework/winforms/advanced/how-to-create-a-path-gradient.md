---
title: '方法: パス グラデーションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: 8399a56fca87704e10456a4cf8109d7c80d4db45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964403"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="8ea37-102">方法: パス グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="8ea37-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="8ea37-103">クラス<xref:System.Drawing.Drawing2D.PathGradientBrush>を使用すると、徐々に変化する色で図形を塗りつぶす方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="8ea37-104">たとえば、パスの中心に色を1つ、パスの境界に別の色を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="8ea37-105">パスの境界に沿って複数のポイントごとに個別の色を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ea37-106">Gdi + では、パスは、 <xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトによって維持される直線と曲線のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="8ea37-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="8ea37-107">GDI + パスの詳細については、「 [GDI + でのグラフィックスのパス](graphics-paths-in-gdi.md)」と「[パスの構築と描画](constructing-and-drawing-paths.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea37-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="8ea37-108">この記事の例は、コントロールの<xref:System.Windows.Forms.Control.Paint>イベントハンドラーから呼び出されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="8ea37-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="8ea37-109">楕円にパスグラデーションを入力するには</span><span class="sxs-lookup"><span data-stu-id="8ea37-109">To fill an ellipse with a path gradient</span></span>  
  
- <span data-ttu-id="8ea37-110">次の例では、楕円にパスグラデーションブラシを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="8ea37-111">中央の色は青に、境界の色は水色に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="8ea37-112">次の図は、塗りつぶされた楕円を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![グラデーションパスは楕円を塗りつぶします。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="8ea37-114">既定では、パスグラデーションブラシはパスの境界の外側では拡張されません。</span><span class="sxs-lookup"><span data-stu-id="8ea37-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="8ea37-115">パスグラデーションブラシを使用して、パスの境界を越える図形を塗りつぶす場合、パスの外側にある画面の領域は塗りつぶされません。</span><span class="sxs-lookup"><span data-stu-id="8ea37-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="8ea37-116">次の図は、次のコードの<xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType>呼び出しをに変更した場合の動作を`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![パスの境界を超えて拡張されたグラデーションパス。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="8ea37-118">上記のコード例は、Windows フォームで使用するように設計され<xref:System.Windows.Forms.PaintEventArgs>ています。これは、 <xref:System.Windows.Forms.PaintEventHandler>のパラメーターである e を必要とします。</span><span class="sxs-lookup"><span data-stu-id="8ea37-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="8ea37-119">境界上にポイントを指定するには</span><span class="sxs-lookup"><span data-stu-id="8ea37-119">To specify points on the boundary</span></span>  
  
- <span data-ttu-id="8ea37-120">次の例では、星形のパスからパスグラデーションブラシを構築します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="8ea37-121">このコードは、 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>星の重心の色を赤に設定するプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="8ea37-122">次に、コードは<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>プロパティを設定して、 `points`配列内の`colors`個々の点に (配列に格納されている) さまざまな色を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="8ea37-123">最後のコードステートメントは、星形のパスをパスグラデーションブラシで塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="8ea37-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- <span data-ttu-id="8ea37-124">次の例では、コードにオブジェクト<xref:System.Drawing.Drawing2D.GraphicsPath>を含まないパスグラデーションを描画します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="8ea37-125">この例<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>の特定のコンストラクターは、ポイントの配列を受け取りますが、 <xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8ea37-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="8ea37-126">また、 <xref:System.Drawing.Drawing2D.PathGradientBrush>はパスではなく四角形を塗りつぶすために使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ea37-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="8ea37-127">四角形は、ブラシを定義するために使用される閉じたパスよりも大きいため、四角形の一部がブラシによって描画されません。</span><span class="sxs-lookup"><span data-stu-id="8ea37-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="8ea37-128">次の図は、四角形 (点線) と、パスグラデーションブラシによって描画される四角形の部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span> 
  
     ![パスグラデーションブラシで塗りつぶされたグラデーション部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="8ea37-130">パスのグラデーションをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="8ea37-130">To customize a path gradient</span></span>  
  
- <span data-ttu-id="8ea37-131">パスグラデーションブラシをカスタマイズする方法の1つは、 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>そのプロパティを設定することです。</span><span class="sxs-lookup"><span data-stu-id="8ea37-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="8ea37-132">フォーカススケールは、メインパス内にある内部パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="8ea37-133">中心の色は、中心点だけではなく、内部パス内のすべての場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="8ea37-134">次の例では、楕円のパスに基づいてパスグラデーションブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="8ea37-135">このコードでは、境界の色を青に設定し、中心の色を水色に設定して、パスグラデーションブラシを使用して楕円のパスを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="8ea37-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="8ea37-136">次に、コードはパスグラデーションブラシのフォーカススケールを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="8ea37-137">X フォーカススケールが0.3 に設定され、y フォーカススケールが0.8 に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="8ea37-138">このコードは、 <xref:System.Drawing.Graphics.TranslateTransform%2A> <xref:System.Drawing.Graphics>オブジェクトのメソッドを呼び出します。これにより<xref:System.Drawing.Graphics.FillPath%2A> 、への後続の呼び出しによって、最初の楕円の右側にある楕円が塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="8ea37-139">フォーカススケールの効果を確認するには、中心をメイン楕円と共有する小さな楕円を想像してください。</span><span class="sxs-lookup"><span data-stu-id="8ea37-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="8ea37-140">小さい (内側の) 楕円は、メインの楕円 (中心の中心) を0.3 の係数で水平方向に0.8 の係数で水平方向にスケーリングしたものです。</span><span class="sxs-lookup"><span data-stu-id="8ea37-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="8ea37-141">外側の楕円の境界から内側の楕円の境界に移動すると、色が青から水色に徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="8ea37-142">内側の楕円の境界から共有センターに移動すると、色は水色のままになります。</span><span class="sxs-lookup"><span data-stu-id="8ea37-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="8ea37-143">以下のコードの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="8ea37-144">左側の楕円は、中心点でのみ水色です。</span><span class="sxs-lookup"><span data-stu-id="8ea37-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="8ea37-145">右側の楕円は、内側のパスのどこでも水色です。</span><span class="sxs-lookup"><span data-stu-id="8ea37-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![フォーカススケールのグラデーション効果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="8ea37-147">補間を使用してカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="8ea37-147">To customize with interpolation</span></span>  
  
- <span data-ttu-id="8ea37-148">パスグラデーションブラシをカスタマイズするもう1つの方法は、補間の色の配列と補間の位置の配列を指定することです。</span><span class="sxs-lookup"><span data-stu-id="8ea37-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="8ea37-149">次の例では、三角形に基づくパスグラデーションブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="8ea37-150">このコードは、 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>パスグラデーションブラシのプロパティを設定して、補間の色 (濃い緑、水色、青) と補間位置 (0、0.25、1) の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="8ea37-151">三角形の境界から中心点に移動すると、色が濃い緑から水色に徐々に変化し、次に水色から青色に変わります。</span><span class="sxs-lookup"><span data-stu-id="8ea37-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="8ea37-152">濃い緑から水色への変更は、濃い緑から青への距離の 25% で行われます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="8ea37-153">次の図は、カスタムパスグラデーションブラシで塗りつぶされた三角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![カスタムパスグラデーションブラシで塗りつぶされた三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="8ea37-155">中心点を設定するには</span><span class="sxs-lookup"><span data-stu-id="8ea37-155">To set the center point</span></span>  
  
- <span data-ttu-id="8ea37-156">既定では、パスグラデーションブラシの中心点は、ブラシの構築に使用されるパスの重心にあります。</span><span class="sxs-lookup"><span data-stu-id="8ea37-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="8ea37-157">中心点の位置を変更するには、 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> <xref:System.Drawing.Drawing2D.PathGradientBrush>クラスのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="8ea37-158">次の例では、楕円に基づくパスグラデーションブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="8ea37-159">楕円の中心は (70, 35) ですが、パスグラデーションブラシの中心点は (120, 40) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="8ea37-160">次の図は、塗りつぶされた楕円とパスグラデーションブラシの中心点を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![塗りつぶされた楕円と中心点を含むグラデーションパス。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- <span data-ttu-id="8ea37-162">パスグラデーションブラシの中心点を、ブラシの作成に使用されたパスの外側の位置に設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ea37-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="8ea37-163">次の例では、呼び出しを置き換え<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>て、前のコードでプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea37-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="8ea37-164">次の図は、この変更による出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea37-164">The following illustration shows the output with this change:</span></span>  
  
     ![パスの外側の中心点を持つグラデーションパス。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="8ea37-166">前の図では、楕円の右端にある点は純粋な青ではありません (ただし、非常に閉じています)。</span><span class="sxs-lookup"><span data-stu-id="8ea37-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="8ea37-167">グラデーションの色は、塗りつぶしがポイント (145, 35) に達した場合と同じように配置されます。この場合、色は純粋な青 (0, 0, 255) になります。</span><span class="sxs-lookup"><span data-stu-id="8ea37-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="8ea37-168">ただし、パスグラデーションブラシはパス内でのみ描画されるため、塗りつぶしは (145, 35) に到達しません。</span><span class="sxs-lookup"><span data-stu-id="8ea37-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ea37-169">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8ea37-169">Compiling the Code</span></span>  
 <span data-ttu-id="8ea37-170">前の例は、Windows フォームで使用するように設計さ<xref:System.Windows.Forms.PaintEventArgs>れており、 <xref:System.Windows.Forms.Control.Paint>イベントハンドラーのパラメーターであるを必要`e`とします。</span><span class="sxs-lookup"><span data-stu-id="8ea37-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea37-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ea37-171">See also</span></span>

- [<span data-ttu-id="8ea37-172">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="8ea37-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
