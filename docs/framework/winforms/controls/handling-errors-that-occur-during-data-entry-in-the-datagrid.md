---
title: 'チュートリアル: DataGridView コントロールでのデータ入力中に発生したエラーの処理'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738739"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3ce0e-102">チュートリアル : Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="3ce0e-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="3ce0e-103">データ入力アプリケーションでは、基になるデータストアからのエラーを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="3ce0e-104">Windows フォーム <xref:System.Windows.Forms.DataGridView> コントロールを使用すると、データストアが制約違反やビジネスルールの破損を検出したときに発生する <xref:System.Windows.Forms.DataGridView.DataError> イベントを公開することで、この操作を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="3ce0e-105">このチュートリアルでは、Northwind サンプルデータベースの `Customers` テーブルから行を取得し、<xref:System.Windows.Forms.DataGridView> コントロールに表示します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3ce0e-106">新しい行または編集済みの既存の行で重複する `CustomerID` 値が検出されると、<xref:System.Windows.Forms.DataGridView.DataError> イベントが発生します。これは、例外を説明する <xref:System.Windows.Forms.MessageBox> を表示することによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="3ce0e-107">このトピックのコードを単一のリストとしてコピーする方法については、「[方法: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーを処理](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ce0e-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="3ce0e-108">Prerequisites</span></span>

<span data-ttu-id="3ce0e-109">このチュートリアルを完了するには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="3ce0e-110">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="3ce0e-111">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="3ce0e-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="3ce0e-112">DataGridView コントロールでのデータ入力エラーを処理するには</span><span class="sxs-lookup"><span data-stu-id="3ce0e-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="3ce0e-113"><xref:System.Windows.Forms.Form> から派生し、<xref:System.Windows.Forms.DataGridView> コントロールと <xref:System.Windows.Forms.BindingSource> コンポーネントを含むクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="3ce0e-114">次のコード例では、基本的な初期化を行い、`Main` メソッドを含めています。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="3ce0e-115">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="3ce0e-116">このコード例では、設定された <xref:System.Data.DataTable> オブジェクトを返す `GetData` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="3ce0e-117">`connectionString` 変数は、データベースに適した値に設定してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3ce0e-118">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="3ce0e-119">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="3ce0e-120">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="3ce0e-121">フォームの <xref:System.Windows.Forms.Form.Load> イベントのハンドラーを実装します。このハンドラーは、<xref:System.Windows.Forms.DataGridView> を初期化し <xref:System.Windows.Forms.BindingSource>、データバインディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="3ce0e-122"><xref:System.Windows.Forms.DataGridView>で <xref:System.Windows.Forms.DataGridView.DataError> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="3ce0e-123">エラーのコンテキストがコミット操作の場合は、<xref:System.Windows.Forms.MessageBox>にエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="3ce0e-124">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="3ce0e-124">Testing the Application</span></span>

<span data-ttu-id="3ce0e-125">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="3ce0e-126">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="3ce0e-126">To test the form</span></span>

- <span data-ttu-id="3ce0e-127">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="3ce0e-128">Customers テーブルのデータが入力された <xref:System.Windows.Forms.DataGridView> コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="3ce0e-129">`CustomerID` に重複する値を入力して編集をコミットすると、セルの値は自動的に元に戻り、データエントリエラーを表示する <xref:System.Windows.Forms.MessageBox> が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ce0e-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="3ce0e-130">Next Steps</span></span>

<span data-ttu-id="3ce0e-131">このアプリケーションでは、<xref:System.Windows.Forms.DataGridView> コントロールの機能についての基本的な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="3ce0e-132"><xref:System.Windows.Forms.DataGridView> コントロールの外観と動作は、次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="3ce0e-133">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-133">Change border and header styles.</span></span> <span data-ttu-id="3ce0e-134">詳細については、「[方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="3ce0e-135"><xref:System.Windows.Forms.DataGridView> コントロールへのユーザー入力を有効または制限します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3ce0e-136">詳細については、「[方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「[方法: Windows フォーム Datagridview コントロールで列を読み取り](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)専用にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="3ce0e-137"><xref:System.Windows.Forms.DataGridView> コントロールへのユーザー入力を検証します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3ce0e-138">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでのデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="3ce0e-139">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="3ce0e-140">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="3ce0e-141">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-141">Customize the appearance of cells.</span></span> <span data-ttu-id="3ce0e-142">詳細については、「[方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)する」および「[方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ce0e-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ce0e-143">参照</span><span class="sxs-lookup"><span data-stu-id="3ce0e-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="3ce0e-144">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="3ce0e-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3ce0e-145">方法: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーを処理する</span><span class="sxs-lookup"><span data-stu-id="3ce0e-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="3ce0e-146">チュートリアル: Windows フォーム DataGridView コントロールのデータの妥当性検査</span><span class="sxs-lookup"><span data-stu-id="3ce0e-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="3ce0e-147">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="3ce0e-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
