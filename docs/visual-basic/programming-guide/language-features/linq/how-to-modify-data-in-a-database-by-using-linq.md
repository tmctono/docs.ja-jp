---
title: '方法: LINQ (Visual Basic) を使用して、データベース内のデータを変更します。'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: 8770a8761af4b55394d9280b21d2a6a5b71b6ed5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61594219"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="3351e-102">方法: LINQ (Visual Basic) を使用して、データベース内のデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="3351e-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="3351e-103">統合言語クエリ (LINQ) クエリを行う簡単にデータベース情報にアクセスして、データベース内の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="3351e-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="3351e-104">次の例では、SQL Server データベースを取得する新しいアプリケーションを作成する方法と更新プログラムの情報を示します。</span><span class="sxs-lookup"><span data-stu-id="3351e-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="3351e-105">このトピックの例では、Northwind サンプル データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="3351e-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="3351e-106">開発用コンピューターにこのデータベースがいない場合は、Microsoft ダウンロード センターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="3351e-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="3351e-107">手順については、次を参照してください。[サンプル データベースのダウンロード](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)します。</span><span class="sxs-lookup"><span data-stu-id="3351e-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="3351e-108">データベースへの接続を作成するには</span><span class="sxs-lookup"><span data-stu-id="3351e-108">To create a connection to a database</span></span>  
  
