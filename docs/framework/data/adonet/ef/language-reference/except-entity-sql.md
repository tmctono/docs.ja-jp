---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: c4df8c2b72ee60a425c98c64a13a1e2d43d4506e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833855"
---
# <a name="except-entity-sql"></a><span data-ttu-id="9bf46-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9bf46-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="9bf46-103">EXCEPT オペランドの左辺のクエリ式から返される結果のうち、右辺のクエリ式でも返される結果を除いた、重複しない値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="9bf46-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="9bf46-104">すべての式は、 `expression`と同じ型であるか、共通の基本型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bf46-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf46-105">構文</span><span class="sxs-lookup"><span data-stu-id="9bf46-105">Syntax</span></span>  
  
```sql  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9bf46-106">引数</span><span class="sxs-lookup"><span data-stu-id="9bf46-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9bf46-107">コレクションを返す任意の有効なクエリ式。もう一方のクエリ式から返されたコレクションと比較されます。</span><span class="sxs-lookup"><span data-stu-id="9bf46-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bf46-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9bf46-108">Return Value</span></span>  
 <span data-ttu-id="9bf46-109">`expression`と同じ型であるか、共通の基本データ型または派生型であるコレクション。</span><span class="sxs-lookup"><span data-stu-id="9bf46-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bf46-110">コメント</span><span class="sxs-lookup"><span data-stu-id="9bf46-110">Remarks</span></span>  
 <span data-ttu-id="9bf46-111">EXCEPT は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="9bf46-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="9bf46-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9bf46-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="9bf46-113">次の表に、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集合演算子の優先順位を示します。</span><span class="sxs-lookup"><span data-stu-id="9bf46-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="9bf46-114">優先順位</span><span class="sxs-lookup"><span data-stu-id="9bf46-114">Precedence</span></span>|<span data-ttu-id="9bf46-115">演算子</span><span class="sxs-lookup"><span data-stu-id="9bf46-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="9bf46-116">最高</span><span class="sxs-lookup"><span data-stu-id="9bf46-116">Highest</span></span>|<span data-ttu-id="9bf46-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="9bf46-117">INTERSECT</span></span>|  
||<span data-ttu-id="9bf46-118">UNION</span><span class="sxs-lookup"><span data-stu-id="9bf46-118">UNION</span></span><br /><br /> <span data-ttu-id="9bf46-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="9bf46-119">UNION ALL</span></span>|  
||<span data-ttu-id="9bf46-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="9bf46-120">EXCEPT</span></span>|  
|<span data-ttu-id="9bf46-121">最低</span><span class="sxs-lookup"><span data-stu-id="9bf46-121">Lowest</span></span>|<span data-ttu-id="9bf46-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="9bf46-122">EXISTS</span></span><br /><br /> <span data-ttu-id="9bf46-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="9bf46-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="9bf46-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="9bf46-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="9bf46-125">SET</span><span class="sxs-lookup"><span data-stu-id="9bf46-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9bf46-126">例</span><span class="sxs-lookup"><span data-stu-id="9bf46-126">Example</span></span>  
 <span data-ttu-id="9bf46-127">次の Entity SQL クエリでは、EXCEPT 演算子を使用して、2 つのクエリ式から重複しない値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="9bf46-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="9bf46-128">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="9bf46-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9bf46-129">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9bf46-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="9bf46-130">@No__t の手順に従います。StructuralType Results @ no__t-0 を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="9bf46-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="9bf46-131">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="9bf46-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#EXCEPT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#except)]  
  
## <a name="see-also"></a><span data-ttu-id="9bf46-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bf46-132">See also</span></span>

- [<span data-ttu-id="9bf46-133">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="9bf46-133">Entity SQL Reference</span></span>](entity-sql-reference.md)
