---
title: '&amp;&amp; (と) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: be6e7120e6c19714f151aa38a8b9a1355de29d1a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039962"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="f2cb9-102">&amp;&amp; (と) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f2cb9-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="f2cb9-103">両方の式が `true` の場合は `true`を返します。それ以外の場合は `false` または `NULL`を返します。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cb9-104">構文</span><span class="sxs-lookup"><span data-stu-id="f2cb9-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```
 
<span data-ttu-id="f2cb9-105">、または</span><span class="sxs-lookup"><span data-stu-id="f2cb9-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f2cb9-106">引数</span><span class="sxs-lookup"><span data-stu-id="f2cb9-106">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="f2cb9-107">ブール値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2cb9-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f2cb9-108">Remarks</span></span>  
 <span data-ttu-id="f2cb9-109">二重のアンパサンド (&&) は、AND 演算子と同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="f2cb9-110">使用可能な入力値と戻り値の型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="f2cb9-111">true</span><span class="sxs-lookup"><span data-stu-id="f2cb9-111">TRUE</span></span>|<span data-ttu-id="f2cb9-112">false</span><span class="sxs-lookup"><span data-stu-id="f2cb9-112">FALSE</span></span>|<span data-ttu-id="f2cb9-113">NULL</span><span class="sxs-lookup"><span data-stu-id="f2cb9-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="f2cb9-114">false</span><span class="sxs-lookup"><span data-stu-id="f2cb9-114">FALSE</span></span>|<span data-ttu-id="f2cb9-115">false</span><span class="sxs-lookup"><span data-stu-id="f2cb9-115">FALSE</span></span>|<span data-ttu-id="f2cb9-116">false</span><span class="sxs-lookup"><span data-stu-id="f2cb9-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="f2cb9-117">NULL</span><span class="sxs-lookup"><span data-stu-id="f2cb9-117">NULL</span></span>|<span data-ttu-id="f2cb9-118">false</span><span class="sxs-lookup"><span data-stu-id="f2cb9-118">FALSE</span></span>|<span data-ttu-id="f2cb9-119">NULL</span><span class="sxs-lookup"><span data-stu-id="f2cb9-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f2cb9-120">例</span><span class="sxs-lookup"><span data-stu-id="f2cb9-120">Example</span></span>  
 <span data-ttu-id="f2cb9-121">次の Entity SQL クエリは、AND 演算子の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="f2cb9-122">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f2cb9-123">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f2cb9-124">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f2cb9-125">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="f2cb9-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="f2cb9-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2cb9-126">See also</span></span>

- [<span data-ttu-id="f2cb9-127">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="f2cb9-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
