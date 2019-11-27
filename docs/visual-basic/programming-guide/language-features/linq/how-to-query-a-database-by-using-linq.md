---
title: '方法: LINQ を使用してデータベースを照会する'
ms.date: 07/20/2015
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
ms.openlocfilehash: f4b2510bad2b23d7a0e179383b34c4e425e6564e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344957"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="24dd0-102">方法 : LINQ を使用してデータベースを照会する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24dd0-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="24dd0-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="24dd0-104">次の例では、SQL Server データベースに対してクエリを実行する新しいアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="24dd0-105">このトピックの例では、Northwind サンプルデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="24dd0-106">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="24dd0-107">手順については、「[サンプルデータベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24dd0-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="24dd0-108">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="24dd0-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="24dd0-109">Visual Studio で**サーバーエクスプローラー**/**データベースエクスプローラー**を開くには、 **[表示]** メニューの [**サーバーエクスプローラー** **/データベースエクスプローラー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="24dd0-110">**サーバーエクスプローラー**/で **[データ接続]** を右クリックし**データベースエクスプローラー** **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="24dd0-111">Northwind サンプルデータベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="24dd0-112">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="24dd0-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="24dd0-113">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="24dd0-114">プロジェクトの種類として [Visual Basic **Windows フォームアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="24dd0-115">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="24dd0-116">**[LINQ to SQL Classes]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="24dd0-117">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="24dd0-118">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-118">Click **Add**.</span></span> <span data-ttu-id="24dd0-119">Northwind .dbml ファイルのオブジェクトリレーショナルデザイナー (O/R デザイナー) が開きます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="24dd0-120">O/R デザイナーに対してクエリを実行するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="24dd0-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="24dd0-121">**サーバーエクスプローラー**/**データベースエクスプローラー**で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="24dd0-122">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="24dd0-123">O/R デザイナーを閉じた場合は、前の手順で追加した northwind .dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="24dd0-124">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="24dd0-125">[Orders] テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="24dd0-126">デザイナーによって、プロジェクトの新しい `Customer` と `Order` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="24dd0-127">デザイナーがテーブル間のリレーションシップを自動的に検出し、関連するオブジェクトの子プロパティを作成することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="24dd0-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="24dd0-128">たとえば、IntelliSense は、`Customer` オブジェクトに、その顧客に関連するすべての注文に対して `Orders` プロパティがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="24dd0-129">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="24dd0-130">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="24dd0-131">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="24dd0-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="24dd0-132">**[ツールボックス]** から、[<xref:System.Windows.Forms.DataGridView>] コントロールをプロジェクト Form1 の既定の Windows フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="24dd0-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="24dd0-133">Form1 をダブルクリックして、フォームの `Load` イベントにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="24dd0-134">O/R デザイナーにテーブルを追加したときに、デザイナーによってプロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトが追加されました。</span><span class="sxs-lookup"><span data-stu-id="24dd0-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="24dd0-135">このオブジェクトには、各テーブルの個々のオブジェクトとコレクションに加えて、それらのテーブルにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="24dd0-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="24dd0-136">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトは、.dbml ファイルの名前に基づいて名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="24dd0-137">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext`という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="24dd0-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="24dd0-138">コード内に <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="24dd0-139">次のコードを `Load` イベントに追加して、データコンテキストのプロパティとして公開されているテーブルに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="24dd0-140">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="24dd0-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="24dd0-141">次のようなクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="24dd0-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="24dd0-142">参照</span><span class="sxs-lookup"><span data-stu-id="24dd0-142">See also</span></span>

- [<span data-ttu-id="24dd0-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="24dd0-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="24dd0-144">クエリ</span><span class="sxs-lookup"><span data-stu-id="24dd0-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="24dd0-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="24dd0-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="24dd0-146">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="24dd0-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
