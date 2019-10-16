---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319351"
---
# <a name="set-entity-sql"></a><span data-ttu-id="3ed22-102">SET (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="3ed22-102">SET (Entity SQL)</span></span>
<span data-ttu-id="3ed22-103">SET 式は、重複する要素をすべて除外した新しいコレクションを生成することによって、オブジェクトのコレクションを 1 つの集合に変換します。</span><span class="sxs-lookup"><span data-stu-id="3ed22-103">The SET expression is used to convert a collection of objects into a set by yielding a new collection with all duplicate elements removed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed22-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ed22-104">Syntax</span></span>  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ed22-105">引数</span><span class="sxs-lookup"><span data-stu-id="3ed22-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="3ed22-106">コレクションを返す任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="3ed22-106">Any valid query expression that returns a collection.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ed22-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3ed22-107">Remarks</span></span>  
 <span data-ttu-id="3ed22-108">集合式 `SET(c)` は、論理上、次の select ステートメントと等価です。</span><span class="sxs-lookup"><span data-stu-id="3ed22-108">The set expression `SET(c)` is logically equivalent to the following select statement:</span></span>  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 <span data-ttu-id="3ed22-109">`SET` は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="3ed22-109">`SET` is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="3ed22-110">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="3ed22-110">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="3ed22-111">@No__t-1 セット演算子の優先順位については、「 [EXCEPT](except-entity-sql.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ed22-111">See [EXCEPT](except-entity-sql.md) for precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ed22-112">例</span><span class="sxs-lookup"><span data-stu-id="3ed22-112">Example</span></span>  
 <span data-ttu-id="3ed22-113">次の Entity SQL クエリでは、SET 式を使用して、オブジェクトのコレクションを 1 つの集合に変換します。</span><span class="sxs-lookup"><span data-stu-id="3ed22-113">The following Entity SQL query uses the SET expression to convert a collection of objects into a set.</span></span> <span data-ttu-id="3ed22-114">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="3ed22-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="3ed22-115">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ed22-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="3ed22-116">[「方法: PrimitiveType の結果を返すクエリを実行](../how-to-execute-a-query-that-returns-primitivetype-results.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3ed22-116">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2. <span data-ttu-id="3ed22-117">次のクエリを引数として `ExecutePrimitiveTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="3ed22-117">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a><span data-ttu-id="3ed22-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ed22-118">See also</span></span>

- [<span data-ttu-id="3ed22-119">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="3ed22-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
