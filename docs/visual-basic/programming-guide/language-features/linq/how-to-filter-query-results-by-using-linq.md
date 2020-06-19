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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344988"
---
# <a name="how-to-filter-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="a2d08-102">方法: LINQ を使用してクエリ結果をフィルター処理する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2d08-102">How to: Filter Query Results by Using LINQ (Visual Basic)</span></span>

<span data-ttu-id="a2d08-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>

<span data-ttu-id="a2d08-104">次の例は、SQL Server データベースに対してクエリを実行し、`Where` 句を使用して特定の値で結果をフィルター処理する新しいアプリケーションの作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a2d08-104">The following example shows how to create a new application that performs queries against a SQL Server database and filters the results by a particular value by using the `Where` clause.</span></span> <span data-ttu-id="a2d08-105">詳細については、「[Where 句](../../../../visual-basic/language-reference/queries/where-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2d08-105">For more information, see [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md).</span></span>

<span data-ttu-id="a2d08-106">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-106">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a2d08-107">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-107">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a2d08-108">手順については、「[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2d08-108">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="a2d08-109">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="a2d08-109">To create a connection to a database</span></span>

1. <span data-ttu-id="a2d08-110">Visual Studio で、 **[表示]** メニューの **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** をクリックして、 **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-110">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>

2. <span data-ttu-id="a2d08-111">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で **[データ接続]** を右クリックしてから、 **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-111">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>

3. <span data-ttu-id="a2d08-112">Northwind サンプル データベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-112">Specify a valid connection to the Northwind sample database.</span></span>

## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a2d08-113">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="a2d08-113">To add a project that contains a LINQ to SQL file</span></span>

1. <span data-ttu-id="a2d08-114">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-114">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a2d08-115">プロジェクト タイプとして、Visual Basic の **[Windows フォーム アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-115">Select Visual Basic **Windows Forms Application** as the project type.</span></span>

2. <span data-ttu-id="a2d08-116">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-116">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a2d08-117">**[LINQ to SQL クラス]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-117">Select the **LINQ to SQL Classes** item template.</span></span>

3. <span data-ttu-id="a2d08-118">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-118">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a2d08-119">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-119">Click **Add**.</span></span> <span data-ttu-id="a2d08-120">オブジェクト リレーショナル デザイナー (O/R デザイナー) が northwind.dbml ファイル用に開きます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-120">The Object Relational Designer (O/R Designer) opens for the northwind.dbml file.</span></span>

## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="a2d08-121">O/R デザイナーにクエリを実行するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="a2d08-121">To add tables to query to the O/R Designer</span></span>

1. <span data-ttu-id="a2d08-122">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-122">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a2d08-123">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-123">Expand the **Tables** folder.</span></span>

     <span data-ttu-id="a2d08-124">O/R デザイナーを閉じている場合は、前に追加した northwind.dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-124">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>

2. <span data-ttu-id="a2d08-125">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-125">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="a2d08-126">Orders テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-126">Click the Orders table and drag it to the left pane of the designer.</span></span>

     <span data-ttu-id="a2d08-127">デザイナーによって、プロジェクトの新しい `Customer` および `Order` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-127">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="a2d08-128">デザイナーによってテーブル間のリレーションシップが自動的に検出され、関連するオブジェクトの子プロパティが作成されることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="a2d08-128">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="a2d08-129">たとえば、IntelliSense では、`Customer` オブジェクトに、その顧客に関連するすべての注文の `Orders` プロパティがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-129">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>

3. <span data-ttu-id="a2d08-130">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-130">Save your changes and close the designer.</span></span>

4. <span data-ttu-id="a2d08-131">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-131">Save your project.</span></span>

## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="a2d08-132">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="a2d08-132">To add code to query the database and display the results</span></span>

1. <span data-ttu-id="a2d08-133">**[ツールボックス]** から、プロジェクトの既定の Windows フォームである Form1 に <xref:System.Windows.Forms.DataGridView> コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-133">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>

2. <span data-ttu-id="a2d08-134">Form1 をダブルクリックして、コードをフォームの `Load` イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-134">Double-click Form1 to add code to the `Load` event of the form.</span></span>

3. <span data-ttu-id="a2d08-135">テーブルを O/R デザイナーに追加したときに、デザイナーによってプロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトが追加されました。</span><span class="sxs-lookup"><span data-stu-id="a2d08-135">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a2d08-136">このオブジェクトには、各テーブルの個々のオブジェクトとコレクションに加え、それらのテーブルにアクセスするために必要なコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-136">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="a2d08-137">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトの名前は、.dbml ファイルの名前に基づいて付けられます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-137">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="a2d08-138">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext` という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="a2d08-138">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>

    <span data-ttu-id="a2d08-139">コードで <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-139">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>

    <span data-ttu-id="a2d08-140">次のコードを `Load` イベントに追加し、データ コンテキストのプロパティとして公開されているテーブルに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-140">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="a2d08-141">クエリでは結果がフィルター処理され、`London` にある顧客のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-141">The query filters the results and returns only customers that are located in `London`.</span></span>

    [!code-vb[VbLINQToSQLHowTos#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#11)]

4. <span data-ttu-id="a2d08-142">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-142">Press F5 to run your project and view the results.</span></span>

5. <span data-ttu-id="a2d08-143">他にも、次のようなフィルターをいくつか試すことができます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-143">Following are some other filters that you can try.</span></span>

    [!code-vb[VbLINQToSQLHowTos#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form5.vb#12)]

## <a name="see-also"></a><span data-ttu-id="a2d08-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2d08-144">See also</span></span>

- [<span data-ttu-id="a2d08-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="a2d08-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="a2d08-146">クエリ</span><span class="sxs-lookup"><span data-stu-id="a2d08-146">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a2d08-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a2d08-147">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="a2d08-148">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="a2d08-148">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
