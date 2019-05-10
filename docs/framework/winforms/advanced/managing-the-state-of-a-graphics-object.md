---
title: Graphics オブジェクトの状態の管理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: be5042e62da6a9a8afd51af08b85dbe16d8eaac0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623632"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="6fc63-102">Graphics オブジェクトの状態の管理</span><span class="sxs-lookup"><span data-stu-id="6fc63-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="6fc63-103"><xref:System.Drawing.Graphics>クラスは、の中核[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-103">The <xref:System.Drawing.Graphics> class is at the heart of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="6fc63-104">取得するものを描画する、<xref:System.Drawing.Graphics>オブジェクトでそのプロパティを設定し、そのメソッドを呼び出す<xref:System.Drawing.Graphics.DrawLine%2A>、 <xref:System.Drawing.Graphics.DrawImage%2A>、<xref:System.Drawing.Graphics.DrawString%2A>など)。</span><span class="sxs-lookup"><span data-stu-id="6fc63-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="6fc63-105">次の例では、<xref:System.Drawing.Graphics.DrawRectangle%2A>のメソッドを<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fc63-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="6fc63-106">渡される最初の引数、<xref:System.Drawing.Graphics.DrawRectangle%2A>メソッドは、<xref:System.Drawing.Pen>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fc63-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="6fc63-107">グラフィックスの状態</span><span class="sxs-lookup"><span data-stu-id="6fc63-107">Graphics State</span></span>  
 <span data-ttu-id="6fc63-108">A<xref:System.Drawing.Graphics>オブジェクトによる描画メソッドは、の提供がなど複数の<xref:System.Drawing.Graphics.DrawLine%2A>と<xref:System.Drawing.Graphics.DrawRectangle%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="6fc63-109">A<xref:System.Drawing.Graphics>オブジェクトでは、グラフィックスの状態は、次のカテゴリに分類できますも保持されます。</span><span class="sxs-lookup"><span data-stu-id="6fc63-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="6fc63-110">品質の設定</span><span class="sxs-lookup"><span data-stu-id="6fc63-110">Quality settings</span></span>  
  
- <span data-ttu-id="6fc63-111">変換</span><span class="sxs-lookup"><span data-stu-id="6fc63-111">Transformations</span></span>  
  
- <span data-ttu-id="6fc63-112">クリッピング領域</span><span class="sxs-lookup"><span data-stu-id="6fc63-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="6fc63-113">品質の設定</span><span class="sxs-lookup"><span data-stu-id="6fc63-113">Quality Settings</span></span>  
 <span data-ttu-id="6fc63-114">A<xref:System.Drawing.Graphics>オブジェクトが描画されるアイテムの品質に影響を与えるいくつかのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="6fc63-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="6fc63-115">たとえば、設定、<xref:System.Drawing.Graphics.TextRenderingHint%2A>プロパティをテキストに適用されます (ある場合) のアンチエイリアシングの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="6fc63-116">品質に影響を与える他のプロパティは<xref:System.Drawing.Graphics.SmoothingMode%2A>、 <xref:System.Drawing.Graphics.CompositingMode%2A>、 <xref:System.Drawing.Graphics.CompositingQuality%2A>、および<xref:System.Drawing.Graphics.InterpolationMode%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="6fc63-117">次の例は、スムージング モードを設定する 2 つの楕円を描画<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>、平滑化のモードを設定するもう 1 つ<xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span><span class="sxs-lookup"><span data-stu-id="6fc63-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="6fc63-118">変換</span><span class="sxs-lookup"><span data-stu-id="6fc63-118">Transformations</span></span>  
 <span data-ttu-id="6fc63-119">A<xref:System.Drawing.Graphics>オブジェクトをで描画されるすべての項目に適用される 2 つの変換 (世界と ページ) を保持する<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fc63-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="6fc63-120">ワールド変換では、任意のアフィン変換を格納できます。</span><span class="sxs-lookup"><span data-stu-id="6fc63-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="6fc63-121">アフィン変換には、拡大縮小、回転、反転、傾斜、および変換が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6fc63-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="6fc63-122">スケーリングの単位 (たとえば、インチをピクセル単位) を変更して、ページの変換を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fc63-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="6fc63-123">詳細については、次を参照してください。[座標系と変換](coordinate-systems-and-transformations.md)します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="6fc63-124">次の例の世界とページの変換の設定、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fc63-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="6fc63-125">ワールド変換は、30 度回転に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6fc63-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="6fc63-126">ページの変換を設定すると、2 番目の座標が渡されるように<xref:System.Drawing.Graphics.DrawEllipse%2A>ピクセルではなくミリメートル単位として扱われます。</span><span class="sxs-lookup"><span data-stu-id="6fc63-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="6fc63-127">コードは、同じ 2 つの呼び出し、<xref:System.Drawing.Graphics.DrawEllipse%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="6fc63-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="6fc63-128">ワールド変換は、最初に適用される<xref:System.Drawing.Graphics.DrawEllipse%2A>、2 つ目に呼び出し、および (世界と ページ) の両方の変換が適用<xref:System.Drawing.Graphics.DrawEllipse%2A>呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="6fc63-129">次の図は、2 つの省略記号を示します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="6fc63-130">30 度の回転は (クライアント領域の左上隅) 座標系の原点を基点、楕円の中心でないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6fc63-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="6fc63-131">1 のペンの幅が 2 番目の楕円の 1 ピクセルの最初の楕円および 1 ミリメートルを意味することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6fc63-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![2 つの楕円を図解: 回転とペンの幅。](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="6fc63-133">クリッピング領域</span><span class="sxs-lookup"><span data-stu-id="6fc63-133">Clipping Region</span></span>  
 <span data-ttu-id="6fc63-134">A<xref:System.Drawing.Graphics>オブジェクトをで描画されるすべての項目に適用されるクリッピング領域を保持する<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fc63-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="6fc63-135">クリッピング領域を設定するには、呼び出すことによって、<xref:System.Drawing.Graphics.SetClip%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="6fc63-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="6fc63-136">次の例では、2 つの四角形の和集合を形成して十字型の領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="6fc63-137">クリッピング領域としてそのリージョンが指定されている、<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6fc63-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="6fc63-138">コードは、クリッピング領域の内部に制限されている 2 つの行を描画します。</span><span class="sxs-lookup"><span data-stu-id="6fc63-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="6fc63-139">次の図は、クリップされた行を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fc63-139">The following illustration shows the clipped lines:</span></span>  
  
 ![制限されたクリップ領域を示す図。](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="6fc63-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fc63-141">See also</span></span>

- [<span data-ttu-id="6fc63-142">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="6fc63-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="6fc63-143">入れ子になっているグラフィックス コンテナーの使用</span><span class="sxs-lookup"><span data-stu-id="6fc63-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
