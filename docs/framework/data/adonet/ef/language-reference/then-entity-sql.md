---
title: THEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
ms.openlocfilehash: f038f242bc0873df3d72700aa05fca2f76f777ff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161673"
---
# <a name="then-entity-sql"></a><span data-ttu-id="43875-102">THEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="43875-102">THEN (Entity SQL)</span></span>

<span data-ttu-id="43875-103">WHEN 句が `true`として評価された場合の結果です。</span><span class="sxs-lookup"><span data-stu-id="43875-103">The result of a WHEN clause when it evaluates to `true`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43875-104">構文</span><span class="sxs-lookup"><span data-stu-id="43875-104">Syntax</span></span>  
  
```sql  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="43875-105">引数</span><span class="sxs-lookup"><span data-stu-id="43875-105">Arguments</span></span>  

 `when_expression`  
 <span data-ttu-id="43875-106">任意の有効なブール式。</span><span class="sxs-lookup"><span data-stu-id="43875-106">Any valid Boolean expression.</span></span>  
  
 `then_expression`  
 <span data-ttu-id="43875-107">コレクションを返す任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="43875-107">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43875-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="43875-108">Remarks</span></span>  

 <span data-ttu-id="43875-109">`when_expression` が `true`として評価された場合、対応する `then-expression`が評価されます。</span><span class="sxs-lookup"><span data-stu-id="43875-109">If `when_expression` evaluates to the value `true`, the result is the corresponding `then-expression`.</span></span> <span data-ttu-id="43875-110">WHEN の条件が満たされなかった場合は、 `else-expression` が評価されます。</span><span class="sxs-lookup"><span data-stu-id="43875-110">If none of the WHEN conditions are satisfied, the `else-expression` is evaluated.</span></span> <span data-ttu-id="43875-111">ただし、 `else-expression`が存在しない場合、結果は NULL になります。</span><span class="sxs-lookup"><span data-stu-id="43875-111">However, if there is no `else-expression`, the result is null.</span></span>  
  
 <span data-ttu-id="43875-112">例については、「[CASE](case-entity-sql.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43875-112">For an example, see [CASE](case-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43875-113">例</span><span class="sxs-lookup"><span data-stu-id="43875-113">Example</span></span>  

 <span data-ttu-id="43875-114">次の Entity SQL クエリでは、CASE 式を使用して、一連の `Boolean` 式を評価します。</span><span class="sxs-lookup"><span data-stu-id="43875-114">The following Entity SQL query uses the CASE expression to evaluate a set of `Boolean` expressions.</span></span> <span data-ttu-id="43875-115">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="43875-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="43875-116">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="43875-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="43875-117">「[方法: PrimitiveType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-primitivetype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="43875-117">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="43875-118">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="43875-118">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#CASE_WHEN_THEN_ELSE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#case_when_then_else)]  
  
## <a name="see-also"></a><span data-ttu-id="43875-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="43875-119">See also</span></span>

- [<span data-ttu-id="43875-120">CASE</span><span class="sxs-lookup"><span data-stu-id="43875-120">CASE</span></span>](case-entity-sql.md)
- [<span data-ttu-id="43875-121">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="43875-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
