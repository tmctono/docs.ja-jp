---
title: IN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 5a07ee79d5452da4341d391fae7c997c33b603a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250669"
---
# <a name="in-entity-sql"></a><span data-ttu-id="52a06-102">IN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="52a06-102">IN (Entity SQL)</span></span>
<span data-ttu-id="52a06-103">コレクション内に一致する値があるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="52a06-103">Determines whether a value matches any value in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a06-104">構文</span><span class="sxs-lookup"><span data-stu-id="52a06-104">Syntax</span></span>  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="52a06-105">引数</span><span class="sxs-lookup"><span data-stu-id="52a06-105">Arguments</span></span>  
 `value`  
 <span data-ttu-id="52a06-106">照合する値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="52a06-106">Any valid expression that returns the value to match.</span></span>  
  
 <span data-ttu-id="52a06-107">[ NOT ]</span><span class="sxs-lookup"><span data-stu-id="52a06-107">[ NOT ]</span></span>  
 <span data-ttu-id="52a06-108">IN の `Boolean` 型の結果を否定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="52a06-108">Specifies that the `Boolean` result of IN be negated.</span></span>  
  
 `expression`  
 <span data-ttu-id="52a06-109">一致の判定対象のコレクションを返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="52a06-109">Any valid expression that returns the collection to test for a match.</span></span> <span data-ttu-id="52a06-110">すべての式は、 `value`と同じ型であるか、共通の基本型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="52a06-110">All expressions must be of the same type or of a common base or derived type as `value`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52a06-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="52a06-111">Return Value</span></span>  
 <span data-ttu-id="52a06-112">コレクションに値が見つかった場合は `true`、値が null またはコレクションが null の場合は null、それ以外の場合は `false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="52a06-112">`true` if the value is found in the collection; null if the value is null or the collection is null; otherwise, `false`.</span></span> <span data-ttu-id="52a06-113">NOT IN を使用すると、IN の結果が否定されます。</span><span class="sxs-lookup"><span data-stu-id="52a06-113">Using NOT IN negates the results of IN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52a06-114">例</span><span class="sxs-lookup"><span data-stu-id="52a06-114">Example</span></span>  
 <span data-ttu-id="52a06-115">次の Entity SQL クエリでは、IN 演算子を使用して、コレクション内に一致する値があるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="52a06-115">The following Entity SQL query uses the IN operator to determine whether a value matches any value in a collection.</span></span> <span data-ttu-id="52a06-116">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="52a06-116">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="52a06-117">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="52a06-117">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="52a06-118">[「方法:StructuralType の結果](../how-to-execute-a-query-that-returns-structuraltype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="52a06-118">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="52a06-119">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="52a06-119">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a><span data-ttu-id="52a06-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="52a06-120">See also</span></span>

- [<span data-ttu-id="52a06-121">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="52a06-121">Entity SQL Reference</span></span>](entity-sql-reference.md)
