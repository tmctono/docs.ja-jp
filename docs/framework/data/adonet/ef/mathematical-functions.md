---
title: 数学関数
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149766"
---
# <a name="mathematical-functions"></a><span data-ttu-id="34125-102">数学関数</span><span class="sxs-lookup"><span data-stu-id="34125-102">Mathematical Functions</span></span>

<span data-ttu-id="34125-103">.NET Framework Data Provider for SQL Server (SqlClient) には、引数として指定された入力値に対して計算を実行し、数値結果を返す数学関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="34125-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="34125-104">これらの関数は、SqlClient の SqlServer 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="34125-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="34125-105">Entity Framework は、プロバイダーの名前空間プロパティを使用することにより、型や関数など、特定のコンストラクターに対してこのプロバイダーによってどのプレフィックスが使用されているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="34125-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="34125-106">次の表は、SqlClient の算術関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="34125-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="34125-107">ABS(式)</span><span class="sxs-lookup"><span data-stu-id="34125-107">ABS(expression)</span></span>

<span data-ttu-id="34125-108">絶対値を求める関数です。</span><span class="sxs-lookup"><span data-stu-id="34125-108">Performs the absolute value function.</span></span>

<span data-ttu-id="34125-109">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-109">**Arguments**</span></span>

<span data-ttu-id="34125-110">`expression`: `Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="34125-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-111">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-111">**Return Value**</span></span>

<span data-ttu-id="34125-112">指定された式の絶対値。</span><span class="sxs-lookup"><span data-stu-id="34125-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="34125-113">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="34125-114">ACOS(式)</span><span class="sxs-lookup"><span data-stu-id="34125-114">ACOS(expression)</span></span>

<span data-ttu-id="34125-115">指定された式のアークコサイン (逆余弦) 値を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="34125-116">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-116">**Arguments**</span></span>

<span data-ttu-id="34125-117">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-118">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-118">**Return Value**</span></span>

<span data-ttu-id="34125-119">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-119">A `Double`.</span></span>

<span data-ttu-id="34125-120">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="34125-121">アシン(式)</span><span class="sxs-lookup"><span data-stu-id="34125-121">ASIN(expression)</span></span>

<span data-ttu-id="34125-122">指定された式のアークサイン (逆正弦) 値を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="34125-123">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-123">**Arguments**</span></span>

<span data-ttu-id="34125-124">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-125">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-125">**Return Value**</span></span>

<span data-ttu-id="34125-126">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-126">A `Double`.</span></span>

<span data-ttu-id="34125-127">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="34125-128">アタン(式)</span><span class="sxs-lookup"><span data-stu-id="34125-128">ATAN(expression)</span></span>

<span data-ttu-id="34125-129">指定された数値式のアークタンジェント (逆正接) 値を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="34125-130">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-130">**Arguments**</span></span>

<span data-ttu-id="34125-131">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-132">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-132">**Return Value**</span></span>

<span data-ttu-id="34125-133">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-133">A `Double`.</span></span>

<span data-ttu-id="34125-134">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="34125-135">ATN2(式、式)</span><span class="sxs-lookup"><span data-stu-id="34125-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="34125-136">指定された 2 つの数値式の商がタンジェント (正接) となる角度をラジアンで返します。</span><span class="sxs-lookup"><span data-stu-id="34125-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="34125-137">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-137">**Arguments**</span></span>

<span data-ttu-id="34125-138">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-139">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-139">**Return Value**</span></span>

<span data-ttu-id="34125-140">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-140">A `Double`.</span></span>

<span data-ttu-id="34125-141">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="34125-142">天井(式)</span><span class="sxs-lookup"><span data-stu-id="34125-142">CEILING(expression)</span></span>

<span data-ttu-id="34125-143">指定された式をその式以上の最小整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="34125-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="34125-144">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-144">**Arguments**</span></span>

<span data-ttu-id="34125-145">`expression`: `Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="34125-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-146">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-146">**Return Value**</span></span>

<span data-ttu-id="34125-147">、 `Int32` `Int64`、 `Double`、`Decimal`または 。</span><span class="sxs-lookup"><span data-stu-id="34125-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-148">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-148">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="34125-149">コス(式)</span><span class="sxs-lookup"><span data-stu-id="34125-149">COS(expression)</span></span>

