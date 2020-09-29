---
title: '&amp;&amp; (AND) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: 86ff43f8ed20c5696d15e21284394c3cb63200e3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198042"
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="f3b5d-102">&amp;&amp; (AND) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f3b5d-102">&amp;&amp; (AND) (Entity SQL)</span></span>

<span data-ttu-id="f3b5d-103">両方の式が `true` の場合は `true`を返します。それ以外の場合は `false` または `NULL`を返します。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3b5d-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3b5d-104">Syntax</span></span>  
  
```csharp  
boolean_expression AND boolean_expression
```

<span data-ttu-id="f3b5d-105">or</span><span class="sxs-lookup"><span data-stu-id="f3b5d-105">or</span></span>  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="f3b5d-106">引数</span><span class="sxs-lookup"><span data-stu-id="f3b5d-106">Arguments</span></span>  

 `boolean_expression`  
 <span data-ttu-id="f3b5d-107">ブール値を返す任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-107">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3b5d-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="f3b5d-108">Remarks</span></span>  

 <span data-ttu-id="f3b5d-109">二重のアンパサンド (&&) は、AND 演算子と同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-109">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="f3b5d-110">使用可能な入力値と戻り値の型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-110">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="f3b5d-111">true</span><span class="sxs-lookup"><span data-stu-id="f3b5d-111">TRUE</span></span>|<span data-ttu-id="f3b5d-112">false</span><span class="sxs-lookup"><span data-stu-id="f3b5d-112">FALSE</span></span>|<span data-ttu-id="f3b5d-113">NULL</span><span class="sxs-lookup"><span data-stu-id="f3b5d-113">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="f3b5d-114">false</span><span class="sxs-lookup"><span data-stu-id="f3b5d-114">FALSE</span></span>|<span data-ttu-id="f3b5d-115">false</span><span class="sxs-lookup"><span data-stu-id="f3b5d-115">FALSE</span></span>|<span data-ttu-id="f3b5d-116">false</span><span class="sxs-lookup"><span data-stu-id="f3b5d-116">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="f3b5d-117">NULL</span><span class="sxs-lookup"><span data-stu-id="f3b5d-117">NULL</span></span>|<span data-ttu-id="f3b5d-118">false</span><span class="sxs-lookup"><span data-stu-id="f3b5d-118">FALSE</span></span>|<span data-ttu-id="f3b5d-119">NULL</span><span class="sxs-lookup"><span data-stu-id="f3b5d-119">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f3b5d-120">例</span><span class="sxs-lookup"><span data-stu-id="f3b5d-120">Example</span></span>  

 <span data-ttu-id="f3b5d-121">次の Entity SQL クエリは、AND 演算子の使い方を示しています。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-121">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="f3b5d-122">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-122">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="f3b5d-123">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-123">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="f3b5d-124">「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-124">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="f3b5d-125">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="f3b5d-125">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="f3b5d-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3b5d-126">See also</span></span>

- [<span data-ttu-id="f3b5d-127">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="f3b5d-127">Entity SQL Reference</span></span>](entity-sql-reference.md)
