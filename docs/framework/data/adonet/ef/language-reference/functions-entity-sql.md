---
title: 関数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: f31f829b53160da5a043617b9aa999b398859f17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080606"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="c020e-102">関数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c020e-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="c020e-103">Entity SQL では、ユーザー定義関数、正規の関数、およびプロバイダー固有の関数がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c020e-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="c020e-104">ユーザー定義関数は、概念モデルまたはクエリでインラインで指定されます。</span><span class="sxs-lookup"><span data-stu-id="c020e-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="c020e-105">詳細については、次を参照してください。[ユーザー定義関数](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="c020e-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="c020e-106">正規の関数は Entity Framework で定義済みであり、データ プロバイダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c020e-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="c020e-107">プロバイダーによってサポートされていない関数を呼び出すと、Entity SQL コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="c020e-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="c020e-108">そのため、通常は、プロバイダー固有の名前空間にあるストア固有の関数よりも正規の関数が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c020e-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="c020e-109">詳細については、次を参照してください。[正規関数](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="c020e-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="c020e-110">Microsoft SQL クライアント マネージド プロバイダーは、プロバイダー固有の一連の関数を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c020e-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="c020e-111">詳細については、次を参照してください。 [Entity Framework の関数の SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="c020e-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c020e-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c020e-112">In This Section</span></span>  
 [<span data-ttu-id="c020e-113">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="c020e-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="c020e-114">関数のオーバーロードの解決方法</span><span class="sxs-lookup"><span data-stu-id="c020e-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="c020e-115">集計関数</span><span class="sxs-lookup"><span data-stu-id="c020e-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="c020e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c020e-116">See also</span></span>

- [<span data-ttu-id="c020e-117">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="c020e-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
