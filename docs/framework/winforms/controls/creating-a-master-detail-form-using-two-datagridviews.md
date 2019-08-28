---
title: 'チュートリアル: 2つの Windows フォーム DataGridView コントロールを使用してマスター詳細フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: 4212c7223aca6a5e7de3189d5f6b2757453cc438
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046097"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="81ede-102">チュートリアル: Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="81ede-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>

<span data-ttu-id="81ede-103"><xref:System.Windows.Forms.DataGridView>コントロールを使用する最も一般的なシナリオの1つは、*マスター/詳細*形式です。このフォームでは、2つのデータベーステーブル間の親子関係が表示されます。</span><span class="sxs-lookup"><span data-stu-id="81ede-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="81ede-104">マスターテーブル内の行を選択すると、対応する子データで詳細テーブルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="81ede-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>

<span data-ttu-id="81ede-105">マスター/詳細フォームの実装は、 <xref:System.Windows.Forms.DataGridView>コントロール<xref:System.Windows.Forms.BindingSource>とコンポーネントの間の相互作用を使用して簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="81ede-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="81ede-106">このチュートリアルでは、2つ<xref:System.Windows.Forms.DataGridView>のコントロールと2つ<xref:System.Windows.Forms.BindingSource>のコンポーネントを使用してフォームをビルドします。</span><span class="sxs-lookup"><span data-stu-id="81ede-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="81ede-107">フォームでは、Northwind SQL Server サンプルデータベース`Customers`にとと`Orders`いう2つの関連テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="81ede-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="81ede-108">完了すると、マスター <xref:System.Windows.Forms.DataGridView>内のデータベースのすべての顧客と、選択した顧客のすべての注文が詳細<xref:System.Windows.Forms.DataGridView>に表示されます。</span><span class="sxs-lookup"><span data-stu-id="81ede-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>

<span data-ttu-id="81ede-109">このトピックのコードを単一のリストとしてコピーするには、「[方法:2つの Windows フォーム DataGridView コントロール](create-a-master-detail-form-using-two-datagridviews.md)を使用してマスター/詳細フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="81ede-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](create-a-master-detail-form-using-two-datagridviews.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81ede-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="81ede-110">Prerequisites</span></span>

<span data-ttu-id="81ede-111">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="81ede-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="81ede-112">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="81ede-112">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="81ede-113">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="81ede-113">Creating the form</span></span>

#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="81ede-114">マスター/詳細フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="81ede-114">To create a master/detail form</span></span>

1. <span data-ttu-id="81ede-115">から<xref:System.Windows.Forms.Form>派生するクラスを作成し、2 <xref:System.Windows.Forms.DataGridView>つのコントロール<xref:System.Windows.Forms.BindingSource>と2つのコンポーネントを格納します。</span><span class="sxs-lookup"><span data-stu-id="81ede-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="81ede-116">次のコードは、基本的なフォームの初期`Main`化を提供し、メソッドを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="81ede-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="81ede-117">Visual Studio デザイナーを使用してフォームを作成する場合は、このコードの代わりにデザイナーで生成されたコードを使用できますが、ここでは変数宣言に示されている名前を使用してください。</span><span class="sxs-lookup"><span data-stu-id="81ede-117">If you use the Visual Studio designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. <span data-ttu-id="81ede-118">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="81ede-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="81ede-119">この例では`GetData` 、 <xref:System.Data.DataSet>オブジェクトを設定し、 <xref:System.Data.DataRelation>オブジェクトをデータセットに追加して、 <xref:System.Windows.Forms.BindingSource>コンポーネントをバインドするメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="81ede-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="81ede-120">`connectionString` 変数は、使用しているデータベースに合った値に設定してください。</span><span class="sxs-lookup"><span data-stu-id="81ede-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="81ede-121">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="81ede-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="81ede-122">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="81ede-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="81ede-123">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81ede-123">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <span data-ttu-id="81ede-124"><xref:System.Windows.Forms.DataGridView>コントロールを<xref:System.Windows.Forms.Form.Load> コンポーネントに<xref:System.Windows.Forms.BindingSource>バインドし、 `GetData`メソッドを呼び出すフォームのイベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="81ede-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="81ede-125">次の例には、表示<xref:System.Windows.Forms.DataGridView>されるデータに合わせて列のサイズを変更するコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="81ede-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a><span data-ttu-id="81ede-126">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="81ede-126">Testing the Application</span></span>

