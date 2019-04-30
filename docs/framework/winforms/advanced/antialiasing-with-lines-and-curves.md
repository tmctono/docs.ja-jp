---
title: 直線と曲線のアンチエイリアシング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: cbc9033f18f1ab255862c8f8e2891aa9b68cf8d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961102"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="4a678-102">直線と曲線のアンチエイリアシング</span><span class="sxs-lookup"><span data-stu-id="4a678-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="4a678-103">使用すると[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]直線を描画する開始点と、直線の終了点を提供するが、行の個々 のピクセルについての情報を提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4a678-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4a678-104">特定のディスプレイ デバイスに、行を表示するにどのピクセルはオンにする、ディスプレイ ドライバー ソフトウェアと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="4a678-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="4a678-105">エイリアス</span><span class="sxs-lookup"><span data-stu-id="4a678-105">Aliasing</span></span>  
 <span data-ttu-id="4a678-106">点 (16, 10) に (4, 2) のポイントから移動する直接赤色の線を検討してください。</span><span class="sxs-lookup"><span data-stu-id="4a678-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="4a678-107">座標システムでは、左上隅の原点とメジャーの単位がピクセルであることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="4a678-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="4a678-108">また、x 軸が下、右、y 軸を指しているとします。</span><span class="sxs-lookup"><span data-stu-id="4a678-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="4a678-109">次の図は、マルチカラーの背景色で描画される赤色の線の拡大表示を示します。</span><span class="sxs-lookup"><span data-stu-id="4a678-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="4a678-110">![行のアンチエイリアシングなし](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="4a678-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="4a678-111">行を表示するために使用される赤いピクセルは不透明です。</span><span class="sxs-lookup"><span data-stu-id="4a678-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="4a678-112">行には、部分的に透明なピクセルがありません。</span><span class="sxs-lookup"><span data-stu-id="4a678-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="4a678-113">この種類の行のレンダリングは、行ぎざぎざに表示し、行では、階段のようにします。</span><span class="sxs-lookup"><span data-stu-id="4a678-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="4a678-114">階段に 1 行を表すには、この手法はエイリアスと呼ばれる階段には、理論上の線のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="4a678-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="4a678-115">アンチエイリアシング</span><span class="sxs-lookup"><span data-stu-id="4a678-115">Antialiasing</span></span>  
 <span data-ttu-id="4a678-116">行を表示するためのより高度な手法では、部分的に透明なピクセルと不透明なピクセルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a678-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="4a678-117">ピクセルが、純粋な赤に設定または red と背景の色のブレンドを閉じる方法によっては行にします。</span><span class="sxs-lookup"><span data-stu-id="4a678-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="4a678-118">この種類の表示では、アンチエイリアシングは呼び出され、人間の目がより滑らかなとして認識する行になります。</span><span class="sxs-lookup"><span data-stu-id="4a678-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="4a678-119">次の図は、アンチ エイリアス処理された行を生成するためにバック グラウンドで特定のピクセルをブレンドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4a678-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="4a678-120">![アンチエイリアシング線](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="4a678-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="4a678-121">アンチエイリアシング、平滑化とも呼ばれるは、曲線にも適用できます。</span><span class="sxs-lookup"><span data-stu-id="4a678-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="4a678-122">次の図は、平滑化された楕円の拡大表示を示します。</span><span class="sxs-lookup"><span data-stu-id="4a678-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="4a678-123">![アンチエイリアシング曲線](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="4a678-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="4a678-124">次の図は、アンチエイリアシングなしで 1 回 1 回のアンチエイリアシングを使用して、実際のサイズで同じ省略記号ボタンを示します。</span><span class="sxs-lookup"><span data-stu-id="4a678-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="4a678-125">![アンチエイリアシング例](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="4a678-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="4a678-126">直線と曲線のアンチエイリアシングの使用を描画するには、インスタンスを作成、<xref:System.Drawing.Graphics>クラスし、設定、<xref:System.Drawing.Graphics.SmoothingMode%2A>プロパティを<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>または<xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>します。</span><span class="sxs-lookup"><span data-stu-id="4a678-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="4a678-127">描画方法の 1 つを同じに呼び出す<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="4a678-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="4a678-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a678-128">See also</span></span>

- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="4a678-129">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="4a678-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="4a678-130">方法: テキストのアンチエイリアシングを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a678-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
