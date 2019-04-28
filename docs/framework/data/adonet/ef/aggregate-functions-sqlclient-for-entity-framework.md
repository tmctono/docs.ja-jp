---
title: 集計関数 (Entity Framework 用 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: f2f2b557cd9f126ddd513a0f42d3ac95114c3822
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606780"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="fbbe0-102">集計関数 (Entity Framework 用 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="fbbe0-103">.NET Framework Data Provider for SQL Server (SqlClient) には、集計関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="fbbe0-104">集計関数は、一連の入力値に対して計算を実行し、値を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="fbbe0-105">これらの関数は、SqlClient の SqlServer 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="fbbe0-106">Entity Framework は、プロバイダーの名前空間プロパティを使用することにより、型や関数など、特定のコンストラクターに対してこのプロバイダーによってどのプレフィックスが使用されているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="fbbe0-107">SqlClient の集計関数を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="fbbe0-108">AVG(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-108">AVG(expression)</span></span>

<span data-ttu-id="fbbe0-109">コレクション内の値の平均値を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="fbbe0-110">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-110">Null values are ignored.</span></span>

<span data-ttu-id="fbbe0-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-111">**Arguments**</span></span>

<span data-ttu-id="fbbe0-112">`Int32`、 `Int64`、 `Double`、および`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="fbbe0-113">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-113">**Return Value**</span></span>

<span data-ttu-id="fbbe0-114">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-114">The type of `expression`.</span></span>

<span data-ttu-id="fbbe0-115">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksumaggcollection"></a><span data-ttu-id="fbbe0-116">CHECKSUM_AGG(collection)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="fbbe0-117">コレクション内にある値のチェックサムを返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="fbbe0-118">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="fbbe0-119">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-119">**Arguments**</span></span>
 
 <span data-ttu-id="fbbe0-120">コレクション (`Int32`)。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="fbbe0-121">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-121">**Return Value**</span></span>
 
 <span data-ttu-id="fbbe0-122">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-122">An `Int32`.</span></span>
 
 <span data-ttu-id="fbbe0-123">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="fbbe0-124">COUNT(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-124">COUNT(expression)</span></span>

<span data-ttu-id="fbbe0-125">コレクション内のアイテムの数を `Int32` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="fbbe0-126">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-126">**Arguments**</span></span>

<span data-ttu-id="fbbe0-127">コレクション\<T >、T は、次の種類のいずれか。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="fbbe0-128">`Guid` (SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="fbbe0-129">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-129">**Return Value**</span></span>

<span data-ttu-id="fbbe0-130">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-130">An `Int32`.</span></span>

<span data-ttu-id="fbbe0-131">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="fbbe0-132">[! コード sql[DP EntityServices 概念 #SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="countbigexpression"></a><span data-ttu-id="fbbe0-133">COUNT_BIG(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="fbbe0-134">コレクション内のアイテムの数を `bigint` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="fbbe0-135">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-135">**Arguments**</span></span>
 
 <span data-ttu-id="fbbe0-136">T は、次の種類のいずれかの Collection(T):</span><span class="sxs-lookup"><span data-stu-id="fbbe0-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="fbbe0-137">`Guid` (SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="fbbe0-138">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-138">**Return Value**</span></span>

<span data-ttu-id="fbbe0-139">`Int64`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-139">An `Int64`.</span></span>

<span data-ttu-id="fbbe0-140">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="fbbe0-141">MAX(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-141">MAX(expression)</span></span>

<span data-ttu-id="fbbe0-142">コレクション内の最大値を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="fbbe0-143">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-143">**Arguments**</span></span>

<span data-ttu-id="fbbe0-144">T は、次の種類のいずれかの Collection(T):</span><span class="sxs-lookup"><span data-stu-id="fbbe0-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="fbbe0-145">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-145">**Return Value**</span></span>

<span data-ttu-id="fbbe0-146">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-146">The type of `expression`.</span></span>

<span data-ttu-id="fbbe0-147">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="fbbe0-148">MIN(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-148">MIN(expression)</span></span>

<span data-ttu-id="fbbe0-149">コレクション内の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="fbbe0-150">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-150">**Arguments**</span></span>

<span data-ttu-id="fbbe0-151">T は、次の種類のいずれかの Collection(T):</span><span class="sxs-lookup"><span data-stu-id="fbbe0-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="fbbe0-152">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-152">**Return Value**</span></span>

<span data-ttu-id="fbbe0-153">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-153">The type of `expression`.</span></span>

<span data-ttu-id="fbbe0-154">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="fbbe0-155">STDEV(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-155">STDEV(expression)</span></span>

<span data-ttu-id="fbbe0-156">指定された式のすべての値の統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="fbbe0-157">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-157">**Arguments**</span></span>

<span data-ttu-id="fbbe0-158">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-158">A Collection(`Double`).</span></span>

<span data-ttu-id="fbbe0-159">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-159">**Return Value**</span></span>

<span data-ttu-id="fbbe0-160">`Double`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-160">A `Double`.</span></span>

<span data-ttu-id="fbbe0-161">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="fbbe0-162">STDEVP(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-162">STDEVP(expression)</span></span>

<span data-ttu-id="fbbe0-163">指定された式のすべての値を母集団として統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="fbbe0-164">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-164">**Arguments**</span></span>

<span data-ttu-id="fbbe0-165">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-165">A Collection(`Double`).</span></span>

<span data-ttu-id="fbbe0-166">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-166">**Return Value**</span></span>

<span data-ttu-id="fbbe0-167">`Double`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-167">A `Double`.</span></span>

<span data-ttu-id="fbbe0-168">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="fbbe0-169">SUM(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-169">SUM(expression)</span></span>

<span data-ttu-id="fbbe0-170">コレクション内のすべての値の合計を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="fbbe0-171">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-171">**Arguments**</span></span>

<span data-ttu-id="fbbe0-172">T は、次の種類のいずれかの Collection(T): `Int32`、 `Int64`、 `Double`、`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="fbbe0-173">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-173">**Return Value**</span></span>

<span data-ttu-id="fbbe0-174">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-174">The type of `expression`.</span></span>

<span data-ttu-id="fbbe0-175">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="fbbe0-176">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-176">VAR(expression)</span></span>

<span data-ttu-id="fbbe0-177">指定された式のすべての値の統計的分散を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="fbbe0-178">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-178">**Arguments**</span></span>

<span data-ttu-id="fbbe0-179">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-179">A Collection(`Double`).</span></span>

<span data-ttu-id="fbbe0-180">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-180">**Return Value**</span></span>

<span data-ttu-id="fbbe0-181">`Double`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-181">A `Double`.</span></span>

<span data-ttu-id="fbbe0-182">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="fbbe0-183">VARP(expression)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-183">VARP(expression)</span></span>

<span data-ttu-id="fbbe0-184">指定した式のすべての値について、母集団に対する統計的変位を返します。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="fbbe0-185">**引数**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-185">**Arguments**</span></span>

<span data-ttu-id="fbbe0-186">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-186">A Collection(`Double`).</span></span>

<span data-ttu-id="fbbe0-187">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-187">**Return Value**</span></span>

<span data-ttu-id="fbbe0-188">`Double`。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-188">A `Double`.</span></span>

<span data-ttu-id="fbbe0-189">**例**</span><span class="sxs-lookup"><span data-stu-id="fbbe0-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="fbbe0-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbbe0-190">See also</span></span>

<span data-ttu-id="fbbe0-191">SqlClient でサポートされる集計関数の詳細については、SqlClient プロバイダー マニフェストで指定した SQL Server のバージョンのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbbe0-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="fbbe0-192">**SQL Server 2005:**[集計関数 (TRANSACT-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="fbbe0-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="fbbe0-193">**SQL Server 2008 以降:**[集計関数 (TRANSACT-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="fbbe0-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="fbbe0-194">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="fbbe0-194">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [<span data-ttu-id="fbbe0-195">集計正規関数</span><span class="sxs-lookup"><span data-stu-id="fbbe0-195">Aggregate Canonical Functions</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
