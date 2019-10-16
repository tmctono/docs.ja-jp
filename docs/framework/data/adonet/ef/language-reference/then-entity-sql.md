---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: ba01a978c53b58f7e6c1ac9bc42a97277ac64bbc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319284"
---
# <a name="then-entity-sql"></a><span data-ttu-id="f2bf1-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f2bf1-102">THEN (Entity SQL)</span></span>
<span data-ttu-id="f2bf1-103">WHEN 句が `true`として評価された場合の結果です。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2bf1-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2bf1-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2bf1-105">引数</span><span class="sxs-lookup"><span data-stu-id="f2bf1-105">Arguments</span></span>  
 `when_expression`  
 <span data-ttu-id="f2bf1-106">任意の有効なブール式。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="f2bf1-107">コレクションを返す任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2bf1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2bf1-108">Remarks</span></span>  
 <span data-ttu-id="f2bf1-109">`when_expression` が `true`として評価された場合、対応する `then-expression`が評価されます。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="f2bf1-110">WHEN の条件が満たされなかった場合は、 `else-expression` が評価されます。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="f2bf1-111">ただし、 `else-expression`が存在しない場合、結果は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="f2bf1-112">例については、「 [CASE](case-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2bf1-113">例</span><span class="sxs-lookup"><span data-stu-id="f2bf1-113">Example</span></span>  
 <span data-ttu-id="f2bf1-114">次の Entity SQL クエリでは、CASE 式を使用して、一連の `Boolean` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="f2bf1-115">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f2bf1-116">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f2bf1-117">[「方法: PrimitiveType の結果を返すクエリを実行](../how-to-execute-a-query-that-returns-primitivetype-results.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="f2bf1-118">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="f2bf1-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="f2bf1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2bf1-119">See also</span></span>

- [<span data-ttu-id="f2bf1-120">CASE</span><span class="sxs-lookup"><span data-stu-id="f2bf1-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="f2bf1-121">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="f2bf1-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
