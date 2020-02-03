---
title: DataGridView コントロールのセルの外観をカスタマイズする
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744056"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8e27b-102">方法 : Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8e27b-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8e27b-103"><xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.CellPainting> イベントを処理することで、任意のセルの外観をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8e27b-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="8e27b-104"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>の <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> プロパティから <xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Drawing.Graphics> を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="8e27b-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="8e27b-105">この <xref:System.Drawing.Graphics>では、<xref:System.Windows.Forms.DataGridView> コントロール全体の外観に影響を与えることができますが、通常は、現在描画されているセルの外観のみに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="8e27b-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="8e27b-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> の <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> プロパティを使用すると、描画操作を現在描画されているセルに制限できます。</span><span class="sxs-lookup"><span data-stu-id="8e27b-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="8e27b-107">次のコード例では、<xref:System.Windows.Forms.DataGridView> コントロールの配色を使用して、`ContactName` 列のすべてのセルを塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="8e27b-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="8e27b-108">各セルのテキストコンテンツは <xref:System.Drawing.Color.Crimson%2A>で描画され、埋め込み四角形は、<xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.GridColor%2A> プロパティと同じ色で描画されます。</span><span class="sxs-lookup"><span data-stu-id="8e27b-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e27b-109">例</span><span class="sxs-lookup"><span data-stu-id="8e27b-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e27b-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="8e27b-110">Compiling the Code</span></span>  
 <span data-ttu-id="8e27b-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8e27b-111">This example requires:</span></span>  
  
- <span data-ttu-id="8e27b-112">Northwind サンプルデータベースの Customers テーブルにあるような `ContactName` 列を持つ `dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="8e27b-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
- <span data-ttu-id="8e27b-113">System、System.Windows.Forms、および System.Drawing の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="8e27b-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e27b-114">参照</span><span class="sxs-lookup"><span data-stu-id="8e27b-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="8e27b-115">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8e27b-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
