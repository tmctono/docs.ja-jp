---
title: CREATEREF (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 489828cf-a335-4449-9360-b0d92eec5481
ms.openlocfilehash: cbaea82108dd3debcca972ca15dea248227330ac
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251101"
---
# <a name="createref-entity-sql"></a><span data-ttu-id="d42b1-102">CREATEREF (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d42b1-102">CREATEREF (Entity SQL)</span></span>
<span data-ttu-id="d42b1-103">エンティティ セット内のエンティティへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d42b1-103">Fabricates references to an entity in an entityset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d42b1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d42b1-104">Syntax</span></span>  
  
```  
CreateRef(entityset_identifier, row_typed_expression)  
```  
  
## <a name="arguments"></a><span data-ttu-id="d42b1-105">引数</span><span class="sxs-lookup"><span data-stu-id="d42b1-105">Arguments</span></span>  
 `entityset_identifier`  
 <span data-ttu-id="d42b1-106">エンティティ セット識別子。文字列リテラルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d42b1-106">The entityset identifier, not a string literal.</span></span>  
  
 `row_typed_expression`  
 <span data-ttu-id="d42b1-107">エンティティ型のキー プロパティに対応する行型の式。</span><span class="sxs-lookup"><span data-stu-id="d42b1-107">A row-typed expression that corresponds to the key properties of the entity type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d42b1-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="d42b1-108">Remarks</span></span>  
 <span data-ttu-id="d42b1-109">`row_typed_expression` は、エンティティのキーの種類に構造的に同等である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d42b1-109">`row_typed_expression` must be structurally equivalent to the key type for the entity.</span></span> <span data-ttu-id="d42b1-110">つまり、エンティティ キーのフィールドの数、型、および順序と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d42b1-110">That is, it must have the same number and types of fields in the same order as the entity keys.</span></span>  
  
 <span data-ttu-id="d42b1-111">次の例では、Orders と BadOrders は両方とも Order 型のエンティティ セットで、ID は Order の 1 つのキー プロパティであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="d42b1-111">In the example below, Orders and BadOrders are both entitysets of type Order, and Id is assumed to be the single key property of Order.</span></span> <span data-ttu-id="d42b1-112">この例は、BadOrders 内のエンティティへの参照を生成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d42b1-112">The example illustrates how we may produce a reference to an entity in BadOrders.</span></span> <span data-ttu-id="d42b1-113">参照は未解決の場合がある点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="d42b1-113">Note that the reference may be dangling.</span></span>  <span data-ttu-id="d42b1-114">つまり、参照は実際には指定のエンティティを識別しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d42b1-114">That is, the reference may not actually identify a specific entity.</span></span> <span data-ttu-id="d42b1-115">そのような場合、その参照に対して `DEREF` 操作を行うと、null が返されます。</span><span class="sxs-lookup"><span data-stu-id="d42b1-115">In those cases, a `DEREF` operation on that reference returns a null.</span></span>  
  
```  
select CreateRef(LOB.BadOrders, row(o.Id))   
from LOB.Orders as o   
```  
  
## <a name="example"></a><span data-ttu-id="d42b1-116">例</span><span class="sxs-lookup"><span data-stu-id="d42b1-116">Example</span></span>  
 <span data-ttu-id="d42b1-117">次の Entity SQL クエリは、CREATEREF 演算子を使用してエンティティ セット内のエンティティへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d42b1-117">The following Entity SQL query uses the CREATEREF operator to fabricate references to an entity in an entity set.</span></span> <span data-ttu-id="d42b1-118">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d42b1-118">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d42b1-119">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d42b1-119">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d42b1-120">[「方法:StructuralType の結果](../how-to-execute-a-query-that-returns-structuraltype-results.md)を返すクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="d42b1-120">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d42b1-121">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="d42b1-121">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CREATEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#createref)]  
  
## <a name="see-also"></a><span data-ttu-id="d42b1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d42b1-122">See also</span></span>

- [<span data-ttu-id="d42b1-123">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="d42b1-123">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="d42b1-124">DEREF</span><span class="sxs-lookup"><span data-stu-id="d42b1-124">DEREF</span></span>](deref-entity-sql.md)
- [<span data-ttu-id="d42b1-125">KEY</span><span class="sxs-lookup"><span data-stu-id="d42b1-125">KEY</span></span>](key-entity-sql.md)
- [<span data-ttu-id="d42b1-126">REF</span><span class="sxs-lookup"><span data-stu-id="d42b1-126">REF</span></span>](ref-entity-sql.md)
