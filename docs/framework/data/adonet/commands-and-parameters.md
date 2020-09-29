---
title: コマンドおよびパラメーター
description: 各 .NET Framework データ プロバイダーの Command オブジェクトを使用してコマンドを実行し、データ ソースからの結果を返す方法について説明します。
ms.date: 03/30/2017
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
ms.openlocfilehash: fb7b86dc3c826805e0e1dcec4764be2e484ec40b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203827"
---
# <a name="commands-and-parameters"></a><span data-ttu-id="57f16-103">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="57f16-103">Commands and Parameters</span></span>

<span data-ttu-id="57f16-104">データ ソースへの接続を確立した後、<xref:System.Data.Common.DbCommand> オブジェクトを使用してコマンドを実行し、データ ソースから結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="57f16-104">After establishing a connection to a data source, you can execute commands and return results from the data source using a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="57f16-105">コマンドは、使用している .NET Framework データ プロバイダーのいずれかのコマンド コンストラクターで作成できます。</span><span class="sxs-lookup"><span data-stu-id="57f16-105">You can create a command using one of the command constructors for the .NET Framework data provider you are working with.</span></span> <span data-ttu-id="57f16-106">コンストラクターには、データ ソースで実行する SQL ステートメント、<xref:System.Data.Common.DbConnection> オブジェクト、<xref:System.Data.Common.DbTransaction> オブジェクトなど、オプションの引数を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="57f16-106">Constructors can take optional arguments, such as an SQL statement to execute at the data source, a <xref:System.Data.Common.DbConnection> object, or a <xref:System.Data.Common.DbTransaction> object.</span></span> <span data-ttu-id="57f16-107">これらのオブジェクトをコマンドのプロパティとして構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="57f16-107">You can also configure those objects as properties of the command.</span></span> <span data-ttu-id="57f16-108">また、<xref:System.Data.Common.DbConnection.CreateCommand%2A> オブジェクトの `DbConnection` メソッドを使用して、特定の接続用のコマンドを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="57f16-108">You can also create a command for a particular connection using the <xref:System.Data.Common.DbConnection.CreateCommand%2A> method of a `DbConnection` object.</span></span> <span data-ttu-id="57f16-109">コマンドによって実行される SQL ステートメントは、<xref:System.Data.Common.DbCommand.CommandText%2A> プロパティを使って構成できます。</span><span class="sxs-lookup"><span data-stu-id="57f16-109">The SQL statement being executed by the command can be configured using the <xref:System.Data.Common.DbCommand.CommandText%2A> property.</span></span>  
  
 <span data-ttu-id="57f16-110">.NET Framework に含まれている各 .NET Framework データ プロバイダーは、`Command` オブジェクトを持ちます。</span><span class="sxs-lookup"><span data-stu-id="57f16-110">Each .NET Framework data provider included with the .NET Framework has a `Command` object.</span></span> <span data-ttu-id="57f16-111">.NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbCommand> オブジェクト、.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlCommand> オブジェクト、.NET Framework Data Provider for ODBC には <xref:System.Data.Odbc.OdbcCommand> オブジェクト、.NET Framework Data Provider for Oracle には <xref:System.Data.OracleClient.OracleCommand> があります。</span><span class="sxs-lookup"><span data-stu-id="57f16-111">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="57f16-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="57f16-112">In This Section</span></span>  

 [<span data-ttu-id="57f16-113">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="57f16-113">Executing a Command</span></span>](executing-a-command.md)  
 <span data-ttu-id="57f16-114">ADO.NET の `Command` オブジェクトと、それを使用してデータ ソースに対してクエリやコマンドを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57f16-114">Describes the ADO.NET `Command` object and how to use it to execute queries and commands against a data source.</span></span>  
  
 [<span data-ttu-id="57f16-115">パラメーターおよびパラメーター データ型の構成</span><span class="sxs-lookup"><span data-stu-id="57f16-115">Configuring Parameters and Parameter Data Types</span></span>](configuring-parameters-and-parameter-data-types.md)  
 <span data-ttu-id="57f16-116">`Command` のパラメーターの使用 (方向、データ型、パラメーター構文など) について説明します。</span><span class="sxs-lookup"><span data-stu-id="57f16-116">Describes working with `Command` parameters, including direction, data types, and parameter syntax.</span></span>  
  
 [<span data-ttu-id="57f16-117">CommandBuilder でのコマンドの生成</span><span class="sxs-lookup"><span data-stu-id="57f16-117">Generating Commands with CommandBuilders</span></span>](generating-commands-with-commandbuilders.md)  
 <span data-ttu-id="57f16-118">`DataAdapter` に単一テーブルを対象とする SELECT コマンドが割り当てられているときに、コマンド ビルダーを使用して INSERT、UPDATE、DELETE の各コマンドを自動的に生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57f16-118">Describes how to use command builders to automatically generate INSERT, UPDATE, and DELETE commands for a `DataAdapter` that has a single-table SELECT command.</span></span>  
  
 [<span data-ttu-id="57f16-119">データベースからの単一の値の取得</span><span class="sxs-lookup"><span data-stu-id="57f16-119">Obtaining a Single Value from a Database</span></span>](obtaining-a-single-value-from-a-database.md)  
 <span data-ttu-id="57f16-120">`ExecuteScalar` オブジェクトの `Command` メソッドを使用してデータベース クエリから単一の値を返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57f16-120">Describes how to use the `ExecuteScalar` method of a `Command` object to return a single value from a database query.</span></span>  
  
 [<span data-ttu-id="57f16-121">コマンドを使用したデータ変更</span><span class="sxs-lookup"><span data-stu-id="57f16-121">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)  
 <span data-ttu-id="57f16-122">データ プロバイダーを使用して、ストアド プロシージャまたはデータ定義言語 (DDL) のステートメントを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57f16-122">Describes how to use a data provider to execute stored procedures or data definition language (DDL) statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f16-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="57f16-123">See also</span></span>

- [<span data-ttu-id="57f16-124">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="57f16-124">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="57f16-125">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="57f16-125">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="57f16-126">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="57f16-126">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="57f16-127">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="57f16-127">ADO.NET Overview</span></span>](ado-net-overview.md)