<span data-ttu-id="81ede-127">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="81ede-127">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="81ede-128">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="81ede-128">To test the form</span></span>

- <span data-ttu-id="81ede-129">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="81ede-129">Compile and run the application.</span></span>

  <span data-ttu-id="81ede-130">2つ<xref:System.Windows.Forms.DataGridView>のコントロールが1つ上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="81ede-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="81ede-131">[上位] は Northwind `Customers`テーブルの顧客であり、一番下`Orders`には選択した顧客に対応するがあります。</span><span class="sxs-lookup"><span data-stu-id="81ede-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="81ede-132">上部<xref:System.Windows.Forms.DataGridView>で異なる行を選択すると、それに応じて下位<xref:System.Windows.Forms.DataGridView>の内容が変化します。</span><span class="sxs-lookup"><span data-stu-id="81ede-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>

## <a name="next-steps"></a><span data-ttu-id="81ede-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="81ede-133">Next Steps</span></span>

<span data-ttu-id="81ede-134">このアプリケーションを使用すると、コントロールの<xref:System.Windows.Forms.DataGridView>機能についての基本的な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="81ede-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="81ede-135"><xref:System.Windows.Forms.DataGridView>コントロールの外観と動作は、次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="81ede-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="81ede-136">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="81ede-136">Change border and header styles.</span></span> <span data-ttu-id="81ede-137">詳細については、「[方法 :Windows フォーム DataGridView コントロール](change-the-border-and-gridline-styles-in-the-datagrid.md)の境界線とグリッド線のスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="81ede-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="81ede-138">コントロールへの<xref:System.Windows.Forms.DataGridView>ユーザー入力を有効または制限します。</span><span class="sxs-lookup"><span data-stu-id="81ede-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="81ede-139">詳細については、「[方法 :Windows フォーム DataGridView コントロール](prevent-row-addition-and-deletion-datagridview.md)で行が追加および削除されない[ようにする方法と、次の操作を実行する方法について説明します。Windows フォーム DataGridView コントロール](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)で列を読み取り専用にします。</span><span class="sxs-lookup"><span data-stu-id="81ede-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="81ede-140">コントロールへの<xref:System.Windows.Forms.DataGridView>ユーザー入力を検証します。</span><span class="sxs-lookup"><span data-stu-id="81ede-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="81ede-141">詳細については、「[チュートリアル:Windows フォーム DataGridView コントロール](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)でデータを検証しています。</span><span class="sxs-lookup"><span data-stu-id="81ede-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="81ede-142">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="81ede-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="81ede-143">詳細については、「[チュートリアル:Windows フォーム DataGridView コントロール](implementing-virtual-mode-wf-datagridview-control.md)での仮想モードの実装。</span><span class="sxs-lookup"><span data-stu-id="81ede-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="81ede-144">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="81ede-144">Customize the appearance of cells.</span></span> <span data-ttu-id="81ede-145">詳細については、「[方法 :Windows フォーム DataGridView コントロール](customize-the-appearance-of-cells-in-the-datagrid.md)でのセルの外観と、次[の操作方法をカスタマイズします。Windows フォーム DataGridView コントロール](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)の既定のセルスタイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="81ede-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="81ede-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="81ede-146">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="81ede-147">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="81ede-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="81ede-148">方法: 2つの Windows フォーム DataGridView コントロールを使用してマスター/詳細フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="81ede-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](create-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="81ede-149">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="81ede-149">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
