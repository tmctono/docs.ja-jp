---
title: OVERLAPS (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: bdee9281fd406a3d029d3a10536cbdd48d2f7a58
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319414"
---
# <a name="overlaps-entity-sql"></a><span data-ttu-id="d85a1-102">OVERLAPS (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d85a1-102">OVERLAPS (Entity SQL)</span></span>
<span data-ttu-id="d85a1-103">2 つのコレクションに共通の要素が存在するかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d85a1-103">Determines whether two collections have common elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d85a1-104">Syntax</span></span>  
  
```sql  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="d85a1-105">引数</span><span class="sxs-lookup"><span data-stu-id="d85a1-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d85a1-106">コレクションを返す任意の有効なクエリ式。もう一方のクエリ式から返されたコレクションと比較されます。</span><span class="sxs-lookup"><span data-stu-id="d85a1-106">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span> <span data-ttu-id="d85a1-107">すべての式は、 `expression`と同じ型であるか、共通の基本型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85a1-107">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d85a1-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="d85a1-108">Return Value</span></span>  
 <span data-ttu-id="d85a1-109">2 つのコレクションに共通の要素がある場合は`true` 、それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="d85a1-109">`true` if the two collections have common elements; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d85a1-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="d85a1-110">Remarks</span></span>  
 <span data-ttu-id="d85a1-111">オーバーラップは、次の機能と同等の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d85a1-111">OVERLAPS provides functionally equivalent to the following:</span></span>  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 <span data-ttu-id="d85a1-112">OVERLAPS は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="d85a1-112">OVERLAPS is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="d85a1-113">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="d85a1-113">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="d85a1-114">@No__t 0 の set 演算子の優先順位については、「 [EXCEPT](except-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d85a1-114">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d85a1-115">例</span><span class="sxs-lookup"><span data-stu-id="d85a1-115">Example</span></span>  
 <span data-ttu-id="d85a1-116">次の Entity SQL クエリでは、OVERLAPS 演算子を使用して、2 つのコレクションに共通の値が存在するかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d85a1-116">The following Entity SQL query uses the OVERLAPS operator to determines whether two collections have a common value.</span></span> <span data-ttu-id="d85a1-117">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d85a1-117">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d85a1-118">これをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d85a1-118">To compile and run this, follow these steps:</span></span>  
  
1. <span data-ttu-id="d85a1-119">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d85a1-119">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d85a1-120">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="d85a1-120">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#OVERLAPS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#overlaps)]  
  
## <a name="see-also"></a><span data-ttu-id="d85a1-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="d85a1-121">See also</span></span>

- [<span data-ttu-id="d85a1-122">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="d85a1-122">Entity SQL Reference</span></span>](entity-sql-reference.md)
