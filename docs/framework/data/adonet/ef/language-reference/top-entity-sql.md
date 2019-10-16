---
title: TOP (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
ms.openlocfilehash: 16be25336bac386c993eae7527c9377be1073d1e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319274"
---
# <a name="top-entity-sql"></a><span data-ttu-id="a52b6-102">TOP (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a52b6-102">TOP (Entity SQL)</span></span>

<span data-ttu-id="a52b6-103">SELECT 句には、オプションの ALL/DISTINCT 修飾子に続けてオプションの TOP サブ句を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a52b6-103">The SELECT clause can have an optional TOP sub-clause following the optional ALL/DISTINCT modifier.</span></span> <span data-ttu-id="a52b6-104">TOP サブ句は、クエリ結果の先頭から指定した行セットだけを返すよう指定します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-104">The TOP sub-clause specifies that only the first set of rows will be returned from the query result.</span></span>

## <a name="syntax"></a><span data-ttu-id="a52b6-105">構文</span><span class="sxs-lookup"><span data-stu-id="a52b6-105">Syntax</span></span>

```sql
[ TOP (n) ]
```

## <a name="arguments"></a><span data-ttu-id="a52b6-106">引数</span><span class="sxs-lookup"><span data-stu-id="a52b6-106">Arguments</span></span>

<span data-ttu-id="a52b6-107">`n` 返される行の数を指定する数値式。</span><span class="sxs-lookup"><span data-stu-id="a52b6-107">`n` The numeric expression that specifies the number of rows to be returned.</span></span> <span data-ttu-id="a52b6-108">`n` は単一の数値リテラルかまたは単一のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a52b6-108">`n` could be a single numeric literal or a single parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="a52b6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="a52b6-109">Remarks</span></span>

<span data-ttu-id="a52b6-110">TOP 式には、単一の数値リテラルまたは単一のパラメーターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="a52b6-110">The TOP expression must be either a single numeric literal or a single parameter.</span></span> <span data-ttu-id="a52b6-111">定数リテラルを使用する場合は、リテラルの種類を Edm.Int64 (byte、int16、int32、int64、または Edm.Int64 に昇格可能な型にマップされる任意のプロバイダー型) に暗黙的に昇格でき、その値が 0 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a52b6-111">If a constant literal is used, the literal type must be implicitly promotable to Edm.Int64 (byte, int16, int32 or int64 or any provider type that maps to a type that is promotable to Edm.Int64) and its value must be greater than or equal to zero.</span></span> <span data-ttu-id="a52b6-112">それ以外の場合は、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-112">Otherwise an exception will be raised.</span></span> <span data-ttu-id="a52b6-113">パラメーターを式として使用する場合は、パラメーター型も Edm.Int64 に暗黙的に昇格できる必要がありますが、パラメーター値は遅延バインドされるため、コンパイル時に実際のパラメーター値は検証されません。</span><span class="sxs-lookup"><span data-stu-id="a52b6-113">If a parameter is used as an expression, the parameter type must also be implicitly promotable to Edm.Int64, but there will be no validation of the actual parameter value during compilation because the parameter values are late bounded.</span></span>

<span data-ttu-id="a52b6-114">定数 TOP 式の例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-114">The following is an example of constant TOP expression:</span></span>

```sql
select distinct top(10) c.a1, c.a2 from T as a
```

<span data-ttu-id="a52b6-115">パラメーター化された TOP 式の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-115">The following is an example of parameterized TOP expression:</span></span>

```sql
select distinct top(@topParam) c.a1, c.a2 from T as a
```

<span data-ttu-id="a52b6-116">TOP は、クエリが並べ替えられていない限り、非決定的です。</span><span class="sxs-lookup"><span data-stu-id="a52b6-116">TOP is non-deterministic unless the query is sorted.</span></span> <span data-ttu-id="a52b6-117">確定的な結果が必要な場合は、 [ORDER BY](skip-entity-sql.md) 句の [SKIP](limit-entity-sql.md) サブ句および [LIMIT](order-by-entity-sql.md) サブ句を使用します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-117">If you require a deterministic result, use the [SKIP](skip-entity-sql.md) and [LIMIT](limit-entity-sql.md) sub-clauses in the [ORDER BY](order-by-entity-sql.md) clause.</span></span> <span data-ttu-id="a52b6-118">TOP     SKIP/LIMIT</span><span class="sxs-lookup"><span data-stu-id="a52b6-118">The TOP and SKIP/LIMIT are mutually exclusive.</span></span>

## <a name="example"></a><span data-ttu-id="a52b6-119">例</span><span class="sxs-lookup"><span data-stu-id="a52b6-119">Example</span></span>

<span data-ttu-id="a52b6-120">次の [!INCLUDE[esql](../../../../../../includes/esql-md.md)] クエリは、TOP を使用して、クエリ結果から返される 1 番上の 1 行を指定します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-120">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the TOP to specify the top one row to be returned from the query result.</span></span> <span data-ttu-id="a52b6-121">このクエリは、AdventureWorks Sales Model に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a52b6-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a52b6-122">このクエリをコンパイルして実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-122">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="a52b6-123">「 [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a52b6-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="a52b6-124">次のクエリを引数として `ExecuteStructuralTypeQuery` メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="a52b6-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

    [!code-sql[DP EntityServices Concepts#TOP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#top)]

## <a name="see-also"></a><span data-ttu-id="a52b6-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a52b6-125">See also</span></span>

- [<span data-ttu-id="a52b6-126">SELECT</span><span class="sxs-lookup"><span data-stu-id="a52b6-126">SELECT</span></span>](select-entity-sql.md)
- [<span data-ttu-id="a52b6-127">SKIP</span><span class="sxs-lookup"><span data-stu-id="a52b6-127">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="a52b6-128">LIMIT</span><span class="sxs-lookup"><span data-stu-id="a52b6-128">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="a52b6-129">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="a52b6-129">ORDER BY</span></span>](order-by-entity-sql.md)
- [<span data-ttu-id="a52b6-130">Entity SQL リファレンス</span><span class="sxs-lookup"><span data-stu-id="a52b6-130">Entity SQL Reference</span></span>](entity-sql-reference.md)
