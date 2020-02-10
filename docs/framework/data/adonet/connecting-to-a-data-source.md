---
title: データ ソースへの接続
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 206a4f741b6bf711b51da794e23f779c2bea6fa0
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094450"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="8a38e-102">ADO.NET でのデータ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="8a38e-102">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="8a38e-103">ADO.NET**では、接続オブジェクトを**使用して、接続文字列に必要な認証情報を提供することにより、特定のデータソースに接続します。</span><span class="sxs-lookup"><span data-stu-id="8a38e-103">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="8a38e-104">使用する**接続**オブジェクトは、データソースの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8a38e-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="8a38e-105">.NET Framework に含まれている各 .NET Framework データ プロバイダーは、<xref:System.Data.Common.DbConnection> オブジェクトを持っています.NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbConnection> オブジェクト、.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlConnection> オブジェクト、.NET Framework Data Provider for ODBC には <xref:System.Data.Odbc.OdbcConnection> オブジェクト、.NET Framework Data Provider for Oracle には <xref:System.Data.OracleClient.OracleConnection> があります。</span><span class="sxs-lookup"><span data-stu-id="8a38e-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a38e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a38e-106">In This Section</span></span>  
 <span data-ttu-id="8a38e-107">[接続の確立](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="8a38e-107">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="8a38e-108">**接続**オブジェクトを使用してデータソースへの接続を確立する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a38e-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="8a38e-109">[接続イベント](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="8a38e-109">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="8a38e-110">**インフォメッセージ**イベントを使用して、データソースから情報メッセージを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a38e-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a38e-111">参照</span><span class="sxs-lookup"><span data-stu-id="8a38e-111">See also</span></span>

- [<span data-ttu-id="8a38e-112">接続文字列</span><span class="sxs-lookup"><span data-stu-id="8a38e-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="8a38e-113">接続プール</span><span class="sxs-lookup"><span data-stu-id="8a38e-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="8a38e-114">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="8a38e-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="8a38e-115">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="8a38e-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="8a38e-116">トランザクションとコンカレンシー</span><span class="sxs-lookup"><span data-stu-id="8a38e-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="8a38e-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="8a38e-117">ADO.NET Overview</span></span>](ado-net-overview.md)
