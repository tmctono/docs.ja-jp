---
title: 'チュートリアル: DataGridView コントロールでのデータの検証'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 45753fb206ad58616c9a727bd81bd2458db6053e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740095"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3a68f-102">チュートリアル : Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="3a68f-102">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="3a68f-103">データ入力機能をユーザーに表示する場合は、フォームに入力されたデータを頻繁に検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a68f-103">When you display data entry functionality to users, you frequently have to validate the data entered into your form.</span></span> <span data-ttu-id="3a68f-104"><xref:System.Windows.Forms.DataGridView> クラスは、データがデータストアにコミットされる前に検証を実行する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-104">The <xref:System.Windows.Forms.DataGridView> class provides a convenient way to perform validation before data is committed to the data store.</span></span> <span data-ttu-id="3a68f-105">現在のセルが変更されたときに <xref:System.Windows.Forms.DataGridView> によって発生する <xref:System.Windows.Forms.DataGridView.CellValidating> イベントを処理することで、データを検証できます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-105">You can validate data by handling the <xref:System.Windows.Forms.DataGridView.CellValidating> event, which is raised by the <xref:System.Windows.Forms.DataGridView> when the current cell changes.</span></span>

<span data-ttu-id="3a68f-106">このチュートリアルでは、Northwind サンプルデータベースの `Customers` テーブルから行を取得し、<xref:System.Windows.Forms.DataGridView> コントロールに表示します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-106">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3a68f-107">ユーザーが `CompanyName` 列のセルを編集し、そのセルから離れようとすると、<xref:System.Windows.Forms.DataGridView.CellValidating> イベントハンドラーは新しい会社名の文字列を調べて、空でないことを確認します。新しい値が空の文字列の場合、<xref:System.Windows.Forms.DataGridView> によって、空でない文字列が入力されるまで、ユーザーのカーソルがセルから離れるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-107">When a user edits a cell in the `CompanyName` column and tries to leave the cell, the <xref:System.Windows.Forms.DataGridView.CellValidating> event handler will examine new company name string to make sure it is not empty; if the new value is an empty string, the <xref:System.Windows.Forms.DataGridView> will prevent the user's cursor from leaving the cell until a non-empty string is entered.</span></span>

