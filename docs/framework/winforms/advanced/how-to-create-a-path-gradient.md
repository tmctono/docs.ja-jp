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
ms.openlocfilehash: a04465c31b160f97568ed88c434e7e3a5126ebb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975755"
---
# <a name="how-to-create-a-path-gradient"></a><span data-ttu-id="3c365-102">方法: パス グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="3c365-102">How to: Create a Path Gradient</span></span>
<span data-ttu-id="3c365-103"><xref:System.Drawing.Drawing2D.PathGradientBrush>クラスでは、徐々 に変化する色に図形を塗りつぶす方法をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3c365-103">The <xref:System.Drawing.Drawing2D.PathGradientBrush> class allows you to customize the way you fill a shape with gradually changing colors.</span></span> <span data-ttu-id="3c365-104">たとえば、パスの中央の 1 つの色とパスの境界に別の色を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3c365-104">For example, you can specify one color for the center of a path and another color for the boundary of a path.</span></span> <span data-ttu-id="3c365-105">各パスの境界に沿って複数ポイントの別の色を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c365-105">You can also specify separate colors for each of several points along the boundary of a path.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c365-106">GDI + でのパスには一連の直線と曲線によって管理される、<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3c365-106">In GDI+, a path is a sequence of lines and curves maintained by a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="3c365-107">GDI + のパスの詳細については、次を参照してください。 [GDI + でのグラフィックス パス](graphics-paths-in-gdi.md)と[描画パスの作成および](constructing-and-drawing-paths.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c365-107">For more information about GDI+ paths, see [Graphics Paths in GDI+](graphics-paths-in-gdi.md) and [Constructing and Drawing Paths](constructing-and-drawing-paths.md).</span></span>  

<span data-ttu-id="3c365-108">この記事の例では、コントロールから呼び出されるメソッド<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="3c365-108">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a><span data-ttu-id="3c365-109">パス グラデーションを使用して楕円の塗りつぶしを</span><span class="sxs-lookup"><span data-stu-id="3c365-109">To fill an ellipse with a path gradient</span></span>  
  
