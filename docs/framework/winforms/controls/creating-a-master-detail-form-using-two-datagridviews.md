---
title: 'チュートリアル: 2 つの DataGridView コントロールを使用してマスター/詳細フォームを作成する'
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
ms.openlocfilehash: bb3da36430c7493b941f3711cb584b4517d5bd54
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740585"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="b2b33-102">チュートリアル : Windows フォームの 2 つの DataGridView コントロールを使用したマスター/詳細形式のフォームの作成</span><span class="sxs-lookup"><span data-stu-id="b2b33-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>

<span data-ttu-id="b2b33-103"><xref:System.Windows.Forms.DataGridView> コントロールを使用する最も一般的なシナリオの1つとして、*マスター/詳細*フォームがあります。このフォームでは、2つのデータベーステーブル間の親子リレーションシップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="b2b33-104">マスターテーブル内の行を選択すると、対応する子データで詳細テーブルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>

<span data-ttu-id="b2b33-105">マスター/詳細フォームの実装は、<xref:System.Windows.Forms.DataGridView> コントロールと <xref:System.Windows.Forms.BindingSource> コンポーネントの間の相互作用を使用して簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="b2b33-106">このチュートリアルでは、2つの <xref:System.Windows.Forms.DataGridView> コントロールと2つの <xref:System.Windows.Forms.BindingSource> コンポーネントを使用してフォームをビルドします。</span><span class="sxs-lookup"><span data-stu-id="b2b33-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="b2b33-107">フォームでは、Northwind SQL Server サンプルデータベースに2つの関連テーブルが表示されます。 `Customers` と `Orders`です。</span><span class="sxs-lookup"><span data-stu-id="b2b33-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="b2b33-108">完了すると、マスター <xref:System.Windows.Forms.DataGridView> 内のデータベース内のすべての顧客と、詳細 <xref:System.Windows.Forms.DataGridView>で選択した顧客のすべての注文を表示するフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>

