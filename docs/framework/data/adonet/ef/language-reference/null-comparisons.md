---
title: NULL 比較
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 0996b7d864c5892e383cb98d4065e99b096206d1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854334"
---
# <a name="null-comparisons"></a><span data-ttu-id="d8328-102">NULL 比較</span><span class="sxs-lookup"><span data-stu-id="d8328-102">Null Comparisons</span></span>
<span data-ttu-id="d8328-103">データ ソースの `null` 値は不明な値を表します。</span><span class="sxs-lookup"><span data-stu-id="d8328-103">A `null` value in the data source indicates that the value is unknown.</span></span> <span data-ttu-id="d8328-104">LINQ to Entities のクエリでは、null 値をチェックして、特定の計算または比較が、有効な、または null 以外のデータを含む行に対してのみ実行されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8328-104">In LINQ to Entities queries, you can check for null values so that certain calculations or comparisons are only performed on rows that have valid, or non-null, data.</span></span> <span data-ttu-id="d8328-105">ただし、CLR の NULL セマンティクスは、データ ソースの NULL セマンティクスとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8328-105">CLR null semantics, however, may differ from the null semantics of the data source.</span></span> <span data-ttu-id="d8328-106">ほとんどのデータベースでは、3 値論理を使用して NULL 比較を処理します。</span><span class="sxs-lookup"><span data-stu-id="d8328-106">Most databases use a version of three-valued logic to handle null comparisons.</span></span> <span data-ttu-id="d8328-107">つまり、null 値に対する比較はまたはに`true`評価されず、と`false`評価`unknown`されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-107">That is, a comparison against a null value does not evaluate to `true` or `false`, it evaluates to `unknown`.</span></span> <span data-ttu-id="d8328-108">これは、多くの場合は ANSI NULL の実装ですが、そうでない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d8328-108">Often this is an implementation of ANSI nulls, but this is not always the case.</span></span>  
  
 <span data-ttu-id="d8328-109">SQL Server の既定では、NULL = NULL の比較は NULL 値を返します。</span><span class="sxs-lookup"><span data-stu-id="d8328-109">By default in SQL Server, the null-equals-null comparison returns a null value.</span></span> <span data-ttu-id="d8328-110">次の例で`ShipDate`は、が null の行が結果セットから除外され、transact-sql ステートメントが0行を返します。</span><span class="sxs-lookup"><span data-stu-id="d8328-110">In the following example, the rows where `ShipDate` is null are excluded from the result set, and the Transact-SQL statement would return 0 rows.</span></span>  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 <span data-ttu-id="d8328-111">これは、NULL = NULL の比較が true を返す CLR の NULL セマンティクスとは大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="d8328-111">This is very different from the CLR null semantics, where the null-equals-null comparison returns true.</span></span>  
  
 <span data-ttu-id="d8328-112">次の LINQ クエリは CLR で表されますが、データ ソースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-112">The following LINQ query is expressed in the CLR, but it is executed in the data source.</span></span> <span data-ttu-id="d8328-113">CLR セマンティクスがデータ ソースで使用される保証はないため、動作は予測できません。</span><span class="sxs-lookup"><span data-stu-id="d8328-113">Because there is no guarantee that CLR semantics will be honored at the data source, the expected behavior is indeterminate.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a><span data-ttu-id="d8328-114">キー セレクター</span><span class="sxs-lookup"><span data-stu-id="d8328-114">Key Selectors</span></span>  
 <span data-ttu-id="d8328-115">*キーセレクター*は、要素からキーを抽出するために標準クエリ演算子で使用される関数です。</span><span class="sxs-lookup"><span data-stu-id="d8328-115">A *key selector* is a function used in the standard query operators to extract a key from an element.</span></span> <span data-ttu-id="d8328-116">キー セレクター関数では、式を定数と比較できます。</span><span class="sxs-lookup"><span data-stu-id="d8328-116">In the key selector function, an expression can be compared with a constant.</span></span> <span data-ttu-id="d8328-117">式が NULL 定数と比較される場合、または 2 つの NULL 定数が比較される場合、CLR の NULL セマンティクスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-117">CLR null semantics are exhibited if an expression is compared to a null constant or if two null constants are compared.</span></span> <span data-ttu-id="d8328-118">データ ソースの NULL 値を持つ 2 つの列が比較される場合は、ストア NULL セマンティクスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-118">Store null semantics are exhibited if two columns with null values in the data source are compared.</span></span> <span data-ttu-id="d8328-119">キー セレクターは、<xref:System.Linq.Queryable.GroupBy%2A> など、グループ化や並べ替えの標準クエリ演算子で使用される場合が多く、クエリ結果の並べ替えやグループ化に使用するキーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8328-119">Key selectors are found in many of the grouping and ordering standard query operators, such as <xref:System.Linq.Queryable.GroupBy%2A>, and are used to select keys by which to order or group the query results.</span></span>  
  