1. <span data-ttu-id="3351e-109">Visual Studio で開く**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**をクリックして、**ビュー** ] メニューの [クリックして**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="3351e-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2. <span data-ttu-id="3351e-110">右クリックして**データ接続**で**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、 をクリック**接続の追加**します。</span><span class="sxs-lookup"><span data-stu-id="3351e-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3. <span data-ttu-id="3351e-111">Northwind サンプル データベースへの接続を有効なを指定します。</span><span class="sxs-lookup"><span data-stu-id="3351e-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="3351e-112">SQL ファイルに、LINQ でのプロジェクトを追加するには</span><span class="sxs-lookup"><span data-stu-id="3351e-112">To add a Project with a LINQ to SQL file</span></span>  
  
1. <span data-ttu-id="3351e-113">Visual Studio で、**[ファイル]** メニューの **[新規作成]** をポイントし、**[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3351e-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="3351e-114">Visual Basic を選択**Windows フォーム アプリケーション**プロジェクトの種類として。</span><span class="sxs-lookup"><span data-stu-id="3351e-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2. <span data-ttu-id="3351e-115">**[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3351e-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="3351e-116">選択、 **LINQ to SQL クラス**項目テンプレート。</span><span class="sxs-lookup"><span data-stu-id="3351e-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3. <span data-ttu-id="3351e-117">そのファイルに `northwind.dbml` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="3351e-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="3351e-118">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3351e-118">Click **Add**.</span></span> <span data-ttu-id="3351e-119">オブジェクト リレーショナル デザイナー (O/R デザイナー) が開かれた、`northwind.dbml`ファイル。</span><span class="sxs-lookup"><span data-stu-id="3351e-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="3351e-120">クエリを実行し、デザイナーを変更するテーブルを追加するには</span><span class="sxs-lookup"><span data-stu-id="3351e-120">To add tables to query and modify to the designer</span></span>  
  
1. <span data-ttu-id="3351e-121">**サーバー エクスプ ローラー**/**データベース エクスプ ローラー**、Northwind データベースへの接続を展開します。</span><span class="sxs-lookup"><span data-stu-id="3351e-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="3351e-122">展開、**テーブル**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3351e-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="3351e-123">O/R デザイナーを閉じた場合をダブルクリックして開くことができます、`northwind.dbml`先ほど追加したファイル。</span><span class="sxs-lookup"><span data-stu-id="3351e-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2. <span data-ttu-id="3351e-124">Customers テーブルをクリックし、デザイナーの左側のペインにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3351e-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="3351e-125">デザイナーは、プロジェクトの新しい Customer オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3351e-125">The designer creates a new Customer object for your project.</span></span>  
  
3. <span data-ttu-id="3351e-126">変更を保存し、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3351e-126">Save your changes and close the designer.</span></span>  
  
4. <span data-ttu-id="3351e-127">プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="3351e-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="3351e-128">データベースを変更し、結果を表示するコードを追加するには</span><span class="sxs-lookup"><span data-stu-id="3351e-128">To add code to modify the database and display the results</span></span>  
  
1. <span data-ttu-id="3351e-129">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.DataGridView>に、プロジェクトの Form1 の既定の Windows フォーム コントロール。</span><span class="sxs-lookup"><span data-stu-id="3351e-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2. <span data-ttu-id="3351e-130">O/R デザイナーにテーブルを追加したときに、デザイナーが追加、<xref:System.Data.Linq.DataContext>オブジェクトをプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="3351e-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="3351e-131">このオブジェクトには、Customers テーブルへのアクセスに使用できるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3351e-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="3351e-132">ローカルの Customer オブジェクトと、テーブルの顧客のコレクションを定義するコードも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3351e-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="3351e-133"><xref:System.Data.Linq.DataContext>オブジェクトの名前は、プロジェクトに基づく .dbml ファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3351e-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="3351e-134">このプロジェクトで、<xref:System.Data.Linq.DataContext>オブジェクトの名前は`northwindDataContext`します。</span><span class="sxs-lookup"><span data-stu-id="3351e-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="3351e-135">インスタンスを作成することができます、<xref:System.Data.Linq.DataContext>コードとクエリ内のオブジェクトし、O/R デザイナーで指定された顧客のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="3351e-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="3351e-136">データベースでは、それらを呼び出すことによって送信されるまで顧客のコレクションに対して行った変更は反映されません、<xref:System.Data.Linq.DataContext.SubmitChanges%2A>のメソッド、<xref:System.Data.Linq.DataContext>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="3351e-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="3351e-137">コードを追加する Windows フォーム、Form1 をダブルクリックして、 <xref:System.Windows.Forms.Form.Load> Customers テーブルを照会するイベントのプロパティとして公開される、<xref:System.Data.Linq.DataContext>します。</span><span class="sxs-lookup"><span data-stu-id="3351e-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="3351e-138">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3351e-138">Add the following code:</span></span>  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3. <span data-ttu-id="3351e-139">**ツールボックス**、3 つをドラッグして<xref:System.Windows.Forms.Button>をフォームにコントロール。</span><span class="sxs-lookup"><span data-stu-id="3351e-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="3351e-140">最初の選択`Button`コントロール。</span><span class="sxs-lookup"><span data-stu-id="3351e-140">Select the first `Button` control.</span></span> <span data-ttu-id="3351e-141">**プロパティ**ウィンドウで、設定、`Name`の`Button`に制御を`AddButton`と`Text`に`Add`します。</span><span class="sxs-lookup"><span data-stu-id="3351e-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="3351e-142">2 番目のボタンを選択し、設定、`Name`プロパティを`UpdateButton`と`Text`プロパティを`Update`します。</span><span class="sxs-lookup"><span data-stu-id="3351e-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="3351e-143">3 番目のボタンを選択し、設定、`Name`プロパティを`DeleteButton`と`Text`プロパティを`Delete`します。</span><span class="sxs-lookup"><span data-stu-id="3351e-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4. <span data-ttu-id="3351e-144">ダブルクリックして、**追加**ボタンのコードを追加するその`Click`イベント。</span><span class="sxs-lookup"><span data-stu-id="3351e-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="3351e-145">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3351e-145">Add the following code:</span></span>  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5. <span data-ttu-id="3351e-146">ダブルクリック、 **Update**ボタンのコードを追加するその`Click`イベント。</span><span class="sxs-lookup"><span data-stu-id="3351e-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="3351e-147">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3351e-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6. <span data-ttu-id="3351e-148">ダブルクリック、**削除**ボタンのコードを追加するその`Click`イベント。</span><span class="sxs-lookup"><span data-stu-id="3351e-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="3351e-149">次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3351e-149">Add the following code:</span></span>  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7. <span data-ttu-id="3351e-150">F5 キーを押してプロジェクトを実行します。</span><span class="sxs-lookup"><span data-stu-id="3351e-150">Press F5 to run your project.</span></span> <span data-ttu-id="3351e-151">クリックして**追加**新しいレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3351e-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="3351e-152">クリックして**Update**新しいレコードを変更します。</span><span class="sxs-lookup"><span data-stu-id="3351e-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="3351e-153">クリックして**削除**新しいレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="3351e-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3351e-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="3351e-154">See also</span></span>

- [<span data-ttu-id="3351e-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="3351e-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="3351e-156">クエリ</span><span class="sxs-lookup"><span data-stu-id="3351e-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="3351e-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="3351e-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="3351e-158">DataContext メソッド (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="3351e-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="3351e-159">方法: 更新、挿入、および削除を実行するストアド プロシージャを割り当てる (O/R デザイナー)</span><span class="sxs-lookup"><span data-stu-id="3351e-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
