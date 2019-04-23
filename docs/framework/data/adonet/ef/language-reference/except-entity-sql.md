---
title: EXCEPT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 69cc23e5-3f8f-4b49-b20e-2f84ff11c80d
ms.openlocfilehash: 32b5148e43a38e5cf8dcce0ae16260d7a6b6a018
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341219"
---
# <a name="except-entity-sql"></a><span data-ttu-id="32997-102">EXCEPT (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="32997-102">EXCEPT (Entity SQL)</span></span>
<span data-ttu-id="32997-103">EXCEPT オペランドの左辺のクエリ式から返される結果のうち、右辺のクエリ式でも返される結果を除いた、重複しない値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="32997-103">Returns a collection of any distinct values from the query expression to the left of the EXCEPT operand that are not also returned from the query expression to the right of the EXCEPT operand.</span></span> <span data-ttu-id="32997-104">すべての式は、 `expression`と同じ型であるか、共通の基本型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="32997-104">All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32997-105">構文</span><span class="sxs-lookup"><span data-stu-id="32997-105">Syntax</span></span>  
  
```  
expression EXCEPT expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="32997-106">引数</span><span class="sxs-lookup"><span data-stu-id="32997-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="32997-107">コレクションを返す任意の有効なクエリ式。もう一方のクエリ式から返されたコレクションと比較されます。</span><span class="sxs-lookup"><span data-stu-id="32997-107">Any valid query expression that returns a collection to compare with the collection returned from another query expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32997-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="32997-108">Return Value</span></span>  
 <span data-ttu-id="32997-109">`expression`と同じ型であるか、共通の基本データ型または派生型であるコレクション。</span><span class="sxs-lookup"><span data-stu-id="32997-109">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32997-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="32997-110">Remarks</span></span>  
 <span data-ttu-id="32997-111">EXCEPT は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="32997-111">EXCEPT is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="32997-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="32997-112">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="32997-113">次の表に、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 集合演算子の優先順位を示します。</span><span class="sxs-lookup"><span data-stu-id="32997-113">The following table shows the precedence of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span>  
  
|<span data-ttu-id="32997-114">優先順位</span><span class="sxs-lookup"><span data-stu-id="32997-114">Precedence</span></span>|<span data-ttu-id="32997-115">演算子</span><span class="sxs-lookup"><span data-stu-id="32997-115">Operators</span></span>|  
|----------------|---------------|  
|<span data-ttu-id="32997-116">最高</span><span class="sxs-lookup"><span data-stu-id="32997-116">Highest</span></span>|<span data-ttu-id="32997-117">INTERSECT</span><span class="sxs-lookup"><span data-stu-id="32997-117">INTERSECT</span></span>|  
||<span data-ttu-id="32997-118">UNION</span><span class="sxs-lookup"><span data-stu-id="32997-118">UNION</span></span><br /><br /> <span data-ttu-id="32997-119">UNION ALL</span><span class="sxs-lookup"><span data-stu-id="32997-119">UNION ALL</span></span>|  
||<span data-ttu-id="32997-120">EXCEPT</span><span class="sxs-lookup"><span data-stu-id="32997-120">EXCEPT</span></span>|  
|<span data-ttu-id="32997-121">最低</span><span class="sxs-lookup"><span data-stu-id="32997-121">Lowest</span></span>|<span data-ttu-id="32997-122">EXISTS</span><span class="sxs-lookup"><span data-stu-id="32997-122">EXISTS</span></span><br /><br /> <span data-ttu-id="32997-123">OVERLAPS</span><span class="sxs-lookup"><span data-stu-id="32997-123">OVERLAPS</span></span><br /><br /> <span data-ttu-id="32997-124">FLATTEN</span><span class="sxs-lookup"><span data-stu-id="32997-124">FLATTEN</span></span><br /><br /> <span data-ttu-id="32997-125">SET</span><span class="sxs-lookup"><span data-stu-id="32997-125">SET</span></span>|  
  
## <a name="example"></a><span data-ttu-id="32997-126">例</span><span class="sxs-lookup"><span data-stu-id="32997-126">Example</span></span>  
 <span data-ttu-id="32997-127">次の Entity SQL クエリでは、EXCEPT 演算子を使用して、2 つのクエリ式から重複しない値のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="32997-127">The following Entity SQL query uses the EXCEPT operator to return a collection of any distinct values from two query expressions.</span></span> <span data-ttu-id="32997-128">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="32997-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="32997-129">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="32997-129">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="32997-130">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="32997-130">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="32997-131">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="32997-131">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EXCEPT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#except)]  
  
## <a name="see-also"></a><span data-ttu-id="32997-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="32997-132">See also</span></span>

- [<span data-ttu-id="32997-133">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="32997-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
