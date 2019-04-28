---
title: 座標系の種類
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 765df4bcd3cef83e624ad8b11676696b95f7d035
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792368"
---
# <a name="types-of-coordinate-systems"></a><span data-ttu-id="42bf4-102">座標系の種類</span><span class="sxs-lookup"><span data-stu-id="42bf4-102">Types of Coordinate Systems</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="42bf4-103">次の 3 つの座標空間を使用して: 世界、ページ、およびデバイス。</span><span class="sxs-lookup"><span data-stu-id="42bf4-103">uses three coordinate spaces: world, page, and device.</span></span> <span data-ttu-id="42bf4-104">ワールド座標は特定のグラフィック ワールドをモデル化するために使用する座標は、.NET Framework のメソッドに渡す座標です。</span><span class="sxs-lookup"><span data-stu-id="42bf4-104">World coordinates are the coordinates used to model a particular graphic world and are the coordinates you pass to methods in the .NET Framework.</span></span> <span data-ttu-id="42bf4-105">ページ座標は、フォームやコントロールなどの描画サーフェイスで使用される座標系を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42bf4-105">Page coordinates refer to the coordinate system used by a drawing surface, such as a form or control.</span></span> <span data-ttu-id="42bf4-106">デバイス座標は、画面や紙など、描画されている物理デバイスで使用される座標です。</span><span class="sxs-lookup"><span data-stu-id="42bf4-106">Device coordinates are the coordinates used by the physical device being drawn on, such as a screen or sheet of paper.</span></span> <span data-ttu-id="42bf4-107">呼び出しを行うとき`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`、ポイントに渡す、<xref:System.Drawing.Graphics.DrawLine%2A>メソッド:`(0, 0)`と`(160, 80)`: ワールド座標空間では。</span><span class="sxs-lookup"><span data-stu-id="42bf4-107">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, the points that you pass to the <xref:System.Drawing.Graphics.DrawLine%2A> method—`(0, 0)` and `(160, 80)`—are in the world coordinate space.</span></span> <span data-ttu-id="42bf4-108">前に[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]画面に、直線を描画することができます、座標変換のシーケンスを通過します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-108">Before [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can draw the line on the screen, the coordinates pass through a sequence of transformations.</span></span> <span data-ttu-id="42bf4-109">ワールド変換と呼ばれる 1 つの変換は、ページ座標にワールド座標を変換し、ページの変換と呼ばれる別の変換は、ページ座標をデバイス座標に変換します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-109">One transformation, called the world transformation, converts world coordinates to page coordinates, and another transformation, called the page transformation, converts page coordinates to device coordinates.</span></span>  
  
## <a name="transforms-and-coordinate-systems"></a><span data-ttu-id="42bf4-110">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="42bf4-110">Transforms and Coordinate Systems</span></span>  
 <span data-ttu-id="42bf4-111">左上隅ではなく、クライアント領域の本体でに原点がある座標系を使用するとします。</span><span class="sxs-lookup"><span data-stu-id="42bf4-111">Suppose you want to work with a coordinate system that has its origin in the body of the client area rather than the upper-left corner.</span></span> <span data-ttu-id="42bf4-112">たとえば、クライアント領域の上部から 50 ピクセルとクライアント領域の左端から 100 ピクセルにする配信元にするとします。</span><span class="sxs-lookup"><span data-stu-id="42bf4-112">Say, for example, that you want the origin to be 100 pixels from the left edge of the client area and 50 pixels from the top of the client area.</span></span> <span data-ttu-id="42bf4-113">次の図は、このような座標系を示します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-113">The following illustration shows such a coordinate system.</span></span>  
  
 <span data-ttu-id="42bf4-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span><span class="sxs-lookup"><span data-stu-id="42bf4-114">![Coordinate System](./media/aboutgdip05-art01.gif "AboutGdip05_art01")</span></span>  
  
 <span data-ttu-id="42bf4-115">呼び出しを行うとき`myGraphics.DrawLine(myPen, 0, 0, 160, 80)`、次の図に示すように行を取得します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-115">When you make the call `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, you get the line shown in the following illustration.</span></span>  
  
 <span data-ttu-id="42bf4-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span><span class="sxs-lookup"><span data-stu-id="42bf4-116">![Coordinate System](./media/aboutgdip05-art02.gif "AboutGdip05_art02")</span></span>  
  
 <span data-ttu-id="42bf4-117">次の 3 つの座標空間で、行の端点の座標は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="42bf4-117">The coordinates of the endpoints of your line in the three coordinate spaces are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42bf4-118">World</span><span class="sxs-lookup"><span data-stu-id="42bf4-118">World</span></span>|<span data-ttu-id="42bf4-119">(0, 0) に (160, 80)</span><span class="sxs-lookup"><span data-stu-id="42bf4-119">(0, 0) to (160, 80)</span></span>|  
