---
title: '方法: DataGrid コントロールを使用して検証を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], validation
- validation [WPF], DataGrid
ms.assetid: ec6078a8-1e42-4648-b414-f4348e81bda1
ms.openlocfilehash: 8ae651b3085b39673a51cf8d5f65e9bfb9da87d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962041"
---
# <a name="how-to-implement-validation-with-the-datagrid-control"></a><span data-ttu-id="f11da-102">方法: DataGrid コントロールを使用して検証を実装する</span><span class="sxs-lookup"><span data-stu-id="f11da-102">How to: Implement Validation with the DataGrid Control</span></span>
<span data-ttu-id="f11da-103"><xref:System.Windows.Controls.DataGrid>コントロールを使用すると、セルレベルと行レベルの両方で検証を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f11da-103">The <xref:System.Windows.Controls.DataGrid> control enables you to perform validation at both the cell and row level.</span></span> <span data-ttu-id="f11da-104">セルレベルの検証では、ユーザーが値を更新するときに、バインドされたデータオブジェクトの個々のプロパティを検証します。</span><span class="sxs-lookup"><span data-stu-id="f11da-104">With cell-level validation, you validate individual properties of a bound data object when a user updates a value.</span></span> <span data-ttu-id="f11da-105">行レベルの検証では、ユーザーが変更を行にコミットするときに、データオブジェクト全体を検証します。</span><span class="sxs-lookup"><span data-stu-id="f11da-105">With row-level validation, you validate entire data objects when a user commits changes to a row.</span></span> <span data-ttu-id="f11da-106">また、検証エラーに対してカスタマイズされた視覚的フィードバックを提供したり、コントロール<xref:System.Windows.Controls.DataGrid>が提供する既定のビジュアルフィードバックを使用したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f11da-106">You can also provide customized visual feedback for validation errors, or use the default visual feedback that the <xref:System.Windows.Controls.DataGrid> control provides.</span></span>  
  
 <span data-ttu-id="f11da-107">次の手順では、バインディングに<xref:System.Windows.Controls.DataGrid>検証規則を適用し、視覚的なフィードバックをカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f11da-107">The following procedures describe how to apply validation rules to <xref:System.Windows.Controls.DataGrid> bindings and customize the visual feedback.</span></span>  
  
### <a name="to-validate-individual-cell-values"></a><span data-ttu-id="f11da-108">個々のセル値を検証するには</span><span class="sxs-lookup"><span data-stu-id="f11da-108">To validate individual cell values</span></span>  
  
