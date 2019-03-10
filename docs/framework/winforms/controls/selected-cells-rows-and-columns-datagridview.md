---
title: '方法: Windows フォーム DataGridView コントロールで選択したセル、行、および列を取得します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: ad6e704b64e3f25f456b98691dfe12c13f8440a2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713301"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2a798-102">方法: Windows フォーム DataGridView コントロールで選択したセル、行、および列を取得します。</span><span class="sxs-lookup"><span data-stu-id="2a798-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2a798-103">選択したセル、行、または列から取得できます、<xref:System.Windows.Forms.DataGridView>対応するプロパティを使用してコントロール: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>、 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>、および<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>します。</span><span class="sxs-lookup"><span data-stu-id="2a798-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="2a798-104">次の手順では、選択したセルを取得しでその行と列のインデックスを表示、<xref:System.Windows.Forms.MessageBox>します。</span><span class="sxs-lookup"><span data-stu-id="2a798-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="2a798-105">DataGridView コントロールで選択したセルを取得するには</span><span class="sxs-lookup"><span data-stu-id="2a798-105">To get the selected cells in a DataGridView control</span></span>  
  
-   <span data-ttu-id="2a798-106"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a798-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a798-107">使用して、<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>メソッド セル数が大きくなる可能性が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="2a798-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="2a798-108">DataGridView コントロールで選択した行を取得するには</span><span class="sxs-lookup"><span data-stu-id="2a798-108">To get the selected rows in a DataGridView control</span></span>  
  
-   <span data-ttu-id="2a798-109"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a798-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="2a798-110">行を選択するユーザーを有効に設定する必要があります、<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>プロパティを<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>または<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>します。</span><span class="sxs-lookup"><span data-stu-id="2a798-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="2a798-111">DataGridView コントロールで選択した列を取得するには</span><span class="sxs-lookup"><span data-stu-id="2a798-111">To get the selected columns in a DataGridView control</span></span>  
  
-   <span data-ttu-id="2a798-112"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="2a798-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="2a798-113">列を選択するユーザーを有効に設定する必要があります、<xref:System.Windows.Forms.DataGridView.SelectionMode%2A>プロパティを<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>または<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>します。</span><span class="sxs-lookup"><span data-stu-id="2a798-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2a798-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="2a798-114">Compiling the Code</span></span>  
 <span data-ttu-id="2a798-115">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a798-115">This example requires:</span></span>  
  
-   <span data-ttu-id="2a798-116"><xref:System.Windows.Forms.Button> という名前のコントロール`selectedCellsButton`、 `selectedRowsButton`、および`selectedColumnsButton`、それぞれのハンドラーを持つ、<xref:System.Windows.Forms.Control.Click>添付イベント。</span><span class="sxs-lookup"><span data-stu-id="2a798-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
-   <span data-ttu-id="2a798-117">
  `dataGridView1\` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="2a798-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="2a798-118">
  <xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Text?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="2a798-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2a798-119">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="2a798-119">Robust Programming</span></span>  
 <span data-ttu-id="2a798-120">このトピックで説明されているコレクションは実行されません効率的に多数のセル、行、または列を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="2a798-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="2a798-121">大量のデータでこれらのコレクションの使用に関する詳細については、次を参照してください。 [Windows フォーム DataGridView コントロールを拡張するためのベスト プラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="2a798-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a798-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a798-122">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="2a798-123">Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用</span><span class="sxs-lookup"><span data-stu-id="2a798-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
