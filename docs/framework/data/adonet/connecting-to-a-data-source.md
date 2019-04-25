---
title: ADO.NET でのデータ ソースへの接続
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: c04624be758e4bc7c8b1981ad6a9dc44430d62b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879984"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="18597-102">ADO.NET でのデータ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="18597-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="18597-103">ADO.NET で使用して、**接続**接続文字列に必要な認証情報を指定して特定のデータ ソースに接続するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="18597-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="18597-104">**接続**オブジェクトを使用するデータ ソースの種類に依存します。</span><span class="sxs-lookup"><span data-stu-id="18597-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="18597-105"> .NET Framework に含まれている各 .NET Framework データ プロバイダーは、<xref:System.Data.Common.DbConnection> オブジェクトを持っています。 .NET Framework Data Provider for OLE DB には <xref:System.Data.OleDb.OleDbConnection> オブジェクト、.NET Framework Data Provider for SQL Server には <xref:System.Data.SqlClient.SqlConnection> オブジェクト、.NET Framework Data Provider for ODBC には <xref:System.Data.Odbc.OdbcConnection> オブジェクト、.NET Framework Data Provider for Oracle には <xref:System.Data.OracleClient.OracleConnection> があります。</span><span class="sxs-lookup"><span data-stu-id="18597-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18597-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="18597-106">In This Section</span></span>  
 [<span data-ttu-id="18597-107">接続の確立</span><span class="sxs-lookup"><span data-stu-id="18597-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="18597-108">使用する方法について説明します、**接続**オブジェクトをデータ ソースへの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="18597-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="18597-109">接続イベント</span><span class="sxs-lookup"><span data-stu-id="18597-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="18597-110">使用する方法について説明します、 **InfoMessage**イベント データ ソースから情報メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="18597-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18597-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="18597-111">See also</span></span>

- [<span data-ttu-id="18597-112">接続文字列</span><span class="sxs-lookup"><span data-stu-id="18597-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="18597-113">接続プール</span><span class="sxs-lookup"><span data-stu-id="18597-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)
- [<span data-ttu-id="18597-114">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="18597-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="18597-115">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="18597-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="18597-116">トランザクションと同時実行</span><span class="sxs-lookup"><span data-stu-id="18597-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [<span data-ttu-id="18597-117">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="18597-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
