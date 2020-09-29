---
title: '方法: 特定の型での LINQ クエリ結果の取得'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 249c3eebaeec3d09a297fead07ab056caff1b618
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071808"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="d1786-102">方法: 特定の型での LINQ クエリ結果の取得 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1786-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>

<span data-ttu-id="d1786-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1786-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="d1786-104">既定では、LINQ クエリは、オブジェクトの一覧を匿名型として返します。</span><span class="sxs-lookup"><span data-stu-id="d1786-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="d1786-105">また、`Select` 句を使用して、クエリが特定の型の一覧を返すように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1786-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="d1786-106">次の例は、SQL Server データベースに対してクエリを実行し、特定の名前付きの型として結果を射影する新しいアプリケーションの作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1786-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="d1786-107">詳細については、「[匿名型](../objects-and-classes/anonymous-types.md)」および「[Select 句](../../../language-reference/queries/select-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1786-107">For more information, see [Anonymous Types](../objects-and-classes/anonymous-types.md) and [Select Clause](../../../language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="d1786-108">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1786-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="d1786-109">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d1786-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="d1786-110">手順については、「[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1786-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="d1786-111">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="d1786-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="d1786-112">Visual Studio で、 **[表示]** メニューの **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** をクリックして、 **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="d1786-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="d1786-113">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で **[データ接続]** を右クリックし、 **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1786-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="d1786-114">Northwind サンプル データベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1786-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="d1786-115">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="d1786-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="d1786-116">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1786-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="d1786-117">プロジェクト タイプとして Visual Basic **[Windows フォーム アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1786-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="d1786-118">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1786-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="d1786-119">**[LINQ to SQL クラス]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1786-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="d1786-120">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="d1786-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="d1786-121">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1786-121">Click **Add**.</span></span> <span data-ttu-id="d1786-122">オブジェクト リレーショナル デザイナー (O/R デザイナー) が northwind.dbml ファイル用に開きます。</span><span class="sxs-lookup"><span data-stu-id="d1786-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="d1786-123">O/R デザイナーにクエリを実行する対象のテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="d1786-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="d1786-124">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="d1786-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="d1786-125">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d1786-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="d1786-126">O/R デザイナーを閉じている場合は、前に追加した northwind.dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d1786-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="d1786-127">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1786-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="d1786-128">デザイナーによって、プロジェクトの新しい `Customer` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1786-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="d1786-129">クエリ結果は、`Customer` 型として、または作成する型として射影できます。</span><span class="sxs-lookup"><span data-stu-id="d1786-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="d1786-130">このサンプルでは、後のプロシージャで新しい型を作成し、その型としてクエリ結果を射影します。</span><span class="sxs-lookup"><span data-stu-id="d1786-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="d1786-131">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d1786-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="d1786-132">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="d1786-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="d1786-133">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="d1786-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="d1786-134">**[ツールボックス]** から、プロジェクトの既定の Windows フォームである Form1 に <xref:System.Windows.Forms.DataGridView> コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="d1786-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="d1786-135">Form1 をダブルクリックして、Form1 クラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="d1786-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="d1786-136">Form1 クラスの `End Class` ステートメントの後に、次のコードを追加して、このサンプルのクエリ結果を保持する `CustomerInfo` 型を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1786-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="d1786-137">テーブルを O/R デザイナーに追加したときに、<xref:System.Data.Linq.DataContext> オブジェクトがプロジェクトに追加されました。</span><span class="sxs-lookup"><span data-stu-id="d1786-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="d1786-138">このオブジェクトには、これらのテーブルにアクセスするため、および各テーブルの個々のオブジェクトとコレクションにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1786-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="d1786-139">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトの名前は、.dbml ファイルの名前に基づいて付けられます。</span><span class="sxs-lookup"><span data-stu-id="d1786-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="d1786-140">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext` という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="d1786-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="d1786-141">コードで <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1786-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="d1786-142">Form1 クラスの `Load` イベントで、データ コンテキストのプロパティとして公開されているテーブルに対してクエリを実行するために、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1786-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="d1786-143">クエリの `Select` 句は、クエリ結果の各項目に対して匿名型ではなく、新しい `CustomerInfo` 型を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1786-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="d1786-144">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1786-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1786-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1786-145">See also</span></span>

- [<span data-ttu-id="d1786-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="d1786-146">LINQ</span></span>](index.md)
- [<span data-ttu-id="d1786-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="d1786-147">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="d1786-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d1786-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="d1786-149">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="d1786-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
