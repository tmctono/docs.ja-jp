---
title: 'チュートリアル: バインドされていない Windows フォーム DataGridView コントロールを作成する'
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
ms.openlocfilehash: 99561490786f3f3569f272138001ea5ad8937410
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792263"
---
# <a name="walkthrough-creating-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="01e30-102">チュートリアル: バインドされていない Windows フォーム DataGridView コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="01e30-102">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="01e30-103">頻繁にデータベースから表形式のデータを表示することがあります。</span><span class="sxs-lookup"><span data-stu-id="01e30-103">You may frequently want to display tabular data that does not originate from a database.</span></span> <span data-ttu-id="01e30-104">たとえば、文字列の 2 次元配列の内容を表示したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="01e30-104">For example, you may want to show the contents of a two-dimensional array of strings.</span></span> <span data-ttu-id="01e30-105"><xref:System.Windows.Forms.DataGridView>クラスには、データ ソースにバインドせずにデータを表示する簡単で高度にカスタマイズ可能な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="01e30-105">The <xref:System.Windows.Forms.DataGridView> class provides an easy and highly customizable way to display data without binding to a data source.</span></span> <span data-ttu-id="01e30-106">このチュートリアルで作成する方法、<xref:System.Windows.Forms.DataGridView>加算と「バインドされていない」モードでの行の削除制御および管理します。</span><span class="sxs-lookup"><span data-stu-id="01e30-106">This walkthrough shows how to populate a <xref:System.Windows.Forms.DataGridView> control and manage the addition and deletion of rows in "unbound" mode.</span></span> <span data-ttu-id="01e30-107">既定では、ユーザーは、新しい行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="01e30-107">By default, the user can add new rows.</span></span> <span data-ttu-id="01e30-108">行の追加を防ぐためには、設定、<xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>プロパティは`false`します。</span><span class="sxs-lookup"><span data-stu-id="01e30-108">To prevent row addition, set the <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="01e30-109">このトピックのコードを単一のリストとしてコピーするには、「[方法:バインドされていない Windows フォーム DataGridView コントロールの作成](how-to-create-an-unbound-windows-forms-datagridview-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="01e30-109">To copy the code in this topic as a single listing, see [How to: Create an Unbound Windows Forms DataGridView Control](how-to-create-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="01e30-110">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="01e30-110">Creating the Form</span></span>  
  
#### <a name="to-use-an-unbound-datagridview-control"></a><span data-ttu-id="01e30-111">バインドされていない DataGridView コントロールを使用するには</span><span class="sxs-lookup"><span data-stu-id="01e30-111">To use an unbound DataGridView control</span></span>  
  
