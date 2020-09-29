---
title: DataAdapter と DataReader
description: データベースからデータを取得する ADO.NET DataReader と、データソースからデータを取得してデータセットを設定する DataAdapter について説明します。
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 2584f8b382dd90f2f8b4554663dc545b9ccceb62
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177606"
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="b0228-103">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="b0228-103">DataAdapters and DataReaders</span></span>

<span data-ttu-id="b0228-104">ADO.NET の **DataReader** を使用すると、データベースから前方への読み取り専用のストリームを取得できます。</span><span class="sxs-lookup"><span data-stu-id="b0228-104">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="b0228-105">結果はクエリを実行すると返され、**DataReader** の **Read** メソッドを使用して要求するまで、クライアントのネットワーク バッファーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b0228-105">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="b0228-106">**DataReader** を使用すると、アプリケーションのパフォーマンスが向上します。これは、使用可能になったデータをすぐに取得するためと、一度に 1 つの行しかメモリに格納しない (既定の設定) ことによってシステムのオーバーヘッドが軽減されるためです。</span><span class="sxs-lookup"><span data-stu-id="b0228-106">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="b0228-107"><xref:System.Data.Common.DataAdapter> は、データ ソースからデータを取得し、1 つの <xref:System.Data.DataSet> 内でテーブルを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b0228-107">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b0228-108">また、`DataAdapter` は、`DataSet` に対して加えられた変更をデータ ソースに反映させます。</span><span class="sxs-lookup"><span data-stu-id="b0228-108">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="b0228-109">`DataAdapter` は .NET Framework データ プロバイダーの `Connection` オブジェクトを使用してデータ ソースに接続し、`Command` オブジェクトを使用してデータ ソースからデータを取得し、変更をデータ ソースに反映させます。</span><span class="sxs-lookup"><span data-stu-id="b0228-109">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="b0228-110">.NET Framework に含まれている各 .NET Framework データ プロバイダーには、<xref:System.Data.Common.DbDataReader> および <xref:System.Data.Common.DbDataAdapter> オブジェクトがあります。.NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbDataReader> および <xref:System.Data.OleDb.OleDbDataAdapter> オブジェクトがあります。.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlDataReader> および <xref:System.Data.SqlClient.SqlDataAdapter> オブジェクトがあります。.NET Framework Data Provider for ODBC には、<xref:System.Data.Odbc.OdbcDataReader> および <xref:System.Data.Odbc.OdbcDataAdapter> オブジェクトがあります。.NET Framework Data Provider for Oracle には、<xref:System.Data.OracleClient.OracleDataReader> および <xref:System.Data.OracleClient.OracleDataAdapter> オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="b0228-110">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0228-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0228-111">In This Section</span></span>  

 [<span data-ttu-id="b0228-112">DataReader によるデータの取得</span><span class="sxs-lookup"><span data-stu-id="b0228-112">Retrieving Data Using a DataReader</span></span>](retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="b0228-113">ADO.NET の **DataReader** オブジェクトと、それを使用してデータ ソースから結果ストリームを返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-113">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="b0228-114">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="b0228-114">Populating a DataSet from a DataAdapter</span></span>](populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="b0228-115">`DataSet` を使用して `DataAdapter` にテーブル、列、および行を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-115">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="b0228-116">DataAdapter パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0228-116">DataAdapter Parameters</span></span>](dataadapter-parameters.md)  
 <span data-ttu-id="b0228-117">`DataAdapter` のコマンド プロパティのパラメーターを使用する方法と、`DataSet` の列の内容をコマンド パラメーターに割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-117">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="b0228-118">DataSet への既存の制約の追加</span><span class="sxs-lookup"><span data-stu-id="b0228-118">Adding Existing Constraints to a DataSet</span></span>](adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="b0228-119">既存の制約を `DataSet` に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-119">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="b0228-120">DataAdapter DataTable と DataColumn のマップ</span><span class="sxs-lookup"><span data-stu-id="b0228-120">DataAdapter DataTable and DataColumn Mappings</span></span>](dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="b0228-121">`DataTableMappings` の `ColumnMappings` および `DataAdapter` を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-121">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="b0228-122">クエリ結果のページング</span><span class="sxs-lookup"><span data-stu-id="b0228-122">Paging Through a Query Result</span></span>](paging-through-a-query-result.md)  
 <span data-ttu-id="b0228-123">クエリの結果をデータ ページとして表示する例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0228-123">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="b0228-124">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="b0228-124">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="b0228-125">`DataAdapter` を使用して `DataSet` の変更内容を解決してデータベースに戻す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-125">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="b0228-126">DataAdapter のイベント処理</span><span class="sxs-lookup"><span data-stu-id="b0228-126">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)  
 <span data-ttu-id="b0228-127">`DataAdapter` のイベントおよびその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-127">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="b0228-128">DataAdapter を使用したバッチ操作の実行</span><span class="sxs-lookup"><span data-stu-id="b0228-128">Performing Batch Operations Using DataAdapters</span></span>](performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="b0228-129">`DataSet` から更新を適用する際に、SQL Server へのラウンド トリップ回数を減らすことにより、アプリケーションのパフォーマンスを向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0228-129">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0228-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0228-130">See also</span></span>

- [<span data-ttu-id="b0228-131">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="b0228-131">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="b0228-132">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="b0228-132">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="b0228-133">トランザクションとコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="b0228-133">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="b0228-134">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="b0228-134">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="b0228-135">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="b0228-135">ADO.NET Overview</span></span>](ado-net-overview.md)
