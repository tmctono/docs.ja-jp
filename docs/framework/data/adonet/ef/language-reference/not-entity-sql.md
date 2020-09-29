---
title: '! (NOT) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0eb9be9ed4cbce45a51d15eea68e9fb1a26f0107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191841"
---
# <a name="-not-entity-sql"></a><span data-ttu-id="2f5e8-103">!</span><span class="sxs-lookup"><span data-stu-id="2f5e8-103">!</span></span> <span data-ttu-id="2f5e8-104">(NOT) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="2f5e8-104">(NOT) (Entity SQL)</span></span>

<span data-ttu-id="2f5e8-105">`Boolean` 型の式を否定します。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-105">Negates a `Boolean` expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f5e8-106">構文</span><span class="sxs-lookup"><span data-stu-id="2f5e8-106">Syntax</span></span>  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a><span data-ttu-id="2f5e8-107">引数</span><span class="sxs-lookup"><span data-stu-id="2f5e8-107">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="2f5e8-108">ブール値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-108">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f5e8-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f5e8-109">Remarks</span></span>  

 <span data-ttu-id="2f5e8-110">感嘆符 (!) には、NOT 演算子と同じ機能があります。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-110">The exclamation point (!) has the same functionality as the NOT operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f5e8-111">例</span><span class="sxs-lookup"><span data-stu-id="2f5e8-111">Example</span></span>  

 <span data-ttu-id="2f5e8-112">次の Entity SQL クエリでは、NOT 演算子を使用して `Boolean` 型の式を否定します。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-112">The following Entity SQL query uses the NOT operator to negates a `Boolean` expression.</span></span> <span data-ttu-id="2f5e8-113">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="2f5e8-114">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="2f5e8-115">「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="2f5e8-116">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="2f5e8-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a><span data-ttu-id="2f5e8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f5e8-117">See also</span></span>

- [<span data-ttu-id="2f5e8-118">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="2f5e8-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