- <span data-ttu-id="f11da-109">列で使用するバインディングに対して1つ以上の検証規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="f11da-109">Specify one or more validation rules on the binding used with a column.</span></span> <span data-ttu-id="f11da-110">これは、「[データバインディングの概要](../data/data-binding-overview.md)」で説明されているように、単純なコントロールでのデータの検証に似ています。</span><span class="sxs-lookup"><span data-stu-id="f11da-110">This is similar to validating data in simple controls, as described in [Data Binding Overview](../data/data-binding-overview.md).</span></span>  
  
     <span data-ttu-id="f11da-111">次の例は、 <xref:System.Windows.Controls.DataGrid>ビジネスオブジェクトのさまざまなプロパティにバインドされた4つの列を持つコントロールを示しています。</span><span class="sxs-lookup"><span data-stu-id="f11da-111">The following example shows a <xref:System.Windows.Controls.DataGrid> control with four columns bound to different properties of a business object.</span></span> <span data-ttu-id="f11da-112">列のうち3つは<xref:System.Windows.Controls.ExceptionValidationRule> 、 <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>プロパティをに設定`true`することによって指定します。</span><span class="sxs-lookup"><span data-stu-id="f11da-112">Three of the columns specify the <xref:System.Windows.Controls.ExceptionValidationRule> by setting the <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> property to `true`.</span></span>  
  
     [!code-xaml[DataGrid_Validation#BasicXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/window1.xaml#basicxaml)]  
  
     <span data-ttu-id="f11da-113">ユーザーが無効な値 ([Course ID] 列に整数以外の値) を入力すると、そのセルの周囲に赤い枠線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f11da-113">When a user enters an invalid value (such as a non-integer in the Course ID column), a red border appears around the cell.</span></span> <span data-ttu-id="f11da-114">この既定の検証フィードバックは、次の手順に従って変更できます。</span><span class="sxs-lookup"><span data-stu-id="f11da-114">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-cell-validation-feedback"></a><span data-ttu-id="f11da-115">セルの検証に関するフィードバックをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f11da-115">To customize cell validation feedback</span></span>  
  
- <span data-ttu-id="f11da-116">列の<xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A>プロパティを、列の編集コントロールに適したスタイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="f11da-116">Set the column's <xref:System.Windows.Controls.DataGridBoundColumn.EditingElementStyle%2A> property to a style appropriate for the column's editing control.</span></span> <span data-ttu-id="f11da-117">編集コントロールは実行時に作成されるため、単純なコントロール<xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType>の場合と同様に、添付プロパティを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f11da-117">Because the editing controls are created at run time, you cannot use the <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> attached property like you would with simple controls.</span></span>  
  
     <span data-ttu-id="f11da-118">次の例では、検証規則を持つ3つの列によって共有されているエラースタイルを追加して、前の例を更新します。</span><span class="sxs-lookup"><span data-stu-id="f11da-118">The following example updates the previous example by adding an error style shared by the three columns with validation rules.</span></span> <span data-ttu-id="f11da-119">ユーザーが無効な値を入力すると、スタイルによってセルの背景色が変更され、ツールヒントが追加されます。</span><span class="sxs-lookup"><span data-stu-id="f11da-119">When a user enters an invalid value, the style changes the cell background color and adds a ToolTip.</span></span> <span data-ttu-id="f11da-120">トリガーを使用して、検証エラーが発生しているかどうかを確認することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f11da-120">Note the use of a trigger to determine whether there is a validation error.</span></span> <span data-ttu-id="f11da-121">これは、セルに専用のエラーテンプレートがないために必要です。</span><span class="sxs-lookup"><span data-stu-id="f11da-121">This is required because there is currently no dedicated error template for cells.</span></span>  
  
     [!code-xaml[DataGrid_Validation#CellValidationXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#cellvalidationxaml)]  
  
     <span data-ttu-id="f11da-122">列によって使用されるを置き換える<xref:System.Windows.Controls.DataGridColumn.CellStyle%2A>ことで、より広範なカスタマイズを実装できます。</span><span class="sxs-lookup"><span data-stu-id="f11da-122">You can implement more extensive customization by replacing the <xref:System.Windows.Controls.DataGridColumn.CellStyle%2A> used by the column.</span></span>  
  
### <a name="to-validate-multiple-values-in-a-single-row"></a><span data-ttu-id="f11da-123">1つの行で複数の値を検証するには</span><span class="sxs-lookup"><span data-stu-id="f11da-123">To validate multiple values in a single row</span></span>  
  
1. <span data-ttu-id="f11da-124">バインドさ<xref:System.Windows.Controls.ValidationRule>れたデータオブジェクトの複数のプロパティをチェックするサブクラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f11da-124">Implement a <xref:System.Windows.Controls.ValidationRule> subclass that checks multiple properties of the bound data object.</span></span> <span data-ttu-id="f11da-125">メソッドの実装では、 `value`パラメーター値を<xref:System.Windows.Data.BindingGroup>インスタンスにキャストします。 <xref:System.Windows.Controls.ValidationRule.Validate%2A></span><span class="sxs-lookup"><span data-stu-id="f11da-125">In your <xref:System.Windows.Controls.ValidationRule.Validate%2A> method implementation, cast the `value` parameter value to a <xref:System.Windows.Data.BindingGroup> instance.</span></span> <span data-ttu-id="f11da-126">その後、 <xref:System.Windows.Data.BindingGroup.Items%2A>プロパティを使用してデータオブジェクトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f11da-126">You can then access the data object through the <xref:System.Windows.Data.BindingGroup.Items%2A> property.</span></span>  
  
     <span data-ttu-id="f11da-127">次の例では、 `StartDate` `Course`オブジェクトのプロパティ値がその`EndDate`プロパティ値よりも前であるかどうかを検証するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="f11da-127">The following example demonstrates this process to validate whether the `StartDate` property value for a `Course` object is earlier than its `EndDate` property value.</span></span>  
  
     [!code-csharp[DataGrid_Validation#CourseValidationRule](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#coursevalidationrule)]
     [!code-vb[DataGrid_Validation#CourseValidationRule](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#coursevalidationrule)]  
  
2. <span data-ttu-id="f11da-128">検証規則を<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType>コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f11da-128">Add the validation rule to the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="f11da-129">プロパティ<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A>は、コントロールによって<xref:System.Windows.Data.BindingGroup.ValidationRules%2A>使用される<xref:System.Windows.Data.BindingGroup>すべてのバインドをグループ化するインスタンスのプロパティへの直接アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f11da-129">The <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property provides direct access to the <xref:System.Windows.Data.BindingGroup.ValidationRules%2A> property of a <xref:System.Windows.Data.BindingGroup> instance that groups all the bindings used by the control.</span></span>  
  
     <span data-ttu-id="f11da-130">次の例では<xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> 、XAML でプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f11da-130">The following example sets the <xref:System.Windows.Controls.DataGrid.RowValidationRules%2A> property in XAML.</span></span> <span data-ttu-id="f11da-131">プロパティはに<xref:System.Windows.Controls.ValidationStep.UpdatedValue>設定されています。これにより、バインドされたデータオブジェクトが更新された後にのみ検証が行われるようになります。 <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A></span><span class="sxs-lookup"><span data-stu-id="f11da-131">The <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> property is set to <xref:System.Windows.Controls.ValidationStep.UpdatedValue> so that the validation occurs only after the bound data object is updated.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationRulesXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationrulesxaml)]  
  
     <span data-ttu-id="f11da-132">ユーザーが開始日よりも前の終了日を指定すると、行ヘッダーに赤い感嘆符 (!) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f11da-132">When a user specifies an end date that is earlier than the start date, a red exclamation mark (!) appears in the row header.</span></span> <span data-ttu-id="f11da-133">この既定の検証フィードバックは、次の手順に従って変更できます。</span><span class="sxs-lookup"><span data-stu-id="f11da-133">You can change this default validation feedback as described in the following procedure.</span></span>  
  
### <a name="to-customize-row-validation-feedback"></a><span data-ttu-id="f11da-134">行の検証に関するフィードバックをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="f11da-134">To customize row validation feedback</span></span>  
  
- <span data-ttu-id="f11da-135"><xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f11da-135">Set the <xref:System.Windows.Controls.DataGrid.RowValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f11da-136">このプロパティを使用すると、個々<xref:System.Windows.Controls.DataGrid>のコントロールに対する行の検証フィードバックをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f11da-136">This property enables you to customize row validation feedback for individual <xref:System.Windows.Controls.DataGrid> controls.</span></span> <span data-ttu-id="f11da-137">また、暗黙的な行スタイルを使用してプロパティを設定すること<xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType>によって、複数のコントロールに影響を与えることもできます。</span><span class="sxs-lookup"><span data-stu-id="f11da-137">You can also affect multiple controls by using an implicit row style to set the <xref:System.Windows.Controls.DataGridRow.ValidationErrorTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     <span data-ttu-id="f11da-138">次の例では、行の検証に関する既定のフィードバックを、よりわかりやすいインジケーターに置き換えています。</span><span class="sxs-lookup"><span data-stu-id="f11da-138">The following example replaces the default row validation feedback with a more visible indicator.</span></span> <span data-ttu-id="f11da-139">ユーザーが無効な値を入力すると、行ヘッダーに白い感嘆符を含む赤い円が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f11da-139">When a user enters an invalid value, a red circle with a white exclamation mark appears in the row header.</span></span> <span data-ttu-id="f11da-140">これは、行とセルの両方の検証エラーに対して発生します。</span><span class="sxs-lookup"><span data-stu-id="f11da-140">This occurs for both row and cell validation errors.</span></span> <span data-ttu-id="f11da-141">関連するエラーメッセージがツールヒントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f11da-141">The associated error message is displayed in a ToolTip.</span></span>  
  
     [!code-xaml[DataGrid_Validation#RowValidationFeedbackXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#rowvalidationfeedbackxaml)]  
  
## <a name="example"></a><span data-ttu-id="f11da-142">例</span><span class="sxs-lookup"><span data-stu-id="f11da-142">Example</span></span>  
 <span data-ttu-id="f11da-143">次の例では、セルと行の検証の完全なデモを示します。</span><span class="sxs-lookup"><span data-stu-id="f11da-143">The following example provides a complete demonstration for cell and row validation.</span></span> <span data-ttu-id="f11da-144">クラス`Course`には、トランザクションをサポートするため<xref:System.ComponentModel.IEditableObject>にを実装するサンプルデータオブジェクトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f11da-144">The `Course` class provides a sample data object that implements <xref:System.ComponentModel.IEditableObject> to support transactions.</span></span> <span data-ttu-id="f11da-145">コントロール<xref:System.Windows.Controls.DataGrid>はと<xref:System.ComponentModel.IEditableObject>対話し、ユーザーが ESC キーを押して変更を元に戻すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="f11da-145">The <xref:System.Windows.Controls.DataGrid> control interacts with <xref:System.ComponentModel.IEditableObject> to enable users to revert changes by pressing ESC.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f11da-146">Visual Basic を使用している場合は、mainwindow.xaml の最初の行でを`x:Class="DataGridValidation.MainWindow"`に`x:Class="MainWindow"`置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f11da-146">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridValidation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
 <span data-ttu-id="f11da-147">検証をテストするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="f11da-147">To test the validation, try the following:</span></span>  
  
- <span data-ttu-id="f11da-148">[Course ID] 列に、整数以外の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="f11da-148">In the Course ID column, enter a non-integer value.</span></span>  
  
- <span data-ttu-id="f11da-149">[終了日] 列に、開始日よりも前の日付を入力します。</span><span class="sxs-lookup"><span data-stu-id="f11da-149">In the End Date column, enter a date that is earlier than the Start Date.</span></span>  
  
- <span data-ttu-id="f11da-150">コース ID、開始日、または終了日の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="f11da-150">Delete the value in Course ID, Start Date, or End Date.</span></span>  
  
- <span data-ttu-id="f11da-151">無効なセル値を元に戻すには、セルにカーソルを置き、ESC キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f11da-151">To undo an invalid cell value, put the cursor back in the cell and press the ESC key.</span></span>  
  
- <span data-ttu-id="f11da-152">現在のセルが編集モードのときに行全体の変更を元に戻すには、ESC キーを2回押します。</span><span class="sxs-lookup"><span data-stu-id="f11da-152">To undo changes for an entire row when the current cell is in edit mode, press the ESC key twice.</span></span>  
  
- <span data-ttu-id="f11da-153">検証エラーが発生した場合は、行ヘッダーのインジケーターの上にマウスポインターを移動すると、関連付けられているエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f11da-153">When a validation error occurs, move your mouse pointer over the indicator in the row header to see the associated error message.</span></span>  
  
 [!code-csharp[DataGrid_Validation#FullCode](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml.cs#fullcode)]
 [!code-vb[DataGrid_Validation#FullCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_validation/vb/mainwindow.xaml.vb#fullcode)]  
  
 [!code-xaml[DataGrid_Validation#FullXaml](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_validation/cs/mainwindow.xaml#fullxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="f11da-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="f11da-154">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="f11da-155">DataGrid</span><span class="sxs-lookup"><span data-stu-id="f11da-155">DataGrid</span></span>](datagrid.md)
- [<span data-ttu-id="f11da-156">データ バインディング</span><span class="sxs-lookup"><span data-stu-id="f11da-156">Data Binding</span></span>](../data/data-binding-wpf.md)
- [<span data-ttu-id="f11da-157">バインディングの検証の実装</span><span class="sxs-lookup"><span data-stu-id="f11da-157">Implement Binding Validation</span></span>](../data/how-to-implement-binding-validation.md)
- [<span data-ttu-id="f11da-158">カスタム オブジェクトに検証ロジックを実装する</span><span class="sxs-lookup"><span data-stu-id="f11da-158">Implement Validation Logic on Custom Objects</span></span>](../data/how-to-implement-validation-logic-on-custom-objects.md)
