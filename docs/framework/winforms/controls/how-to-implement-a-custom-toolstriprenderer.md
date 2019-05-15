---
title: '方法: カスタムの ToolStripRenderer を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: 4a84571bf8b81cd26c864edcd4d313a4009dda16
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592426"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a><span data-ttu-id="a34ff-102">方法: カスタムの ToolStripRenderer を実装する</span><span class="sxs-lookup"><span data-stu-id="a34ff-102">How to: Implement a Custom ToolStripRenderer</span></span>
<span data-ttu-id="a34ff-103"><xref:System.Windows.Forms.ToolStripRenderer> から派生するクラスを実装することで、<xref:System.Windows.Forms.ToolStrip> コントロールの外観をカスタマイズできます</span><span class="sxs-lookup"><span data-stu-id="a34ff-103">You can customize the appearance of a <xref:System.Windows.Forms.ToolStrip> control by implementing a class that derives from <xref:System.Windows.Forms.ToolStripRenderer>.</span></span> <span data-ttu-id="a34ff-104">これによって、<xref:System.Windows.Forms.ToolStripProfessionalRenderer> クラスや <xref:System.Windows.Forms.ToolStripSystemRenderer> クラスで提供される外観とは異なる外観を柔軟に作成できます。</span><span class="sxs-lookup"><span data-stu-id="a34ff-104">This gives you the flexibility to create an appearance that differs from the appearance provided the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> and <xref:System.Windows.Forms.ToolStripSystemRenderer> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a34ff-105">例</span><span class="sxs-lookup"><span data-stu-id="a34ff-105">Example</span></span>  
 <span data-ttu-id="a34ff-106">次のコード例は、カスタムの <xref:System.Windows.Forms.ToolStripRenderer> クラスを実装する方法を示しています</span><span class="sxs-lookup"><span data-stu-id="a34ff-106">The following code example demonstrates how to implement a custom <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="a34ff-107">この例では、`GridStrip` コントロールでタイルをスライドさせるパズルを実装します。これは、ユーザーがテーブル レイアウト内のタイルを移動して 1 つの画像を作成するパズルです。</span><span class="sxs-lookup"><span data-stu-id="a34ff-107">In this example, the `GridStrip` control implements a sliding-tile puzzle, which allows the user to move tiles in a table layout to form an image.</span></span> <span data-ttu-id="a34ff-108">カスタムの <xref:System.Windows.Forms.ToolStrip> コントロールで、グリッド レイアウトの <xref:System.Windows.Forms.ToolStripButton> コントロールを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a34ff-108">A custom <xref:System.Windows.Forms.ToolStrip> control arranges its <xref:System.Windows.Forms.ToolStripButton> controls in a grid layout.</span></span> <span data-ttu-id="a34ff-109">レイアウトには空のセルが 1 つ含まれており、ユーザーは、ドラッグ アンド ドロップ操作を使用することにより、隣接するタイルを空のセルにスライドできます。</span><span class="sxs-lookup"><span data-stu-id="a34ff-109">The layout contains one empty cell, into which the user can slide an adjacent tile by using a drag-and-drop operation.</span></span> <span data-ttu-id="a34ff-110">ユーザーが移動できるタイルは強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="a34ff-110">Tiles that the user can move are highlighted.</span></span>  
  
 <span data-ttu-id="a34ff-111">`GridStripRenderer` クラスでは `GridStrip` コントロールの外観を 3 つの点でカスタマイズしています。</span><span class="sxs-lookup"><span data-stu-id="a34ff-111">The `GridStripRenderer` class customizes three aspects of the `GridStrip` control's appearance:</span></span>  
  
- <span data-ttu-id="a34ff-112">`GridStrip` の境界線</span><span class="sxs-lookup"><span data-stu-id="a34ff-112">`GridStrip` border</span></span>  
  
- <span data-ttu-id="a34ff-113"><xref:System.Windows.Forms.ToolStripButton> の境界線</span><span class="sxs-lookup"><span data-stu-id="a34ff-113"><xref:System.Windows.Forms.ToolStripButton> border</span></span>  
  
- <span data-ttu-id="a34ff-114"><xref:System.Windows.Forms.ToolStripButton> イメージ</span><span class="sxs-lookup"><span data-stu-id="a34ff-114"><xref:System.Windows.Forms.ToolStripButton> image</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a34ff-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="a34ff-115">Compiling the Code</span></span>  
 <span data-ttu-id="a34ff-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a34ff-116">This example requires:</span></span>  
  
- <span data-ttu-id="a34ff-117">System.Drawing アセンブリおよび System.Windows.Forms アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="a34ff-117">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a34ff-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="a34ff-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="a34ff-119">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="a34ff-119">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
