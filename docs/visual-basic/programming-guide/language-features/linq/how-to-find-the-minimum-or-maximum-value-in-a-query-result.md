---
title: '方法: LINQ を使用してクエリ結果の最小値または最大値を検索する'
ms.date: 07/20/2015
helpviewer_keywords:
- max operator [LINQ in Visual Basic]
- aggregate operator [LINQ in Visual Basic]
- aggregate queries
- minimum values [LINQ in Visual Basic]
- min operator [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], minimum and maximum values
- Max property
- maximum values [LINQ in Visual Basic]
- Aggregate clause [Visual Basic]
- queries [LINQ in Visual Basic], aggregate queries
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 238b763b-7dcd-4b14-8050-b65500a4f71c
ms.openlocfilehash: bddb90baa0b01fd9d724583b472af9f9fa7569e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344977"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="b396e-102">方法 : LINQ を使用したクエリ結果内の最小値と最大値の検索 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b396e-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="b396e-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b396e-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="b396e-104">次の例では、SQL Server データベースに対してクエリを実行する新しいアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b396e-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="b396e-105">このサンプルでは、`Aggregate` 句と `Group By` 句を使用して、結果の最小値と最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="b396e-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="b396e-106">詳細については、「 [Aggregate 句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)と[Group by 句](../../../../visual-basic/language-reference/queries/group-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b396e-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="b396e-107">このトピックの例では、Northwind サンプルデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="b396e-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="b396e-108">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b396e-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="b396e-109">手順については、「[サンプルデータベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b396e-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="b396e-110">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="b396e-110">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="b396e-111">Visual Studio で**サーバーエクスプローラー**/**データベースエクスプローラー**を開くには、 **[表示]** メニューの [**サーバーエクスプローラー** **/データベースエクスプローラー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b396e-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="b396e-112">**サーバーエクスプローラー**/で **[データ接続]** を右クリックし**データベースエクスプローラー** **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b396e-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="b396e-113">Northwind サンプルデータベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="b396e-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="b396e-114">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="b396e-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="b396e-115">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b396e-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="b396e-116">プロジェクトの種類として [Visual Basic **Windows フォームアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b396e-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="b396e-117">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b396e-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="b396e-118">**[LINQ to SQL Classes]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="b396e-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="b396e-119">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="b396e-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="b396e-120">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b396e-120">Click **Add**.</span></span> <span data-ttu-id="b396e-121">Northwind .dbml ファイルのオブジェクトリレーショナルデザイナー (O/R デザイナー) が開きます。</span><span class="sxs-lookup"><span data-stu-id="b396e-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="b396e-122">O/R デザイナーに対してクエリを実行するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="b396e-122">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="b396e-123">**サーバーエクスプローラー**/**データベースエクスプローラー**で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="b396e-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="b396e-124">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="b396e-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="b396e-125">O/R デザイナーを閉じた場合は、前の手順で追加した northwind .dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b396e-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="b396e-126">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b396e-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="b396e-127">[Orders] テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b396e-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="b396e-128">デザイナーによって、プロジェクトの新しい `Customer` と `Order` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b396e-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="b396e-129">デザイナーがテーブル間のリレーションシップを自動的に検出し、関連するオブジェクトの子プロパティを作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b396e-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="b396e-130">たとえば、IntelliSense は、`Customer` オブジェクトに、その顧客に関連するすべての注文に対して `Orders` プロパティがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="b396e-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="b396e-131">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b396e-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="b396e-132">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="b396e-132">Save your project.</span></span>  
  
### <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="b396e-133">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="b396e-133">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="b396e-134">**[ツールボックス]** から、[<xref:System.Windows.Forms.DataGridView>] コントロールをプロジェクト Form1 の既定の Windows フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="b396e-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="b396e-135">Form1 をダブルクリックして、フォームの `Load` イベントにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b396e-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="b396e-136">O/R デザイナーにテーブルを追加したときに、デザイナーによってプロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b396e-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="b396e-137">このオブジェクトには、各テーブルの個々のオブジェクトとコレクションに加えて、それらのテーブルにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b396e-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="b396e-138">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトは、.dbml ファイルの名前に基づいて名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="b396e-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="b396e-139">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext`という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="b396e-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="b396e-140">コード内に <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b396e-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="b396e-141">`Load` イベントに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="b396e-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="b396e-142">このコードは、データコンテキストのプロパティとして公開されているテーブルに対してクエリを実行し、結果の最小値と最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="b396e-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="b396e-143">このサンプルでは、`Aggregate` 句を使用して1つの結果をクエリし、`Group By` 句を使用してグループ化された結果の平均を表示します。</span><span class="sxs-lookup"><span data-stu-id="b396e-143">The sample uses he `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="b396e-144">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="b396e-144">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b396e-145">参照</span><span class="sxs-lookup"><span data-stu-id="b396e-145">See also</span></span>

- [<span data-ttu-id="b396e-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="b396e-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="b396e-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="b396e-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="b396e-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b396e-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="b396e-149">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="b396e-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
