---
title: '方法: 線形グラデーションを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: b836659821b54698b675d48acd4e46466001d654
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977276"
---
# <a name="how-to-create-a-linear-gradient"></a><span data-ttu-id="008f2-102">方法: 線形グラデーションを作成する</span><span class="sxs-lookup"><span data-stu-id="008f2-102">How to: Create a Linear Gradient</span></span>
<span data-ttu-id="008f2-103">GDI + 水平、垂直方向、および対角線方向の線形グラデーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="008f2-103">GDI+ provides horizontal, vertical, and diagonal linear gradients.</span></span> <span data-ttu-id="008f2-104">既定では、線形グラデーションの色を均一に変更します。</span><span class="sxs-lookup"><span data-stu-id="008f2-104">By default, the color in a linear gradient changes uniformly.</span></span> <span data-ttu-id="008f2-105">ただし、色が一様でない方法で変更されるように、線形グラデーションをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="008f2-105">However, you can customize a linear gradient so that the color changes in a non-uniform fashion.</span></span>  

> [!NOTE]
> <span data-ttu-id="008f2-106">この記事の例では、コントロールから呼び出されるメソッド<xref:System.Windows.Forms.Control.Paint>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="008f2-106">The examples in this article are methods that are called from a control's <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  

<span data-ttu-id="008f2-107">次の例では、線、楕円、および水平方向の線状グラデーション ブラシを四角形を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="008f2-107">The following example fills a line, an ellipse, and a rectangle with a horizontal linear gradient brush.</span></span>  
  
<span data-ttu-id="008f2-108"><xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>コンス トラクターが 4 つの引数を受け取ります。 2 つのポイントと 2 つの色。</span><span class="sxs-lookup"><span data-stu-id="008f2-108">The <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor receives four arguments: two points and two colors.</span></span> <span data-ttu-id="008f2-109">(0, 10) は、最初のポイントは最初の色 (赤) に関連付けられていると、2 番目の点 (200, 10) が 2 番目の色 (青) に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="008f2-109">The first point (0, 10) is associated with the first color (red), and the second point (200, 10) is associated with the second color (blue).</span></span> <span data-ttu-id="008f2-110">想像どおりから描画される直線 (0, 10) に (200, 10) が赤から青に徐々 に変化します。</span><span class="sxs-lookup"><span data-stu-id="008f2-110">As you would expect, the line drawn from (0, 10) to (200, 10) changes gradually from red to blue.</span></span>  
  
 <span data-ttu-id="008f2-111">点 (0, 10) と (200, 10) で 10 件が重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="008f2-111">The 10s in the points (0, 10) and (200, 10) are not important.</span></span> <span data-ttu-id="008f2-112">2 つのポイントが同じ 2 つ目の座標にあることが重要なは、それらを結ぶ線が水平方向。</span><span class="sxs-lookup"><span data-stu-id="008f2-112">What is important is that the two points have the same second coordinate — the line connecting them is horizontal.</span></span> <span data-ttu-id="008f2-113">楕円と四角形変更も徐々 に赤から青の水平方向の座標が 0 から 200 にようにできます。</span><span class="sxs-lookup"><span data-stu-id="008f2-113">The ellipse and the rectangle also change gradually from red to blue as the horizontal coordinate goes from 0 to 200.</span></span>  
  
 <span data-ttu-id="008f2-114">次の図は、線、楕円、四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="008f2-114">The following illustration shows the line, the ellipse, and the rectangle.</span></span> <span data-ttu-id="008f2-115">色のグラデーション繰り返される自体の水平方向座標が 200 を超えるとに注意してください。</span><span class="sxs-lookup"><span data-stu-id="008f2-115">Note that the color gradient repeats itself as the horizontal coordinate increases beyond 200.</span></span>  
  
 <span data-ttu-id="008f2-116">![線形グラデーション](./media/cslineargradient1.png "cslineargradient1")</span><span class="sxs-lookup"><span data-stu-id="008f2-116">![Linear Gradient](./media/cslineargradient1.png "cslineargradient1")</span></span>  
  