<span data-ttu-id="b2b33-109">このトピックのコードを単一のリストとしてコピーする方法については、「[方法: 2 つの Windows フォーム DataGridView コントロールを使用してマスター/詳細フォームを作成](create-a-master-detail-form-using-two-datagridviews.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](create-a-master-detail-form-using-two-datagridviews.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2b33-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="b2b33-110">Prerequisites</span></span>

<span data-ttu-id="b2b33-111">このチュートリアルを完了するには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="b2b33-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="b2b33-112">Northwind SQL Server サンプルデータベースを持つサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="b2b33-112">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="b2b33-113">フォームの作成</span><span class="sxs-lookup"><span data-stu-id="b2b33-113">Creating the form</span></span>

#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="b2b33-114">マスター/詳細フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="b2b33-114">To create a master/detail form</span></span>

1. <span data-ttu-id="b2b33-115"><xref:System.Windows.Forms.Form> から派生し、2つの <xref:System.Windows.Forms.DataGridView> コントロールと2つの <xref:System.Windows.Forms.BindingSource> コンポーネントを含むクラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="b2b33-116">次のコードは、基本的なフォーム初期化を提供し、`Main` メソッドを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="b2b33-117">Visual Studio デザイナーを使用してフォームを作成する場合は、このコードの代わりにデザイナーで生成されたコードを使用できますが、ここでは変数宣言に示されている名前を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-117">If you use the Visual Studio designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. <span data-ttu-id="b2b33-118">データベースへの接続の詳細を処理するために、フォームのクラス定義にメソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="b2b33-119">この例では、`GetData` メソッドを使用して、<xref:System.Data.DataSet> オブジェクトを設定し、<xref:System.Data.DataRelation> オブジェクトをデータセットに追加して、<xref:System.Windows.Forms.BindingSource> コンポーネントをバインドします。</span><span class="sxs-lookup"><span data-stu-id="b2b33-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="b2b33-120">`connectionString` 変数は、使用しているデータベースに合った値に設定してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b2b33-121">接続文字列内に機密情報 (パスワードなど) を格納すると、アプリケーションのセキュリティに影響を及ぼすことがあります。</span><span class="sxs-lookup"><span data-stu-id="b2b33-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="b2b33-122">データベースへのアクセスを制御する方法としては、Windows 認証 (統合セキュリティとも呼ばれます) を使用する方が安全です。</span><span class="sxs-lookup"><span data-stu-id="b2b33-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="b2b33-123">詳細については、「[接続情報の保護](../../data/adonet/protecting-connection-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-123">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <span data-ttu-id="b2b33-124">フォームの <xref:System.Windows.Forms.Form.Load> イベントのハンドラーを実装します。このハンドラーは、<xref:System.Windows.Forms.DataGridView> コントロールを <xref:System.Windows.Forms.BindingSource> コンポーネントにバインドし、`GetData` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="b2b33-125">次の例には、表示データに合わせて列の <xref:System.Windows.Forms.DataGridView> サイズを変更するコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2b33-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a><span data-ttu-id="b2b33-126">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="b2b33-126">Testing the Application</span></span>

<span data-ttu-id="b2b33-127">フォームをテストして、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-127">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="b2b33-128">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="b2b33-128">To test the form</span></span>

- <span data-ttu-id="b2b33-129">アプリケーションをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-129">Compile and run the application.</span></span>

  <span data-ttu-id="b2b33-130">2つの <xref:System.Windows.Forms.DataGridView> コントロールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="b2b33-131">[上位] は Northwind `Customers` テーブルの顧客であり、下部は選択した顧客に対応する `Orders` です。</span><span class="sxs-lookup"><span data-stu-id="b2b33-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="b2b33-132">上部 <xref:System.Windows.Forms.DataGridView>で異なる行を選択すると、それに応じて低い <xref:System.Windows.Forms.DataGridView> の内容が変更されます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2b33-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="b2b33-133">Next Steps</span></span>

<span data-ttu-id="b2b33-134">このアプリケーションでは、<xref:System.Windows.Forms.DataGridView> コントロールの機能についての基本的な理解を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="b2b33-135"><xref:System.Windows.Forms.DataGridView> コントロールの外観と動作は、次のいくつかの方法でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b2b33-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="b2b33-136">罫線とヘッダーのスタイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-136">Change border and header styles.</span></span> <span data-ttu-id="b2b33-137">詳細については、「[方法: Windows フォーム DataGridView コントロールの境界線とグリッド線のスタイルを変更する](change-the-border-and-gridline-styles-in-the-datagrid.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="b2b33-138"><xref:System.Windows.Forms.DataGridView> コントロールへのユーザー入力を有効または制限します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b2b33-139">詳細については、「[方法: Windows フォーム Datagridview コントロールで行の追加と削除を回避](prevent-row-addition-and-deletion-datagridview.md)する」および「[方法: Windows フォーム Datagridview コントロールで列を読み取り](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)専用にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="b2b33-140"><xref:System.Windows.Forms.DataGridView> コントロールへのユーザー入力を検証します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b2b33-141">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでのデータの検証](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="b2b33-142">仮想モードを使用して非常に大きなデータセットを処理します。</span><span class="sxs-lookup"><span data-stu-id="b2b33-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="b2b33-143">詳細については、「[チュートリアル: Windows フォーム DataGridView コントロールでの仮想モードの実装](implementing-virtual-mode-wf-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="b2b33-144">セルの外観をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b2b33-144">Customize the appearance of cells.</span></span> <span data-ttu-id="b2b33-145">詳細については、「[方法: Windows フォーム Datagridview コントロールのセルの外観をカスタマイズ](customize-the-appearance-of-cells-in-the-datagrid.md)する」および「[方法: Windows フォーム Datagridview コントロールの既定のセルスタイルを設定する](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2b33-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2b33-146">参照</span><span class="sxs-lookup"><span data-stu-id="b2b33-146">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="b2b33-147">Windows フォーム DataGridView コントロールでのデータの表示</span><span class="sxs-lookup"><span data-stu-id="b2b33-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="b2b33-148">方法: Windows フォームの 2 つの DataGridView コントロールを使用してマスター/詳細形式のフォームを作成する</span><span class="sxs-lookup"><span data-stu-id="b2b33-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](create-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="b2b33-149">接続情報の保護</span><span class="sxs-lookup"><span data-stu-id="b2b33-149">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
