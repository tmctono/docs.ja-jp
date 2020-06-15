---
title: データの取得と変更
description: .NET Framework では、ADO.NET のデータ プロバイダーは、アプリケーションとデータ ソースの間でデータの読み取りや更新を行うためのブリッジとして機能します。
ms.date: 03/30/2017
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
ms.openlocfilehash: f916324dc829526a5e6b0078021b09786755f666
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286612"
---
# <a name="retrieving-and-modifying-data-in-adonet"></a><span data-ttu-id="43d1d-103">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="43d1d-103">Retrieving and Modifying Data in ADO.NET</span></span>
<span data-ttu-id="43d1d-104">データベース アプリケーションの主な機能は、データ ソースとの接続およびデータベースに格納されているデータの取得です。</span><span class="sxs-lookup"><span data-stu-id="43d1d-104">A primary function of any database application is connecting to a data source and retrieving the data that it contains.</span></span> <span data-ttu-id="43d1d-105">ADO.NET の .NET Framework データ プロバイダーは、アプリケーションとデータ ソースの間のブリッジとして機能し、**DataReader** または **DataAdapter** を使用して、コマンドを実行したり、データを取得したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="43d1d-105">The .NET Framework data providers of ADO.NET serve as a bridge between an application and a data source, allowing you to execute commands as well as to retrieve data by using a **DataReader** or a **DataAdapter**.</span></span> <span data-ttu-id="43d1d-106">データベースに格納されているデータを更新する機能は、データベース アプリケーションの重要な機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="43d1d-106">A key function of any database application is the ability to update the data that is stored in the database.</span></span> <span data-ttu-id="43d1d-107">ADO.NET でデータを更新するには、**DataAdapter** と <xref:System.Data.DataSet>、および **Command** オブジェクトを使用する必要があります。また、トランザクションを使用することが必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="43d1d-107">In ADO.NET, updating data involves using the **DataAdapter** and <xref:System.Data.DataSet>, and **Command** objects; and it may also involve using transactions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43d1d-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="43d1d-108">In This Section</span></span>  
 [<span data-ttu-id="43d1d-109">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="43d1d-109">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)  
 <span data-ttu-id="43d1d-110">データ ソースへの接続を確立する方法、および接続イベントを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-110">Describes how to establish a connection to a data source and how to work with connection events.</span></span>  
  
 [<span data-ttu-id="43d1d-111">接続文字列</span><span class="sxs-lookup"><span data-stu-id="43d1d-111">Connection Strings</span></span>](connection-strings.md)  
 <span data-ttu-id="43d1d-112">接続文字列のキーワード、セキュリティ情報、セキュリティ情報の格納や取得など、接続文字列を使用するうえでのさまざまな側面について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-112">Contains topics describing various aspects of using connection strings, including connection string keywords, security info, and storing and retrieving them.</span></span>  
  
 [<span data-ttu-id="43d1d-113">接続プール</span><span class="sxs-lookup"><span data-stu-id="43d1d-113">Connection Pooling</span></span>](connection-pooling.md)  
 <span data-ttu-id="43d1d-114">.NET Framework Data Provider の接続プールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-114">Describes connection pooling for the .NET Framework data providers.</span></span>  
  
 [<span data-ttu-id="43d1d-115">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="43d1d-115">Commands and Parameters</span></span>](commands-and-parameters.md)  
 <span data-ttu-id="43d1d-116">コマンドおよびコマンド ビルダーを作成する方法、パラメーターを構成する方法、およびコマンドを実行してデータを取得および変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-116">Contains topics describing how to create commands and command builders, configure parameters, and how to execute commands to retrieve and modify data.</span></span>  
  
 [<span data-ttu-id="43d1d-117">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="43d1d-117">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)  
 <span data-ttu-id="43d1d-118">DataReaders、DataAdapters、パラメーター、DataAdapter イベントの処理、およびバッチ操作の実行について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-118">Contains topics describing DataReaders, DataAdapters, parameters, handling DataAdapter events and performing batch operations.</span></span>  
  
 [<span data-ttu-id="43d1d-119">トランザクションとコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="43d1d-119">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)  
 <span data-ttu-id="43d1d-120">ローカル トランザクションや分散トランザクションの実行方法、およびオプティミスティック コンカレンシーの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-120">Contains topics describing how to perform local transactions, distributed transactions, and work with optimistic concurrency.</span></span>  
  
 [<span data-ttu-id="43d1d-121">ID 値および Autonumber 値の取得</span><span class="sxs-lookup"><span data-stu-id="43d1d-121">Retrieving Identity or Autonumber Values</span></span>](retrieving-identity-or-autonumber-values.md)  
 <span data-ttu-id="43d1d-122">SQL Server テーブルの **identity** 列または Microsoft Access テーブルの **Autonumber** フィールド用に生成された値を、テーブルの挿入行の列にマップする例を示します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-122">Provides an example of mapping the values generated for an **identity** column in a SQL Server table or for an **Autonumber** field in a Microsoft Access table, to a column of an inserted row in a table.</span></span> <span data-ttu-id="43d1d-123">`DataTable` での ID 値の結合について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-123">Discusses merging identity values in a `DataTable`.</span></span>  
  
 [<span data-ttu-id="43d1d-124">バイナリ データの取得</span><span class="sxs-lookup"><span data-stu-id="43d1d-124">Retrieving Binary Data</span></span>](retrieving-binary-data.md)  
 <span data-ttu-id="43d1d-125">`CommandBehavior`.`SequentialAccess` を使用してバイナリ データまたは大きなデータ構造を取得し、</span><span class="sxs-lookup"><span data-stu-id="43d1d-125">Describes how to retrieve binary data or large data structures using `CommandBehavior`.`SequentialAccess`</span></span> <span data-ttu-id="43d1d-126">`DataReader` の既定の動作を変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-126">to modify the default behavior of a `DataReader`.</span></span>  
  
 [<span data-ttu-id="43d1d-127">ストアド プロシージャでのデータの変更</span><span class="sxs-lookup"><span data-stu-id="43d1d-127">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)  
 <span data-ttu-id="43d1d-128">ストアド プロシージャの入力パラメーターおよび出力パラメーターを使用してデータベースに行を挿入し、新しい ID 値を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-128">Describes how to use stored procedure input parameters and output parameters to insert a row in a database, returning a new identity value.</span></span>  
  
 [<span data-ttu-id="43d1d-129">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="43d1d-129">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)  
 <span data-ttu-id="43d1d-130">データベースまたはカタログ、データベース内のテーブルおよびビュー、テーブルに対して存在する制約、およびその他のスキーマ情報をデータ ソースから取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-130">Describes how to obtain available databases or catalogs, tables and views in a database, constraints that exist for tables, and other schema information from a data source.</span></span>  
  
 [<span data-ttu-id="43d1d-131">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="43d1d-131">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="43d1d-132">プロバイダー ファクトリ モデルについて説明し、`System.Data.Common` 名前空間の基本クラスの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-132">Describes the provider factory model and demonstrates how to use the base classes in the `System.Data.Common` namespace.</span></span>  
  
 [<span data-ttu-id="43d1d-133">ADO.NET のデータ追跡</span><span class="sxs-lookup"><span data-stu-id="43d1d-133">Data Tracing in ADO.NET</span></span>](data-tracing.md)  
 <span data-ttu-id="43d1d-134">ADO.NET が備える組み込みデータ トレース機能のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-134">Describes how ADO.NET provides built-in data tracing functionality.</span></span>  
  
 [<span data-ttu-id="43d1d-135">パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="43d1d-135">Performance Counters</span></span>](performance-counters.md)  
 <span data-ttu-id="43d1d-136">`SqlClient` および `OracleClient` で使用できるパフォーマンス カウンターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-136">Describes performance counters available for `SqlClient` and `OracleClient`.</span></span>  
  
 [<span data-ttu-id="43d1d-137">非同期の概要</span><span class="sxs-lookup"><span data-stu-id="43d1d-137">Asynchronous Programming</span></span>](asynchronous-programming.md)  
 <span data-ttu-id="43d1d-138">非同期プログラミングに対する ADO.NET のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-138">Describes ADO.NET support for asynchronous programming.</span></span>  
  
 [<span data-ttu-id="43d1d-139">SqlClient ストリーミング サポート</span><span class="sxs-lookup"><span data-stu-id="43d1d-139">SqlClient Streaming Support</span></span>](sqlclient-streaming-support.md)  
 <span data-ttu-id="43d1d-140">完全にメモリに読み込むことなく SQL Server からデータをストリーミングするアプリケーションの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43d1d-140">Discusses how to write applications that stream data from SQL Server without having it fully loaded in memory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43d1d-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="43d1d-141">See also</span></span>

- [<span data-ttu-id="43d1d-142">ADO.NET でのデータ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="43d1d-142">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="43d1d-143">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="43d1d-143">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="43d1d-144">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="43d1d-144">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)
- [<span data-ttu-id="43d1d-145">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="43d1d-145">SQL Server and ADO.NET</span></span>](./sql/index.md)
- [<span data-ttu-id="43d1d-146">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="43d1d-146">ADO.NET Overview</span></span>](ado-net-overview.md)