## <a name="null-property-on-a-null-object"></a><span data-ttu-id="d8328-120">NULL オブジェクトの NULL プロパティ</span><span class="sxs-lookup"><span data-stu-id="d8328-120">Null Property on a Null Object</span></span>  
 <span data-ttu-id="d8328-121">Entity Framework では、null オブジェクトのプロパティは null です。</span><span class="sxs-lookup"><span data-stu-id="d8328-121">In the Entity Framework, the properties of a null object are null.</span></span> <span data-ttu-id="d8328-122">CLR で NULL オブジェクトのプロパティを参照しようとすると、<xref:System.NullReferenceException> が返されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-122">When you attempt to reference a property of a null object in the CLR, you will receive a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="d8328-123">LINQ クエリに NULL オブジェクトのプロパティが含まれている場合、動作の一貫性が失われることがあります。</span><span class="sxs-lookup"><span data-stu-id="d8328-123">When a LINQ query involves a property of a null object, this can result in inconsistent behavior.</span></span>  
  
 <span data-ttu-id="d8328-124">たとえば、次のクエリでは、`NewProduct` へのキャストはコマンド ツリー レイヤーで行われ、`Introduced` プロパティが NULL になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d8328-124">For example, in the following query, the cast to `NewProduct` is done in the command tree layer, which might result in the `Introduced` property being null.</span></span> <span data-ttu-id="d8328-125"><xref:System.DateTime> の比較が true に評価されるように NULL 比較がデータベースで定義されている場合に、その行が含められます。</span><span class="sxs-lookup"><span data-stu-id="d8328-125">If the database defined null comparisons such that the <xref:System.DateTime> comparison evaluates to true, the row will be included.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a><span data-ttu-id="d8328-126">集計関数に NULL コレクションを渡す</span><span class="sxs-lookup"><span data-stu-id="d8328-126">Passing Null Collections to Aggregate Functions</span></span>  
 <span data-ttu-id="d8328-127">LINQ to Entities では、をサポート`IQueryable`するコレクションを集計関数に渡すと、集計操作がデータベースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-127">In LINQ to Entities, when you pass a collection that supports `IQueryable` to an aggregate function, aggregate operations are performed at the database.</span></span> <span data-ttu-id="d8328-128">メモリ内で実行されたクエリの結果と、データベースで実行されたクエリの結果が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d8328-128">There might be differences in the results of a query that was performed in-memory and a query that was performed at the database.</span></span> <span data-ttu-id="d8328-129">メモリ内クエリで一致するものがない場合、クエリは0を返します。</span><span class="sxs-lookup"><span data-stu-id="d8328-129">With an in-memory query, if there are no matches, the query returns zero.</span></span> <span data-ttu-id="d8328-130">データベースでは、これと同じクエリから `null` が返されます。</span><span class="sxs-lookup"><span data-stu-id="d8328-130">At the database, the same query returns `null`.</span></span> <span data-ttu-id="d8328-131">LINQ 集計関数に値が渡されると、例外がスローされます。`null`</span><span class="sxs-lookup"><span data-stu-id="d8328-131">If a `null` value is passed to a LINQ aggregate function, an exception will be thrown.</span></span> <span data-ttu-id="d8328-132">使用可能な`null`値を受け入れるには、クエリ結果を受け取る型の型とプロパティを null 許容型にキャストします。</span><span class="sxs-lookup"><span data-stu-id="d8328-132">To accept possible `null` values, cast the types and the properties of the types that receive query results to nullable types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8328-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8328-133">See also</span></span>

- [<span data-ttu-id="d8328-134">LINQ to Entities クエリ内の式</span><span class="sxs-lookup"><span data-stu-id="d8328-134">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