### <a name="to-use-horizontal-linear-gradients"></a><span data-ttu-id="008f2-117">水平方向の線形グラデーションを使用するには</span><span class="sxs-lookup"><span data-stu-id="008f2-117">To use horizontal linear gradients</span></span>  
  
-   <span data-ttu-id="008f2-118">3 番目と 4 番目の引数として、それぞれ不透明な赤と不透明青を渡します。</span><span class="sxs-lookup"><span data-stu-id="008f2-118">Pass in the opaque red and opaque blue as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 <span data-ttu-id="008f2-119">色要素は前の例では 0 の水平座標から 200 の水平座標に移動すると直線的に変更します。</span><span class="sxs-lookup"><span data-stu-id="008f2-119">In the preceding example, the color components change linearly as you move from a horizontal coordinate of 0 to a horizontal coordinate of 200.</span></span> <span data-ttu-id="008f2-120">たとえば、最初の座標が 0 と 200 の中間点は、0 から 255 までの中間に位置が青要素があります。</span><span class="sxs-lookup"><span data-stu-id="008f2-120">For example, a point whose first coordinate is halfway between 0 and 200 will have a blue component that is halfway between 0 and 255.</span></span>  
  
 <span data-ttu-id="008f2-121">GDI + を使用すると、調整、他のグラデーションの 1 つのエッジから色が異なります。</span><span class="sxs-lookup"><span data-stu-id="008f2-121">GDI+ allows you to adjust the way a color varies from one edge of a gradient to the other.</span></span> <span data-ttu-id="008f2-122">黒から次の表に従って赤に変更されるグラデーション ブラシを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="008f2-122">Suppose you want to create a gradient brush that changes from black to red according to the following table.</span></span>  
  
