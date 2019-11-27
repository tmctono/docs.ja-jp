---
title: '方法: LINQ を使用してストアドプロシージャを呼び出す'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
ms.openlocfilehash: f91ccda1842887b3785ce304fd41bdd020a55479
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345020"
---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a><span data-ttu-id="7cedb-102">方法 : LINQ を使用してストアド プロシージャを呼び出す (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7cedb-102">How to: Call a Stored Procedure by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="7cedb-103">統合言語クエリ (LINQ) を使用すると、ストアドプロシージャなどのデータベースオブジェクトを含むデータベース情報に簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-103">Language-Integrated Query (LINQ) makes it easy to access database information, including database objects such as stored procedures.</span></span>  
  
 <span data-ttu-id="7cedb-104">次の例では、SQL Server データベースでストアドプロシージャを呼び出すアプリケーションを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-104">The following example shows how to create an application that calls a stored procedure in a SQL Server database.</span></span> <span data-ttu-id="7cedb-105">このサンプルでは、データベースで2つの異なるストアドプロシージャを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-105">The sample shows how to call two different stored procedures in the database.</span></span> <span data-ttu-id="7cedb-106">各プロシージャは、クエリの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-106">Each procedure returns the results of a query.</span></span> <span data-ttu-id="7cedb-107">1つのプロシージャは入力パラメーターを受け取り、もう一方のプロシージャはパラメーターを受け取りません。</span><span class="sxs-lookup"><span data-stu-id="7cedb-107">One procedure takes input parameters, and the other procedure does not take parameters.</span></span>  
  
 <span data-ttu-id="7cedb-108">このトピックの例では、Northwind サンプルデータベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-108">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="7cedb-109">開発用コンピューターにこのデータベースがない場合は、Microsoft ダウンロード センターからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-109">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="7cedb-110">手順については、「[サンプルデータベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7cedb-110">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="7cedb-111">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="7cedb-111">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="7cedb-112">Visual Studio で**サーバーエクスプローラー**/**データベースエクスプローラー**を開くには、 **[表示]** メニューの [**サーバーエクスプローラー** **/データベースエクスプローラー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-112">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking **Server Explorer**/**Database Explorer** on the **View** menu.</span></span>  
  
2. <span data-ttu-id="7cedb-113">**サーバーエクスプローラー**/で **[データ接続]** を右クリックし**データベースエクスプローラー** **[接続の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-113">Right-click **Data Connections** in **Server Explorer**/**Database Explorer** and then click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="7cedb-114">Northwind サンプルデータベースへの有効な接続を指定します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-114">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a><span data-ttu-id="7cedb-115">LINQ to SQL ファイルを含むプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="7cedb-115">To add a project that contains a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="7cedb-116">Visual Studio で、 **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-116">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="7cedb-117">プロジェクトの種類として [Visual Basic **Windows フォームアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-117">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="7cedb-118">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-118">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7cedb-119">**[LINQ to SQL Classes]** 項目テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-119">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="7cedb-120">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-120">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="7cedb-121">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-121">Click **Add**.</span></span> <span data-ttu-id="7cedb-122">Northwind .dbml ファイルのオブジェクトリレーショナルデザイナー (O/R デザイナー) が開きます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-122">The Object Relational Designer (O/R Designer) is opened for the northwind.dbml file.</span></span>  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a><span data-ttu-id="7cedb-123">ストアドプロシージャを O/R デザイナーに追加するには</span><span class="sxs-lookup"><span data-stu-id="7cedb-123">To add stored procedures to the O/R Designer</span></span>  
  
1. <span data-ttu-id="7cedb-124">**サーバーエクスプローラー**/**データベースエクスプローラー**で、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-124">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="7cedb-125">**[ストアドプロシージャ]** フォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-125">Expand the **Stored Procedures** folder.</span></span>  
  
     <span data-ttu-id="7cedb-126">O/R デザイナーを閉じた場合は、前の手順で追加した northwind .dbml ファイルをダブルクリックして再度開くことができます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-126">If you have closed the O/R Designer, you can reopen it by double-clicking the northwind.dbml file that you added earlier.</span></span>  
  
2. <span data-ttu-id="7cedb-127">**[Sales By Year]** ストアドプロシージャをクリックし、デザイナーの右ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-127">Click the **Sales by Year** stored procedure and drag it to the right pane of the designer.</span></span> <span data-ttu-id="7cedb-128">**[最もコストの高い10個の製品]** ストアドプロシージャをクリックして、デザイナーの右ペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-128">Click the **Ten Most Expensive Products** stored procedure drag it to the right pane of the designer.</span></span>  
  
3. <span data-ttu-id="7cedb-129">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-129">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="7cedb-130">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-130">Save your project.</span></span>  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a><span data-ttu-id="7cedb-131">ストアドプロシージャの結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="7cedb-131">To add code to display the results of the stored procedures</span></span>  
  
1. <span data-ttu-id="7cedb-132">**[ツールボックス]** から、[<xref:System.Windows.Forms.DataGridView>] コントロールをプロジェクト Form1 の既定の Windows フォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="7cedb-132">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="7cedb-133">Form1 をダブルクリックして、`Load` イベントにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-133">Double-click Form1 to add code to its `Load` event.</span></span>  
  
3. <span data-ttu-id="7cedb-134">ストアドプロシージャを O/R デザイナーに追加したときに、デザイナーによってプロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトが追加されました。</span><span class="sxs-lookup"><span data-stu-id="7cedb-134">When you added stored procedures to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object for your project.</span></span> <span data-ttu-id="7cedb-135">このオブジェクトには、これらのプロシージャにアクセスするために必要なコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7cedb-135">This object contains the code that you must have to access those procedures.</span></span> <span data-ttu-id="7cedb-136">プロジェクトの <xref:System.Data.Linq.DataContext> オブジェクトの名前は、.dbml ファイルの名前に基づいて付けられます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-136">The <xref:System.Data.Linq.DataContext> object for the project is named based on the name of the .dbml file.</span></span> <span data-ttu-id="7cedb-137">このプロジェクトでは、<xref:System.Data.Linq.DataContext> オブジェクトに `northwindDataContext`という名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="7cedb-137">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="7cedb-138">コード内に <xref:System.Data.Linq.DataContext> のインスタンスを作成し、O/R デザイナーによって指定されたストアドプロシージャメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-138">You can create an instance of the <xref:System.Data.Linq.DataContext> in your code and call the stored procedure methods specified by the O/R Designer.</span></span> <span data-ttu-id="7cedb-139"><xref:System.Windows.Forms.DataGridView> オブジェクトにバインドするには、ストアドプロシージャの結果に対して <xref:System.Linq.Enumerable.ToList%2A> メソッドを呼び出すことによって、クエリの実行を直ちに強制する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7cedb-139">To bind to the <xref:System.Windows.Forms.DataGridView> object, you may have to force the query to execute immediately by calling the <xref:System.Linq.Enumerable.ToList%2A> method on the results of the stored procedure.</span></span>  
  
     <span data-ttu-id="7cedb-140">次のコードを `Load` イベントに追加して、データコンテキストのメソッドとして公開されているストアドプロシージャのいずれかを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7cedb-140">Add the following code to the `Load` event to call either of the stored procedures exposed as methods for your data context.</span></span>  
  
     [!code-vb[VbLINQtoSQLHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#1)]  
    [!code-vb[VbLINQtoSQLHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQtoSQLHowTos/VB/Form3.vb#2)]  
  
4. <span data-ttu-id="7cedb-141">F5 キーを押してプロジェクトを実行し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="7cedb-141">Press F5 to run your project and view the results.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cedb-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="7cedb-142">See also</span></span>

- [<span data-ttu-id="7cedb-143">LINQ</span><span class="sxs-lookup"><span data-stu-id="7cedb-143">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="7cedb-144">クエリ</span><span class="sxs-lookup"><span data-stu-id="7cedb-144">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="7cedb-145">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7cedb-145">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="7cedb-146">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="7cedb-146">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="7cedb-147">方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="7cedb-147">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
