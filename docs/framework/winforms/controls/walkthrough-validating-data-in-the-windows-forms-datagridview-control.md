---
title: 'チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査'
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
ms.openlocfilehash: 89569feb0cb741f56d09f4e58154b4eecb5a89d4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046379"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a8f52-102">チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="a8f52-102">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="a8f52-103">データ入力機能をユーザーに表示する場合は、フォームに入力されたデータを頻繁に検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8f52-103">When you display data entry functionality to users, you frequently have to validate the data entered into your form.</span></span> <span data-ttu-id="a8f52-104">クラス<xref:System.Windows.Forms.DataGridView>は、データがデータストアにコミットされる前に検証を実行する便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-104">The <xref:System.Windows.Forms.DataGridView> class provides a convenient way to perform validation before data is committed to the data store.</span></span> <span data-ttu-id="a8f52-105">現在の<xref:System.Windows.Forms.DataGridView.CellValidating> <xref:System.Windows.Forms.DataGridView>セルが変更されたときにによって発生するイベントを処理することで、データを検証できます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-105">You can validate data by handling the <xref:System.Windows.Forms.DataGridView.CellValidating> event, which is raised by the <xref:System.Windows.Forms.DataGridView> when the current cell changes.</span></span>

<span data-ttu-id="a8f52-106">このチュートリアルでは、Northwind サンプルデータベースの`Customers`テーブルから行を取得し、 <xref:System.Windows.Forms.DataGridView>コントロールに表示します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-106">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a8f52-107">ユーザーが`CompanyName`列のセルを編集し、セルから離れようとすると<xref:System.Windows.Forms.DataGridView.CellValidating> 、イベントハンドラーは新しい会社名の文字列を調べて空でないことを確認します。新しい値が空の文字列<xref:System.Windows.Forms.DataGridView>の場合、はユーザーのカーソルを防止します。空でない文字列が入力されるまで、セルから離れます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-107">When a user edits a cell in the `CompanyName` column and tries to leave the cell, the <xref:System.Windows.Forms.DataGridView.CellValidating> event handler will examine new company name string to make sure it is not empty; if the new value is an empty string, the <xref:System.Windows.Forms.DataGridView> will prevent the user's cursor from leaving the cell until a non-empty string is entered.</span></span>

<span data-ttu-id="a8f52-108">このトピックのコードを単一のリストとしてコピーするには、「[方法:Windows フォーム DataGridView コントロール](how-to-validate-data-in-the-windows-forms-datagridview-control.md)でデータを検証します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-108">To copy the code in this topic as a single listing, see [How to: Validate Data in the Windows Forms DataGridView Control](how-to-validate-data-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8f52-109">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a8f52-109">Prerequisites</span></span>

<span data-ttu-id="a8f52-110">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a8f52-110">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="a8f52-111">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="a8f52-111">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="a8f52-112">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="a8f52-112">Creating the Form</span></span>

#### <a name="to-validate-data-entered-in-a-datagridview"></a><span data-ttu-id="a8f52-113">DataGridView に入力されたデータを検証するには</span><span class="sxs-lookup"><span data-stu-id="a8f52-113">To validate data entered in a DataGridView</span></span>

1. <span data-ttu-id="a8f52-114">から<xref:System.Windows.Forms.Form>派生するクラスを作成し、コントロール<xref:System.Windows.Forms.DataGridView>と<xref:System.Windows.Forms.BindingSource>コンポーネントを格納します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-114">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="a8f52-115">次のコード例では、基本的な初期化`Main`を行い、メソッドを含めています。</span><span class="sxs-lookup"><span data-stu-id="a8f52-115">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. <span data-ttu-id="a8f52-116">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-116">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="a8f52-117">このコード例では`GetData` 、設定<xref:System.Data.DataTable>されたオブジェクトを返すメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-117">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="a8f52-118">`connectionString`変数には、データベースに適した値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="a8f52-118">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a8f52-119">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="a8f52-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="a8f52-120">Windows 認証 (統合セキュリティとも呼ばれます) を使用すると、データベースへのアクセスをより安全に制御することができます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-120">Using Windows Authentication, also known as integrated security, is a more secure way to control access to a database.</span></span> <span data-ttu-id="a8f52-121">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8f52-121">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. <span data-ttu-id="a8f52-122">と<xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.Form.Load> を初期化し、データバインディングを設定するフォームのイベントのハンドラーを<xref:System.Windows.Forms.BindingSource>実装します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-122">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. <span data-ttu-id="a8f52-123"><xref:System.Windows.Forms.DataGridView>コントロールの<xref:System.Windows.Forms.DataGridView.CellValidating>イベントと<xref:System.Windows.Forms.DataGridView.CellEndEdit>イベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-123">Implement handlers for the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellValidating> and <xref:System.Windows.Forms.DataGridView.CellEndEdit> events.</span></span>

    <span data-ttu-id="a8f52-124">イベントハンドラーでは、 `CompanyName`列のセルの値が空かどうかを判断します。 <xref:System.Windows.Forms.DataGridView.CellValidating></span><span class="sxs-lookup"><span data-stu-id="a8f52-124">The <xref:System.Windows.Forms.DataGridView.CellValidating> event handler is where you determine whether the value of a cell in the `CompanyName` column is empty.</span></span> <span data-ttu-id="a8f52-125">セル値が検証に失敗した場合<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>は、 <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType>クラスのプロパティ`true`をに設定します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-125">If the cell value fails validation, set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property of the <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> class to `true`.</span></span> <span data-ttu-id="a8f52-126">これにより<xref:System.Windows.Forms.DataGridView> 、コントロールによって、カーソルがセルから離れるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-126">This causes the <xref:System.Windows.Forms.DataGridView> control to prevent the cursor from leaving the cell.</span></span> <span data-ttu-id="a8f52-127">行の<xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>プロパティを説明の文字列に設定します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-127">Set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to an explanatory string.</span></span> <span data-ttu-id="a8f52-128">エラーアイコンと、エラーテキストを含むツールヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-128">This displays an error icon with a ToolTip that contains the error text.</span></span> <span data-ttu-id="a8f52-129">イベントハンドラーで、行の<xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>プロパティを空の文字列に設定します。 <xref:System.Windows.Forms.DataGridView.CellEndEdit></span><span class="sxs-lookup"><span data-stu-id="a8f52-129">In the <xref:System.Windows.Forms.DataGridView.CellEndEdit> event handler, set the <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> property on the row to the empty string.</span></span> <span data-ttu-id="a8f52-130">イベント<xref:System.Windows.Forms.DataGridView.CellEndEdit>は、セルが編集モードを終了したときにのみ発生します。これは、検証に失敗した場合には実行できません。</span><span class="sxs-lookup"><span data-stu-id="a8f52-130">The <xref:System.Windows.Forms.DataGridView.CellEndEdit> event occurs only when the cell exits edit mode, which it cannot do if it fails validation.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="a8f52-131">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="a8f52-131">Testing the Application</span></span>

