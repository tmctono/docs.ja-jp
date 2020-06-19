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
ms.openlocfilehash: ad4744e1734fd968f610ec02b60814eadd3ebe9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404966"
---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="74913-102">方法: LINQ を使用してデータベースを照会する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74913-102">How to: Query a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="74913-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスしてクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="74913-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="74913-104">次の例は、SQL Server データベースに対してクエリを実行する新しいアプリケーションを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="74913-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span>  
  
 <span data-ttu-id="74913-105">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="74913-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="74913-106">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="74913-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="74913-107">手順については、「[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74913-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="74913-108">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="74913-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="74913-109">Visual Studio で、 **[表示]** メニューの **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** をクリックして、 **[サーバー エクスプローラー]** / **[データベース エクスプローラー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="74913-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="74913-110">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で **[データ接続]** を右クリックし、 **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74913-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="74913-111">Northwind サンプル データベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="74913-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="74913-112">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="74913-112">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="74913-113">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74913-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="74913-114">プロジェクト タイプとして Visual Basic **[Windows フォーム アプリケーション]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74913-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="74913-115">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74913-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="74913-116">**[LINQ to SQL クラス]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="74913-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="74913-117">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="74913-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="74913-118">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74913-118">Click **Add**.</span></span> <span data-ttu-id="74913-119">オブジェクト リレーショナル デザイナー (O/R デザイナー) が northwind.dbml ファイル用に開きます。</span><span class="sxs-lookup"><span data-stu-id="74913-119">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="74913-120">O/R デザイナーにクエリを実行するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="74913-120">To add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="74913-121">**[サーバー エクスプローラー]** / **[データベース エクスプローラー]** で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="74913-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="74913-122">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="74913-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="74913-123">O/R デザイナーを閉じている場合は、前に追加した northwind.dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="74913-123">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="74913-124">Customers テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="74913-124">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="74913-125">Orders テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="74913-125">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="74913-126">デザイナーによって、プロジェクトの新しい `Customer` と `Order` オブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="74913-126">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="74913-127">デザイナーによってテーブル間のリレーションシップが自動的に検出され、関連するオブジェクトの子プロパティが作成されることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="74913-127">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="74913-128">たとえば、IntelliSense では、`Customer` オブジェクトに、その顧客に関連するすべての注文の `Orders` プロパティがあることを示します。</span><span class="sxs-lookup"><span data-stu-id="74913-128">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="74913-129">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="74913-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="74913-130">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="74913-130">Save your project.</span></span>  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="74913-131">データベースに対してクエリを実行し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="74913-131">To add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="74913-132">**[ツールボックス]** から、プロジェクトの既定の Windows フォームである Form1 に <xref:System.Windows.Forms.DataGridView> コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="74913-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="74913-133">Form1 をダブルクリックして、コードをフォームの `Load` イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="74913-133">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="74913-134">テーブルを O/R デザイナーに追加したときに、<xref:System.Data.Linq.DataContext> オブジェクトがプロジェクトに追加されました。</span><span class="sxs-lookup"><span data-stu-id="74913-134">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="74913-135">このオブジェクトには、各テーブルの個々のオブジェクトとコレクションに加え、それらのテーブルにアクセスするために必要なコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="74913-135">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="74913-136">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトの名前は、.dbml ファイルの名前に基づいて付けられます。</span><span class="sxs-lookup"><span data-stu-id="74913-136">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="74913-137">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext` という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="74913-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="74913-138">コードで <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたテーブルに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="74913-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="74913-139">次のコードを `Load` イベントに追加し、データ コンテキストのプロパティとして公開されているテーブルに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="74913-139">Add the following code to the `Load` event to query the tables that are exposed as properties of your data context.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#3)]  
  
4. <span data-ttu-id="74913-140">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="74913-140">Press F5 to run your project and view the results.</span></span>  
  
5. <span data-ttu-id="74913-141">他にも、次のようなクエリをいくつか試すことができます。</span><span class="sxs-lookup"><span data-stu-id="74913-141">Following are some additional queries that you can try:</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#4)]  
    [!code-vb[VbLINQToSQLHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form2.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="74913-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="74913-142">See also</span></span>

- [<span data-ttu-id="74913-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="74913-143">LINQ</span></span>](index.md)
- [<span data-ttu-id="74913-144">クエリ</span><span class="sxs-lookup"><span data-stu-id="74913-144">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="74913-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="74913-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="74913-146">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="74913-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
