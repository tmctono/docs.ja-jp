---
title: DataGridView コントロールで選択されたセル、行、および列を取得します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 0079c590ee6e4732523fd50be157bd58ec1bfb1b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743073"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="4c29e-102">方法 : Windows フォーム DataGridView コントロールの選択されたセル、行、および列を取得する</span><span class="sxs-lookup"><span data-stu-id="4c29e-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="4c29e-103">選択したセル、行、または列は、対応するプロパティ (<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>、<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>、および <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>) を使用して、<xref:System.Windows.Forms.DataGridView> コントロールから取得できます。</span><span class="sxs-lookup"><span data-stu-id="4c29e-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="4c29e-104">次の手順では、選択したセルを取得し、そのセルの行インデックスと列インデックスを <xref:System.Windows.Forms.MessageBox>に表示します。</span><span class="sxs-lookup"><span data-stu-id="4c29e-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="4c29e-105">DataGridView コントロール内の選択されたセルを取得するには</span><span class="sxs-lookup"><span data-stu-id="4c29e-105">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="4c29e-106"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c29e-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4c29e-107">多くのセルが表示されないようにするには、<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c29e-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="4c29e-108">DataGridView コントロールで選択された行を取得するには</span><span class="sxs-lookup"><span data-stu-id="4c29e-108">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="4c29e-109"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c29e-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="4c29e-110">ユーザーが行を選択できるようにするには、<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> プロパティを <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> または <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c29e-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="4c29e-111">DataGridView コントロールで選択されている列を取得するには</span><span class="sxs-lookup"><span data-stu-id="4c29e-111">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="4c29e-112"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c29e-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="4c29e-113">ユーザーが列を選択できるようにするには、<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> プロパティを <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> または <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c29e-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c29e-114">コードのコンパイル方法</span><span class="sxs-lookup"><span data-stu-id="4c29e-114">Compiling the Code</span></span>  
 <span data-ttu-id="4c29e-115">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c29e-115">This example requires:</span></span>  
  
- <span data-ttu-id="4c29e-116">`selectedCellsButton`、`selectedRowsButton`、および `selectedColumnsButton`という名前のコントロールを <xref:System.Windows.Forms.Button> します。各コントロールには、アタッチされている <xref:System.Windows.Forms.Control.Click> イベントのハンドラーがあります。</span><span class="sxs-lookup"><span data-stu-id="4c29e-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="4c29e-117">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="4c29e-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="4c29e-118"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Text?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="4c29e-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4c29e-119">堅牢性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="4c29e-119">Robust Programming</span></span>  
 <span data-ttu-id="4c29e-120">このトピックで説明するコレクションは、多数のセル、行、または列が選択されている場合は、効率的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="4c29e-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="4c29e-121">大量のデータでこれらのコレクションを使用する方法の詳細については、「 [Windows フォーム DataGridView コントロールのスケーリングに関するベストプラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c29e-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c29e-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c29e-122">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="4c29e-123">Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用</span><span class="sxs-lookup"><span data-stu-id="4c29e-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