<span data-ttu-id="a8f52-132">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-132">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="a8f52-133">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="a8f52-133">To test the form</span></span>

- <span data-ttu-id="a8f52-134">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-134">Compile and run the application.</span></span>

  <span data-ttu-id="a8f52-135">`Customers`テーブルのデータが<xref:System.Windows.Forms.DataGridView>いっぱいになっていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="a8f52-135">You will see a <xref:System.Windows.Forms.DataGridView> filled with data from the `Customers` table.</span></span> <span data-ttu-id="a8f52-136">`CompanyName`列のセルをダブルクリックすると、値を編集できます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-136">When you double-click a cell in the `CompanyName` column, you can edit the value.</span></span> <span data-ttu-id="a8f52-137">すべての文字を削除し、TAB キーを押してセルを終了すると<xref:System.Windows.Forms.DataGridView> 、で終了できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a8f52-137">If you delete all the characters and hit the TAB key to exit the cell, the <xref:System.Windows.Forms.DataGridView> prevents you from exiting.</span></span> <span data-ttu-id="a8f52-138">空でない文字列をセルに入力すると、コントロールに<xref:System.Windows.Forms.DataGridView>よってセルを終了できます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-138">When you type a non-empty string into the cell, the <xref:System.Windows.Forms.DataGridView> control lets you exit the cell.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8f52-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="a8f52-139">Next Steps</span></span>

<span data-ttu-id="a8f52-140">このアプリケーションを使用すると、コントロールの<xref:System.Windows.Forms.DataGridView>機能についての基本的な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-140">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="a8f52-141"><xref:System.Windows.Forms.DataGridView>コントロールの外観と動作は、次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a8f52-141">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="a8f52-142">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-142">Change border and header styles.</span></span> <span data-ttu-id="a8f52-143">詳細については、「[方法 :Windows フォーム DataGridView コントロール](change-the-border-and-gridline-styles-in-the-datagrid.md)の境界線とグリッド線のスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-143">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="a8f52-144">コントロールへの<xref:System.Windows.Forms.DataGridView>ユーザー入力を有効または制限します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-144">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a8f52-145">詳細については、「[方法 :Windows フォーム DataGridView コントロール](prevent-row-addition-and-deletion-datagridview.md)で行が追加および削除されない[ようにする方法と、次の操作を実行する方法について説明します。Windows フォーム DataGridView コントロール](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)で列を読み取り専用にします。</span><span class="sxs-lookup"><span data-stu-id="a8f52-145">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="a8f52-146">データベース関連のエラーについては、ユーザー入力を確認してください。</span><span class="sxs-lookup"><span data-stu-id="a8f52-146">Check user input for database-related errors.</span></span> <span data-ttu-id="a8f52-147">詳細については、「[チュートリアル:Windows フォーム DataGridView コントロール](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)でのデータ入力中に発生したエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-147">For more information, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

- <span data-ttu-id="a8f52-148">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-148">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="a8f52-149">詳細については、「[チュートリアル:Windows フォーム DataGridView コントロール](implementing-virtual-mode-wf-datagridview-control.md)での仮想モードの実装。</span><span class="sxs-lookup"><span data-stu-id="a8f52-149">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="a8f52-150">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="a8f52-150">Customize the appearance of cells.</span></span> <span data-ttu-id="a8f52-151">詳細については、「[方法 :Windows フォーム DataGridView コントロール](customize-the-appearance-of-cells-in-the-datagrid.md)でのセルの外観と、次[の操作方法をカスタマイズします。Windows フォーム DataGridView コントロール](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)でフォントと色のスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="a8f52-151">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Font and Color Styles in the Windows Forms DataGridView Control](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8f52-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8f52-152">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="a8f52-153">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="a8f52-153">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a8f52-154">方法: Windows フォーム DataGridView コントロールでデータを検証する</span><span class="sxs-lookup"><span data-stu-id="a8f52-154">How to: Validate Data in the Windows Forms DataGridView Control</span></span>](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a8f52-155">チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="a8f52-155">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="a8f52-156">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="a8f52-156">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
