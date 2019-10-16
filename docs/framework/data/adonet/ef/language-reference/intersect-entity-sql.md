---
title: INTERSECT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: dc7338d176302b8683d541ab0dc715dd8d149c6f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319765"
---
# <a name="intersect-entity-sql"></a><span data-ttu-id="bf1f8-102">INTERSECT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="bf1f8-102">INTERSECT (Entity SQL)</span></span>
<span data-ttu-id="bf1f8-103">INTERSECT オペランドの左右両方のクエリ式によって返される個別の値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-103">Returns a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="bf1f8-104">すべての式は、 `expression`と同じ型であるか、共通の基本型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf1f8-105">構文</span><span class="sxs-lookup"><span data-stu-id="bf1f8-105">Syntax</span></span>  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="bf1f8-106">引数</span><span class="sxs-lookup"><span data-stu-id="bf1f8-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="bf1f8-107">コレクションを返す任意の有効なクエリ式。もう一方のクエリ式から返されたコレクションと比較されます。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf1f8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="bf1f8-108">Return Value</span></span>  
 <span data-ttu-id="bf1f8-109">`expression`と同じ型であるか、共通の基本データ型または派生型であるコレクション。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf1f8-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf1f8-110">Remarks</span></span>  
 <span data-ttu-id="bf1f8-111">INTERSECT は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-111">INTERSECT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="bf1f8-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="bf1f8-113">@No__t 0 の set 演算子の優先順位については、「 [EXCEPT](except-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-113">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf1f8-114">例</span><span class="sxs-lookup"><span data-stu-id="bf1f8-114">Example</span></span>  
 <span data-ttu-id="bf1f8-115">次の Entity SQL クエリでは、INTERSECT 演算子を使用して、INTERSECT オペランドの左右両方のクエリ式によって返される個別の値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-115">The following Entity SQL query uses the INTERSECT operator to return a collection of any distinct values that are returned by both the query expressions on the left and right sides of the INTERSECT operand.</span></span> <span data-ttu-id="bf1f8-116">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="bf1f8-117">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="bf1f8-118">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="bf1f8-119">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="bf1f8-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a><span data-ttu-id="bf1f8-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf1f8-120">See also</span></span>

- [<span data-ttu-id="bf1f8-121">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="bf1f8-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
