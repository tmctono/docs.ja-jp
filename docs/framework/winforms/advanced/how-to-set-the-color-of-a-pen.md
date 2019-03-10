---
title: '方法: ペンの色を設定します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: a2645112950be88cbc569e0be7889c0f1019223d
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710387"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="95e50-102">方法: ペンの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="95e50-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="95e50-103">この例は、既存の色を変更<xref:System.Drawing.Pen>オブジェクト</span><span class="sxs-lookup"><span data-stu-id="95e50-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="95e50-104">例</span><span class="sxs-lookup"><span data-stu-id="95e50-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="95e50-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="95e50-105">Compiling the Code</span></span>  
 <span data-ttu-id="95e50-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="95e50-106">This example requires:</span></span>  
  
-   <span data-ttu-id="95e50-107">A<xref:System.Drawing.Pen>という名前のオブジェクト`myPen`します。</span><span class="sxs-lookup"><span data-stu-id="95e50-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="95e50-108">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="95e50-108">Robust Programming</span></span>  
 <span data-ttu-id="95e50-109">呼び出す必要があります<xref:System.Drawing.Pen.Dispose%2A>システム リソースを消費するオブジェクト (など<xref:System.Drawing.Pen>オブジェクト) を使用してそれらが完了した後。</span><span class="sxs-lookup"><span data-stu-id="95e50-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e50-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="95e50-110">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="95e50-111">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="95e50-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="95e50-112">方法: ペンを作成します。</span><span class="sxs-lookup"><span data-stu-id="95e50-112">How to: Create a Pen</span></span>](how-to-create-a-pen.md)
- [<span data-ttu-id="95e50-113">ペンを使用した直線と図形の描画</span><span class="sxs-lookup"><span data-stu-id="95e50-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="95e50-114">GDI+ でのペン、直線、および四角形</span><span class="sxs-lookup"><span data-stu-id="95e50-114">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
