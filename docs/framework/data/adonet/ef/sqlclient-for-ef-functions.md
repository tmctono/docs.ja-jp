---
title: Entity Framework 用 SqlClient 関数
ms.date: 03/30/2017
ms.assetid: 71a3613c-b94e-494c-8ad8-90cf86ae0b87
ms.openlocfilehash: 9fb495284108e97bd0cd8ce01b145c77c07c9939
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248394"
---
# <a name="sqlclient-for-entity-framework-functions"></a><span data-ttu-id="b0f13-102">Entity Framework 用 SqlClient 関数</span><span class="sxs-lookup"><span data-stu-id="b0f13-102">SqlClient for Entity Framework Functions</span></span>
<span data-ttu-id="b0f13-103">Entity Framework 用の .NET Framework Data Provider for SQL Server (SqlClient) には、`System.DateTime` や `string` の操作を実行する関数の他に、数学計算および集計計算を実行する関数のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b0f13-103">The .NET Framework Data Provider for SQL Server (SqlClient) for the Entity Framework provides a set of functions to perform mathematical and aggregation calculations, as well as functions to perform `System.DateTime` and `string` operations.</span></span> <span data-ttu-id="b0f13-104">これらの関数は `SQLServer` 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="b0f13-104">These functions are in the `SQLServer` namespace.</span></span>  
  
 <span data-ttu-id="b0f13-105">すべてのプロバイダーで動作する関数の一覧については、「[正規関数](./language-reference/canonical-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0f13-105">For a list of functions that should work with any provider, see [Canonical Functions](./language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="b0f13-106">正規関数を SQL Server 関数にマップする方法の詳細については、「[概念モデル正規の関数のマッピング」 SQL Server を](conceptual-model-canonical-to-sql-server-functions-mapping.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0f13-106">For information about how canonical functions map to SQL Server functions, see [Conceptual Model Canonical to SQL Server Functions Mapping](conceptual-model-canonical-to-sql-server-functions-mapping.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0f13-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b0f13-107">In This Section</span></span>  
 [<span data-ttu-id="b0f13-108">概念モデル正規関数と SQL Server 関数とのマッピング</span><span class="sxs-lookup"><span data-stu-id="b0f13-108">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](conceptual-model-canonical-to-sql-server-functions-mapping.md)  
  
 [<span data-ttu-id="b0f13-109">集計関数</span><span class="sxs-lookup"><span data-stu-id="b0f13-109">Aggregate Functions</span></span>](aggregate-functions-sqlclient-for-entity-framework.md)  
  
 [<span data-ttu-id="b0f13-110">日付と時刻関数</span><span class="sxs-lookup"><span data-stu-id="b0f13-110">Date and Time Functions</span></span>](date-and-time-functions.md)  
  
 [<span data-ttu-id="b0f13-111">数学関数</span><span class="sxs-lookup"><span data-stu-id="b0f13-111">Mathematical Functions</span></span>](mathematical-functions.md)  
  
 [<span data-ttu-id="b0f13-112">文字列関数</span><span class="sxs-lookup"><span data-stu-id="b0f13-112">String Functions</span></span>](string-functions.md)  
  
 [<span data-ttu-id="b0f13-113">システム関数</span><span class="sxs-lookup"><span data-stu-id="b0f13-113">System Functions</span></span>](system-functions.md)  
  
## <a name="see-also"></a><span data-ttu-id="b0f13-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0f13-114">See also</span></span>

- [<span data-ttu-id="b0f13-115">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="b0f13-115">Entity SQL Reference</span></span>](./language-reference/entity-sql-reference.md)
- [<span data-ttu-id="b0f13-116">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="b0f13-116">Entity SQL Overview</span></span>](./language-reference/entity-sql-overview.md)
