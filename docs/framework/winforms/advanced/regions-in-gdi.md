---
title: GDI+ での領域
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 33d4f4ecca7b9d777fa4eab5b6d031de10f03ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956811"
---
# <a name="regions-in-gdi"></a><span data-ttu-id="a726c-102">GDI+ での領域</span><span class="sxs-lookup"><span data-stu-id="a726c-102">Regions in GDI+</span></span>
<span data-ttu-id="a726c-103">リージョンは、出力デバイスの表示領域の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="a726c-103">A region is a portion of the display area of an output device.</span></span> <span data-ttu-id="a726c-104">リージョンは、単純な (1 つの四角形) または複合 (多角形と閉じた曲線の組み合わせ) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a726c-104">Regions can be simple (a single rectangle) or complex (a combination of polygons and closed curves).</span></span> <span data-ttu-id="a726c-105">次の図は、2 つのリージョン: 四角形から構築された 1 つと、パスから構築されました。</span><span class="sxs-lookup"><span data-stu-id="a726c-105">The following illustration shows two regions: one constructed from a rectangle, and the other constructed from a path.</span></span>  
  
 <span data-ttu-id="a726c-106">![リージョン](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span><span class="sxs-lookup"><span data-stu-id="a726c-106">![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")</span></span>  
  
## <a name="using-regions"></a><span data-ttu-id="a726c-107">領域の使用</span><span class="sxs-lookup"><span data-stu-id="a726c-107">Using Regions</span></span>  
 <span data-ttu-id="a726c-108">リージョンは、クリッピングは多くの場合、使用され、ヒット テストします。</span><span class="sxs-lookup"><span data-stu-id="a726c-108">Regions are often used for clipping and hit testing.</span></span> <span data-ttu-id="a726c-109">クリッピングでは、更新する必要がある部分は、通常、表示領域の特定の領域に描画を制限します。</span><span class="sxs-lookup"><span data-stu-id="a726c-109">Clipping involves restricting drawing to a certain region of the display area, usually the portion that needs to be updated.</span></span> <span data-ttu-id="a726c-110">ヒット テストには、マウス ボタンが押されたときにカーソルが、画面の特定のリージョン内かどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a726c-110">Hit testing involves checking to determine whether the cursor is in a certain region of the screen when a mouse button is pressed.</span></span>  
  
 <span data-ttu-id="a726c-111">四角形またはパスからリージョンを構築できます。</span><span class="sxs-lookup"><span data-stu-id="a726c-111">You can construct a region from a rectangle or a path.</span></span> <span data-ttu-id="a726c-112">既存のリージョンを組み合わせることで、複雑な領域を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a726c-112">You can also create complex regions by combining existing regions.</span></span> <span data-ttu-id="a726c-113"><xref:System.Drawing.Region>クラスは領域を結合するために、次のメソッドを提供します。 <xref:System.Drawing.Region.Intersect%2A>、 <xref:System.Drawing.Region.Union%2A>、 <xref:System.Drawing.Region.Xor%2A>、 <xref:System.Drawing.Region.Exclude%2A>、および<xref:System.Drawing.Region.Complement%2A>します。</span><span class="sxs-lookup"><span data-stu-id="a726c-113">The <xref:System.Drawing.Region> class provides the following methods for combining regions: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, and <xref:System.Drawing.Region.Complement%2A>.</span></span>  
  
 <span data-ttu-id="a726c-114">2 つのリージョンの積集合は、両方のリージョンに属しているすべての点のセットです。</span><span class="sxs-lookup"><span data-stu-id="a726c-114">The intersection of two regions is the set of all points belonging to both regions.</span></span> <span data-ttu-id="a726c-115">共用体は、1 つまたはもう一方または両方のリージョンに属しているすべての点のセットです。</span><span class="sxs-lookup"><span data-stu-id="a726c-115">The union is the set of all points belonging to one or the other or both regions.</span></span> <span data-ttu-id="a726c-116">領域の補数は、一連のリージョンにないすべてのポイントです。</span><span class="sxs-lookup"><span data-stu-id="a726c-116">The complement of a region is the set of all points that are not in the region.</span></span> <span data-ttu-id="a726c-117">次の図は、前の図に示すように 2 つのリージョンの和集合、積集合を示します。</span><span class="sxs-lookup"><span data-stu-id="a726c-117">The following illustration shows the intersection and union of the two regions shown in the preceding illustration.</span></span>  
  
 <span data-ttu-id="a726c-118">![リージョン](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span><span class="sxs-lookup"><span data-stu-id="a726c-118">![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")</span></span>  
  
 <span data-ttu-id="a726c-119"><xref:System.Drawing.Region.Xor%2A>のリージョンのペアに適用される、メソッドが 1 つのリージョンまたは両方ではなく、その他に属しているすべてのポイントを格納する領域を生成します。</span><span class="sxs-lookup"><span data-stu-id="a726c-119">The <xref:System.Drawing.Region.Xor%2A> method, applied to a pair of regions, produces a region that contains all points that belong to one region or the other, but not both.</span></span> <span data-ttu-id="a726c-120"><xref:System.Drawing.Region.Exclude%2A>のリージョンのペアに適用される、メソッドが 2 番目のリージョンにない最初のリージョン内のすべてのポイントが含まれる領域が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a726c-120">The <xref:System.Drawing.Region.Exclude%2A> method, applied to a pair of regions, produces a region that contains all points in the first region that are not in the second region.</span></span> <span data-ttu-id="a726c-121">次の図は、適用することに起因するリージョン、<xref:System.Drawing.Region.Xor%2A>と<xref:System.Drawing.Region.Exclude%2A>メソッドをこのトピックの冒頭で示した 2 つのリージョン。</span><span class="sxs-lookup"><span data-stu-id="a726c-121">The following illustration shows the regions that result from applying the <xref:System.Drawing.Region.Xor%2A> and <xref:System.Drawing.Region.Exclude%2A> methods to the two regions shown at the beginning of this topic.</span></span>  
  
 <span data-ttu-id="a726c-122">![リージョン](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span><span class="sxs-lookup"><span data-stu-id="a726c-122">![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")</span></span>  
  
 <span data-ttu-id="a726c-123">領域の塗りつぶしにする必要があります、<xref:System.Drawing.Graphics>オブジェクト、<xref:System.Drawing.Brush>オブジェクト、および<xref:System.Drawing.Region>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a726c-123">To fill a region, you need a <xref:System.Drawing.Graphics> object, a <xref:System.Drawing.Brush> object, and a <xref:System.Drawing.Region> object.</span></span> <span data-ttu-id="a726c-124"><xref:System.Drawing.Graphics>オブジェクトを提供、<xref:System.Drawing.Graphics.FillRegion%2A>メソッド、および<xref:System.Drawing.Brush>オブジェクトは、塗りつぶしの色またはパターンなどの属性を格納します。</span><span class="sxs-lookup"><span data-stu-id="a726c-124">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.FillRegion%2A> method, and the <xref:System.Drawing.Brush> object stores attributes of the fill, such as color or pattern.</span></span> <span data-ttu-id="a726c-125">次の例では、純色で領域を塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="a726c-125">The following example fills a region with a solid color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="a726c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a726c-126">See also</span></span>

- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="a726c-127">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="a726c-127">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="a726c-128">領域の使用</span><span class="sxs-lookup"><span data-stu-id="a726c-128">Using Regions</span></span>](using-regions.md)
