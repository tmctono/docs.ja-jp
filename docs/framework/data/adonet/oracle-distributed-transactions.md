---
title: Oracle 分散トランザクション
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: edd06b94ce4157e90d334ee7feac2a449f7ee74b
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040476"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="ae27d-102">Oracle 分散トランザクション</span><span class="sxs-lookup"><span data-stu-id="ae27d-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="ae27d-103"><xref:System.Data.OracleClient.OracleConnection> オブジェクトはトランザクションがアクティブであると判断した場合、既存の分散トランザクションに自動的に参加します。</span><span class="sxs-lookup"><span data-stu-id="ae27d-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="ae27d-104">自動トランザクション参加は、接続が開かれた場合または接続プールから取得された場合に行われます。</span><span class="sxs-lookup"><span data-stu-id="ae27d-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="ae27d-105">既存のトランザクションへの自動参加を無効にするには、</span><span class="sxs-lookup"><span data-stu-id="ae27d-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```csharp  
Enlist=false  
```  
  
 <span data-ttu-id="ae27d-106">を <xref:System.Data.OracleClient.OracleConnection> の接続文字列パラメーターとして指定します。</span><span class="sxs-lookup"><span data-stu-id="ae27d-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae27d-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae27d-107">See also</span></span>

- [<span data-ttu-id="ae27d-108">Oracle および ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ae27d-108">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="ae27d-109">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ae27d-109">ADO.NET Overview</span></span>](ado-net-overview.md)