<span data-ttu-id="34125-150">ラジアンで指定された角度のコサイン (余弦) を計算します。</span><span class="sxs-lookup"><span data-stu-id="34125-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="34125-151">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-151">**Arguments**</span></span>

<span data-ttu-id="34125-152">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-152">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-153">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-153">**Return Value**</span></span>

<span data-ttu-id="34125-154">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-154">A `Double`.</span></span>

<span data-ttu-id="34125-155">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-155">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="34125-156">COT(式)</span><span class="sxs-lookup"><span data-stu-id="34125-156">COT(expression)</span></span>

<span data-ttu-id="34125-157">ラジアンで指定された角度のコタンジェント (余接) を計算します。</span><span class="sxs-lookup"><span data-stu-id="34125-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="34125-158">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-158">**Arguments**</span></span>

<span data-ttu-id="34125-159">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-159">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-160">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-160">**Return Value**</span></span>

<span data-ttu-id="34125-161">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-161">A `Double`.</span></span>

<span data-ttu-id="34125-162">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-162">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="34125-163">度(ラジアン)</span><span class="sxs-lookup"><span data-stu-id="34125-163">DEGREES(radians)</span></span>

<span data-ttu-id="34125-164">対応する角度を度数で返します。</span><span class="sxs-lookup"><span data-stu-id="34125-164">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="34125-165">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-165">**Arguments**</span></span>

<span data-ttu-id="34125-166">`expression`: `Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="34125-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-167">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-167">**Return Value**</span></span>

<span data-ttu-id="34125-168">、 `Int32` `Int64`、 `Double`、`Decimal`または 。</span><span class="sxs-lookup"><span data-stu-id="34125-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-169">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-169">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="34125-170">EXP(式)</span><span class="sxs-lookup"><span data-stu-id="34125-170">EXP(expression)</span></span>

<span data-ttu-id="34125-171">指定された数値式の指数値を計算します。</span><span class="sxs-lookup"><span data-stu-id="34125-171">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="34125-172">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-172">**Arguments**</span></span>

<span data-ttu-id="34125-173">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-173">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-174">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-174">**Return Value**</span></span>

<span data-ttu-id="34125-175">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-175">A `Double`.</span></span>

<span data-ttu-id="34125-176">**例**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="34125-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="34125-177">フロア(式)</span><span class="sxs-lookup"><span data-stu-id="34125-177">FLOOR(expression)</span></span>

<span data-ttu-id="34125-178">指定された式をその式以下の最大整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="34125-178">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="34125-179">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-179">**Arguments**</span></span>

<span data-ttu-id="34125-180">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-180">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-181">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-181">**Return Value**</span></span>

<span data-ttu-id="34125-182">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-182">A `Double`.</span></span>

<span data-ttu-id="34125-183">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-183">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="34125-184">ログ(式)</span><span class="sxs-lookup"><span data-stu-id="34125-184">LOG(expression)</span></span>

<span data-ttu-id="34125-185">指定された `float` 型の式の自然対数を計算します。</span><span class="sxs-lookup"><span data-stu-id="34125-185">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="34125-186">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-186">**Arguments**</span></span>

<span data-ttu-id="34125-187">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-187">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-188">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-188">**Return Value**</span></span>

<span data-ttu-id="34125-189">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-189">A `Double`.</span></span>

<span data-ttu-id="34125-190">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-190">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="34125-191">ログ10(式)</span><span class="sxs-lookup"><span data-stu-id="34125-191">LOG10(expression)</span></span>

<span data-ttu-id="34125-192">指定された `Double` 型の式の 10 を底とした対数を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="34125-193">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-193">**Arguments**</span></span>

<span data-ttu-id="34125-194">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-194">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-195">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-195">**Return Value**</span></span>

<span data-ttu-id="34125-196">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-196">A `Double`.</span></span>

<span data-ttu-id="34125-197">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-197">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="34125-198">PI()</span><span class="sxs-lookup"><span data-stu-id="34125-198">PI()</span></span>

<span data-ttu-id="34125-199">π の定数値を `Double` として返します。</span><span class="sxs-lookup"><span data-stu-id="34125-199">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="34125-200">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-200">**Return Value**</span></span>

<span data-ttu-id="34125-201">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-201">A `Double`.</span></span>

<span data-ttu-id="34125-202">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-202">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="34125-203">パワー(numeric_expression、power_expression)</span><span class="sxs-lookup"><span data-stu-id="34125-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="34125-204">指定された式の指定されたべき乗を計算します。</span><span class="sxs-lookup"><span data-stu-id="34125-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="34125-205">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-205">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="34125-206">、 `Int32` `Int64`、 `Double`、`Decimal`または 。</span><span class="sxs-lookup"><span data-stu-id="34125-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="34125-207">を`Double`上げる累乗を表す`numeric_expression`A</span><span class="sxs-lookup"><span data-stu-id="34125-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="34125-208">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-208">**Return Value**</span></span>

<span data-ttu-id="34125-209">指定された `numeric_expression` を指定された `power_expression` でべき乗した値。</span><span class="sxs-lookup"><span data-stu-id="34125-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="34125-210">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-210">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="34125-211">ラジアン(式)</span><span class="sxs-lookup"><span data-stu-id="34125-211">RADIANS(expression)</span></span>

<span data-ttu-id="34125-212">角度をラジアンに変換します。</span><span class="sxs-lookup"><span data-stu-id="34125-212">Converts degrees to radians.</span></span>

<span data-ttu-id="34125-213">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-213">**Arguments**</span></span>

<span data-ttu-id="34125-214">`expression`: `Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="34125-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-215">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-215">**Return Value**</span></span>

