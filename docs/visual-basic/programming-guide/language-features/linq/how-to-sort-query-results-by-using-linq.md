---
title: '方法: LINQ を使用してクエリ結果を並べ替える'
ms.date: 07/20/2015
helpviewer_keywords:
- sorting query results, multiple columns
- sorting data [Visual Basic]
- sorting data [LINQ in Visual Basic]
- sorting query results [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], sorting results
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 07a4584d-9fd8-4a1d-b7d9-ccf2efa5c84e
ms.openlocfilehash: c1bc6ab863f9de118d59e102d3d5d251d326f497
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404940"
---
# <a name="how-to-sort-query-results-by-using-linq-visual-basic"></a><span data-ttu-id="f8a48-102">方法: LINQ を使用してクエリ結果を並べ替える (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8a48-102">How to: Sort Query Results by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="f8a48-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="f8a48-104">次の例は、SQL Server データベースに対してクエリを実行し、`Order By` 句を使用して複数のフィールドで結果を並べ替える新しいアプリケーションの作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8a48-104">The following example shows how to create a new application that performs queries against a SQL Server database and sorts the results by multiple fields by using the `Order By` clause.</span></span> <span data-ttu-id="f8a48-105">各フィールドの並べ替え順序は、昇順または降順にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-105">The sort order for each field can be ascending order or descending order.</span></span> <span data-ttu-id="f8a48-106">詳細については、「[Order By 句](../../../language-reference/queries/order-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a48-106">For more information, see [Order By Clause](../../../language-reference/queries/order-by-clause.md).</span></span>  
  
 <span data-ttu-id="f8a48-107">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="f8a48-108">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="f8a48-109">手順については、「[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8a48-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="f8a48-110">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="f8a48-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="f8a48-111">Visual Studio で、 **[表示]** メニューの **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** をクリックして、 **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="f8a48-112">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で **[データ接続]** を右クリックし、 **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="f8a48-113">Northwind サンプル データベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="f8a48-114">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="f8a48-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="f8a48-115">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="f8a48-116">プロジェクト タイプとして Visual Basic **[Windows フォーム アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="f8a48-117">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="f8a48-118">**[LINQ to SQL クラス]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="f8a48-119">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="f8a48-120">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-120">Click **Add**.</span></span> <span data-ttu-id="f8a48-121">オブジェクト リレーショナル デザイナー (O/R デザイナー) が northwind.dbml ファイル用に開きます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="f8a48-122">O/R デザイナーにクエリを実行する対象のテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="f8a48-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="f8a48-123">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="f8a48-124">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="f8a48-125">O/R デザイナーを閉じている場合は、前に追加した northwind.dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="f8a48-126">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="f8a48-127">Orders テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="f8a48-128">デザイナーによって、プロジェクトの新しい `Customer` と `Order` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="f8a48-129">デザイナーがテーブル間のリレーションシップを自動的に検出し、関連するオブジェクトの子プロパティを作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f8a48-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="f8a48-130">たとえば、IntelliSense は、`Customer` オブジェクトに、その顧客に関連するすべての注文のための `Orders` プロパティがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="f8a48-131">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="f8a48-132">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="f8a48-133">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="f8a48-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="f8a48-134">**[ツールボックス]** から、プロジェクトの既定の Windows フォームである Form1 に <xref:System.Windows.Forms.DataGridView> コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="f8a48-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="f8a48-135">Form1 をダブルクリックして、フォームの `Load` イベントにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="f8a48-136">テーブルを O/R デザイナーに追加したときに、デザイナーによって <xref:System.Data.Linq.DataContext> オブジェクトがプロジェクトに追加されました。</span><span class="sxs-lookup"><span data-stu-id="f8a48-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="f8a48-137">このオブジェクトには、これらのテーブルにアクセスするため、および各テーブルの個々のオブジェクトとコレクションにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f8a48-137">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="f8a48-138">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトの名前は、.dbml ファイルの名前に基づいて付けられます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="f8a48-139">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext` という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="f8a48-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="f8a48-140">コード内で <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="f8a48-141">データ コンテキストのプロパティとして公開されているテーブルに対してクエリを実行し、その結果を並べ替えるために、次のコードを `Load` イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-141">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context and sort the results.</span></span> <span data-ttu-id="f8a48-142">このクエリでは、顧客の注文数の降順で結果が並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-142">The query sorts the results by the number of customer orders, in descending order.</span></span> <span data-ttu-id="f8a48-143">顧客の注文数が同じ場合は、会社名の昇順 (既定) で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="f8a48-143">Customers that have the same number of orders are ordered by company name in ascending order (the default).</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form4.vb#10)]  
  
4. <span data-ttu-id="f8a48-144">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="f8a48-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a48-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8a48-145">See also</span></span>

- [<span data-ttu-id="f8a48-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="f8a48-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="f8a48-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="f8a48-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="f8a48-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f8a48-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="f8a48-149">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="f8a48-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
