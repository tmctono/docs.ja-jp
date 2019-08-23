---
title: '方法: Windows フォーム DataGridView コントロールの選択されたセル、行、および列を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 25b3ed50081add77b9f522ca8e597f2b3306cb2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960514"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="30bb9-102">方法: Windows フォーム DataGridView コントロールの選択されたセル、行、および列を取得する</span><span class="sxs-lookup"><span data-stu-id="30bb9-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="30bb9-103"><xref:System.Windows.Forms.DataGridView>コントロールから選択されたセル、行、または列を取得するには<xref:System.Windows.Forms.DataGridView.SelectedCells%2A>、対応する<xref:System.Windows.Forms.DataGridView.SelectedRows%2A>プロパティで<xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>ある、、およびを使用します。</span><span class="sxs-lookup"><span data-stu-id="30bb9-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="30bb9-104">次の手順では、選択したセルを取得し、そのセルの行インデックスと<xref:System.Windows.Forms.MessageBox>列インデックスをに表示します。</span><span class="sxs-lookup"><span data-stu-id="30bb9-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="30bb9-105">DataGridView コントロール内の選択されたセルを取得するには</span><span class="sxs-lookup"><span data-stu-id="30bb9-105">To get the selected cells in a DataGridView control</span></span>  
  
- <span data-ttu-id="30bb9-106"><xref:System.Windows.Forms.DataGridView.SelectedCells%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="30bb9-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="30bb9-107">多くの<xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>セルが表示されないようにするには、メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="30bb9-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="30bb9-108">DataGridView コントロールで選択された行を取得するには</span><span class="sxs-lookup"><span data-stu-id="30bb9-108">To get the selected rows in a DataGridView control</span></span>  
  
- <span data-ttu-id="30bb9-109"><xref:System.Windows.Forms.DataGridView.SelectedRows%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="30bb9-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="30bb9-110">ユーザーが行を選択できるようにするには<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 、プロパティ<xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>を<xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>またはに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30bb9-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="30bb9-111">DataGridView コントロールで選択されている列を取得するには</span><span class="sxs-lookup"><span data-stu-id="30bb9-111">To get the selected columns in a DataGridView control</span></span>  
  
- <span data-ttu-id="30bb9-112"><xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="30bb9-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="30bb9-113">ユーザーが列を選択できるようにするには<xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 、プロパティ<xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>を<xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>またはに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30bb9-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30bb9-114">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="30bb9-114">Compiling the Code</span></span>  
 <span data-ttu-id="30bb9-115">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="30bb9-115">This example requires:</span></span>  
  
- <span data-ttu-id="30bb9-116"><xref:System.Windows.Forms.Button>、 `selectedCellsButton` 、`selectedRowsButton`および<xref:System.Windows.Forms.Control.Click>という名前のコントロール。それぞれに、アタッチされるイベントのハンドラーがあります。 `selectedColumnsButton`</span><span class="sxs-lookup"><span data-stu-id="30bb9-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
- <span data-ttu-id="30bb9-117">`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView> コントロール。</span><span class="sxs-lookup"><span data-stu-id="30bb9-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="30bb9-118"><xref:System?displayProperty=nameWithType>、<xref:System.Windows.Forms?displayProperty=nameWithType>、および <xref:System.Text?displayProperty=nameWithType> の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="30bb9-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="30bb9-119">信頼性の高いプログラミング</span><span class="sxs-lookup"><span data-stu-id="30bb9-119">Robust Programming</span></span>  
 <span data-ttu-id="30bb9-120">このトピックで説明するコレクションは、多数のセル、行、または列が選択されている場合は、効率的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="30bb9-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="30bb9-121">大量のデータでこれらのコレクションを使用する方法の詳細については、「 [Windows フォーム DataGridView コントロールのスケーリングに関するベストプラクティス](best-practices-for-scaling-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bb9-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30bb9-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="30bb9-122">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [<span data-ttu-id="30bb9-123">Windows フォーム DataGridView コントロールでの選択およびクリップボードの使用</span><span class="sxs-lookup"><span data-stu-id="30bb9-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
