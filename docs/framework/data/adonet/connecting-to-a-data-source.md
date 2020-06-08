---
title: データ ソースへの接続
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: a14fe179cf2fc8714a54e52252c53bd71346cad3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287078"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="95e64-102">ADO.NET でのデータ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="95e64-102">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="95e64-103">ADO.NET では、**Connection** オブジェクトを使用して、接続文字列に必要な認証情報を指定することにより、特定のデータ ソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="95e64-103">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="95e64-104">どの **Connection** オブジェクトを使用するかは、データ ソースの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="95e64-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="95e64-105">.NET Framework に含まれている各 .NET Framework データ プロバイダーは、<xref:System.Data.Common.DbConnection> オブジェクトを持っています。.NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbConnection> オブジェクト、.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlConnection> オブジェクト、.NET Framework Data Provider for ODBC には <xref:System.Data.Odbc.OdbcConnection> オブジェクト、.NET Framework Data Provider for Oracle には <xref:System.Data.OracleClient.OracleConnection> があります。</span><span class="sxs-lookup"><span data-stu-id="95e64-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="95e64-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="95e64-106">In This Section</span></span>  
 <span data-ttu-id="95e64-107">[接続の確立](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="95e64-107">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="95e64-108">**Connection** オブジェクトを使用して、データ ソースとの接続を確立する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95e64-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="95e64-109">[接続イベント](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="95e64-109">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="95e64-110">**InfoMessage** イベントを使用してデータ ソースから情報メッセージを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95e64-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e64-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="95e64-111">See also</span></span>

- [<span data-ttu-id="95e64-112">接続文字列</span><span class="sxs-lookup"><span data-stu-id="95e64-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="95e64-113">接続プール</span><span class="sxs-lookup"><span data-stu-id="95e64-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="95e64-114">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="95e64-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="95e64-115">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="95e64-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="95e64-116">トランザクションとコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="95e64-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="95e64-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="95e64-117">ADO.NET Overview</span></span>](ado-net-overview.md)
