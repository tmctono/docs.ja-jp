---
title: サンプル プロバイダーでの SQL 生成
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 88223930b65ccec9d030104c62d8b4b2e77ddbe2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079422"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="cf152-102">サンプル プロバイダーでの SQL 生成</span><span class="sxs-lookup"><span data-stu-id="cf152-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="cf152-103">[Entity Framework サンプル プロバイダー](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)をサポートする ADO.NET データ プロバイダーの新しいコンポーネントを示して、[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cf152-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="cf152-104">これは、SQL Server 2005 データベースで動作し、System.Data.SqlClient ADO.NET 2.0 データ プロバイダーのラッパーとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="cf152-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="cf152-105">サンプル プロバイダーの SQL 生成モジュール (DmlSqlGenerator.cs ファイルを除き、SQL Generation フォルダーにあります) では、入力として DbQueryCommandTree を使用し、単一の SQL SELECT ステートメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="cf152-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf152-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cf152-106">In This Section</span></span>  
 <span data-ttu-id="cf152-107">ここでは、次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf152-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="cf152-108">アーキテクチャとデザイン</span><span class="sxs-lookup"><span data-stu-id="cf152-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="cf152-109">チュートリアル: SQL 生成</span><span class="sxs-lookup"><span data-stu-id="cf152-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf152-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf152-110">See also</span></span>

- [<span data-ttu-id="cf152-111">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="cf152-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
