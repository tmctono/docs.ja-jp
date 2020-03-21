---
title: '方法 : パス グラデーションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182642"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="f5ad5-102">方法 : パス グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="f5ad5-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="f5ad5-103">この<xref:System.Drawing.Drawing2D.PathGradientBrush>クラスでは、徐々に変化する色で図形を塗りつぶす方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="f5ad5-104">たとえば、パスの中心に 1 色、パスの境界に別の色を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="f5ad5-105">パスの境界に沿った複数の点ごとに、個別の色を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5ad5-106">GDI+ では、パスはオブジェクトによって維持される一連の直線と曲線<xref:System.Drawing.Drawing2D.GraphicsPath>です。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="f5ad5-107">GDI+ パスの詳細については[、「GDI+ のグラフィックス パス](graphics-paths-in-gdi.md)」および「[パスの作成と描画](constructing-and-drawing-paths.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="f5ad5-108">この記事の例は、コントロールのイベント ハンドラーから呼び出<xref:System.Windows.Forms.Control.Paint>されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="f5ad5-109">楕円をパス グラデーションで塗りつぶすには</span><span class="sxs-lookup"><span data-stu-id="f5ad5-109">To fill an ellipse with a path gradient</span></span>  
  
- <span data-ttu-id="f5ad5-110">次の例では、楕円をパス グラデーション ブラシで塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="f5ad5-111">中心の色は青に設定され、境界カラーは水色に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="f5ad5-112">塗りつぶされた楕円を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![グラデーションパスは楕円を塗りつぶします。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="f5ad5-114">デフォルトでは、パスグラデーションブラシはパスの境界の外側に伸びません。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="f5ad5-115">パス グラデーション ブラシを使用して、パスの境界を越えた図形を塗りつぶすと、パスの外側にある画面の領域は塗りつぶされません。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="f5ad5-116">次の図は、次のコードの呼<xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType>び出しをに変更`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`した場合の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![パスの境界を越えて拡張されたグラデーション パス。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="f5ad5-118">上記のコード例は Windows フォームで使用するように設計されており<xref:System.Windows.Forms.PaintEventArgs>、e を必要とします。 <xref:System.Windows.Forms.PaintEventHandler></span><span class="sxs-lookup"><span data-stu-id="f5ad5-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="f5ad5-119">境界上の点を指定するには</span><span class="sxs-lookup"><span data-stu-id="f5ad5-119">To specify points on the boundary</span></span>  
  
- <span data-ttu-id="f5ad5-120">次の例では、星型のパスからパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="f5ad5-121">このコードでは、<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>星の中心の色を赤に設定するプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="f5ad5-122">次に、配列内<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>の個々のポイントでさまざまな色 (`colors`配列に格納されている) を指定`points`するプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="f5ad5-123">最後のコード ステートメントは、星形のパスをパス グラデーション ブラシで塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- <span data-ttu-id="f5ad5-124">コード内にオブジェクトを含まないパス<xref:System.Drawing.Drawing2D.GraphicsPath>グラデーションを描画する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="f5ad5-125">この例<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>の特定のコンストラクターは、ポイントの配列を受け取りますが<xref:System.Drawing.Drawing2D.GraphicsPath>、オブジェクトは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="f5ad5-126">また、 は<xref:System.Drawing.Drawing2D.PathGradientBrush>パスではなく四角形を塗りつぶすために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="f5ad5-127">この四角形はブラシの定義に使用した閉じたパスよりも大きいので、一部の矩形はブラシで描画されません。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="f5ad5-128">次の図は、四角形 (点線) と、パス グラデーション ブラシで描画された四角形の部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span>
  
     ![パスグラデーションブラシで塗りつぶされたグラデーション部分。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="f5ad5-130">パスグラデーションをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f5ad5-130">To customize a path gradient</span></span>  
  
- <span data-ttu-id="f5ad5-131">パス グラデーション ブラシをカスタマイズする方法の 1<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>つは、そのプロパティを設定することです。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="f5ad5-132">フォーカススケールは、メインパスの内側にある内側のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="f5ad5-133">中心点だけでなく、その内側のパス内のどこにでも中心の色が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="f5ad5-134">次の例では、楕円パスに基づいてパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="f5ad5-135">このコードでは、境界の色を青に設定し、中心カラーを水色に設定し、次にパス グラデーション ブラシを使用して楕円パスを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="f5ad5-136">次に、パス グラデーション ブラシのフォーカス スケールを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="f5ad5-137">x フォーカススケールは 0.3 に設定され、y フォーカススケールは 0.8 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="f5ad5-138">このコードはオブジェクト<xref:System.Drawing.Graphics.TranslateTransform%2A>のメソッドを<xref:System.Drawing.Graphics>呼び出して、後続の<xref:System.Drawing.Graphics.FillPath%2A>呼び出しで最初の楕円の右側にある楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="f5ad5-139">フォーカススケールの効果を確認するには、中心をメインの楕円と共有する小さな楕円を想像します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="f5ad5-140">小さな楕円は、中心を中心にして、0.3 倍、垂直方向に 0.8 倍の倍率でスケーリングされた主な楕円です。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="f5ad5-141">外側の楕円の境界から内側の楕円の境界に移動すると、色が青から水色に徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="f5ad5-142">内側の楕円の境界から共有の中心に移動しても、色はアクアのままです。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="f5ad5-143">以下のコードの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="f5ad5-144">左側の楕円は、中心点でのみ水上です。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="f5ad5-145">右側の楕円は、内側のパスの内側の至る所にアクアです。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![フォーカススケールのグラデーション効果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="f5ad5-147">補間を使用してカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f5ad5-147">To customize with interpolation</span></span>  
  
- <span data-ttu-id="f5ad5-148">パス グラデーション ブラシをカスタマイズするもう 1 つの方法は、補間色の配列と補間位置の配列を指定することです。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="f5ad5-149">次の例では、三角形に基づいてパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="f5ad5-150">このコードでは、<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>パス グラデーション ブラシのプロパティを設定して、補間色 (濃い緑、アクア、青) の配列と補間位置 (0, 0.25, 1) の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="f5ad5-151">三角形の境界から中心点に移動すると、色は濃い緑色から水色に、次に水色から青に徐々に変化します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="f5ad5-152">濃い緑からアクアへの変化は、濃い緑から青までの距離の25%で起こります。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="f5ad5-153">次の図は、カスタム パス グラデーション ブラシで塗りつぶされた三角形を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![カスタム パス グラデーション ブラシで塗りつぶされた三角形。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="f5ad5-155">中心点を設定するには</span><span class="sxs-lookup"><span data-stu-id="f5ad5-155">To set the center point</span></span>  
  
- <span data-ttu-id="f5ad5-156">デフォルトでは、パスグラデーションブラシの中心点は、ブラシの構築に使用されるパスの重心にあります。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="f5ad5-157">中心点の位置は、クラスのプロパティを<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>設定することによって変更できます。 <xref:System.Drawing.Drawing2D.PathGradientBrush></span><span class="sxs-lookup"><span data-stu-id="f5ad5-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="f5ad5-158">次の例では、楕円に基づいてパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="f5ad5-159">楕円の中心は (70, 35) ですが、パスグラデーションブラシの中心点は (120, 40) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="f5ad5-160">次の図は、塗りつぶされた楕円とパス グラデーション ブラシの中心点を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![塗りつぶされた楕円と中心点を持つグラデーションパス。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- <span data-ttu-id="f5ad5-162">パス グラデーション ブラシの中心点を、ブラシの構築に使用したパスの外側の位置に設定できます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="f5ad5-163">次の例では、上記のコードで<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>プロパティを設定する呼び出しを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="f5ad5-164">次の図は、この変更の出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-164">The following illustration shows the output with this change:</span></span>  
  
     ![パスの外側に中心点があるグラデーションパス。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="f5ad5-166">上の図では、楕円の右端の点は純粋な青ではありません (ただし、非常に近い点です)。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="f5ad5-167">グラデーションの色は、塗りつぶしが純粋な青 (0, 0, 255) になる点 (145, 35) に達したかのように配置されます。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="f5ad5-168">しかし、パスグラデーションブラシはパスの内側にのみ描画されるため、塗りつぶしが決して (145, 35) に達することはありません。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5ad5-169">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="f5ad5-169">Compiling the Code</span></span>  
 <span data-ttu-id="f5ad5-170">上記の例は Windows フォームで使用するように設計されており、<xref:System.Windows.Forms.PaintEventArgs>`e`<xref:System.Windows.Forms.Control.Paint>イベント ハンドラーのパラメーターである が必要です。</span><span class="sxs-lookup"><span data-stu-id="f5ad5-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ad5-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5ad5-171">See also</span></span>

- [<span data-ttu-id="f5ad5-172">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="f5ad5-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
