---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 41036e629837bd5861368df545bed9423eac5b23
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251292"
---
# <a name="between-entity-sql"></a><span data-ttu-id="e2599-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e2599-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="e2599-103">式の結果が指定の範囲内の値になるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e2599-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e2599-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Between 式は、transact-sql との間の transact-sql と同じ機能を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e2599-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2599-105">構文</span><span class="sxs-lookup"><span data-stu-id="e2599-105">Syntax</span></span>  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="e2599-106">引数</span><span class="sxs-lookup"><span data-stu-id="e2599-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e2599-107">`begin_expression` と `end_expression` で定義される範囲についてテストするための任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="e2599-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="e2599-108">`expression` は、`begin_expression` と `end_expression` の両方と同じ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2599-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="e2599-109">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="e2599-109">Any valid expression.</span></span> <span data-ttu-id="e2599-110">`begin_expression` は、`expression` と `end_expression` の両方と同じ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2599-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="e2599-111">`begin_expression` は、`end_expression` 未満でなければなりません。それ以外の場合、戻り値は否定されます。</span><span class="sxs-lookup"><span data-stu-id="e2599-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="e2599-112">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="e2599-112">Any valid expression.</span></span> <span data-ttu-id="e2599-113">`end_expression` は、`expression` と `begin_expression` の両方と同じ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2599-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="e2599-114">NOT</span><span class="sxs-lookup"><span data-stu-id="e2599-114">NOT</span></span>  
 <span data-ttu-id="e2599-115">BETWEEN の結果を否定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="e2599-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="e2599-116">AND</span><span class="sxs-lookup"><span data-stu-id="e2599-116">AND</span></span>  
 <span data-ttu-id="e2599-117">`expression` と `begin_expression` で表される範囲内で `end_expression` をテストする必要があることを示すプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="e2599-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2599-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="e2599-118">Return Value</span></span>  
 <span data-ttu-id="e2599-119">`true` が、`expression` と `begin_expression` で指定される範囲内にある場合は `end_expression`。それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="e2599-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="e2599-120">`null` が `expression` であるか、`null` または `begin_expression` が `end_expression` である場合は、`null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="e2599-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2599-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="e2599-121">Remarks</span></span>  
 <span data-ttu-id="e2599-122">限定範囲を指定するには、BETWEEN の代わりに、より大きい (>) 演算子とより小さい (<) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2599-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2599-123">例</span><span class="sxs-lookup"><span data-stu-id="e2599-123">Example</span></span>  
 <span data-ttu-id="e2599-124">次の Entity SQL クエリでは、BETWEEN 演算子を使用して、式の結果が指定の範囲内の値になるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="e2599-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="e2599-125">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e2599-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e2599-126">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2599-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e2599-127">[「方法:StructuralType の結果](../how-to-execute-a-query-that-returns-structuraltype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2599-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e2599-128">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="e2599-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="e2599-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2599-129">See also</span></span>

- [<span data-ttu-id="e2599-130">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="e2599-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