<span data-ttu-id="3a68f-108">このトピックのコードを単一のリストとしてコピーする方法については、「[方法: Windows フォーム DataGridView コントロールでデータを検証](how-to-validate-data-in-the-windows-forms-datagridview-control.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-108">To copy the code in this topic as a single listing, see [How to: Validate Data in the Windows Forms DataGridView Control](how-to-validate-data-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3a68f-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="3a68f-109">Prerequisites</span></span>

<span data-ttu-id="3a68f-110">このチュートリアルを完了するには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a68f-110">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="3a68f-111">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="3a68f-111">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="3a68f-112">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="3a68f-112">Creating the Form</span></span>

#### <a name="to-validate-data-entered-in-a-datagridview"></a><span data-ttu-id="3a68f-113">DataGridView に入力されたデータを検証するには</span><span class="sxs-lookup"><span data-stu-id="3a68f-113">To validate data entered in a DataGridView</span></span>

1. <span data-ttu-id="3a68f-114"><xref:System.Windows.Forms.Form> から派生し、<xref:System.Windows.Forms.DataGridView> コントロールと <xref:System.Windows.Forms.BindingSource> コンポーネントを含むクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-114">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="3a68f-115">次のコード例では、基本的な初期化を行い、`Main` メソッドを含めています。</span><span class="sxs-lookup"><span data-stu-id="3a68f-115">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. <span data-ttu-id="3a68f-116">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-116">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="3a68f-117">このコード例では、設定された <xref:System.Data.DataTable> オブジェクトを返す `GetData` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-117">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="3a68f-118">`connectionString` 変数は、データベースに適した値に設定してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-118">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3a68f-119">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="3a68f-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="3a68f-120">Windows 認証 (統合セキュリティとも呼ばれます) を使用すると、データベースへのアクセスをより安全に制御することができます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-120">Using Windows Authentication, also known as integrated security, is a more secure way to control access to a database.</span></span> <span data-ttu-id="3a68f-121">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-121">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. <span data-ttu-id="3a68f-122">フォームの <xref:System.Windows.Forms.Form.Load> イベントのハンドラーを実装します。このハンドラーは、<xref:System.Windows.Forms.DataGridView> を初期化し <xref:System.Windows.Forms.BindingSource>、データバインディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-122">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. <span data-ttu-id="3a68f-123"><xref:System.Windows.Forms.DataGridView> コントロールの <xref:System.Windows.Forms.DataGridView.CellValidating> イベントと <xref:System.Windows.Forms.DataGridView.CellEndEdit> イベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-123">Implement handlers for the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellValidating> and <xref:System.Windows.Forms.DataGridView.CellEndEdit> events.</span></span>

    <span data-ttu-id="3a68f-124"><xref:System.Windows.Forms.DataGridView.CellValidating> イベントハンドラーでは、`CompanyName` 列のセルの値が空であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-124">The <xref:System.Windows.Forms.DataGridView.CellValidating> event handler is where you determine whether the value of a cell in the `CompanyName` column is empty.</span></span> <span data-ttu-id="3a68f-125">セル値が検証に失敗した場合は、<xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> クラスの <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-125">If the cell value fails validation, set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property of the <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> class to `true`.</span></span> <span data-ttu-id="3a68f-126">これにより、<xref:System.Windows.Forms.DataGridView> コントロールによって、カーソルがセルから離れるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-126">This causes the <xref:System.Windows.Forms.DataGridView> control to prevent the cursor from leaving the cell.</span></span> <span data-ttu-id="3a68f-127">行の <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> プロパティを説明の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-127">Set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to an explanatory string.</span></span> <span data-ttu-id="3a68f-128">エラーアイコンと、エラーテキストを含むツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-128">This displays an error icon with a ToolTip that contains the error text.</span></span> <span data-ttu-id="3a68f-129"><xref:System.Windows.Forms.DataGridView.CellEndEdit> イベントハンドラーで、行の <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> プロパティを空の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-129">In the <xref:System.Windows.Forms.DataGridView.CellEndEdit> event handler, set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to the empty string.</span></span> <span data-ttu-id="3a68f-130"><xref:System.Windows.Forms.DataGridView.CellEndEdit> イベントは、セルが編集モードを終了したときにのみ発生します。これは、検証に失敗した場合には実行できません。</span><span class="sxs-lookup"><span data-stu-id="3a68f-130">The <xref:System.Windows.Forms.DataGridView.CellEndEdit> event occurs only when the cell exits edit mode, which it cannot do if it fails validation.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="3a68f-131">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="3a68f-131">Testing the Application</span></span>

<span data-ttu-id="3a68f-132">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-132">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="3a68f-133">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="3a68f-133">To test the form</span></span>

- <span data-ttu-id="3a68f-134">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-134">Compile and run the application.</span></span>

  <span data-ttu-id="3a68f-135">`Customers` テーブルのデータが入力された <xref:System.Windows.Forms.DataGridView> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-135">You will see a <xref:System.Windows.Forms.DataGridView> filled with data from the `Customers` table.</span></span> <span data-ttu-id="3a68f-136">[`CompanyName`] 列のセルをダブルクリックすると、値を編集できます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-136">When you double-click a cell in the `CompanyName` column, you can edit the value.</span></span> <span data-ttu-id="3a68f-137">すべての文字を削除し、TAB キーを押してセルを終了すると、<xref:System.Windows.Forms.DataGridView> によって終了できなくなります。</span><span class="sxs-lookup"><span data-stu-id="3a68f-137">If you delete all the characters and hit the TAB key to exit the cell, the <xref:System.Windows.Forms.DataGridView> prevents you from exiting.</span></span> <span data-ttu-id="3a68f-138">空でない文字列をセルに入力すると、<xref:System.Windows.Forms.DataGridView> コントロールによってセルを終了できます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-138">When you type a non-empty string into the cell, the <xref:System.Windows.Forms.DataGridView> control lets you exit the cell.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a68f-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="3a68f-139">Next Steps</span></span>

<span data-ttu-id="3a68f-140">このアプリケーションでは、<xref:System.Windows.Forms.DataGridView> コントロールの機能についての基本的な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-140">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="3a68f-141"><xref:System.Windows.Forms.DataGridView> コントロールの外観と動作は、次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3a68f-141">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="3a68f-142">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-142">Change border and header styles.</span></span> <span data-ttu-id="3a68f-143">詳細については、「[方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-143">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="3a68f-144"><xref:System.Windows.Forms.DataGridView> コントロールへのユーザー入力を有効または制限します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-144">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3a68f-145">詳細については、「[方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「[方法: Windows フォーム Datagridview コントロールで列を読み取り](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)専用にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-145">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="3a68f-146">データベース関連のエラーについては、ユーザー入力を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-146">Check user input for database-related errors.</span></span> <span data-ttu-id="3a68f-147">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-147">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

- <span data-ttu-id="3a68f-148">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="3a68f-148">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="3a68f-149">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-149">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="3a68f-150">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3a68f-150">Customize the appearance of cells.</span></span> <span data-ttu-id="3a68f-151">詳細については、「[方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)する」および「[方法: Windows フォーム Datagridview コントロールのフォントと色のスタイルを設定する](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a68f-151">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Font and Color Styles in the Windows Forms DataGridView Control](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a68f-152">参照</span><span class="sxs-lookup"><span data-stu-id="3a68f-152">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="3a68f-153">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="3a68f-153">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3a68f-154">方法: Windows フォーム DataGridView コントロールのデータを検証する</span><span class="sxs-lookup"><span data-stu-id="3a68f-154">How to: Validate Data in the Windows Forms DataGridView Control</span></span>](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3a68f-155">チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="3a68f-155">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="3a68f-156">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="3a68f-156">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
