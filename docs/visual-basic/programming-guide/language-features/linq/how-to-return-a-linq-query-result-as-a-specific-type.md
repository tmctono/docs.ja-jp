---
title: '方法 : 特定の型での LINQ クエリ結果の取得'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], specific type returned
- projection [LINQ in Visual Basic]
- anonymous types [Visual Basic]
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: 621bb10a-e5d7-44fb-a025-317964b19d92
ms.openlocfilehash: 1084743b0c50d381375b76a3116ed7c9e6f9d769
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354200"
---
# <a name="how-to-return-a-linq-query-result-as-a-specific-type-visual-basic"></a><span data-ttu-id="ee20f-102">方法 : LINQ クエリ結果を特定の型で返す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee20f-102">How to: Return a LINQ Query Result as a Specific Type (Visual Basic)</span></span>
<span data-ttu-id="ee20f-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span> <span data-ttu-id="ee20f-104">既定では、LINQ クエリは、オブジェクトの一覧を匿名型として返します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-104">By default, LINQ queries return a list of objects as an anonymous type.</span></span> <span data-ttu-id="ee20f-105">また、`Select` 句を使用して、クエリが特定の型のリストを返すように指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-105">You can also specify that a query return a list of a specific type by using the `Select` clause.</span></span>  
  
 <span data-ttu-id="ee20f-106">次の例では、SQL Server データベースに対してクエリを実行する新しいアプリケーションを作成し、その結果を特定の名前付きの型として射影する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-106">The following example shows how to create a new application that performs queries against a SQL Server database and projects the results as a specific named type.</span></span> <span data-ttu-id="ee20f-107">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」と「 [Select 句](../../../../visual-basic/language-reference/queries/select-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee20f-107">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md).</span></span>  
  
 <span data-ttu-id="ee20f-108">このトピックの例では、Northwind サンプルデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="ee20f-109">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="ee20f-110">手順については、「[サンプルデータベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee20f-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="ee20f-111">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="ee20f-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="ee20f-112">Visual Studio で**サーバーエクスプローラー**/**データベースエクスプローラー**を開くには、 **[表示]** メニューの [**サーバーエクスプローラー** **/データベースエクスプローラー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="ee20f-113">**サーバーエクスプローラー**/で **[データ接続]** を右クリックし**データベースエクスプローラー** **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="ee20f-114">Northwind サンプルデータベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="ee20f-115">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="ee20f-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="ee20f-116">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="ee20f-117">プロジェクトの種類として [Visual Basic **Windows フォームアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="ee20f-118">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="ee20f-119">**[LINQ to SQL Classes]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="ee20f-120">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="ee20f-121">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-121">Click **Add**.</span></span> <span data-ttu-id="ee20f-122">Northwind .dbml ファイルのオブジェクトリレーショナルデザイナー (O/R デザイナー) が開きます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="ee20f-123">O/R デザイナーに対してクエリを実行するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="ee20f-123">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="ee20f-124">**サーバーエクスプローラー**/**データベースエクスプローラー**で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="ee20f-125">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-125">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="ee20f-126">O/R デザイナーを閉じた場合は、前の手順で追加した northwind .dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="ee20f-127">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-127">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="ee20f-128">デザイナーによって、プロジェクトの新しい `Customer` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-128">The designer creates a new `Customer` object for your project.</span></span> <span data-ttu-id="ee20f-129">クエリ結果は、`Customer` の種類として、または作成する型として射影できます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-129">You can project a query result as the `Customer` type or as a type that you create.</span></span> <span data-ttu-id="ee20f-130">このサンプルでは、後の手順で新しい型を作成し、その型としてクエリ結果を射影します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-130">This sample will create a new type in a later procedure and project a query result as that type.</span></span>  
  
3. <span data-ttu-id="ee20f-131">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="ee20f-132">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="ee20f-133">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="ee20f-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="ee20f-134">**[ツールボックス]** から、[<xref:System.Windows.Forms.DataGridView>] コントロールをプロジェクト Form1 の既定の Windows フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ee20f-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="ee20f-135">Form1 をダブルクリックして、Form1 クラスを変更します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-135">Double-click Form1 to modify the Form1 class.</span></span>  
  
3. <span data-ttu-id="ee20f-136">Form1 クラスの `End Class` ステートメントの後に、次のコードを追加して、このサンプルのクエリ結果を保持する `CustomerInfo` 型を作成します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-136">After the `End Class` statement of the Form1 class, add the following code to create a `CustomerInfo` type to hold the query results for this sample.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#16)]  
  
4. <span data-ttu-id="ee20f-137">O/R デザイナーにテーブルを追加すると、デザイナーによって <xref:System.Data.Linq.DataContext> オブジェクトがプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-137">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="ee20f-138">このオブジェクトには、これらのテーブルにアクセスし、各テーブルの個々のオブジェクトとコレクションにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee20f-138">This object contains the code that you must have to access those tables, and to access individual objects and collections for each table.</span></span> <span data-ttu-id="ee20f-139">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトは、.dbml ファイルの名前に基づいて名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-139">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="ee20f-140">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext`という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="ee20f-140">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="ee20f-141">コード内に <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ee20f-141">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="ee20f-142">Form1 クラスの `Load` イベントで、次のコードを追加して、データコンテキストのプロパティとして公開されているテーブルに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-142">In the `Load` event of the Form1 class, add the following code to query the tables that are exposed as properties of your data context.</span></span> <span data-ttu-id="ee20f-143">クエリの `Select` 句は、クエリ結果の各項目に対して匿名型ではなく、新しい `CustomerInfo` 型を作成します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-143">The `Select` clause of the query will create a new `CustomerInfo` type instead of an anonymous type for each item of the query result.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form8.vb#15)]  
  
5. <span data-ttu-id="ee20f-144">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="ee20f-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee20f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee20f-145">See also</span></span>

- [<span data-ttu-id="ee20f-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="ee20f-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="ee20f-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="ee20f-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="ee20f-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="ee20f-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="ee20f-149">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="ee20f-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
