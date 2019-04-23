---
title: 'チュートリアル: DataGrid コントロールで SQL Server データベースのデータを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 274ec2e8ef16190da53061bb197bc3b1a1fadcf8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336110"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="40b96-102">チュートリアル: DataGrid コントロールでの SQL Server データベースのデータを表示</span><span class="sxs-lookup"><span data-stu-id="40b96-102">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="40b96-103">このチュートリアルで、SQL Server データベースからデータを取得およびそのデータを表示、<xref:System.Windows.Controls.DataGrid>コントロール。</span><span class="sxs-lookup"><span data-stu-id="40b96-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="40b96-104">ADO.NET Entity Framework を使用するには、データを表し、エンティティ クラスから指定されたデータを取得するクエリを記述するのに LINQ を使用するエンティティ クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40b96-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="40b96-105">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="40b96-105">Prerequisites</span></span>

<span data-ttu-id="40b96-106">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="40b96-106">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="40b96-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="40b96-107">Visual Studio.</span></span>

-   <span data-ttu-id="40b96-108">SQL Server または SQL Server Express を接続して、AdventureWorks サンプル データベースを持つの実行中のインスタンスへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="40b96-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="40b96-109">AdventureWorks データベースをダウンロードすることができます、 [GitHub](https://github.com/Microsoft/sql-server-samples/releases)します。</span><span class="sxs-lookup"><span data-stu-id="40b96-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="40b96-110">エンティティ クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="40b96-110">Create entity classes</span></span>

1. <span data-ttu-id="40b96-111">Visual Basic または c# の場合で新しい WPF アプリケーション プロジェクトを作成し、名前`DataGridSQLExample`します。</span><span class="sxs-lookup"><span data-stu-id="40b96-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="40b96-112">ソリューション エクスプ ローラーでプロジェクトを右クリックして**追加**、し、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="40b96-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="40b96-113">新しい項目の追加 ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40b96-113">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="40b96-114">インストールされたテンプレート ウィンドウで次のように選択します。**データ**でテンプレートの一覧で、次のように選択します。 **ADO.NET Entity Data Model**します。</span><span class="sxs-lookup"><span data-stu-id="40b96-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![ADO.NET Entity Data Model 項目テンプレート](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="40b96-116">ファイルに名前を`AdventureWorksModel.edmx`し**追加**します。</span><span class="sxs-lookup"><span data-stu-id="40b96-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="40b96-117">Entity Data Model ウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40b96-117">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="40b96-118">[モデルのコンテンツの選択] 画面で、次のように選択します。**データベースの EF デザイナー**順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="40b96-118">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="40b96-119">データ接続の選択 画面で、AdventureWorksLT2008 データベースへの接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="40b96-119">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="40b96-120">詳細については、次を参照してください。 [Your のデータ接続のダイアログ ボックスを選択](https://go.microsoft.com/fwlink/?LinkId=160190)します。</span><span class="sxs-lookup"><span data-stu-id="40b96-120">For more information, see [Choose Your Data Connection Dialog Box](https://go.microsoft.com/fwlink/?LinkId=160190).</span></span>

    <span data-ttu-id="40b96-121">名前があるかどうかを確認`AdventureWorksLT2008Entities`ことと、**エンティティ接続設定の app.config に保存** チェック ボックスが選択されているし、順にクリックします**次へ**します。</span><span class="sxs-lookup"><span data-stu-id="40b96-121">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="40b96-122">データベース オブジェクトの選択 画面で、テーブル ノードを展開し、選択、**製品**と**ProductCategory**テーブル。</span><span class="sxs-lookup"><span data-stu-id="40b96-122">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="40b96-123">は、テーブルのすべてのエンティティ クラスを生成することができますただし、この例ではのみからデータを取り出すこれら 2 つのテーブル。</span><span class="sxs-lookup"><span data-stu-id="40b96-123">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="40b96-124">![テーブルからの Product および ProductCategory の選択](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="40b96-124">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="40b96-125">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40b96-125">Click **Finish**.</span></span>

     <span data-ttu-id="40b96-126">エンティティ デザイナーでは、Product および ProductCategory エンティティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40b96-126">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="40b96-127">![Product および ProductCategory エンティティ モデル](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="40b96-127">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="40b96-128">データを取得して</span><span class="sxs-lookup"><span data-stu-id="40b96-128">Retrieve and present the data</span></span>

1. <span data-ttu-id="40b96-129">MainWindow.xaml ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="40b96-129">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="40b96-130">設定、<xref:System.Windows.FrameworkElement.Width%2A>プロパティを<xref:System.Windows.Window>450 にします。</span><span class="sxs-lookup"><span data-stu-id="40b96-130">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="40b96-131">XAML エディターで次のコードを追加<xref:System.Windows.Controls.DataGrid>タグの間、`<Grid>`と`</Grid>`タグを追加する、<xref:System.Windows.Controls.DataGrid>という`dataGrid1`。</span><span class="sxs-lookup"><span data-stu-id="40b96-131">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="40b96-132">![DataGrid のあるウィンドウ](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="40b96-132">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="40b96-133"><xref:System.Windows.Window>を選択します。</span><span class="sxs-lookup"><span data-stu-id="40b96-133">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="40b96-134">イベント ハンドラーを作成する [プロパティ] ウィンドウまたは XAML のエディターを使用して、<xref:System.Windows.Window>という`Window_Loaded`の<xref:System.Windows.FrameworkElement.Loaded>イベント。</span><span class="sxs-lookup"><span data-stu-id="40b96-134">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="40b96-135">詳細については、「[方法 :単純なイベント ハンドラーを作成](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))です。</span><span class="sxs-lookup"><span data-stu-id="40b96-135">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="40b96-136">次は、MainWindow.xaml の XAML を示します。</span><span class="sxs-lookup"><span data-stu-id="40b96-136">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40b96-137">Visual Basic では、MainWindow.xaml の最初の行でを使用している場合は置き換えます`x:Class="DataGridSQLExample.MainWindow"`で`x:Class="MainWindow"`します。</span><span class="sxs-lookup"><span data-stu-id="40b96-137">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="40b96-138">分離コード ファイル (MainWindow.xaml.vb または MainWindow.xaml.cs) を開き、<xref:System.Windows.Window>します。</span><span class="sxs-lookup"><span data-stu-id="40b96-138">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="40b96-139">結合されたテーブルから特定の値を取得および設定するには、次のコードを追加、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>のプロパティ、<xref:System.Windows.Controls.DataGrid>クエリの結果にします。</span><span class="sxs-lookup"><span data-stu-id="40b96-139">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="40b96-140">例を実行します。</span><span class="sxs-lookup"><span data-stu-id="40b96-140">Run the example.</span></span>

     <span data-ttu-id="40b96-141">表示する必要があります、<xref:System.Windows.Controls.DataGrid>データを表示します。</span><span class="sxs-lookup"><span data-stu-id="40b96-141">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="40b96-142">![SQL database からデータを DataGrid](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="40b96-142">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="40b96-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="40b96-143">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
- [<span data-ttu-id="40b96-144">How Do i:WPF アプリケーションで Entity Framework で開始できますか。</span><span class="sxs-lookup"><span data-stu-id="40b96-144">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](https://go.microsoft.com/fwlink/?LinkId=159868)