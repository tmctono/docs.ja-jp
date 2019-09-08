---
title: DataAdapter と DataReader
ms.date: 03/30/2017
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
ms.openlocfilehash: 20c6d514e70d2e4db451e0fff02e72688bf7d0ba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786649"
---
# <a name="dataadapters-and-datareaders"></a><span data-ttu-id="bc3c2-102">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="bc3c2-102">DataAdapters and DataReaders</span></span>
<span data-ttu-id="bc3c2-103">ADO.NET **DataReader**を使用して、データベースから読み取り専用、順方向専用のデータストリームを取得できます。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-103">You can use the ADO.NET **DataReader** to retrieve a read-only, forward-only stream of data from a database.</span></span> <span data-ttu-id="bc3c2-104">結果はクエリの実行時に返され、 **DataReader**の**Read**メソッドを使用して要求するまで、クライアントのネットワークバッファーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-104">Results are returned as the query executes, and are stored in the network buffer on the client until you request them using the **Read** method of the **DataReader**.</span></span> <span data-ttu-id="bc3c2-105">**DataReader**を使用すると、使用可能なデータをすぐに取得することによってアプリケーションのパフォーマンスを向上させることができます。また、既定では、メモリに一度に1行だけを格納するため、システムのオーバーヘッドが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-105">Using the **DataReader** can increase application performance both by retrieving data as soon as it is available, and (by default) storing only one row at a time in memory, reducing system overhead.</span></span>  
  
 <span data-ttu-id="bc3c2-106"><xref:System.Data.Common.DataAdapter> は、データ ソースからデータを取得し、1 つの <xref:System.Data.DataSet> 内でテーブルを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-106">A <xref:System.Data.Common.DataAdapter> is used to retrieve data from a data source and populate tables within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bc3c2-107">また、`DataAdapter` は、`DataSet` に対して加えられた変更をデータ ソースに反映させます。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-107">The `DataAdapter` also resolves changes made to the `DataSet` back to the data source.</span></span> <span data-ttu-id="bc3c2-108">`DataAdapter` は .NET Framework データ プロバイダーの `Connection` オブジェクトを使用してデータ ソースに接続し、`Command` オブジェクトを使用してデータ ソースからデータを取得し、変更をデータ ソースに反映させます。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-108">The `DataAdapter` uses the `Connection` object of the .NET Framework data provider to connect to a data source, and it uses `Command` objects to retrieve data from and resolve changes to the data source.</span></span>  
  
 <span data-ttu-id="bc3c2-109">.NET Framework に含まれている各 .NET Framework データ プロバイダーには、<xref:System.Data.Common.DbDataReader> および <xref:System.Data.Common.DbDataAdapter> オブジェクトがあります.NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbDataReader> および <xref:System.Data.OleDb.OleDbDataAdapter> オブジェクトがあります.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlDataReader> および <xref:System.Data.SqlClient.SqlDataAdapter> オブジェクトがあります.NET Framework Data Provider for ODBC には、<xref:System.Data.Odbc.OdbcDataReader> および <xref:System.Data.Odbc.OdbcDataAdapter> オブジェクトがあります.NET Framework Data Provider for Oracle には、<xref:System.Data.OracleClient.OracleDataReader> および <xref:System.Data.OracleClient.OracleDataAdapter> オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-109">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbDataReader> and a <xref:System.Data.Common.DbDataAdapter> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbDataReader> and an <xref:System.Data.OleDb.OleDbDataAdapter> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlDataReader> and a <xref:System.Data.SqlClient.SqlDataAdapter> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcDataReader> and an <xref:System.Data.Odbc.OdbcDataAdapter> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleDataReader> and an <xref:System.Data.OracleClient.OracleDataAdapter> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc3c2-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bc3c2-110">In This Section</span></span>  
 [<span data-ttu-id="bc3c2-111">DataReader によるデータの取得</span><span class="sxs-lookup"><span data-stu-id="bc3c2-111">Retrieving Data Using a DataReader</span></span>](retrieving-data-using-a-datareader.md)  
 <span data-ttu-id="bc3c2-112">ADO.NET **DataReader**オブジェクトと、それを使用してデータソースから結果のストリームを返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-112">Describes the ADO.NET **DataReader** object and how to use it to return a stream of results from a data source.</span></span>  
  
 [<span data-ttu-id="bc3c2-113">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="bc3c2-113">Populating a DataSet from a DataAdapter</span></span>](populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="bc3c2-114">`DataSet` を使用して `DataAdapter` にテーブル、列、および行を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-114">Describes how to fill a `DataSet` with tables, columns, and rows by using a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="bc3c2-115">DataAdapter パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc3c2-115">DataAdapter Parameters</span></span>](dataadapter-parameters.md)  
 <span data-ttu-id="bc3c2-116">`DataAdapter` のコマンド プロパティのパラメーターを使用する方法と、`DataSet` の列の内容をコマンド パラメーターに割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-116">Describes how to use parameters with the command properties of a `DataAdapter` including how to map the contents of a column in a `DataSet` to a command parameter.</span></span>  
  
 [<span data-ttu-id="bc3c2-117">DataSet への既存の制約の追加</span><span class="sxs-lookup"><span data-stu-id="bc3c2-117">Adding Existing Constraints to a DataSet</span></span>](adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="bc3c2-118">既存の制約を `DataSet` に追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-118">Describes how to add existing constraints to a `DataSet`.</span></span>  
  
 [<span data-ttu-id="bc3c2-119">DataAdapter DataTable と DataColumn のマップ</span><span class="sxs-lookup"><span data-stu-id="bc3c2-119">DataAdapter DataTable and DataColumn Mappings</span></span>](dataadapter-datatable-and-datacolumn-mappings.md)  
 <span data-ttu-id="bc3c2-120">`DataTableMappings` の `ColumnMappings` および `DataAdapter` を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-120">Describes how to set up `DataTableMappings` and `ColumnMappings` for a `DataAdapter`.</span></span>  
  
 [<span data-ttu-id="bc3c2-121">クエリ結果のページング</span><span class="sxs-lookup"><span data-stu-id="bc3c2-121">Paging Through a Query Result</span></span>](paging-through-a-query-result.md)  
 <span data-ttu-id="bc3c2-122">クエリの結果をデータ ページとして表示する例を示します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-122">Provides an example of viewing the results of a query as pages of data.</span></span>  
  
 [<span data-ttu-id="bc3c2-123">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="bc3c2-123">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="bc3c2-124">`DataAdapter` を使用して `DataSet` の変更内容を解決してデータベースに戻す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-124">Describes how to use a `DataAdapter` to resolve changes in a `DataSet` back to the database.</span></span>  
  
 [<span data-ttu-id="bc3c2-125">DataAdapter のイベント処理</span><span class="sxs-lookup"><span data-stu-id="bc3c2-125">Handling DataAdapter Events</span></span>](handling-dataadapter-events.md)  
 <span data-ttu-id="bc3c2-126">`DataAdapter` のイベントおよびその使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-126">Describes `DataAdapter` events and how to use them.</span></span>  
  
 [<span data-ttu-id="bc3c2-127">DataAdapter を使用したバッチ操作の実行</span><span class="sxs-lookup"><span data-stu-id="bc3c2-127">Performing Batch Operations Using DataAdapters</span></span>](performing-batch-operations-using-dataadapters.md)  
 <span data-ttu-id="bc3c2-128">`DataSet` から更新を適用する際に、SQL Server へのラウンド トリップ回数を減らすことにより、アプリケーションのパフォーマンスを向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc3c2-128">Describes enhancing application performance by reducing the number of round trips to SQL Server when applying updates from the `DataSet`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3c2-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc3c2-129">See also</span></span>

- [<span data-ttu-id="bc3c2-130">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="bc3c2-130">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="bc3c2-131">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="bc3c2-131">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="bc3c2-132">トランザクションと同時実行</span><span class="sxs-lookup"><span data-stu-id="bc3c2-132">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="bc3c2-133">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="bc3c2-133">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="bc3c2-134">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="bc3c2-134">ADO.NET Overview</span></span>](ado-net-overview.md)
