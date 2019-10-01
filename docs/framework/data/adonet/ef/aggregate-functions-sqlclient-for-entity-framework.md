---
title: 集計関数 (Entity Framework 用 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 3dbd4c0a24a5fc41153ea16747325e824669b0e5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700054"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="342e8-102">集計関数 (Entity Framework 用 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="342e8-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="342e8-103">.NET Framework Data Provider for SQL Server (SqlClient) には、集計関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="342e8-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="342e8-104">集計関数は、一連の入力値に対して計算を実行し、値を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="342e8-105">これらの関数は、SqlClient の SqlServer 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="342e8-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="342e8-106">Entity Framework は、プロバイダーの名前空間プロパティを使用することにより、型や関数など、特定のコンストラクターに対してこのプロバイダーによってどのプレフィックスが使用されているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="342e8-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="342e8-107">次に、SqlClient 集計関数を示します。</span><span class="sxs-lookup"><span data-stu-id="342e8-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="342e8-108">AVG (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-108">AVG(expression)</span></span>

<span data-ttu-id="342e8-109">コレクション内の値の平均値を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="342e8-110">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="342e8-110">Null values are ignored.</span></span>

<span data-ttu-id="342e8-111">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-111">**Arguments**</span></span>

<span data-ttu-id="342e8-112">@No__t-0、`Int64`、`Double`、および `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="342e8-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="342e8-113">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-113">**Return Value**</span></span>

<span data-ttu-id="342e8-114">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="342e8-114">The type of `expression`.</span></span>

<span data-ttu-id="342e8-115">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="342e8-116">CHECKSUM_AGG (コレクション)</span><span class="sxs-lookup"><span data-stu-id="342e8-116">CHECKSUM_AGG(collection)</span></span>
 
 <span data-ttu-id="342e8-117">コレクション内にある値のチェックサムを返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="342e8-118">NULL 値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="342e8-118">Null values are ignored.</span></span>
 
 <span data-ttu-id="342e8-119">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-119">**Arguments**</span></span>
 
 <span data-ttu-id="342e8-120">コレクション (`Int32`)。</span><span class="sxs-lookup"><span data-stu-id="342e8-120">A Collection(`Int32`).</span></span>
 
 <span data-ttu-id="342e8-121">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-121">**Return Value**</span></span>
 
 <span data-ttu-id="342e8-122">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="342e8-122">An `Int32`.</span></span>
 
 <span data-ttu-id="342e8-123">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-123">**Example**</span></span>
 
[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]
   
## <a name="countexpression"></a><span data-ttu-id="342e8-124">COUNT (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-124">COUNT(expression)</span></span>

<span data-ttu-id="342e8-125">コレクション内のアイテムの数を `Int32` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="342e8-126">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-126">**Arguments**</span></span>

<span data-ttu-id="342e8-127">コレクション @ no__t ~ 0T >。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="342e8-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="342e8-128">`Guid` (SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="342e8-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="342e8-129">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-129">**Return Value**</span></span>

<span data-ttu-id="342e8-130">`Int32`。</span><span class="sxs-lookup"><span data-stu-id="342e8-130">An `Int32`.</span></span>

<span data-ttu-id="342e8-131">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]
 
## <a name="count_bigexpression"></a><span data-ttu-id="342e8-132">COUNT_BIG (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-132">COUNT_BIG(expression)</span></span>
 
<span data-ttu-id="342e8-133">コレクション内のアイテムの数を `bigint` 型の値として返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-133">Returns the number of items in a collection as a `bigint`.</span></span>
 
 <span data-ttu-id="342e8-134">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-134">**Arguments**</span></span>
 
 <span data-ttu-id="342e8-135">Collection (T)。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="342e8-135">A Collection(T), where T is one of the following types:</span></span>
 
 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="342e8-136">`Guid` (SQL Server 2000 では返されません)</span><span class="sxs-lookup"><span data-stu-id="342e8-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="342e8-137">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-137">**Return Value**</span></span>

<span data-ttu-id="342e8-138">`Int64`。</span><span class="sxs-lookup"><span data-stu-id="342e8-138">An `Int64`.</span></span>

<span data-ttu-id="342e8-139">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="342e8-140">MAX (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-140">MAX(expression)</span></span>

<span data-ttu-id="342e8-141">コレクション内の最大値を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="342e8-142">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-142">**Arguments**</span></span>

<span data-ttu-id="342e8-143">Collection (T)。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="342e8-143">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="342e8-144">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-144">**Return Value**</span></span>

<span data-ttu-id="342e8-145">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="342e8-145">The type of `expression`.</span></span>

<span data-ttu-id="342e8-146">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="342e8-147">MIN (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-147">MIN(expression)</span></span>

<span data-ttu-id="342e8-148">コレクション内の最小値を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="342e8-149">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-149">**Arguments**</span></span>

<span data-ttu-id="342e8-150">Collection (T)。ここで、T は次のいずれかの型になります。</span><span class="sxs-lookup"><span data-stu-id="342e8-150">A Collection(T), where T is one of the following types:</span></span> 

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="342e8-151">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-151">**Return Value**</span></span>

<span data-ttu-id="342e8-152">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="342e8-152">The type of `expression`.</span></span>

<span data-ttu-id="342e8-153">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="342e8-154">STDEV (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-154">STDEV(expression)</span></span>

<span data-ttu-id="342e8-155">指定された式のすべての値の統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="342e8-156">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-156">**Arguments**</span></span>

<span data-ttu-id="342e8-157">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="342e8-157">A Collection(`Double`).</span></span>

<span data-ttu-id="342e8-158">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-158">**Return Value**</span></span>

<span data-ttu-id="342e8-159">`Double`。</span><span class="sxs-lookup"><span data-stu-id="342e8-159">A `Double`.</span></span>

<span data-ttu-id="342e8-160">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="342e8-161">STDEVP (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-161">STDEVP(expression)</span></span>

<span data-ttu-id="342e8-162">指定された式のすべての値を母集団として統計的標準偏差を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="342e8-163">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-163">**Arguments**</span></span>

<span data-ttu-id="342e8-164">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="342e8-164">A Collection(`Double`).</span></span>

<span data-ttu-id="342e8-165">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-165">**Return Value**</span></span>

<span data-ttu-id="342e8-166">`Double`。</span><span class="sxs-lookup"><span data-stu-id="342e8-166">A `Double`.</span></span>

<span data-ttu-id="342e8-167">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="342e8-168">SUM (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-168">SUM(expression)</span></span>

<span data-ttu-id="342e8-169">コレクション内のすべての値の合計を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="342e8-170">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-170">**Arguments**</span></span>

<span data-ttu-id="342e8-171">Collection (T)。ここで、T は次のいずれかの型になります。 `Int32`、`Int64`、`Double`、`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="342e8-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="342e8-172">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-172">**Return Value**</span></span>

<span data-ttu-id="342e8-173">`expression` の型。</span><span class="sxs-lookup"><span data-stu-id="342e8-173">The type of `expression`.</span></span>

<span data-ttu-id="342e8-174">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="342e8-175">VAR(expression)</span><span class="sxs-lookup"><span data-stu-id="342e8-175">VAR(expression)</span></span>

<span data-ttu-id="342e8-176">指定された式のすべての値の統計的分散を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="342e8-177">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-177">**Arguments**</span></span>

<span data-ttu-id="342e8-178">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="342e8-178">A Collection(`Double`).</span></span>

<span data-ttu-id="342e8-179">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-179">**Return Value**</span></span>

<span data-ttu-id="342e8-180">`Double`。</span><span class="sxs-lookup"><span data-stu-id="342e8-180">A `Double`.</span></span>

<span data-ttu-id="342e8-181">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="342e8-182">VARP (式)</span><span class="sxs-lookup"><span data-stu-id="342e8-182">VARP(expression)</span></span>

<span data-ttu-id="342e8-183">指定した式のすべての値について、母集団に対する統計的変位を返します。</span><span class="sxs-lookup"><span data-stu-id="342e8-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="342e8-184">**引数**</span><span class="sxs-lookup"><span data-stu-id="342e8-184">**Arguments**</span></span>

<span data-ttu-id="342e8-185">コレクション (`Double`)。</span><span class="sxs-lookup"><span data-stu-id="342e8-185">A Collection(`Double`).</span></span>

<span data-ttu-id="342e8-186">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="342e8-186">**Return Value**</span></span>

<span data-ttu-id="342e8-187">`Double`。</span><span class="sxs-lookup"><span data-stu-id="342e8-187">A `Double`.</span></span>

<span data-ttu-id="342e8-188">**例**</span><span class="sxs-lookup"><span data-stu-id="342e8-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)] 
  
## <a name="see-also"></a><span data-ttu-id="342e8-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="342e8-189">See also</span></span>

- [<span data-ttu-id="342e8-190">集計関数 (Transact-sql)</span><span class="sxs-lookup"><span data-stu-id="342e8-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="342e8-191">Entity SQL 言語</span><span class="sxs-lookup"><span data-stu-id="342e8-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="342e8-192">集計正規関数</span><span class="sxs-lookup"><span data-stu-id="342e8-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
