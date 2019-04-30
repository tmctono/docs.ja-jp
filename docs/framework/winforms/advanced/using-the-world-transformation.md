---
title: ワールド変換の使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969144"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="f15b9-102">ワールド変換の使用</span><span class="sxs-lookup"><span data-stu-id="f15b9-102">Using the World Transformation</span></span>
<span data-ttu-id="f15b9-103">ワールド変換のプロパティである、<xref:System.Drawing.Graphics>クラス。</span><span class="sxs-lookup"><span data-stu-id="f15b9-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="f15b9-104">ワールド変換を指定する数値が格納されている、<xref:System.Drawing.Drawing2D.Matrix>オブジェクトで、3 × 3 行列を表します。</span><span class="sxs-lookup"><span data-stu-id="f15b9-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="f15b9-105"><xref:System.Drawing.Drawing2D.Matrix>と<xref:System.Drawing.Graphics>クラス ワールド変換行列の数値を設定するためのいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f15b9-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="f15b9-106">異なる種類の変換</span><span class="sxs-lookup"><span data-stu-id="f15b9-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="f15b9-107">次の例では、コードは、最初 50 × 50 四角形を作成し、その原点 (0, 0)。</span><span class="sxs-lookup"><span data-stu-id="f15b9-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="f15b9-108">原点は、クライアント領域の左上隅にあること。</span><span class="sxs-lookup"><span data-stu-id="f15b9-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="f15b9-109">次のコードでは、x 方向に 1.75 倍、四角形を拡大し、y 方向に 0.5 倍で、四角形を縮小するためのスケーリング変換を適用します。</span><span class="sxs-lookup"><span data-stu-id="f15b9-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="f15b9-110">X 方向に時間が長く、y 方向の元よりも短いとなる四角形になります。</span><span class="sxs-lookup"><span data-stu-id="f15b9-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="f15b9-111">スケールではなく四角形を回転するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f15b9-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="f15b9-112">四角形を変換するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f15b9-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="f15b9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f15b9-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="f15b9-114">座標系と変換</span><span class="sxs-lookup"><span data-stu-id="f15b9-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="f15b9-115">マネージド GDI+ での変換の使用</span><span class="sxs-lookup"><span data-stu-id="f15b9-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