|<span data-ttu-id="008f2-123">水平方向の座標</span><span class="sxs-lookup"><span data-stu-id="008f2-123">Horizontal coordinate</span></span>|<span data-ttu-id="008f2-124">RGB コンポーネント</span><span class="sxs-lookup"><span data-stu-id="008f2-124">RGB components</span></span>|  
|---------------------------|--------------------|  
|<span data-ttu-id="008f2-125">0</span><span class="sxs-lookup"><span data-stu-id="008f2-125">0</span></span>|<span data-ttu-id="008f2-126">(0, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="008f2-126">(0, 0, 0)</span></span>|  
|<span data-ttu-id="008f2-127">40</span><span class="sxs-lookup"><span data-stu-id="008f2-127">40</span></span>|<span data-ttu-id="008f2-128">(128, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="008f2-128">(128, 0, 0)</span></span>|  
|<span data-ttu-id="008f2-129">200</span><span class="sxs-lookup"><span data-stu-id="008f2-129">200</span></span>|<span data-ttu-id="008f2-130">(255, 0, 0)</span><span class="sxs-lookup"><span data-stu-id="008f2-130">(255, 0, 0)</span></span>|  
  
 <span data-ttu-id="008f2-131">水平座標が 0 から 200 の方法の 20% のみである場合に、赤のコンポーネントが半分の強さではことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="008f2-131">Note that the red component is at half intensity when the horizontal coordinate is only 20 percent of the way from 0 to 200.</span></span>  
  
 <span data-ttu-id="008f2-132">次の例のセット、<xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType>に 3 つの相対強度を 3 つの相対位置に関連付けるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="008f2-132">The following example sets the <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> property to associate three relative intensities with three relative positions.</span></span> <span data-ttu-id="008f2-133">上の表のように 0.5 の相対強度は 0.2 の相対位置に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="008f2-133">As in the preceding table, a relative intensity of 0.5 is associated with a relative position of 0.2.</span></span> <span data-ttu-id="008f2-134">コードでは、楕円と四角形をグラデーション ブラシを設定します。</span><span class="sxs-lookup"><span data-stu-id="008f2-134">The code fills an ellipse and a rectangle with the gradient brush.</span></span>  
  
 <span data-ttu-id="008f2-135">次の図は、結果として得られる楕円と四角形を示します。</span><span class="sxs-lookup"><span data-stu-id="008f2-135">The following illustration shows the resulting ellipse and rectangle.</span></span>  
  
 <span data-ttu-id="008f2-136">![線形グラデーション](./media/cslineargradient2.png "cslineargradient2")</span><span class="sxs-lookup"><span data-stu-id="008f2-136">![Linear Gradient](./media/cslineargradient2.png "cslineargradient2")</span></span>  

### <a name="to-customize-linear-gradients"></a><span data-ttu-id="008f2-137">線形グラデーションをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="008f2-137">To customize linear gradients</span></span>  
  
-   <span data-ttu-id="008f2-138">3 番目と 4 番目の引数として、それぞれ不透明な黒と不透明な赤を渡します。</span><span class="sxs-lookup"><span data-stu-id="008f2-138">Pass in the opaque black and opaque red as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 <span data-ttu-id="008f2-139">上記の例のグラデーションを水平にされています。つまり、色は、水平線のいずれかに移動すると、段階的に変更します。</span><span class="sxs-lookup"><span data-stu-id="008f2-139">The gradients in the preceding examples have been horizontal; that is, the color changes gradually as you move along any horizontal line.</span></span> <span data-ttu-id="008f2-140">垂直方向のグラデーションと対角線方向のグラデーションを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="008f2-140">You can also define vertical gradients and diagonal gradients.</span></span>  
  
 <span data-ttu-id="008f2-141">次の例に、点 (0, 0) と (200, 100) を渡す、<xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="008f2-141">The following example passes the points (0, 0) and (200, 100) to a <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="008f2-142">青色の色が関連付けられている (0, 0) と、緑色の色が関連付けられます (200, 100)。</span><span class="sxs-lookup"><span data-stu-id="008f2-142">The color blue is associated with (0, 0), and the color green is associated with (200, 100).</span></span> <span data-ttu-id="008f2-143">(ペンの幅が 10)、行と楕円は、線状グラデーション ブラシで塗りつぶされます。</span><span class="sxs-lookup"><span data-stu-id="008f2-143">A line (with pen width 10) and an ellipse are filled with the linear gradient brush.</span></span>  
  
 <span data-ttu-id="008f2-144">次の図は、線、楕円を示します。</span><span class="sxs-lookup"><span data-stu-id="008f2-144">The following illustration shows the line and the ellipse.</span></span> <span data-ttu-id="008f2-145">楕円内色徐々 にに沿って移動すると行のメモが並列に渡される行には (0, 0) と (200, 100)。</span><span class="sxs-lookup"><span data-stu-id="008f2-145">Note that the color in the ellipse changes gradually as you move along any line that is parallel to the line passing through (0, 0) and (200, 100).</span></span>  
  
 <span data-ttu-id="008f2-146">![線形グラデーション](./media/cslineargradient3.png "cslineargradient3")</span><span class="sxs-lookup"><span data-stu-id="008f2-146">![Linear Gradient](./media/cslineargradient3.png "cslineargradient3")</span></span>  
  
### <a name="to-create-diagonal-linear-gradients"></a><span data-ttu-id="008f2-147">対角線方向の線形グラデーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="008f2-147">To create diagonal linear gradients</span></span>  
  
-   <span data-ttu-id="008f2-148">3 番目と 4 番目の引数として、それぞれ不透明青と不透明な緑を渡します。</span><span class="sxs-lookup"><span data-stu-id="008f2-148">Pass in the opaque blue and opaque green as the third and fourth argument, respectively.</span></span>  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="008f2-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="008f2-149">See also</span></span>

- [<span data-ttu-id="008f2-150">グラデーション ブラシを使用した図形の塗りつぶし</span><span class="sxs-lookup"><span data-stu-id="008f2-150">Using a Gradient Brush to Fill Shapes</span></span>](using-a-gradient-brush-to-fill-shapes.md)
- [<span data-ttu-id="008f2-151">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="008f2-151">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
