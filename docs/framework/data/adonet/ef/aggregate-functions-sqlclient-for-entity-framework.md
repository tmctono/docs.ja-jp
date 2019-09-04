---
title: 集計関数 (Entity Framework 用 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: cf476192cf049f230c1956e390d215ad4abaa821
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251704"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="d3c85-102">集計関数 (Entity Framework 用 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="d3c85-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="d3c85-103">.NET Framework Data Provider for SQL Server (SqlClient) には、集計関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d3c85-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="d3c85-104">集計関数は、一連の入力値に対して計算を実行し、値を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="d3c85-105">これらの関数は、SqlClient の SqlServer 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="d3c85-106">Entity Framework は、プロバイダーの名前空間プロパティを使用することにより、型や関数など、特定のコンストラクターに対してこのプロバイダーによってどのプレフィックスが使用されているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="d3c85-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="d3c85-107">次に、SqlClient 集計関数を示します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="d3c85-108">AVG (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-108">AVG(expression)</span></span>

<span data-ttu-id="d3c85-109">コレクション内の値の平均値を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="d3c85-110">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d3c85-110">Null values are ignored.</span></span>

<span data-ttu-id="d3c85-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-111">**Arguments**</span></span>

<span data-ttu-id="d3c85-112">、、、および`Decimal`。 `Int32` `Int64` `Double`</span><span class="sxs-lookup"><span data-stu-id="d3c85-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="d3c85-113">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-113">**Return Value**</span></span>

<span data-ttu-id="d3c85-114">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="d3c85-114">The type of `expression`.</span></span>

<span data-ttu-id="d3c85-115">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-115">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="d3c85-116">CHECKSUM_AGG (コレクション)</span><span class="sxs-lookup"><span data-stu-id="d3c85-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="d3c85-117">コレクション内にある値のチェックサムを返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="d3c85-118">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d3c85-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="d3c85-119">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-119">**Arguments**</span></span>
 
 <span data-ttu-id="d3c85-120">コレクション (`Int32`)。</span><span class="sxs-lookup"><span data-stu-id="d3c85-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="d3c85-121">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-121">**Return Value**</span></span>
 
 <span data-ttu-id="d3c85-122">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-122">An `Int32`.</span></span>
 
 <span data-ttu-id="d3c85-123">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-123">**Example**</span></span>
 
 [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="d3c85-124">COUNT (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-124">COUNT(expression)</span></span>

<span data-ttu-id="d3c85-125">コレクション内のアイテムの数を `Int32` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="d3c85-126">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-126">**Arguments**</span></span>

<span data-ttu-id="d3c85-127">コレクション\<t >。ここで、t は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="d3c85-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="d3c85-128">`Guid`(SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="d3c85-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="d3c85-129">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-129">**Return Value**</span></span>

<span data-ttu-id="d3c85-130">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-130">An `Int32`.</span></span>

<span data-ttu-id="d3c85-131">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-131">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
<span data-ttu-id="d3c85-132">[! コード-sql[DP EntityServices の概念 # SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span><span class="sxs-lookup"><span data-stu-id="d3c85-132">[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)</span></span>
 
## <a name="count_bigexpression"></a><span data-ttu-id="d3c85-133">COUNT_BIG (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-133">COUNT_BIG(expression)</span></span>
 
 <span data-ttu-id="d3c85-134">コレクション内のアイテムの数を `bigint` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-134">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="d3c85-135">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-135">**Arguments**</span></span>
 
 <span data-ttu-id="d3c85-136">Collection (T)。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="d3c85-136">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="d3c85-137">`Guid`(SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="d3c85-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="d3c85-138">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-138">**Return Value**</span></span>

<span data-ttu-id="d3c85-139">`Int64`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-139">An `Int64`.</span></span>

<span data-ttu-id="d3c85-140">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-140">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="d3c85-141">MAX (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-141">MAX(expression)</span></span>

<span data-ttu-id="d3c85-142">コレクション内の最大値を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="d3c85-143">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-143">**Arguments**</span></span>

<span data-ttu-id="d3c85-144">Collection (T)。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="d3c85-144">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="d3c85-145">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-145">**Return Value**</span></span>

<span data-ttu-id="d3c85-146">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="d3c85-146">The type of `expression`.</span></span>

<span data-ttu-id="d3c85-147">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-147">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="d3c85-148">MIN (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-148">MIN(expression)</span></span>

<span data-ttu-id="d3c85-149">コレクション内の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="d3c85-150">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-150">**Arguments**</span></span>

<span data-ttu-id="d3c85-151">Collection (T)。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="d3c85-151">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="d3c85-152">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-152">**Return Value**</span></span>

<span data-ttu-id="d3c85-153">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="d3c85-153">The type of `expression`.</span></span>

<span data-ttu-id="d3c85-154">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-154">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="d3c85-155">STDEV (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-155">STDEV(expression)</span></span>

<span data-ttu-id="d3c85-156">指定された式のすべての値の統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="d3c85-157">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-157">**Arguments**</span></span>

<span data-ttu-id="d3c85-158">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="d3c85-158">A Collection(`Double`).</span></span>

<span data-ttu-id="d3c85-159">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-159">**Return Value**</span></span>

<span data-ttu-id="d3c85-160">`Double`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-160">A `Double`.</span></span>

<span data-ttu-id="d3c85-161">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-161">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="d3c85-162">STDEVP (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-162">STDEVP(expression)</span></span>

<span data-ttu-id="d3c85-163">指定された式のすべての値を母集団として統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="d3c85-164">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-164">**Arguments**</span></span>

<span data-ttu-id="d3c85-165">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="d3c85-165">A Collection(`Double`).</span></span>

<span data-ttu-id="d3c85-166">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-166">**Return Value**</span></span>

<span data-ttu-id="d3c85-167">`Double`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-167">A `Double`.</span></span>

<span data-ttu-id="d3c85-168">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-168">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="d3c85-169">SUM (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-169">SUM(expression)</span></span>

<span data-ttu-id="d3c85-170">コレクション内のすべての値の合計を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="d3c85-171">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-171">**Arguments**</span></span>

<span data-ttu-id="d3c85-172">Collection (T) `Int32`。ここ`Double`で、t は、 `Int64`、、、 `Decimal`のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="d3c85-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="d3c85-173">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-173">**Return Value**</span></span>

<span data-ttu-id="d3c85-174">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="d3c85-174">The type of `expression`.</span></span>

<span data-ttu-id="d3c85-175">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-175">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="d3c85-176">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="d3c85-176">VAR(expression)</span></span>

<span data-ttu-id="d3c85-177">指定された式のすべての値の統計的分散を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="d3c85-178">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-178">**Arguments**</span></span>

<span data-ttu-id="d3c85-179">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="d3c85-179">A Collection(`Double`).</span></span>

<span data-ttu-id="d3c85-180">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-180">**Return Value**</span></span>

<span data-ttu-id="d3c85-181">`Double`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-181">A `Double`.</span></span>

<span data-ttu-id="d3c85-182">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-182">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="d3c85-183">VARP (式)</span><span class="sxs-lookup"><span data-stu-id="d3c85-183">VARP(expression)</span></span>

<span data-ttu-id="d3c85-184">指定した式のすべての値について、母集団に対する統計的変位を返します。</span><span class="sxs-lookup"><span data-stu-id="d3c85-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="d3c85-185">**引数**</span><span class="sxs-lookup"><span data-stu-id="d3c85-185">**Arguments**</span></span>

<span data-ttu-id="d3c85-186">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="d3c85-186">A Collection(`Double`).</span></span>

<span data-ttu-id="d3c85-187">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="d3c85-187">**Return Value**</span></span>

<span data-ttu-id="d3c85-188">`Double`。</span><span class="sxs-lookup"><span data-stu-id="d3c85-188">A `Double`.</span></span>

<span data-ttu-id="d3c85-189">**例**</span><span class="sxs-lookup"><span data-stu-id="d3c85-189">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="d3c85-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3c85-190">See also</span></span>

<span data-ttu-id="d3c85-191">SqlClient でサポートされる集計関数の詳細については、SqlClient プロバイダー マニフェストで指定した SQL Server のバージョンのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c85-191">For more information about the aggregate functions that SqlClient supports, see the documentation for the SQL Server version that you specified in the SqlClient provider manifest:</span></span>

- <span data-ttu-id="d3c85-192">**SQL Server 2005:** [集計関数 (Transact-sql)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="d3c85-192">**SQL Server 2005:** [Aggregate Functions (Transact-SQL)](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms173454(v=sql.90))</span></span>
- <span data-ttu-id="d3c85-193">**SQL Server 2008 以降:** [集計関数 (Transact-sql)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="d3c85-193">**SQL Server 2008 and later:** [Aggregate Functions (Transact-SQL)](/sql/t-sql/functions/aggregate-functions-transact-sql)</span></span>

- [<span data-ttu-id="d3c85-194">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="d3c85-194">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="d3c85-195">集計正規関数</span><span class="sxs-lookup"><span data-stu-id="d3c85-195">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
