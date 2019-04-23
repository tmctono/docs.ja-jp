---
title: '方法: Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 415cf18aa4cf01b151a414dbc26609af638a7af7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213286"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="919c2-102">方法: Windows フォームの DataGridView コントロールのセルの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="919c2-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="919c2-103">任意のセルの外観をカスタマイズするには処理することによって、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.CellPainting>イベント。</span><span class="sxs-lookup"><span data-stu-id="919c2-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="919c2-104">抽出することができます、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Drawing.Graphics>から、<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A>のプロパティ、<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="919c2-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="919c2-105">この<xref:System.Drawing.Graphics>、全体の外観に影響を及ぼすことができます<xref:System.Windows.Forms.DataGridView>コントロールは通常するには描画されるセルの外観だけに影響します。</span><span class="sxs-lookup"><span data-stu-id="919c2-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="919c2-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>のプロパティ、<xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>描画されるセルに、描画操作を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="919c2-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="919c2-107">次のコード例では、すべてのセルを描画します、`ContactName`列を使用して、<xref:System.Windows.Forms.DataGridView>コントロールの色のスキーム。</span><span class="sxs-lookup"><span data-stu-id="919c2-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="919c2-108">各セルのテキスト コンテンツが描画される<xref:System.Drawing.Color.Crimson%2A>と同じ色に埋め込みの四角形が描画されると、<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.GridColor%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="919c2-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="919c2-109">例</span><span class="sxs-lookup"><span data-stu-id="919c2-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="919c2-110">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="919c2-110">Compiling the Code</span></span>  
 <span data-ttu-id="919c2-111">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="919c2-111">This example requires:</span></span>  
  
-   <span data-ttu-id="919c2-112">A<xref:System.Windows.Forms.DataGridView>という名前のコントロール`dataGridView1`で、`ContactName`など、Northwind サンプル データベースの Customers テーブルの列。</span><span class="sxs-lookup"><span data-stu-id="919c2-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="919c2-113">System、System.Windows.Forms、および System.Drawing の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="919c2-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="919c2-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="919c2-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [<span data-ttu-id="919c2-115">Windows フォーム DataGridView コントロールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="919c2-115">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
