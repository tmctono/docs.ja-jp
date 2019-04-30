---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 736b92f7aac89c309b37a8ac61a295c8d1495d6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034094"
---
# <a name="union-entity-sql"></a><span data-ttu-id="91d13-102">UNION (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="91d13-102">UNION (Entity SQL)</span></span>
<span data-ttu-id="91d13-103">複数のクエリの結果を 1 つのコレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="91d13-103">Combines the results of two or more queries into a single collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d13-104">構文</span><span class="sxs-lookup"><span data-stu-id="91d13-104">Syntax</span></span>  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="91d13-105">引数</span><span class="sxs-lookup"><span data-stu-id="91d13-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="91d13-106">コレクションと結合するコレクションを返す任意の有効なクエリ式。すべての式は、 `expression`と同じ型であるか、共通の基本データ型または派生型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="91d13-106">Any valid query expression that returns a collection to combine with the collection All expressions must be of the same type or of a common base or derived type as `expression`.</span></span>  
  
 <span data-ttu-id="91d13-107">UNION</span><span class="sxs-lookup"><span data-stu-id="91d13-107">UNION</span></span>  
 <span data-ttu-id="91d13-108">複数のコレクションを結合し、1 つのコレクションとして返すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="91d13-108">Specifies that multiple collections are to be combined and returned as a single collection.</span></span>  
  
 <span data-ttu-id="91d13-109">ALL</span><span class="sxs-lookup"><span data-stu-id="91d13-109">ALL</span></span>  
 <span data-ttu-id="91d13-110">複数のコレクションを結合し、重複も含めて 1 つのコレクションとして返すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="91d13-110">Specifies that multiple collections are to be combined and returned as a single collection, including duplicates.</span></span> <span data-ttu-id="91d13-111">指定しない場合、重複は結果コレクションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="91d13-111">If not specified, duplicates are removed from the result collection.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91d13-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="91d13-112">Return Value</span></span>  
 <span data-ttu-id="91d13-113">`expression`と同じ型であるか、共通の基本データ型または派生型であるコレクション。</span><span class="sxs-lookup"><span data-stu-id="91d13-113">A collection of the same type or of a common base or derived type as `expression`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91d13-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="91d13-114">Remarks</span></span>  
 <span data-ttu-id="91d13-115">UNION は、 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] の集合演算子の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="91d13-115">UNION is one of the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators.</span></span> <span data-ttu-id="91d13-116">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] のすべての集合演算子は左から右に評価されます。</span><span class="sxs-lookup"><span data-stu-id="91d13-116">All [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators are evaluated from left to right.</span></span> <span data-ttu-id="91d13-117">優先順位は、[!INCLUDE[esql](../../../../../../includes/esql-md.md)]集合演算子を参照してください[EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)します。</span><span class="sxs-lookup"><span data-stu-id="91d13-117">For precedence information for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] set operators, see [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91d13-118">例</span><span class="sxs-lookup"><span data-stu-id="91d13-118">Example</span></span>  
 <span data-ttu-id="91d13-119">次の Entity SQL クエリでは、UNION ALL 演算子を使用して、2 つのクエリの結果を 1 つのコレクションに結合します。</span><span class="sxs-lookup"><span data-stu-id="91d13-119">The following Entity SQL query uses the UNION ALL operator to combine the results of two queries into a single collection.</span></span> <span data-ttu-id="91d13-120">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="91d13-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="91d13-121">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="91d13-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="91d13-122">」の手順に従って[方法。StructuralType 結果を返すクエリを実行](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="91d13-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="91d13-123">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="91d13-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a><span data-ttu-id="91d13-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="91d13-124">See also</span></span>

- [<span data-ttu-id="91d13-125">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="91d13-125">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
