---
title: 集計関数 (Entity Framework 用 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150650"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="161d5-102">集計関数 (Entity Framework 用 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="161d5-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="161d5-103">.NET Framework Data Provider for SQL Server (SqlClient) には、集計関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="161d5-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="161d5-104">集計関数は、一連の入力値に対して計算を実行し、値を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="161d5-105">これらの関数は、SqlClient の SqlServer 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="161d5-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="161d5-106">Entity Framework は、プロバイダーの名前空間プロパティを使用することにより、型や関数など、特定のコンストラクターに対してこのプロバイダーによってどのプレフィックスが使用されているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="161d5-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="161d5-107">以下は、SqlClient の集計関数です。</span><span class="sxs-lookup"><span data-stu-id="161d5-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="161d5-108">AVG(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-108">AVG(expression)</span></span>

<span data-ttu-id="161d5-109">コレクション内の値の平均値を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="161d5-110">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="161d5-110">Null values are ignored.</span></span>

<span data-ttu-id="161d5-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-111">**Arguments**</span></span>

<span data-ttu-id="161d5-112">`Int32`、`Int64`、`Double`、および `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="161d5-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="161d5-113">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-113">**Return Value**</span></span>

<span data-ttu-id="161d5-114">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="161d5-114">The type of `expression`.</span></span>

<span data-ttu-id="161d5-115">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="161d5-116">CHECKSUM_AGG(collection)</span><span class="sxs-lookup"><span data-stu-id="161d5-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="161d5-117">コレクション内にある値のチェックサムを返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="161d5-118">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="161d5-118">Null values are ignored.</span></span>

 <span data-ttu-id="161d5-119">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-119">**Arguments**</span></span>

 <span data-ttu-id="161d5-120">Collection(`Int32`)。</span><span class="sxs-lookup"><span data-stu-id="161d5-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="161d5-121">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-121">**Return Value**</span></span>

 <span data-ttu-id="161d5-122">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="161d5-122">An `Int32`.</span></span>

 <span data-ttu-id="161d5-123">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="161d5-124">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-124">COUNT(expression)</span></span>

<span data-ttu-id="161d5-125">コレクション内のアイテムの数を `Int32` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="161d5-126">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-126">**Arguments**</span></span>

<span data-ttu-id="161d5-127">Collection\<T>。T は次のいずれかの型です。</span><span class="sxs-lookup"><span data-stu-id="161d5-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="161d5-128">`Guid` (SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="161d5-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="161d5-129">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-129">**Return Value**</span></span>

<span data-ttu-id="161d5-130">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="161d5-130">An `Int32`.</span></span>

<span data-ttu-id="161d5-131">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="161d5-132">COUNT_BIG(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="161d5-133">コレクション内のアイテムの数を `bigint` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="161d5-134">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-134">**Arguments**</span></span>

 <span data-ttu-id="161d5-135">Collection(T)。T は次のいずれかの型です。</span><span class="sxs-lookup"><span data-stu-id="161d5-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="161d5-136">`Guid` (SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="161d5-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="161d5-137">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-137">**Return Value**</span></span>

<span data-ttu-id="161d5-138">`Int64`。</span><span class="sxs-lookup"><span data-stu-id="161d5-138">An `Int64`.</span></span>

<span data-ttu-id="161d5-139">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="161d5-140">MAX(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-140">MAX(expression)</span></span>

<span data-ttu-id="161d5-141">コレクション内の最大値を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="161d5-142">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-142">**Arguments**</span></span>

<span data-ttu-id="161d5-143">Collection(T)。T は次のいずれかの型です。</span><span class="sxs-lookup"><span data-stu-id="161d5-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="161d5-144">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-144">**Return Value**</span></span>

<span data-ttu-id="161d5-145">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="161d5-145">The type of `expression`.</span></span>

<span data-ttu-id="161d5-146">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="161d5-147">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-147">MIN(expression)</span></span>

<span data-ttu-id="161d5-148">コレクション内の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="161d5-149">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-149">**Arguments**</span></span>

<span data-ttu-id="161d5-150">Collection(T)。T は次のいずれかの型です。</span><span class="sxs-lookup"><span data-stu-id="161d5-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="161d5-151">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-151">**Return Value**</span></span>

<span data-ttu-id="161d5-152">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="161d5-152">The type of `expression`.</span></span>

<span data-ttu-id="161d5-153">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="161d5-154">STDEV(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-154">STDEV(expression)</span></span>

<span data-ttu-id="161d5-155">指定された式のすべての値の統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="161d5-156">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-156">**Arguments**</span></span>

<span data-ttu-id="161d5-157">Collection(`Double`)。</span><span class="sxs-lookup"><span data-stu-id="161d5-157">A Collection(`Double`).</span></span>

<span data-ttu-id="161d5-158">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-158">**Return Value**</span></span>

<span data-ttu-id="161d5-159">`Double`。</span><span class="sxs-lookup"><span data-stu-id="161d5-159">A `Double`.</span></span>

<span data-ttu-id="161d5-160">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="161d5-161">STDEVP(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-161">STDEVP(expression)</span></span>

<span data-ttu-id="161d5-162">指定された式のすべての値を母集団として統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="161d5-163">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-163">**Arguments**</span></span>

<span data-ttu-id="161d5-164">Collection(`Double`)。</span><span class="sxs-lookup"><span data-stu-id="161d5-164">A Collection(`Double`).</span></span>

<span data-ttu-id="161d5-165">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-165">**Return Value**</span></span>

<span data-ttu-id="161d5-166">`Double`。</span><span class="sxs-lookup"><span data-stu-id="161d5-166">A `Double`.</span></span>

<span data-ttu-id="161d5-167">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="161d5-168">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-168">SUM(expression)</span></span>

<span data-ttu-id="161d5-169">コレクション内のすべての値の合計を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="161d5-170">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-170">**Arguments**</span></span>

<span data-ttu-id="161d5-171">Collection(T)。T は次のいずれかの型です: `Int32`、`Int64`、`Double`、`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="161d5-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="161d5-172">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-172">**Return Value**</span></span>

<span data-ttu-id="161d5-173">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="161d5-173">The type of `expression`.</span></span>

<span data-ttu-id="161d5-174">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="161d5-175">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-175">VAR(expression)</span></span>

<span data-ttu-id="161d5-176">指定された式のすべての値の統計的分散を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="161d5-177">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-177">**Arguments**</span></span>

<span data-ttu-id="161d5-178">Collection(`Double`)。</span><span class="sxs-lookup"><span data-stu-id="161d5-178">A Collection(`Double`).</span></span>

<span data-ttu-id="161d5-179">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-179">**Return Value**</span></span>

<span data-ttu-id="161d5-180">`Double`。</span><span class="sxs-lookup"><span data-stu-id="161d5-180">A `Double`.</span></span>

<span data-ttu-id="161d5-181">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="161d5-182">VARP(expression)</span><span class="sxs-lookup"><span data-stu-id="161d5-182">VARP(expression)</span></span>

<span data-ttu-id="161d5-183">指定した式のすべての値について、母集団に対する統計的変位を返します。</span><span class="sxs-lookup"><span data-stu-id="161d5-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="161d5-184">**引数**</span><span class="sxs-lookup"><span data-stu-id="161d5-184">**Arguments**</span></span>

<span data-ttu-id="161d5-185">Collection(`Double`)。</span><span class="sxs-lookup"><span data-stu-id="161d5-185">A Collection(`Double`).</span></span>

<span data-ttu-id="161d5-186">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="161d5-186">**Return Value**</span></span>

<span data-ttu-id="161d5-187">`Double`。</span><span class="sxs-lookup"><span data-stu-id="161d5-187">A `Double`.</span></span>

<span data-ttu-id="161d5-188">**例**</span><span class="sxs-lookup"><span data-stu-id="161d5-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="161d5-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="161d5-189">See also</span></span>

- [<span data-ttu-id="161d5-190">集計関数 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="161d5-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="161d5-191">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="161d5-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="161d5-192">集計正規関数</span><span class="sxs-lookup"><span data-stu-id="161d5-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
