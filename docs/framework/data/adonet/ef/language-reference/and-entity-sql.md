---
title: '&amp;&amp; (および)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: f0b20a8c1960bd6191a35c426dbea45c30ccc1c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084070"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="260a1-102">&amp;&amp; (および)(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="260a1-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="260a1-103">両方の式が `true` の場合は `true`を返します。それ以外の場合は `false` または `NULL`を返します。</span><span class="sxs-lookup"><span data-stu-id="260a1-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="260a1-104">構文</span><span class="sxs-lookup"><span data-stu-id="260a1-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="260a1-105">引数</span><span class="sxs-lookup"><span data-stu-id="260a1-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="260a1-106">ブール値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="260a1-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="260a1-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="260a1-107">Remarks</span></span>  
 <span data-ttu-id="260a1-108">二重のアンパサンド (&&) は、AND 演算子と同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="260a1-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="260a1-109">使用可能な入力値と戻り値の型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="260a1-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="260a1-110">true</span><span class="sxs-lookup"><span data-stu-id="260a1-110">TRUE</span></span>|<span data-ttu-id="260a1-111">false</span><span class="sxs-lookup"><span data-stu-id="260a1-111">FALSE</span></span>|<span data-ttu-id="260a1-112">NULL</span><span class="sxs-lookup"><span data-stu-id="260a1-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="260a1-113">false</span><span class="sxs-lookup"><span data-stu-id="260a1-113">FALSE</span></span>|<span data-ttu-id="260a1-114">false</span><span class="sxs-lookup"><span data-stu-id="260a1-114">FALSE</span></span>|<span data-ttu-id="260a1-115">false</span><span class="sxs-lookup"><span data-stu-id="260a1-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="260a1-116">NULL</span><span class="sxs-lookup"><span data-stu-id="260a1-116">NULL</span></span>|<span data-ttu-id="260a1-117">false</span><span class="sxs-lookup"><span data-stu-id="260a1-117">FALSE</span></span>|<span data-ttu-id="260a1-118">NULL</span><span class="sxs-lookup"><span data-stu-id="260a1-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="260a1-119">例</span><span class="sxs-lookup"><span data-stu-id="260a1-119">Example</span></span>  
 <span data-ttu-id="260a1-120">次の Entity SQL クエリは、AND 演算子の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="260a1-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="260a1-121">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="260a1-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="260a1-122">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="260a1-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="260a1-123">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="260a1-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="260a1-124">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="260a1-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="260a1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="260a1-125">See also</span></span>

- [<span data-ttu-id="260a1-126">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="260a1-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