<span data-ttu-id="34125-216">、 `Int32` `Int64`、 `Double`、`Decimal`または 。</span><span class="sxs-lookup"><span data-stu-id="34125-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-217">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-217">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="34125-218">ランド[シード])</span><span class="sxs-lookup"><span data-stu-id="34125-218">RAND([seed])</span></span>

<span data-ttu-id="34125-219">0 から 1 までの範囲の乱数を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-219">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="34125-220">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-220">**Arguments**</span></span>

<span data-ttu-id="34125-221">シード値をとして使用`Int32`します。</span><span class="sxs-lookup"><span data-stu-id="34125-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="34125-222">シードを指定しない場合は、SQL Server データベース エンジンによってシード値がランダムに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="34125-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="34125-223">指定されたシード値に対し、返される結果は常に同じです。</span><span class="sxs-lookup"><span data-stu-id="34125-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="34125-224">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-224">**Return Value**</span></span>

<span data-ttu-id="34125-225">0 から 1 までの範囲の `Double` 型の乱数。</span><span class="sxs-lookup"><span data-stu-id="34125-225">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="34125-226">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-226">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="34125-227">ROUND(numeric_expression、長さ[,関数])</span><span class="sxs-lookup"><span data-stu-id="34125-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="34125-228">指定された長さまたは有効桁数に丸めた数値式を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-228">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="34125-229">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-229">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="34125-230">、 `Int32` `Int64`、 `Double`、`Decimal`または 。</span><span class="sxs-lookup"><span data-stu-id="34125-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="34125-231">`Int32` を丸めた後の有効桁数を表す `numeric_expression`。</span><span class="sxs-lookup"><span data-stu-id="34125-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="34125-232">`length` に正の値を指定した場合、`numeric_expression` は `length` で指定した小数点以下桁数に丸められます。</span><span class="sxs-lookup"><span data-stu-id="34125-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="34125-233">`length` に負の値を指定した場合、`numeric_expression` は `length` で指定した小数点の左側の位置で丸められます。</span><span class="sxs-lookup"><span data-stu-id="34125-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="34125-234">省略可能。</span><span class="sxs-lookup"><span data-stu-id="34125-234">Optional.</span></span> <span data-ttu-id="34125-235">実行`Int32`する操作の種類を表す。</span><span class="sxs-lookup"><span data-stu-id="34125-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="34125-236">関数が省略された場合、または値が 0 (デフォルト`numeric_expression`) の場合は、丸められます。</span><span class="sxs-lookup"><span data-stu-id="34125-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="34125-237">0 以外の値を指定すると、`numeric_expression`切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="34125-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="34125-238">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-238">**Return Value**</span></span>