|<span data-ttu-id="42bf4-120">ページ</span><span class="sxs-lookup"><span data-stu-id="42bf4-120">Page</span></span>|<span data-ttu-id="42bf4-121">(100, 50) を (260、130)</span><span class="sxs-lookup"><span data-stu-id="42bf4-121">(100, 50) to (260, 130)</span></span>|  
|<span data-ttu-id="42bf4-122">デバイス</span><span class="sxs-lookup"><span data-stu-id="42bf4-122">Device</span></span>|<span data-ttu-id="42bf4-123">(100, 50) を (260、130)</span><span class="sxs-lookup"><span data-stu-id="42bf4-123">(100, 50) to (260, 130)</span></span>|  
  
 <span data-ttu-id="42bf4-124">ページ座標空間がクライアント領域の左上隅にある原点を持つことに注意してください。これは、大文字と小文字を常になります。</span><span class="sxs-lookup"><span data-stu-id="42bf4-124">Note that the page coordinate space has its origin at the upper-left corner of the client area; this will always be the case.</span></span> <span data-ttu-id="42bf4-125">測定単位がピクセルであるため、デバイス座標がページ座標と同じにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="42bf4-125">Also note that because the unit of measure is the pixel, the device coordinates are the same as the page coordinates.</span></span> <span data-ttu-id="42bf4-126">測定単位をピクセル (たとえば、インチ) 以外に設定した場合は、デバイス座標がページ座標から別になります。</span><span class="sxs-lookup"><span data-stu-id="42bf4-126">If you set the unit of measure to something other than pixels (for example, inches), then the device coordinates will be different from the page coordinates.</span></span>  
  
 <span data-ttu-id="42bf4-127">ワールド座標をマップ ページ座標、ワールド変換に保持されている、<xref:System.Drawing.Graphics.Transform%2A>のプロパティ、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="42bf4-127">The world transformation, which maps world coordinates to page coordinates, is held in the <xref:System.Drawing.Graphics.Transform%2A> property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="42bf4-128">前の例では、ワールド変換は x 方向に翻訳 100 単位と y 軸方向で 50 ユニット。</span><span class="sxs-lookup"><span data-stu-id="42bf4-128">In the preceding example, the world transformation is a translation 100 units in the x direction and 50 units in the y direction.</span></span> <span data-ttu-id="42bf4-129">次の例のワールド変換の設定、<xref:System.Drawing.Graphics>オブジェクトを使用して<xref:System.Drawing.Graphics>上記の図に示すように行を描画するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="42bf4-129">The following example sets the world transformation of a <xref:System.Drawing.Graphics> object and then uses that <xref:System.Drawing.Graphics> object to draw the line shown in the preceding figure:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 <span data-ttu-id="42bf4-130">ページの変換は、デバイス座標にページ座標をマップします。</span><span class="sxs-lookup"><span data-stu-id="42bf4-130">The page transformation maps page coordinates to device coordinates.</span></span> <span data-ttu-id="42bf4-131"><xref:System.Drawing.Graphics>クラスには、<xref:System.Drawing.Graphics.PageUnit%2A>と<xref:System.Drawing.Graphics.PageScale%2A>ページ変換を操作するためのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="42bf4-131">The <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.PageUnit%2A> and <xref:System.Drawing.Graphics.PageScale%2A> properties for manipulating the page transformation.</span></span> <span data-ttu-id="42bf4-132"><xref:System.Drawing.Graphics>クラスでは、2 つの読み取り専用のプロパティも提供します<xref:System.Drawing.Graphics.DpiX%2A>と<xref:System.Drawing.Graphics.DpiY%2A>、ディスプレイ デバイスの 1 インチあたりのドット数水平および垂直方向を確認するためです。</span><span class="sxs-lookup"><span data-stu-id="42bf4-132">The <xref:System.Drawing.Graphics> class also provides two read-only properties, <xref:System.Drawing.Graphics.DpiX%2A> and <xref:System.Drawing.Graphics.DpiY%2A>, for examining the horizontal and vertical dots per inch of the display device.</span></span>  
  
 <span data-ttu-id="42bf4-133">使用することができます、<xref:System.Drawing.Graphics.PageUnit%2A>のプロパティ、<xref:System.Drawing.Graphics>ピクセル以外のメジャーの単位を指定するクラス。</span><span class="sxs-lookup"><span data-stu-id="42bf4-133">You can use the <xref:System.Drawing.Graphics.PageUnit%2A> property of the <xref:System.Drawing.Graphics> class to specify a unit of measure other than the pixel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42bf4-134">設定することはできません、<xref:System.Drawing.Graphics.PageUnit%2A>プロパティを<xref:System.Drawing.GraphicsUnit.World>をこの物理単位でないし、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-134">You cannot set the <xref:System.Drawing.Graphics.PageUnit%2A> property to <xref:System.Drawing.GraphicsUnit.World>, as this is not a physical unit and will cause an exception.</span></span>  
  
 <span data-ttu-id="42bf4-135">次の例から線を描画します (0, 0) に (2, 1)、ここ 2 インチ右側に、点 (0, 0) からダウン 1 インチは、ポイント (2, 1)。</span><span class="sxs-lookup"><span data-stu-id="42bf4-135">The following example draws a line from (0, 0) to (2, 1), where the point (2, 1) is 2 inches to the right and 1 inch down from the point (0, 0):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  <span data-ttu-id="42bf4-136">ペンの幅を指定しないのは、ペンを構築するときに、前の例は 1 インチ幅の線を描画します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-136">If you don't specify a pen width when you construct your pen, the preceding example will draw a line that is one inch wide.</span></span> <span data-ttu-id="42bf4-137">ペンの幅を指定するには、2 番目の引数で、<xref:System.Drawing.Pen>コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="42bf4-137">You can specify the pen width in the second argument to the <xref:System.Drawing.Pen> constructor:</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 <span data-ttu-id="42bf4-138">ディスプレイ デバイスが 96 ドット/インチで水平方向と垂直方向の 1 インチあたり 96 ドットであると、想定した場合、3 つの座標空間に次座標がある前の例では行のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="42bf4-138">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42bf4-139">World</span><span class="sxs-lookup"><span data-stu-id="42bf4-139">World</span></span>|<span data-ttu-id="42bf4-140">(0, 0) に (2, 1)</span><span class="sxs-lookup"><span data-stu-id="42bf4-140">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="42bf4-141">ページ</span><span class="sxs-lookup"><span data-stu-id="42bf4-141">Page</span></span>|<span data-ttu-id="42bf4-142">(0, 0) に (2, 1)</span><span class="sxs-lookup"><span data-stu-id="42bf4-142">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="42bf4-143">デバイス</span><span class="sxs-lookup"><span data-stu-id="42bf4-143">Device</span></span>|<span data-ttu-id="42bf4-144">(0, 0, に (192, 96)</span><span class="sxs-lookup"><span data-stu-id="42bf4-144">(0, 0, to (192, 96)</span></span>|  
  
 <span data-ttu-id="42bf4-145">ワールド座標の原点がクライアント領域の左上隅にあるため、ページ座標がワールド座標と同じに注意してください。</span><span class="sxs-lookup"><span data-stu-id="42bf4-145">Note that because the origin of the world coordinate space is at the upper-left corner of the client area, the page coordinates are the same as the world coordinates.</span></span>  
  
 <span data-ttu-id="42bf4-146">さまざまな効果を実現するために世界とページの変換を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="42bf4-146">You can combine the world and page transformations to achieve a variety of effects.</span></span> <span data-ttu-id="42bf4-147">たとえば、メジャーの単位として (インチ) を使用して、クライアント領域の上端からの 1/2 インチ、クライアント領域の左端から 2 インチ、座標系の原点します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-147">For example, suppose you want to use inches as the unit of measure and you want the origin of your coordinate system to be 2 inches from the left edge of the client area and 1/2 inch from the top of the client area.</span></span> <span data-ttu-id="42bf4-148">次の例の世界とページの変換の設定、<xref:System.Drawing.Graphics>オブジェクトし、後から線を描画します (0, 0) に (2, 1)。</span><span class="sxs-lookup"><span data-stu-id="42bf4-148">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object and then draws a line from (0, 0) to (2, 1):</span></span>  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 <span data-ttu-id="42bf4-149">次の図は、行と座標系を示します。</span><span class="sxs-lookup"><span data-stu-id="42bf4-149">The following illustration shows the line and coordinate system.</span></span>  
  
 <span data-ttu-id="42bf4-150">![座標系](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span><span class="sxs-lookup"><span data-stu-id="42bf4-150">![Coordinate System](./media/aboutgdip05-art03.gif "AboutGdip05_art03")</span></span>  
  
 <span data-ttu-id="42bf4-151">ディスプレイ デバイスが 96 ドット/インチで水平方向と垂直方向の 1 インチあたり 96 ドットであると、想定した場合、3 つの座標空間に次座標がある前の例では行のエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="42bf4-151">If we assume that the display device has 96 dots per inch in the horizontal direction and 96 dots per inch in the vertical direction, the endpoints of the line in the preceding example have the following coordinates in the three coordinate spaces:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42bf4-152">World</span><span class="sxs-lookup"><span data-stu-id="42bf4-152">World</span></span>|<span data-ttu-id="42bf4-153">(0, 0) に (2, 1)</span><span class="sxs-lookup"><span data-stu-id="42bf4-153">(0, 0) to (2, 1)</span></span>|  
|<span data-ttu-id="42bf4-154">ページ</span><span class="sxs-lookup"><span data-stu-id="42bf4-154">Page</span></span>|<span data-ttu-id="42bf4-155">(2, 0.5) に (4, 1.5)</span><span class="sxs-lookup"><span data-stu-id="42bf4-155">(2, 0.5) to (4, 1.5)</span></span>|  
|<span data-ttu-id="42bf4-156">デバイス</span><span class="sxs-lookup"><span data-stu-id="42bf4-156">Device</span></span>|<span data-ttu-id="42bf4-157">(192, 48) に (384、144)</span><span class="sxs-lookup"><span data-stu-id="42bf4-157">(192, 48) to (384, 144)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42bf4-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="42bf4-158">See also</span></span>

- [<span data-ttu-id="42bf4-159">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="42bf4-159">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="42bf4-160">変換の行列表現</span><span class="sxs-lookup"><span data-stu-id="42bf4-160">Matrix Representation of Transformations</span></span>](matrix-representation-of-transformations.md)
