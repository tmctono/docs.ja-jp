---
title: '方法: LINQ を使用してクエリ結果をフィルター処理する'
ms.date: 07/20/2015
helpviewer_keywords:
- filtering [Visual Basic]
- filtering data [LINQ in Visual Basic]
- filtering [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], filtering results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
- filtering data [Visual Basic]
ms.assetid: ef103092-9bed-4134-97f4-2db696e83c12
ms.openlocfilehash: 2ea8a852a2f012ddb25ec1198c66e09df880ff47
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344988"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="79a3a-102">方法 : LINQ を使用してクエリ結果をフィルター処理する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79a3a-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="79a3a-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="79a3a-104">次の例では、SQL Server データベースに対してクエリを実行し、`Where` 句を使用して結果を特定の値でフィルター処理する新しいアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="79a3a-105">詳細については、「 [Where 句](../../../../visual-basic/language-reference/queries/where-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79a3a-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="79a3a-106">このトピックの例では、Northwind サンプルデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="79a3a-107">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="79a3a-108">手順については、「[サンプルデータベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79a3a-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="79a3a-109">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="79a3a-109">To create a connection to a database</span></span>

1. <span data-ttu-id="79a3a-110">Visual Studio で**サーバーエクスプローラー**/**データベースエクスプローラー**を開くには、 **[表示]** メニューの [**サーバーエクスプローラー** **/データベースエクスプローラー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="79a3a-111">**サーバーエクスプローラー**/で **[データ接続]** を右クリックし**データベースエクスプローラー** **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="79a3a-112">Northwind サンプルデータベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="79a3a-113">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="79a3a-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="79a3a-114">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="79a3a-115">プロジェクトの種類として [Visual Basic **Windows フォームアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="79a3a-116">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="79a3a-117">**[LINQ to SQL Classes]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="79a3a-118">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="79a3a-119">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-119">Click **Add**.</span></span> <span data-ttu-id="79a3a-120">Northwind .dbml ファイルのオブジェクトリレーショナルデザイナー (O/R デザイナー) が開きます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="79a3a-121">O/R デザイナーに対してクエリを実行するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="79a3a-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="79a3a-122">**サーバーエクスプローラー**/**データベースエクスプローラー**で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="79a3a-123">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="79a3a-124">O/R デザイナーを閉じた場合は、前の手順で追加した northwind .dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="79a3a-125">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="79a3a-126">[Orders] テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="79a3a-127">デザイナーによって、プロジェクトの新しい `Customer` と `Order` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="79a3a-128">デザイナーがテーブル間のリレーションシップを自動的に検出し、関連するオブジェクトの子プロパティを作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="79a3a-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="79a3a-129">たとえば、IntelliSense は、`Customer` オブジェクトに、その顧客に関連するすべての注文に対して `Orders` プロパティがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="79a3a-130">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="79a3a-131">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="79a3a-132">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="79a3a-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="79a3a-133">**[ツールボックス]** から、[<xref:System.Windows.Forms.DataGridView>] コントロールをプロジェクト Form1 の既定の Windows フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="79a3a-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="79a3a-134">Form1 をダブルクリックして、フォームの `Load` イベントにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="79a3a-135">O/R デザイナーにテーブルを追加したときに、デザイナーによってプロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトが追加されました。</span><span class="sxs-lookup"><span data-stu-id="79a3a-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="79a3a-136">このオブジェクトには、各テーブルの個々のオブジェクトとコレクションに加えて、それらのテーブルにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="79a3a-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="79a3a-137">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトは、.dbml ファイルの名前に基づいて名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="79a3a-138">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext`という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="79a3a-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="79a3a-139">コード内に <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="79a3a-140">次のコードを `Load` イベントに追加して、データコンテキストのプロパティとして公開されているテーブルに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="79a3a-141">クエリは結果をフィルター処理し、`London`にある顧客のみを返します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="79a3a-142">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="79a3a-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="79a3a-143">他にも、次のようなフィルターを試してみることができます。</span><span class="sxs-lookup"><span data-stu-id="79a3a-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="79a3a-144">参照</span><span class="sxs-lookup"><span data-stu-id="79a3a-144">See also</span></span>

- [<span data-ttu-id="79a3a-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="79a3a-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="79a3a-146">クエリ</span><span class="sxs-lookup"><span data-stu-id="79a3a-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="79a3a-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="79a3a-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="79a3a-148">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="79a3a-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
