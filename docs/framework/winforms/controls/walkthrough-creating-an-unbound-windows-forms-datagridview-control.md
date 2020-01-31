---
title: バインドしていない DataGridView コントロールを作成する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], displaying without binding to data source
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
ms.openlocfilehash: ceb75d4ee845d1f643d4d88d5a9f1bde73edcc70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740179"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="065b4-102">チュートリアル : バインドされていない Windows フォーム DataGridView コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="065b4-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="065b4-103">データベースから生成されていない表形式のデータを表示することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="065b4-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="065b4-104">たとえば、文字列の2次元配列の内容を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="065b4-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="065b4-105"><xref:System.Windows.Forms.DataGridView> クラスを使用すると、データソースにバインドせずに、簡単かつ高度にカスタマイズ可能な方法でデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="065b4-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="065b4-106">このチュートリアルでは、<xref:System.Windows.Forms.DataGridView> コントロールにデータを設定し、"非バインド" モードで行の追加と削除を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="065b4-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="065b4-107">既定では、ユーザーは新しい行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="065b4-107">By default, the user can add new rows.</span></span> <span data-ttu-id="065b4-108">行が追加されないようにするには、<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> プロパティを `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="065b4-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="065b4-109">このトピックのコードを単一のリストとしてコピーする方法については、「方法: バインドされていない[Windows フォーム DataGridView コントロールを作成](how-to-create-an-unbound-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="065b4-110">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="065b4-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="065b4-111">バインドされていない DataGridView コントロールを使用するには</span><span class="sxs-lookup"><span data-stu-id="065b4-111">To use an unbound DataGridView control</span></span>  
  
1. <span data-ttu-id="065b4-112"><xref:System.Windows.Forms.Form> から派生し、次の変数宣言と `Main` メソッドを含むクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="065b4-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. <span data-ttu-id="065b4-113">フォームのクラス定義に `SetupLayout` メソッドを実装して、フォームのレイアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="065b4-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. <span data-ttu-id="065b4-114"><xref:System.Windows.Forms.DataGridView> の列およびプロパティを設定する `SetupDataGridView` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="065b4-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="065b4-115">このメソッドは、まず、フォームの <xref:System.Windows.Forms.Control.Controls%2A> コレクションに <xref:System.Windows.Forms.DataGridView> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="065b4-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="065b4-116">次に、<xref:System.Windows.Forms.DataGridView.ColumnCount%2A> プロパティを使用して、表示する列の数を設定します。</span><span class="sxs-lookup"><span data-stu-id="065b4-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="065b4-117">列ヘッダーの既定のスタイルは、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> プロパティによって返される <xref:System.Windows.Forms.DataGridViewCellStyle> の <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>、<xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>、および <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> の各プロパティを設定することによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="065b4-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="065b4-118">レイアウトと外観のプロパティが設定され、列名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="065b4-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="065b4-119">このメソッドが終了すると、<xref:System.Windows.Forms.DataGridView> コントロールを設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="065b4-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <span data-ttu-id="065b4-120"><xref:System.Windows.Forms.DataGridView> コントロールに行を追加する `PopulateDataGridView` メソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="065b4-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="065b4-121">各行は、曲とそれに関連付けられた情報を表します。</span><span class="sxs-lookup"><span data-stu-id="065b4-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. <span data-ttu-id="065b4-122">ユーティリティメソッドを配置すると、イベントハンドラーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="065b4-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="065b4-123">**[追加]** ボタンと **[削除]** ボタンの <xref:System.Windows.Forms.Control.Click> イベント、フォームの <xref:System.Windows.Forms.Form.Load> イベント、および <xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.CellFormatting> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="065b4-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="065b4-124">**[追加]** ボタンの <xref:System.Windows.Forms.Control.Click> イベントが発生すると、新しい空の行が <xref:System.Windows.Forms.DataGridView>に追加されます。</span><span class="sxs-lookup"><span data-stu-id="065b4-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="065b4-125">**[削除]** ボタンの <xref:System.Windows.Forms.Control.Click> イベントが発生すると、選択した行が削除されます。ただし、新しいレコードの行でない限り、ユーザーは新しい行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="065b4-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="065b4-126">この行は常に、<xref:System.Windows.Forms.DataGridView> コントロールの最後の行になります。</span><span class="sxs-lookup"><span data-stu-id="065b4-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="065b4-127">フォームの <xref:System.Windows.Forms.Form.Load> イベントが発生すると、`SetupLayout`、`SetupDataGridView`、および `PopulateDataGridView` ユーティリティメソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="065b4-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="065b4-128"><xref:System.Windows.Forms.DataGridView.CellFormatting> イベントが発生した場合、セルの値を解析できない場合を除き、`Date` 列の各セルは長い日付形式として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="065b4-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="065b4-129">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="065b4-129">Testing the Application</span></span>  
 <span data-ttu-id="065b4-130">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="065b4-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="065b4-131">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="065b4-131">To test the form</span></span>  
  
- <span data-ttu-id="065b4-132">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="065b4-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="065b4-133">`PopulateDataGridView`に表示されている曲を表示する <xref:System.Windows.Forms.DataGridView> コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="065b4-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="065b4-134">**[行の追加]** ボタンを使用して新しい行を追加できます。また、 **[行の削除]** ボタンを使用して、選択した行を削除できます。</span><span class="sxs-lookup"><span data-stu-id="065b4-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="065b4-135">バインドされていない <xref:System.Windows.Forms.DataGridView> コントロールはデータストアであり、そのデータは、<xref:System.Data.DataSet> や配列などの外部ソースからは独立しています。</span><span class="sxs-lookup"><span data-stu-id="065b4-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="065b4-136">次のステップ</span><span class="sxs-lookup"><span data-stu-id="065b4-136">Next Steps</span></span>  
 <span data-ttu-id="065b4-137">このアプリケーションでは、<xref:System.Windows.Forms.DataGridView> コントロールの機能についての基本的な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="065b4-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="065b4-138"><xref:System.Windows.Forms.DataGridView> コントロールの外観と動作は、次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="065b4-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="065b4-139">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="065b4-139">Change border and header styles.</span></span> <span data-ttu-id="065b4-140">詳細については、「[方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="065b4-141"><xref:System.Windows.Forms.DataGridView> コントロールへのユーザー入力を有効または制限します。</span><span class="sxs-lookup"><span data-stu-id="065b4-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="065b4-142">詳細については、「[方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「[方法: Windows フォーム Datagridview コントロールで列を読み取り](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)専用にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="065b4-143">データベース関連のエラーについては、ユーザー入力を確認してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-143">Check user input for database-related errors.</span></span> <span data-ttu-id="065b4-144">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="065b4-145">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="065b4-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="065b4-146">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="065b4-147">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="065b4-147">Customize the appearance of cells.</span></span> <span data-ttu-id="065b4-148">詳細については、「[方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)する」および「[方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="065b4-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="065b4-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="065b4-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="065b4-150">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="065b4-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="065b4-151">方法: 連結されていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="065b4-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="065b4-152">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="065b4-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
