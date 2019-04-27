---
title: GDI+ での描画サーフェイスの制限
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672641"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="c1f41-102">GDI+ での描画サーフェイスの制限</span><span class="sxs-lookup"><span data-stu-id="c1f41-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="c1f41-103">クリッピングでは、描画を四角形または領域を制限します。</span><span class="sxs-lookup"><span data-stu-id="c1f41-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="c1f41-104">次の図、文字列「こんにちは」ハート形の領域にクリップされます。</span><span class="sxs-lookup"><span data-stu-id="c1f41-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="c1f41-105">![制限付き描画面](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="c1f41-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="c1f41-106">領域でクリッピング</span><span class="sxs-lookup"><span data-stu-id="c1f41-106">Clipping with Regions</span></span>  
 <span data-ttu-id="c1f41-107">パスからリージョンを作成し、クリッピングを中抜きの文字列を使用できるように、パスは、文字列のアウトラインを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c1f41-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="c1f41-108">次の図は、一連の同心構造の省略記号のテキスト文字列の内部に切り取られます。</span><span class="sxs-lookup"><span data-stu-id="c1f41-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="c1f41-109">![制限付き描画面](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="c1f41-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="c1f41-110">クリッピングを描画するには、作成、<xref:System.Drawing.Graphics>オブジェクト、設定、<xref:System.Drawing.Graphics.Clip%2A>プロパティをその描画メソッドを呼び出して同じ<xref:System.Drawing.Graphics>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1f41-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="c1f41-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1f41-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="c1f41-112">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="c1f41-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="c1f41-113">領域の使用</span><span class="sxs-lookup"><span data-stu-id="c1f41-113">Using Regions</span></span>](using-regions.md)
