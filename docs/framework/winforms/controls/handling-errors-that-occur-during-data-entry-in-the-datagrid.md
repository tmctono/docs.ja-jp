---
title: 'チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理'
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
ms.openlocfilehash: 9e803b6450fb8c9ade4adde5bf98fb1c3c62c861
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313219"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="885d6-102">チュートリアル: Windows フォーム DataGridView コントロールでのデータ入力中に発生したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="885d6-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="885d6-103">基になるデータ ストアからのエラーの処理は、データ入力アプリケーションの必要な機能です。</span><span class="sxs-lookup"><span data-stu-id="885d6-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="885d6-104">Windows フォーム<xref:System.Windows.Forms.DataGridView>コントロールによって、この簡単に公開することで、<xref:System.Windows.Forms.DataGridView.DataError>制約違反または壊れているビジネス ルールをデータ ストアを検出したときに発生するイベントです。</span><span class="sxs-lookup"><span data-stu-id="885d6-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>  
  
 <span data-ttu-id="885d6-105">このチュートリアルから行を取得、`Customers`テーブルに Northwind サンプル データベースとその表示、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="885d6-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="885d6-106">重複しているときに`CustomerID`新しい行または編集された既存の行で値が検出された、<xref:System.Windows.Forms.DataGridView.DataError>は、表示することで処理するイベントが発生、<xref:System.Windows.Forms.MessageBox>例外を説明します。</span><span class="sxs-lookup"><span data-stu-id="885d6-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>  
  
 <span data-ttu-id="885d6-107">このトピックのコードを単一のリストとしてコピーするには、「[方法:フォームの DataGridView コントロールを Windows でのデータ入力中に発生するエラーを処理](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="885d6-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="885d6-108">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="885d6-108">Prerequisites</span></span>  
 <span data-ttu-id="885d6-109">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="885d6-109">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="885d6-110">Northwind SQL Server のサンプル データベースが存在するサーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="885d6-110">Access to a server that has the Northwind SQL Server sample database.</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="885d6-111">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="885d6-111">Creating the Form</span></span>  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="885d6-112">DataGridView コントロールでのデータ エントリ エラーを処理するには</span><span class="sxs-lookup"><span data-stu-id="885d6-112">To handle data-entry errors in the DataGridView control</span></span>  
  
1. <span data-ttu-id="885d6-113">派生するクラスを作成<xref:System.Windows.Forms.Form>が含まれています、<xref:System.Windows.Forms.DataGridView>コントロールと<xref:System.Windows.Forms.BindingSource>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="885d6-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     <span data-ttu-id="885d6-114">次のコード例は基本的な初期化を提供しが含まれています、`Main`メソッド。</span><span class="sxs-lookup"><span data-stu-id="885d6-114">The following code example provides basic initialization and includes a `Main` method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2. <span data-ttu-id="885d6-115">データベースへの接続の詳細を処理するためのフォームのクラス定義でメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="885d6-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>  
  
     <span data-ttu-id="885d6-116">このコード例では、`GetData`設定されてを返すメソッド<xref:System.Data.DataTable>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="885d6-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="885d6-117">設定することを必ず、`connectionString`変数は、データベースの適切な値にします。</span><span class="sxs-lookup"><span data-stu-id="885d6-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="885d6-118">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="885d6-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="885d6-119">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="885d6-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="885d6-120">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="885d6-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3. <span data-ttu-id="885d6-121">フォームのハンドラーを実装<xref:System.Windows.Forms.Form.Load>を初期化するイベント、<xref:System.Windows.Forms.DataGridView>と<xref:System.Windows.Forms.BindingSource>し、データ バインディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="885d6-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4. <span data-ttu-id="885d6-122">処理、<xref:System.Windows.Forms.DataGridView.DataError>上のイベント、<xref:System.Windows.Forms.DataGridView>します。</span><span class="sxs-lookup"><span data-stu-id="885d6-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
     <span data-ttu-id="885d6-123">コミット操作の場合は、エラーのコンテキストでエラーを表示、<xref:System.Windows.Forms.MessageBox>します。</span><span class="sxs-lookup"><span data-stu-id="885d6-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="885d6-124">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="885d6-124">Testing the Application</span></span>  
 <span data-ttu-id="885d6-125">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="885d6-125">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="885d6-126">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="885d6-126">To test the form</span></span>  
  
-   <span data-ttu-id="885d6-127">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="885d6-127">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="885d6-128">表示されます、 <xref:System.Windows.Forms.DataGridView> Customers テーブルからデータが格納されたコントロール。</span><span class="sxs-lookup"><span data-stu-id="885d6-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="885d6-129">重複する値を入力する場合`CustomerID`編集をコミットし、セルの値が自動的に元に戻すおよびが表示されます、<xref:System.Windows.Forms.MessageBox>データ エントリ エラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="885d6-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="885d6-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="885d6-130">Next Steps</span></span>  
 <span data-ttu-id="885d6-131">このアプリケーションでは、基本を理解、<xref:System.Windows.Forms.DataGridView>コントロールの機能です。</span><span class="sxs-lookup"><span data-stu-id="885d6-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="885d6-132">動作と外観をカスタマイズすることができます、<xref:System.Windows.Forms.DataGridView>いくつかの方法で制御します。</span><span class="sxs-lookup"><span data-stu-id="885d6-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>  
  
-   <span data-ttu-id="885d6-133">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="885d6-133">Change border and header styles.</span></span> <span data-ttu-id="885d6-134">詳細については、「[方法 :罫線を変更して、グリッド線のスタイルで、Windows フォーム DataGridView コントロール](change-the-border-and-gridline-styles-in-the-datagrid.md)します。</span><span class="sxs-lookup"><span data-stu-id="885d6-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>  
  
-   <span data-ttu-id="885d6-135">有効にするか、ユーザー入力を制限、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="885d6-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="885d6-136">詳細については、「[方法 :行の追加を回避し、削除を Windows フォーム DataGridView コントロール](prevent-row-addition-and-deletion-datagridview.md)、および[方法。列を読み取り専用の Windows フォーム DataGridView コントロール](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="885d6-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="885d6-137">ユーザー入力を検証、<xref:System.Windows.Forms.DataGridView>コントロール。</span><span class="sxs-lookup"><span data-stu-id="885d6-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="885d6-138">詳細については、「[チュートリアル:フォームの DataGridView コントロールを Windows のデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)です。</span><span class="sxs-lookup"><span data-stu-id="885d6-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="885d6-139">仮想モードを使用して、非常に大きなデータ セットを処理します。</span><span class="sxs-lookup"><span data-stu-id="885d6-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="885d6-140">詳細については、「[チュートリアル:仮想モードの実装で、Windows フォーム DataGridView コントロール](implementing-virtual-mode-wf-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="885d6-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>  
  
-   <span data-ttu-id="885d6-141">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="885d6-141">Customize the appearance of cells.</span></span> <span data-ttu-id="885d6-142">詳細については、「[方法 :Windows フォームの DataGridView コントロール内のセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)と[方法。Windows フォーム DataGridView コントロールの既定のセル スタイルを設定](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="885d6-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885d6-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="885d6-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="885d6-144">Windows フォーム DataGridView コントロールでのデータ入力</span><span class="sxs-lookup"><span data-stu-id="885d6-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="885d6-145">方法: Windows フォームの DataGridView コントロールでのデータ入力中に発生したエラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="885d6-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="885d6-146">チュートリアル: Windows フォームの DataGridView コントロールのデータの検証</span><span class="sxs-lookup"><span data-stu-id="885d6-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="885d6-147">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="885d6-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
