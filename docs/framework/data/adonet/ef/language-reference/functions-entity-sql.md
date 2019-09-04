---
title: 関数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: ec94a0f16fb3b836297f6675cc938a711816555b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250916"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="7ca81-102">関数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7ca81-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="7ca81-103">Entity SQL では、ユーザー定義関数、正規の関数、およびプロバイダー固有の関数がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ca81-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="7ca81-104">ユーザー定義関数は、概念モデルまたはクエリでインラインで指定されます。</span><span class="sxs-lookup"><span data-stu-id="7ca81-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="7ca81-105">詳細については、「[ユーザー定義関数](user-defined-functions-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca81-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="7ca81-106">正規の関数は Entity Framework で定義済みであり、データ プロバイダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7ca81-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="7ca81-107">プロバイダーによってサポートされていない関数を呼び出すと、Entity SQL コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7ca81-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="7ca81-108">そのため、通常は、プロバイダー固有の名前空間にあるストア固有の関数よりも正規の関数が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="7ca81-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="7ca81-109">詳細については、「[正規関数](canonical-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca81-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="7ca81-110">Microsoft SQL クライアント マネージド プロバイダーは、プロバイダー固有の一連の関数を提供しています。</span><span class="sxs-lookup"><span data-stu-id="7ca81-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="7ca81-111">詳細については、「 [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ca81-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ca81-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ca81-112">In This Section</span></span>  
 [<span data-ttu-id="7ca81-113">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="7ca81-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="7ca81-114">関数のオーバーロードの解決方法</span><span class="sxs-lookup"><span data-stu-id="7ca81-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="7ca81-115">集計関数</span><span class="sxs-lookup"><span data-stu-id="7ca81-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="7ca81-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ca81-116">See also</span></span>

- [<span data-ttu-id="7ca81-117">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="7ca81-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
