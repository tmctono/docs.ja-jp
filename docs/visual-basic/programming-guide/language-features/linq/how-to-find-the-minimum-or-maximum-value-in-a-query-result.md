---
title: '方法 : LINQ を使用したクエリ結果内の最小値と最大値の検索'
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
ms.openlocfilehash: ef5f218cdcc7275f616486110825ad0b9df11cc3
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112363"
---
# <a name="how-to-find-the-minimum-or-maximum-value-in-a-query-result-by-using-linq-visual-basic"></a><span data-ttu-id="a2d5d-102">方法 : LINQ を使用したクエリ結果内の最小値と最大値の検索 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2d5d-102">How to: Find the Minimum or Maximum Value in a Query Result by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="a2d5d-103">統合言語クエリ (LINQ) を使用すると、データベース情報に簡単にアクセスし、クエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-103">Language-Integrated Query (LINQ) makes it easy to access database information and execute queries.</span></span>  
  
 <span data-ttu-id="a2d5d-104">SQL Server データベースに対してクエリを実行する新しいアプリケーションを作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-104">The following example shows how to create a new application that performs queries against a SQL Server database.</span></span> <span data-ttu-id="a2d5d-105">サンプルでは、 および`Aggregate``Group By`句を使用して、結果の最小値と最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-105">The sample determines the minimum and maximum values for the results by using the `Aggregate` and `Group By` clauses.</span></span> <span data-ttu-id="a2d5d-106">詳細については、「[集計句](../../../../visual-basic/language-reference/queries/aggregate-clause.md)と[グループ化句](../../../../visual-basic/language-reference/queries/group-by-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-106">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="a2d5d-107">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-107">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="a2d5d-108">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-108">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="a2d5d-109">手順については、「[サンプル データベースのダウンロード」を参照してください](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-109">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="create-a-connection-to-a-database"></a><span data-ttu-id="a2d5d-110">データベースへの接続を作成する</span><span class="sxs-lookup"><span data-stu-id="a2d5d-110">Create a connection to a database</span></span>  
  
1. <span data-ttu-id="a2d5d-111">Visual Studio で、[**表示**] メニューの **[サーバー エクスプローラ**/**データベース エクスプローラー** ] をクリックして **、サーバー エクスプローラ**/データベース**エクスプローラー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-111">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="a2d5d-112">**サーバー エクスプローラ**/**データベース エクスプローラ**で **[データ接続**] を右クリックし、[**接続の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-112">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="a2d5d-113">ノースウィンド サンプル データベースへの有効な接続を指定してください。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-113">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="a2d5d-114">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="a2d5d-114">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="a2d5d-115">Visual Studio で、[**ファイル**] メニューの [**新規作成**] をポイントし、[**プロジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-115">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="a2d5d-116">プロジェクトの種類**として [Visual** Basic Windows フォーム アプリケーション] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-116">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="a2d5d-117">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-117">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a2d5d-118">[LINQ **to SQL クラス]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-118">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="a2d5d-119">このファイルには `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-119">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="a2d5d-120">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-120">Click **Add**.</span></span> <span data-ttu-id="a2d5d-121">northwind.dbml ファイル用にオブジェクト リレーショナル デザイナー (O/R デザイナー) が開かれます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-121">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
## <a name="add-tables-to-query-to-the-or-designer"></a><span data-ttu-id="a2d5d-122">O/R デザイナーにクエリするテーブルを追加する</span><span class="sxs-lookup"><span data-stu-id="a2d5d-122">Add tables to query to the O/R Designer</span></span>  
  
1. <span data-ttu-id="a2d5d-123">**サーバー エクスプローラ**/**のデータベース エクスプローラ**で、ノースウィンド データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-123">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="a2d5d-124">**[テーブル]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-124">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="a2d5d-125">O/R デザイナーを閉じた場合は、前に追加した northwind.dbml ファイルをダブルクリックして、再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-125">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="a2d5d-126">[得意先] テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-126">Click the Customers table and drag it to the left pane of the designer.</span></span> <span data-ttu-id="a2d5d-127">[受注] テーブルをクリックし、デザイナーの左ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-127">Click the Orders table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="a2d5d-128">デザイナーは、プロジェクト`Customer`の`Order`新しいオブジェクトとオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-128">The designer creates new `Customer` and `Order` objects for your project.</span></span> <span data-ttu-id="a2d5d-129">デザイナーは、テーブル間のリレーションシップを自動的に検出し、関連するオブジェクトの子プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-129">Notice that the designer automatically detects relationships between the tables and creates child properties for related objects.</span></span> <span data-ttu-id="a2d5d-130">たとえば、IntelliSense は、その顧客`Customer`に関連するすべての`Orders`注文のプロパティをオブジェクトが持っていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-130">For example, IntelliSense will show that the `Customer` object has an `Orders` property for all orders related to that customer.</span></span>  
  
3. <span data-ttu-id="a2d5d-131">変更を保存してデザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-131">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="a2d5d-132">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-132">Save your project.</span></span>  
  
## <a name="add-code-to-query-the-database-and-display-the-results"></a><span data-ttu-id="a2d5d-133">データベースにクエリを実行して結果を表示するコードを追加する</span><span class="sxs-lookup"><span data-stu-id="a2d5d-133">Add code to query the database and display the results</span></span>  
  
1. <span data-ttu-id="a2d5d-134">[**ツールボックス**] から、<xref:System.Windows.Forms.DataGridView>プロジェクトの既定の Windows フォーム Form1 にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="a2d5d-135">Form1 をダブルクリックして、フォームの`Load`イベントにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-135">Double-click Form1 to add code to the `Load` event of the form.</span></span>  
  
3. <span data-ttu-id="a2d5d-136">テーブルを O/R デザイナーに追加すると、デザイナーによってプロジェクト<xref:System.Data.Linq.DataContext>のオブジェクトが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-136">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="a2d5d-137">このオブジェクトには、各テーブルの個々のオブジェクトとコレクションに加えて、これらのテーブルにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-137">This object contains the code that you must have to access those tables, in addition to individual objects and collections for each table.</span></span> <span data-ttu-id="a2d5d-138">プロジェクト<xref:System.Data.Linq.DataContext>のオブジェクトは、.dbml ファイルの名前に基づいて命名されます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-138">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="a2d5d-139">このプロジェクトでは、オブジェクト<xref:System.Data.Linq.DataContext>の名前`northwindDataContext`は です。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-139">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="a2d5d-140">のインスタンスをコード<xref:System.Data.Linq.DataContext>に作成し、O/R デザイナーで指定されたテーブルにクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-140">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and query the tables specified by the O/R Designer.</span></span>  
  
     <span data-ttu-id="a2d5d-141">イベントに次のコードを`Load`追加します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-141">Add the following code to the `Load` event.</span></span> <span data-ttu-id="a2d5d-142">このコードは、データ コンテキストのプロパティとして公開されているテーブルを照会し、結果の最小値と最大値を決定します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-142">This code queries the tables that are exposed as properties of your data context and determines the minimum and maximum values for the results.</span></span> <span data-ttu-id="a2d5d-143">このサンプルでは、`Aggregate`この句を使用して 1 つの結果`Group By`を照会し、句を使用してグループ化された結果の平均を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-143">The sample uses the `Aggregate` clause to query for a single result, and the `Group By` clause to show an average for grouped results.</span></span>  
  
     [!code-vb[VbLINQToSQLHowTos#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form7.vb#14)]  
  
4. <span data-ttu-id="a2d5d-144">**F5 キー**を押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2d5d-144">Press **F5** to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d5d-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2d5d-145">See also</span></span>

- [<span data-ttu-id="a2d5d-146">LINQ</span><span class="sxs-lookup"><span data-stu-id="a2d5d-146">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="a2d5d-147">クエリ</span><span class="sxs-lookup"><span data-stu-id="a2d5d-147">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a2d5d-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a2d5d-148">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="a2d5d-149">データ コンテキスト メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="a2d5d-149">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
