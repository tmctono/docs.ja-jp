---
title: 関数 (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: bef959ae6a835b5d1d696162528a8f904c59e8e5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201071"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="9a45b-102">関数 (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9a45b-102">Functions (Entity SQL)</span></span>

<span data-ttu-id="9a45b-103">Entity SQL では、ユーザー定義関数、正規の関数、およびプロバイダー固有の関数がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9a45b-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="9a45b-104">ユーザー定義関数は、概念モデルまたはクエリでインラインで指定されます。</span><span class="sxs-lookup"><span data-stu-id="9a45b-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="9a45b-105">詳しくは、「[ユーザー定義関数](user-defined-functions-entity-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9a45b-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="9a45b-106">正規の関数は Entity Framework で定義済みであり、データ プロバイダーによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9a45b-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="9a45b-107">プロバイダーによってサポートされていない関数を呼び出すと、Entity SQL コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a45b-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="9a45b-108">そのため、通常は、プロバイダー固有の名前空間にあるストア固有の関数よりも正規の関数が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9a45b-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="9a45b-109">詳しくは、「[正規関数](canonical-functions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9a45b-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="9a45b-110">Microsoft SQL クライアント マネージド プロバイダーは、プロバイダー固有の一連の関数を提供しています。</span><span class="sxs-lookup"><span data-stu-id="9a45b-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="9a45b-111">詳細については、「[Entity Framework 用 SqlClient 関数](../sqlclient-for-ef-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a45b-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a45b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9a45b-112">In This Section</span></span>  

 [<span data-ttu-id="9a45b-113">ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="9a45b-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="9a45b-114">関数のオーバーロードの解決方法</span><span class="sxs-lookup"><span data-stu-id="9a45b-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="9a45b-115">集計関数</span><span class="sxs-lookup"><span data-stu-id="9a45b-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="9a45b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a45b-116">See also</span></span>

- [<span data-ttu-id="9a45b-117">Entity SQL の概要</span><span class="sxs-lookup"><span data-stu-id="9a45b-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