-   <span data-ttu-id="3c365-110">次の例では、パスのグラデーション ブラシを使用して楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="3c365-110">The following example fills an ellipse with a path gradient brush.</span></span> <span data-ttu-id="3c365-111">中心の色を青に設定し、境界の色を水色に設定します。</span><span class="sxs-lookup"><span data-stu-id="3c365-111">The center color is set to blue and the boundary color is set to aqua.</span></span> <span data-ttu-id="3c365-112">次の図は、塗りつぶされた楕円を示します。</span><span class="sxs-lookup"><span data-stu-id="3c365-112">The following illustration shows the filled ellipse.</span></span>  
  
     ![グラデーション パスでは、楕円を塗りつぶします。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     <span data-ttu-id="3c365-114">既定では、パスのグラデーション ブラシは、パスの境界の外側には拡張されません。</span><span class="sxs-lookup"><span data-stu-id="3c365-114">By default, a path gradient brush does not extend outside the boundary of the path.</span></span> <span data-ttu-id="3c365-115">パスの境界を越える図形を塗りつぶすパス グラデーション ブラシを使用する場合、パスの外側の画面の領域は埋められません。</span><span class="sxs-lookup"><span data-stu-id="3c365-115">If you use the path gradient brush to fill a figure that extends beyond the boundary of the path, the area of the screen outside the path will not be filled.</span></span>  
  
     <span data-ttu-id="3c365-116">変更する場合、次の図は、<xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType>で次のコードを呼び出す`e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span><span class="sxs-lookup"><span data-stu-id="3c365-116">The following illustration shows what happens if you change the <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> call in the following code to `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:</span></span>  
  
     ![グラデーション パス、パスの境界を超えて拡張します。](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     <span data-ttu-id="3c365-118">上記のコード例が、Windows フォームで使用するために設計されており、必要があります、 <xref:System.Windows.Forms.PaintEventArgs> e で、パラメーターの<xref:System.Windows.Forms.PaintEventHandler>します。</span><span class="sxs-lookup"><span data-stu-id="3c365-118">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs> e, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
### <a name="to-specify-points-on-the-boundary"></a><span data-ttu-id="3c365-119">境界でポイントを指定するには</span><span class="sxs-lookup"><span data-stu-id="3c365-119">To specify points on the boundary</span></span>  
  
-   <span data-ttu-id="3c365-120">次の例では、星型のパスからのパスのグラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c365-120">The following example constructs a path gradient brush from a star-shaped path.</span></span> <span data-ttu-id="3c365-121">コードのセット、<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A>プロパティで、赤色の星の重心で色を設定します。</span><span class="sxs-lookup"><span data-stu-id="3c365-121">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> property, which sets the color at the centroid of the star to red.</span></span> <span data-ttu-id="3c365-122">コード セットし、<xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A>さまざまな色を指定するプロパティ (に格納されている、`colors`配列) の個々 のポイントで、`points`配列。</span><span class="sxs-lookup"><span data-stu-id="3c365-122">Then the code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> property to specify various colors (stored in the `colors` array) at the individual points in the `points` array.</span></span> <span data-ttu-id="3c365-123">最後のコード ステートメントは、パスのグラデーション ブラシで星型のパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3c365-123">The final code statement fills the star-shaped path with the path gradient brush.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   <span data-ttu-id="3c365-124">次の例では、描画せずパス グラデーションを<xref:System.Drawing.Drawing2D.GraphicsPath>コード内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3c365-124">The following example draws a path gradient without a <xref:System.Drawing.Drawing2D.GraphicsPath> object in the code.</span></span> <span data-ttu-id="3c365-125">特定<xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A>コンス トラクターの例では、点の配列を受け取りますは必要ありません、<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3c365-125">The particular <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> constructor in the example receives an array of points but does not require a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="3c365-126">また、<xref:System.Drawing.Drawing2D.PathGradientBrush>パスではなく、四角形の塗りつぶしに使用します。</span><span class="sxs-lookup"><span data-stu-id="3c365-126">Also, note that the <xref:System.Drawing.Drawing2D.PathGradientBrush> is used to fill a rectangle, not a path.</span></span> <span data-ttu-id="3c365-127">四角形は四角形の一部は、ブラシによって描画されませんので、ブラシを定義するために使用する閉じたパスを超えています。</span><span class="sxs-lookup"><span data-stu-id="3c365-127">The rectangle is larger than the closed path used to define the brush, so some of the rectangle is not painted by the brush.</span></span> <span data-ttu-id="3c365-128">次の図は、(点線) 四角形とパスのグラデーション ブラシで塗りつぶされた四角形の部分を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c365-128">The following illustration shows the rectangle (dotted line) and the portion of the rectangle painted by the path gradient brush:</span></span> 
  
     ![パス グラデーション ブラシで描画されたグラデーション部分です。](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a><span data-ttu-id="3c365-130">パス グラデーションをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="3c365-130">To customize a path gradient</span></span>  
  
-   <span data-ttu-id="3c365-131">パス グラデーション ブラシをカスタマイズする方法の 1 つを設定するのにはその<xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="3c365-131">One way to customize a path gradient brush is to set its <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> property.</span></span> <span data-ttu-id="3c365-132">フォーカスのスケールでは、メインのパスの内側にある内部のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3c365-132">The focus scales specify an inner path that lies inside the main path.</span></span> <span data-ttu-id="3c365-133">中心点だけでなく、その内部のパス内で、すべての場所で中心の色が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c365-133">The center color is displayed everywhere inside that inner path rather than only at the center point.</span></span>  
  
     <span data-ttu-id="3c365-134">次の例では、楕円のパスに基づくパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c365-134">The following example creates a path gradient brush based on an elliptical path.</span></span> <span data-ttu-id="3c365-135">コードは、境界の色を青に設定を水色に中心の色を設定し、パス グラデーション ブラシを使用して、楕円のモーション パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3c365-135">The code sets the boundary color to blue, sets the center color to aqua, and then uses the path gradient brush to fill the elliptical path.</span></span>  
  
     <span data-ttu-id="3c365-136">次に、コードは、パスのグラデーション ブラシのフォーカスのスケールを設定します。</span><span class="sxs-lookup"><span data-stu-id="3c365-136">Next, the code sets the focus scales of the path gradient brush.</span></span> <span data-ttu-id="3c365-137">X フォーカス スケールは、0.3 に設定され、y のフォーカスのスケールが 0.8 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3c365-137">The x focus scale is set to 0.3, and the y focus scale is set to 0.8.</span></span> <span data-ttu-id="3c365-138">コードの呼び出し、<xref:System.Drawing.Graphics.TranslateTransform%2A>のメソッド、<xref:System.Drawing.Graphics>オブジェクトように後続の呼び出し<xref:System.Drawing.Graphics.FillPath%2A>最初の楕円の右側に配置される楕円を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="3c365-138">The code calls the <xref:System.Drawing.Graphics.TranslateTransform%2A> method of a <xref:System.Drawing.Graphics> object so that the subsequent call to <xref:System.Drawing.Graphics.FillPath%2A> fills an ellipse that sits to the right of the first ellipse.</span></span>  
  
     <span data-ttu-id="3c365-139">フォーカスのスケールの効果を表示するには、メインの楕円の中心を共有する小さな楕円を想像してください。</span><span class="sxs-lookup"><span data-stu-id="3c365-139">To see the effect of the focus scales, imagine a small ellipse that shares its center with the main ellipse.</span></span> <span data-ttu-id="3c365-140">小規模 (内部) 楕円は、メインの楕円の 0.3 の係数を使用して、垂直方向に 0.8 の係数 (の中心) 水平方向に拡張です。</span><span class="sxs-lookup"><span data-stu-id="3c365-140">The small (inner) ellipse is the main ellipse scaled (about its center) horizontally by a factor of 0.3 and vertically by a factor of 0.8.</span></span> <span data-ttu-id="3c365-141">内側の楕円の境界線の外側の楕円の境界から移動すると、色が徐々 に変化青からを水色にします。</span><span class="sxs-lookup"><span data-stu-id="3c365-141">As you move from the boundary of the outer ellipse to the boundary of the inner ellipse, the color changes gradually from blue to aqua.</span></span> <span data-ttu-id="3c365-142">内部の楕円の境界を水色、色は、共有のセンターに移動します。</span><span class="sxs-lookup"><span data-stu-id="3c365-142">As you move from the boundary of the inner ellipse to the shared center, the color remains aqua.</span></span>  
  
     <span data-ttu-id="3c365-143">以下のコードの出力を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="3c365-143">The following illustration shows the output of the following code.</span></span> <span data-ttu-id="3c365-144">左側の楕円は、中心点にのみ aqua です。</span><span class="sxs-lookup"><span data-stu-id="3c365-144">The ellipse on the left is aqua only at the center point.</span></span> <span data-ttu-id="3c365-145">右側の楕円は、内部のパス内ですべての場所で aqua です。</span><span class="sxs-lookup"><span data-stu-id="3c365-145">The ellipse on the right is aqua everywhere inside the inner path.</span></span>  
  
 ![フォーカスの規模のグラデーション効果](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a><span data-ttu-id="3c365-147">補間でカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="3c365-147">To customize with interpolation</span></span>  
  
-   <span data-ttu-id="3c365-148">パス グラデーション ブラシをカスタマイズする別の方法では、補間の色の配列と、補間の位置の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="3c365-148">Another way to customize a path gradient brush is to specify an array of interpolation colors and an array of interpolation positions.</span></span>  
  
     <span data-ttu-id="3c365-149">次の例では、三角形に基づくパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c365-149">The following example creates a path gradient brush based on a triangle.</span></span> <span data-ttu-id="3c365-150">コードのセット、<xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A>補間の色 (濃い緑、aqua、青) の配列と、補間の位置 (0, 0.25, 1) の配列を指定するパスのグラデーション ブラシのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3c365-150">The code sets the <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> property of the path gradient brush to specify an array of interpolation colors (dark green, aqua, blue) and an array of interpolation positions (0, 0.25, 1).</span></span> <span data-ttu-id="3c365-151">中心点にある三角形の境界から移動すると、色が徐々 に変化濃い緑からを水色に、青に aqua から。</span><span class="sxs-lookup"><span data-stu-id="3c365-151">As you move from the boundary of the triangle to the center point, the color changes gradually from dark green to aqua and then from aqua to blue.</span></span> <span data-ttu-id="3c365-152">濃い緑から青からの距離の 25% でを水色に濃い緑から変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="3c365-152">The change from dark green to aqua happens in 25 percent of the distance from dark green to blue.</span></span>  
  
     <span data-ttu-id="3c365-153">次の図は、カスタム パスのグラデーション ブラシで塗りつぶした三角形を示します。</span><span class="sxs-lookup"><span data-stu-id="3c365-153">The following illustration shows the triangle filled with the custom path gradient brush.</span></span>  
  
     ![三角形は、カスタム パス グラデーション ブラシで塗りつぶされます。](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a><span data-ttu-id="3c365-155">中心点を設定するには</span><span class="sxs-lookup"><span data-stu-id="3c365-155">To set the center point</span></span>  
  
-   <span data-ttu-id="3c365-156">既定では、パスのグラデーション ブラシの中心点は、ブラシを作成するために使用するパスの重心では。</span><span class="sxs-lookup"><span data-stu-id="3c365-156">By default, the center point of a path gradient brush is at the centroid of the path used to construct the brush.</span></span> <span data-ttu-id="3c365-157">中心点の位置を設定して変更することができます、<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>のプロパティ、<xref:System.Drawing.Drawing2D.PathGradientBrush>クラス。</span><span class="sxs-lookup"><span data-stu-id="3c365-157">You can change the location of the center point by setting the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property of the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
     <span data-ttu-id="3c365-158">次の例では、楕円に基づくパス グラデーション ブラシを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c365-158">The following example creates a path gradient brush based on an ellipse.</span></span> <span data-ttu-id="3c365-159">楕円の中心 (70、35) に設定されているパスのグラデーション ブラシの中心点が (120, 40)。</span><span class="sxs-lookup"><span data-stu-id="3c365-159">The center of the ellipse is at (70, 35), but the center point of the path gradient brush is set to (120, 40).</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     <span data-ttu-id="3c365-160">次の図は、塗りつぶされた楕円とパスのグラデーション ブラシの中心点を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c365-160">The following illustration shows the filled ellipse and the center point of the path gradient brush:</span></span>  
  
     ![塗りつぶされた楕円と center ポイントとグラデーションのパス。](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
-   <span data-ttu-id="3c365-162">パス グラデーション ブラシの中心点は、ブラシを作成するために使用されたパスの外部の場所に設定できます。</span><span class="sxs-lookup"><span data-stu-id="3c365-162">You can set the center point of a path gradient brush to a location outside the path that was used to construct the brush.</span></span> <span data-ttu-id="3c365-163">次の例では、置換を設定する呼び出し、<xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A>上記のコードでのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="3c365-163">The following example replaces the call to set the <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> property in the preceding code.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     <span data-ttu-id="3c365-164">次の図は、この変更により、出力を示しています。</span><span class="sxs-lookup"><span data-stu-id="3c365-164">The following illustration shows the output with this change:</span></span>  
  
     ![パスの外側の中心点でグラデーションのパス。](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     <span data-ttu-id="3c365-166">前の図では、楕円の右端にある点のない純粋な青 (ただし、これらはよく似ています)。</span><span class="sxs-lookup"><span data-stu-id="3c365-166">In the preceding illustration, the points at the far right of the ellipse are not pure blue (although they are very close).</span></span> <span data-ttu-id="3c365-167">グラデーションの色は、塗りつぶし色が純粋な青 (0, 0, 255) をすると、点 (145, 35) に達するかのように配置されます。</span><span class="sxs-lookup"><span data-stu-id="3c365-167">The colors in the gradient are positioned as if the fill reached the point (145, 35) where the color would be pure blue (0, 0, 255).</span></span> <span data-ttu-id="3c365-168">塗りつぶしに決して到達しませんが、(145, 35) ため、そのパス内でのみパス グラデーション ブラシを描画します。</span><span class="sxs-lookup"><span data-stu-id="3c365-168">But the fill never reaches (145, 35) because a path gradient brush paints only inside its path.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c365-169">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3c365-169">Compiling the Code</span></span>  
 <span data-ttu-id="3c365-170">上記の例は、Windows フォームで使用するために設計されていて、必要な<xref:System.Windows.Forms.PaintEventArgs>`e`はのパラメーター、<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="3c365-170">The preceding examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c365-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="3c365-171">See also</span></span>

- [<span data-ttu-id="3c365-172">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="3c365-172">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
