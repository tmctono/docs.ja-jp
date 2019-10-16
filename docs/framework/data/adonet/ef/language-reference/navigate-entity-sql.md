---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319553"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="7e5fe-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="7e5fe-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="7e5fe-103">エンティティ間で確立されたリレーションシップをナビゲートします。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e5fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="7e5fe-104">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="7e5fe-105">引数</span><span class="sxs-lookup"><span data-stu-id="7e5fe-105">Arguments</span></span>

<span data-ttu-id="7e5fe-106">`instance-expression` エンティティのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="7e5fe-107">`relationship-type` 概念スキーマ定義言語 (CSDL) ファイルからのリレーションシップの型名。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="7e5fe-108">@No__t-0 は \< 名前空間 > として修飾されています。 \<relationship 型名 >。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="7e5fe-109">`to` リレーションシップの終了。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="7e5fe-110">`from` リレーションシップの先頭。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="7e5fe-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="7e5fe-111">Return Value</span></span>

<span data-ttu-id="7e5fe-112">終端のカーディナリティが 1 の場合、戻り値は `Ref<T>` になります。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="7e5fe-113">終端のカーディナリティが n の場合、戻り値は `Collection<Ref<T>>` になります。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e5fe-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="7e5fe-114">Remarks</span></span>

<span data-ttu-id="7e5fe-115">リレーションシップは、Entity Data Model (EDM) のファーストクラスの構造体です。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-115">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="7e5fe-116">リレーションシップは、複数のエンティティ型の間で確立され、ユーザーはエンティティ間のリレーションシップをナビゲートできます。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="7e5fe-117">`from` と `to` は、リレーションシップ内の名前解決があいまいでない場合の条件付きのオプションです。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="7e5fe-118">NAVIGATE は、O および C 空間で有効です。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="7e5fe-119">ナビゲーション構造の一般的な形式は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="7e5fe-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="7e5fe-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="7e5fe-121">(例:</span><span class="sxs-lookup"><span data-stu-id="7e5fe-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="7e5fe-122">ここで、OrderCustomer は `relationship`であり、Customer と Order はリレーションシップの `to-end` (顧客) と `from-end` (注文) です。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="7e5fe-123">OrderCustomer が n:1 のリレーションシップである場合、navigate 式の結果の型は Ref @ no__t-0Customer > になります。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="7e5fe-124">この式をより簡略化すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="7e5fe-125">同様に、次の形式のクエリでは、navigate 式によって < Ref @ no__t-0Order > > のコレクションが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="7e5fe-126">インスタンス式は、エンティティ/参照型になる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="7e5fe-127">例</span><span class="sxs-lookup"><span data-stu-id="7e5fe-127">Example</span></span>

<span data-ttu-id="7e5fe-128">次の Entity SQL クエリでは、NAVIGATE 演算子を使用して、Address エンティティ型と SalesOrderHeader エンティティ型間で確立されたリレーションシップをナビゲートします。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="7e5fe-129">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="7e5fe-130">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="7e5fe-131">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="7e5fe-132">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="7e5fe-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e5fe-133">See also</span></span>

- [<span data-ttu-id="7e5fe-134">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="7e5fe-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="7e5fe-135">Navigate 演算子を使用してリレーションシップをナビゲートする方法</span><span class="sxs-lookup"><span data-stu-id="7e5fe-135">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
