---
title: 接続プール
description: データ ソースへの接続を開くコストを最小限にするために ADO.NET で使用される、接続プールと呼ばれる最適化の手法について説明します。
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: b8f89dfda7edbde14dbb5945f10f2284ac43c3d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287091"
---
# <a name="connection-pooling"></a><span data-ttu-id="cebf0-103">接続プール</span><span class="sxs-lookup"><span data-stu-id="cebf0-103">Connection Pooling</span></span>
<span data-ttu-id="cebf0-104">データ ソースへの接続は時間のかかる処理です。</span><span class="sxs-lookup"><span data-stu-id="cebf0-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="cebf0-105">接続を開くコストを最小限にするため、ADO.NET では、"*接続プール*" と呼ばれる最適化の手法が使われています。接続プールを使うことで、接続を開いて閉じるという処理の繰り返しによって生じるコストを、最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="cebf0-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="cebf0-106">接続プールは、.NET Framework データ プロバイダーに応じて異なる処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="cebf0-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cebf0-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cebf0-107">In This Section</span></span>  
 [<span data-ttu-id="cebf0-108">SQL Server の接続プール (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="cebf0-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="cebf0-109">接続プールの概要および SQL Server における接続プールの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="cebf0-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="cebf0-110">OLE DB、ODBC、および Oracle 接続プール</span><span class="sxs-lookup"><span data-stu-id="cebf0-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="cebf0-111">.NET Framework Data Provider for OLE DB、.NET Framework Data Provider for ODBC、および .NET Framework Data Provider for Oracle の接続プールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cebf0-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cebf0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="cebf0-112">See also</span></span>

- [<span data-ttu-id="cebf0-113">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="cebf0-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="cebf0-114">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="cebf0-114">ADO.NET Overview</span></span>](ado-net-overview.md)
