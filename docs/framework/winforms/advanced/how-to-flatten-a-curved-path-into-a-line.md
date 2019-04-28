---
title: '方法: 曲線のパスを直線に平坦化する'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781366"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="35373-102">方法: 曲線のパスを直線に平坦化する</span><span class="sxs-lookup"><span data-stu-id="35373-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="35373-103">A<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクトは、一連の行とベジエ スプラインを格納します。</span><span class="sxs-lookup"><span data-stu-id="35373-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="35373-104">パスに曲線 (省略記号、円弧、カーディナル スプライン) のいくつかの種類を追加できますが、パスに格納する前に、各曲線がベジエ スプラインに変換されます。</span><span class="sxs-lookup"><span data-stu-id="35373-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="35373-105">パスをフラット化は、パス内の各本のベジエ スプラインを一連の直線に変換するので構成されます。</span><span class="sxs-lookup"><span data-stu-id="35373-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="35373-106">次の図は前に、とフラット化した後にパスを示します。</span><span class="sxs-lookup"><span data-stu-id="35373-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="35373-107">![直線と曲線](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="35373-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="35373-108">パスをフラット化するには</span><span class="sxs-lookup"><span data-stu-id="35373-108">To Flatten a Path</span></span>  
  
- <span data-ttu-id="35373-109">呼び出す、<xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>のメソッドを<xref:System.Drawing.Drawing2D.GraphicsPath>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="35373-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="35373-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>メソッドは、フラット化されたパスと元のパスの最大距離を指定する平坦度引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="35373-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35373-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="35373-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="35373-112">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="35373-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="35373-113">パスの作成および描画</span><span class="sxs-lookup"><span data-stu-id="35373-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