<span data-ttu-id="34125-239">指定された `numeric_expression` を指定された `power_expression` でべき乗した値。</span><span class="sxs-lookup"><span data-stu-id="34125-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="34125-240">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-240">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="34125-241">記号(式)</span><span class="sxs-lookup"><span data-stu-id="34125-241">SIGN(expression)</span></span>

<span data-ttu-id="34125-242">指定された式の符号として正 (+1)、ゼロ (0)、負 (-1) のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="34125-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="34125-243">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-243">**Arguments**</span></span>

<span data-ttu-id="34125-244">`expression`: `Int32`、`Int64`、`Double`、または `Decimal`</span><span class="sxs-lookup"><span data-stu-id="34125-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="34125-245">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-245">**Return Value**</span></span>

<span data-ttu-id="34125-246">、 `Int32` `Int64`、 `Double`、`Decimal`または 。</span><span class="sxs-lookup"><span data-stu-id="34125-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="34125-247">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-247">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="34125-248">SIN(式)</span><span class="sxs-lookup"><span data-stu-id="34125-248">SIN(expression)</span></span>

<span data-ttu-id="34125-249">ラジアンで指定された角度のサイン (正弦) を計算し、`Double` 式を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="34125-250">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-250">**Arguments**</span></span>

<span data-ttu-id="34125-251">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-251">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-252">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-252">**Return Value**</span></span>

<span data-ttu-id="34125-253">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-253">A `Double`.</span></span>

<span data-ttu-id="34125-254">**例**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="34125-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="34125-255">SQRT(式)</span><span class="sxs-lookup"><span data-stu-id="34125-255">SQRT(expression)</span></span>

<span data-ttu-id="34125-256">指定された式の平方根を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-256">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="34125-257">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-257">**Arguments**</span></span>

<span data-ttu-id="34125-258">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-258">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-259">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-259">**Return Value**</span></span>

<span data-ttu-id="34125-260">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-260">A `Double`.</span></span>

<span data-ttu-id="34125-261">**例**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="34125-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="34125-262">スクエア(式)</span><span class="sxs-lookup"><span data-stu-id="34125-262">SQUARE(expression)</span></span>

<span data-ttu-id="34125-263">指定された式の 2 乗値を返します。</span><span class="sxs-lookup"><span data-stu-id="34125-263">Returns the square of the specified expression.</span></span>

<span data-ttu-id="34125-264">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-264">**Arguments**</span></span>

<span data-ttu-id="34125-265">`expression`: `Double`。</span><span class="sxs-lookup"><span data-stu-id="34125-265">`expression`: A `Double`.</span></span>

<span data-ttu-id="34125-266">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-266">**Return Value**</span></span>

<span data-ttu-id="34125-267">`Double` です。</span><span class="sxs-lookup"><span data-stu-id="34125-267">A `Double`.</span></span>

<span data-ttu-id="34125-268">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-268">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="34125-269">タン(式)</span><span class="sxs-lookup"><span data-stu-id="34125-269">TAN(expression)</span></span>

<span data-ttu-id="34125-270">指定された式のタンジェントを計算します。</span><span class="sxs-lookup"><span data-stu-id="34125-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="34125-271">**引数**</span><span class="sxs-lookup"><span data-stu-id="34125-271">**Arguments**</span></span>

<span data-ttu-id="34125-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="34125-272">`expression`: `Double`</span></span>

<span data-ttu-id="34125-273">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="34125-273">**Return Value**</span></span>

`Double`

<span data-ttu-id="34125-274">**例**</span><span class="sxs-lookup"><span data-stu-id="34125-274">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="34125-275">関連項目</span><span class="sxs-lookup"><span data-stu-id="34125-275">See also</span></span>

- [<span data-ttu-id="34125-276">数学関数 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="34125-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="34125-277">Entity Framework 用 SqlClient 関数</span><span class="sxs-lookup"><span data-stu-id="34125-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
