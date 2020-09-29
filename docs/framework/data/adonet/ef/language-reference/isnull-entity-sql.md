---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 3360ad4ca7306a8cc1b7d6948204f825ff9a93c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203619"
---
# <a name="isnull-entity-sql"></a><span data-ttu-id="d0d90-102">ISNULL (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d0d90-102">ISNULL (Entity SQL)</span></span>

<span data-ttu-id="d0d90-103">クエリ式が NULL かどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d0d90-103">Determines if a query expression is null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0d90-104">構文</span><span class="sxs-lookup"><span data-stu-id="d0d90-104">Syntax</span></span>  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a><span data-ttu-id="d0d90-105">引数</span><span class="sxs-lookup"><span data-stu-id="d0d90-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="d0d90-106">任意の有効なクエリ式。</span><span class="sxs-lookup"><span data-stu-id="d0d90-106">Any valid query expression.</span></span> <span data-ttu-id="d0d90-107">コレクションにすることはできません。また、コレクション メンバーや、コレクション型のプロパティを持つレコード型を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="d0d90-107">Cannot be a collection, have collection members, or a record type with collection type properties.</span></span>  
  
 <span data-ttu-id="d0d90-108">NOT</span><span class="sxs-lookup"><span data-stu-id="d0d90-108">NOT</span></span>  
 <span data-ttu-id="d0d90-109">IS NULL の EDM.Boolean の結果を否定します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-109">Negates the EDM.Boolean result of IS NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0d90-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="d0d90-110">Return Value</span></span>  

 <span data-ttu-id="d0d90-111">`true` によって NULL が返される場合は `expression`、それ以外の場合は `false` です。</span><span class="sxs-lookup"><span data-stu-id="d0d90-111">`true` if `expression` returns null; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0d90-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="d0d90-112">Remarks</span></span>  

 <span data-ttu-id="d0d90-113">外部結合の要素が NULL かどうかを確認するには、`IS NULL` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-113">Use `IS NULL` to determine if the element of an outer join is null:</span></span>  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 <span data-ttu-id="d0d90-114">メンバーに実際の値が含まれているかどうかを確認するには、`IS NULL` を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-114">Use `IS NULL` to determine if a member has an actual value:</span></span>  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 <span data-ttu-id="d0d90-115">次の表は、いくつかのパターンにおける `IS NULL` の動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="d0d90-115">The following table shows the behavior of `IS NULL` over some patterns.</span></span> <span data-ttu-id="d0d90-116">すべての例外はクライアント側にスローされてから、プロバイダーが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d0d90-116">All exceptions are thrown from the client side before the provider gets invoked:</span></span>  
  
|<span data-ttu-id="d0d90-117">パターン</span><span class="sxs-lookup"><span data-stu-id="d0d90-117">Pattern</span></span>|<span data-ttu-id="d0d90-118">動作</span><span class="sxs-lookup"><span data-stu-id="d0d90-118">Behavior</span></span>|  
|-------------|--------------|  
|<span data-ttu-id="d0d90-119">null IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-119">null IS NULL</span></span>|<span data-ttu-id="d0d90-120">`true` を返します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-120">Returns `true`.</span></span>|  
|<span data-ttu-id="d0d90-121">TREAT (null AS EntityType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-121">TREAT (null AS EntityType) IS NULL</span></span>|<span data-ttu-id="d0d90-122">`true` を返します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-122">Returns `true`.</span></span>|  
|<span data-ttu-id="d0d90-123">TREAT (null AS ComplexType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-123">TREAT (null AS ComplexType) IS NULL</span></span>|<span data-ttu-id="d0d90-124">エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="d0d90-124">Throws an error.</span></span>|  
|<span data-ttu-id="d0d90-125">TREAT (null AS RowType) IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-125">TREAT (null AS RowType) IS NULL</span></span>|<span data-ttu-id="d0d90-126">エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="d0d90-126">Throws an error.</span></span>|  
|<span data-ttu-id="d0d90-127">EntityType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-127">EntityType IS NULL</span></span>|<span data-ttu-id="d0d90-128">`true` または `false`を返します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-128">Returns `true` or `false`.</span></span>|  
|<span data-ttu-id="d0d90-129">ComplexType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-129">ComplexType IS NULL</span></span>|<span data-ttu-id="d0d90-130">エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="d0d90-130">Throws an error.</span></span>|  
|<span data-ttu-id="d0d90-131">RowType IS NULL</span><span class="sxs-lookup"><span data-stu-id="d0d90-131">RowType IS NULL</span></span>|<span data-ttu-id="d0d90-132">エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="d0d90-132">Throws an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0d90-133">例</span><span class="sxs-lookup"><span data-stu-id="d0d90-133">Example</span></span>  

 <span data-ttu-id="d0d90-134">次の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリでは、IS NOT NULL 演算子を使用して、クエリ式が NULL でないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-134">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the IS NOT NULL operator to determine if a query expression is not null.</span></span> <span data-ttu-id="d0d90-135">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="d0d90-135">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d0d90-136">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-136">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d0d90-137">「[方法: StructuralType 結果を返すクエリを実行する](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d0d90-137">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d0d90-138">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="d0d90-138">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a><span data-ttu-id="d0d90-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0d90-139">See also</span></span>

- [<span data-ttu-id="d0d90-140">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="d0d90-140">Entity SQL Reference</span></span>](entity-sql-reference.md)