1. <span data-ttu-id="01e30-112">派生するクラスを作成<xref:System.Windows.Forms.Form>次の変数宣言が含まれていると`Main`メソッド。</span><span class="sxs-lookup"><span data-stu-id="01e30-112">Create a class that derives from <xref:System.Windows.Forms.Form> and contains the following variable declarations and `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2. <span data-ttu-id="01e30-113">実装を`SetupLayout`フォームのレイアウトを設定するフォームのクラス定義内のメソッド。</span><span class="sxs-lookup"><span data-stu-id="01e30-113">Implement a `SetupLayout` method in your form's class definition to set up the form's layout.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3. <span data-ttu-id="01e30-114">作成、`SetupDataGridView`を設定するメソッド、<xref:System.Windows.Forms.DataGridView>列とプロパティ。</span><span class="sxs-lookup"><span data-stu-id="01e30-114">Create a `SetupDataGridView` method to set up the <xref:System.Windows.Forms.DataGridView> columns and properties.</span></span>  
  
     <span data-ttu-id="01e30-115">このメソッドを追加、<xref:System.Windows.Forms.DataGridView>コントロールをフォームの<xref:System.Windows.Forms.Control.Controls%2A>コレクション。</span><span class="sxs-lookup"><span data-stu-id="01e30-115">This method first adds the <xref:System.Windows.Forms.DataGridView> control to the form's <xref:System.Windows.Forms.Control.Controls%2A> collection.</span></span> <span data-ttu-id="01e30-116">次に、表示する列の数を使用してを設定するが、<xref:System.Windows.Forms.DataGridView.ColumnCount%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="01e30-116">Next, the number of columns to be displayed is set using the <xref:System.Windows.Forms.DataGridView.ColumnCount%2A> property.</span></span> <span data-ttu-id="01e30-117">設定して、列ヘッダーの既定のスタイルを設定、 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>、 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>、および<xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>のプロパティ、<xref:System.Windows.Forms.DataGridViewCellStyle>によって返される、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="01e30-117">The default style for the column headers is set by setting the <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A>, and <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> properties of the <xref:System.Windows.Forms.DataGridViewCellStyle> returned by the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> property.</span></span>  
  
     <span data-ttu-id="01e30-118">レイアウトと外観のプロパティが設定されてし、し、列名が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="01e30-118">Layout and appearance properties are set, and then the column names are assigned.</span></span> <span data-ttu-id="01e30-119">このメソッドの終了時に、<xref:System.Windows.Forms.DataGridView>コントロールが事前設定する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="01e30-119">When this method exits, the <xref:System.Windows.Forms.DataGridView> control is ready to be populated.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4. <span data-ttu-id="01e30-120">作成、`PopulateDataGridView`行を追加する方法、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="01e30-120">Create a `PopulateDataGridView` method to add rows to the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="01e30-121">各行は、曲とその関連情報を表します。</span><span class="sxs-lookup"><span data-stu-id="01e30-121">Each row represents a song and its associated information.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5. <span data-ttu-id="01e30-122">インプレース ユーティリティ メソッドを使って、イベント ハンドラーをアタッチできます。</span><span class="sxs-lookup"><span data-stu-id="01e30-122">With the utility methods in place, you can attach event handlers.</span></span>  
  
     <span data-ttu-id="01e30-123">処理する、**追加**と**削除**ボタンの<xref:System.Windows.Forms.Control.Click>イベント、フォームの<xref:System.Windows.Forms.Form.Load>イベント、および<xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.CellFormatting>イベント。</span><span class="sxs-lookup"><span data-stu-id="01e30-123">You will handle the **Add** and **Delete** buttons' <xref:System.Windows.Forms.Control.Click> events, the form's <xref:System.Windows.Forms.Form.Load> event, and the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
     <span data-ttu-id="01e30-124">ときに、**追加**ボタンの<xref:System.Windows.Forms.Control.Click>イベントが発生すると、新しい空の行を追加する、<xref:System.Windows.Forms.DataGridView>します。</span><span class="sxs-lookup"><span data-stu-id="01e30-124">When the **Add** button's <xref:System.Windows.Forms.Control.Click> event is raised, a new, empty row is added to the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="01e30-125">ときに、**削除**ボタンの<xref:System.Windows.Forms.Control.Click>イベントは、選択した行が削除されたである場合を除き、ユーザーは、新しいレコードの行が新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="01e30-125">When the **Delete** button's <xref:System.Windows.Forms.Control.Click> event is raised, the selected row is deleted, unless it is the row for new records, which enables the user add new rows.</span></span> <span data-ttu-id="01e30-126">この行は、最後の行では常に、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="01e30-126">This row is always the last row in the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="01e30-127">ときに、フォームの<xref:System.Windows.Forms.Form.Load>イベントが発生、 `SetupLayout`、 `SetupDataGridView`、および`PopulateDataGridView`ユーティリティ メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="01e30-127">When the form's <xref:System.Windows.Forms.Form.Load> event is raised, the `SetupLayout`, `SetupDataGridView`, and `PopulateDataGridView` utility methods are called.</span></span>  
  
     <span data-ttu-id="01e30-128">ときに、<xref:System.Windows.Forms.DataGridView.CellFormatting>イベントが発生すると、各セルに、`Date`セルの値を解析できない場合を除き、列が長い日付として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="01e30-128">When the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is raised, each cell in the `Date` column is formatted as a long date, unless the cell's value cannot be parsed.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="01e30-129">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="01e30-129">Testing the Application</span></span>  
 <span data-ttu-id="01e30-130">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="01e30-130">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="01e30-131">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="01e30-131">To test the form</span></span>  
  
- <span data-ttu-id="01e30-132">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="01e30-132">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="01e30-133">表示されます、<xref:System.Windows.Forms.DataGridView>記載曲を表示するコントロール`PopulateDataGridView`します。</span><span class="sxs-lookup"><span data-stu-id="01e30-133">You will see a <xref:System.Windows.Forms.DataGridView> control that displays the songs listed in `PopulateDataGridView`.</span></span> <span data-ttu-id="01e30-134">新しい行を追加することができます、**行の追加**で選択した行を削除できます、クリックして、**行の削除**ボタン。</span><span class="sxs-lookup"><span data-stu-id="01e30-134">You can add new rows with the **Add Row** button, and you can delete selected rows with the **Delete Row** button.</span></span> <span data-ttu-id="01e30-135">バインドされていない<xref:System.Windows.Forms.DataGridView>コントロールは、データ ストアとそのデータは任意の外部ソースに依存しないなど、<xref:System.Data.DataSet>または配列。</span><span class="sxs-lookup"><span data-stu-id="01e30-135">The unbound <xref:System.Windows.Forms.DataGridView> control is the data store, and its data is independent of any external source, such as a <xref:System.Data.DataSet> or an array.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="01e30-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="01e30-136">Next Steps</span></span>  
 <span data-ttu-id="01e30-137">このアプリケーションでは、基本を理解、<xref:System.Windows.Forms.DataGridView>コントロールの機能です。</span><span class="sxs-lookup"><span data-stu-id="01e30-137">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="01e30-138">動作と外観をカスタマイズすることができます、<xref:System.Windows.Forms.DataGridView>いくつかの方法で制御します。</span><span class="sxs-lookup"><span data-stu-id="01e30-138">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
- <span data-ttu-id="01e30-139">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="01e30-139">Change border and header styles.</span></span> <span data-ttu-id="01e30-140">詳細については、「[方法 :罫線を変更して、グリッド線のスタイルで、Windows フォーム DataGridView コントロール](change-the-border-and-gridline-styles-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e30-140">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="01e30-141">有効にするか、ユーザー入力を制限、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="01e30-141">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="01e30-142">詳細については、「[方法 :行の追加を回避し、削除を Windows フォーム DataGridView コントロール](prevent-row-addition-and-deletion-datagridview.md)、および[方法。列を読み取り専用の Windows フォーム DataGridView コントロール](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e30-142">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="01e30-143">データベース関連のエラーをユーザー入力を確認します。</span><span class="sxs-lookup"><span data-stu-id="01e30-143">Check user input for database-related errors.</span></span> <span data-ttu-id="01e30-144">詳細については、「[チュートリアル:フォームの DataGridView コントロールを Windows でのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e30-144">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
- <span data-ttu-id="01e30-145">仮想モードを使用して、非常に大きなデータ セットを処理します。</span><span class="sxs-lookup"><span data-stu-id="01e30-145">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="01e30-146">詳細については、「[チュートリアル:仮想モードの実装で、Windows フォーム DataGridView コントロール](implementing-virtual-mode-wf-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e30-146">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
- <span data-ttu-id="01e30-147">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="01e30-147">Customize the appearance of cells.</span></span> <span data-ttu-id="01e30-148">詳細については、「[方法 :Windows フォームの DataGridView コントロール内のセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)と[方法。Windows フォーム DataGridView コントロールの既定のセル スタイルを設定](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="01e30-148">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e30-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="01e30-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="01e30-150">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="01e30-150">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="01e30-151">方法: バインドされていない Windows フォーム DataGridView コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="01e30-151">How to: Create an Unbound Windows Forms DataGridView Control</span></span>](how-to-create-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="01e30-152">Windows フォーム DataGridView コントロールでのデータ表示モード</span><span class="sxs-lookup"><span data-stu-id="01e30-152">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
