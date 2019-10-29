---
title: BETWEEN (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 611e90f362bbc0eac521e1e1998fb85200169c19
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039945"
---
# <a name="between-entity-sql"></a><span data-ttu-id="ad9e7-102">BETWEEN (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="ad9e7-102">BETWEEN (Entity SQL)</span></span>
<span data-ttu-id="ad9e7-103">式の結果が指定の範囲内の値になるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-103">Determines whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="ad9e7-104">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN 式は、Transact-sql との間の Transact-sql と同じ機能を持ちます。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-104">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN expression has the same functionality as the Transact-SQL BETWEEN expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad9e7-105">構文</span><span class="sxs-lookup"><span data-stu-id="ad9e7-105">Syntax</span></span>  
  
```csharp  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a><span data-ttu-id="ad9e7-106">引数</span><span class="sxs-lookup"><span data-stu-id="ad9e7-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="ad9e7-107">`begin_expression` と `end_expression` で定義される範囲についてテストするための任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-107">Any valid expression to test for in the range defined by `begin_expression` and `end_expression`.</span></span> <span data-ttu-id="ad9e7-108">`expression` は、`begin_expression` と `end_expression` の両方と同じ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-108">`expression` must be the same type as both `begin_expression` and `end_expression`.</span></span>  
  
 `begin_expression`  
 <span data-ttu-id="ad9e7-109">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-109">Any valid expression.</span></span> <span data-ttu-id="ad9e7-110">`begin_expression` は、`expression` と `end_expression` の両方と同じ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-110">`begin_expression` must be the same type as both `expression` and `end_expression`.</span></span> <span data-ttu-id="ad9e7-111">`begin_expression` は、`end_expression` 未満でなければなりません。それ以外の場合、戻り値は否定されます。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-111">`begin_expression` should be less than `end_expression`, else the return value will be negated.</span></span>  
  
 `end_expression`  
 <span data-ttu-id="ad9e7-112">任意の有効な式。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-112">Any valid expression.</span></span> <span data-ttu-id="ad9e7-113">`end_expression` は、`expression` と `begin_expression` の両方と同じ型にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-113">`end_expression` must be the same type as both `expression` and `begin_expression`.</span></span>  
  
 <span data-ttu-id="ad9e7-114">NOT</span><span class="sxs-lookup"><span data-stu-id="ad9e7-114">NOT</span></span>  
 <span data-ttu-id="ad9e7-115">BETWEEN の結果を否定することを指定します。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-115">Specifies that the result of BETWEEN be negated.</span></span>  
  
 <span data-ttu-id="ad9e7-116">AND</span><span class="sxs-lookup"><span data-stu-id="ad9e7-116">AND</span></span>  
 <span data-ttu-id="ad9e7-117">`expression` と `begin_expression` で表される範囲内で `end_expression` をテストする必要があることを示すプレースホルダーです。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-117">Acts as a placeholder that indicates `expression` should be within the range indicated by `begin_expression` and `end_expression`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad9e7-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="ad9e7-118">Return Value</span></span>  
 <span data-ttu-id="ad9e7-119">`true` が、`expression` と `begin_expression` で指定される範囲内にある場合は `end_expression`。それ以外の場合は `false`。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-119">`true` if `expression` is between the range indicated by `begin_expression` and `end_expression`; otherwise, `false`.</span></span> <span data-ttu-id="ad9e7-120">`null` が `expression` であるか、`null` または `begin_expression` が `end_expression` である場合は、`null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-120">`null` will be returned if `expression` is `null` or if `begin_expression` or `end_expression` is `null`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad9e7-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad9e7-121">Remarks</span></span>  
 <span data-ttu-id="ad9e7-122">限定範囲を指定するには、BETWEEN の代わりに、より大きい (>) 演算子とより小さい (<) 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-122">To specify an exclusive range, use the greater than (>) and less than (<) operators instead of BETWEEN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad9e7-123">例</span><span class="sxs-lookup"><span data-stu-id="ad9e7-123">Example</span></span>  
 <span data-ttu-id="ad9e7-124">次の Entity SQL クエリでは、BETWEEN 演算子を使用して、式の結果が指定の範囲内の値になるかどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-124">The following Entity SQL query uses BETWEEN operator to determine whether an expression results in a value in a specified range.</span></span> <span data-ttu-id="ad9e7-125">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-125">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="ad9e7-126">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-126">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="ad9e7-127">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-127">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="ad9e7-128">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="ad9e7-128">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a><span data-ttu-id="ad9e7-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad9e7-129">See also</span></span>

- [<span data-ttu-id="ad9e7-130">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="ad9e7-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
