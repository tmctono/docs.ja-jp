---
title: 数学関数
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149766"
---
# <a name="mathematical-functions"></a><span data-ttu-id="64bbe-102">数学関数</span><span class="sxs-lookup"><span data-stu-id="64bbe-102">Mathematical Functions</span></span>

<span data-ttu-id="64bbe-103">.NET Framework Data Provider for SQL Server (SqlClient) には、引数として指定された入力値に対して計算を実行し、数値結果を返す数学関数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="64bbe-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="64bbe-104">これらの関数は、SqlClient の SqlServer 名前空間に存在します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="64bbe-105">Entity Framework は、プロバイダーの名前空間プロパティを使用することにより、型や関数など、特定のコンストラクターに対してこのプロバイダーによってどのプレフィックスが使用されているかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="64bbe-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="64bbe-106">SqlClient の数学関数を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="64bbe-107">ABS(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-107">ABS(expression)</span></span>

<span data-ttu-id="64bbe-108">絶対値を求める関数です。</span><span class="sxs-lookup"><span data-stu-id="64bbe-108">Performs the absolute value function.</span></span>

<span data-ttu-id="64bbe-109">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-109">**Arguments**</span></span>

<span data-ttu-id="64bbe-110">`expression`:`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-111">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-111">**Return Value**</span></span>

<span data-ttu-id="64bbe-112">指定された式の絶対値。</span><span class="sxs-lookup"><span data-stu-id="64bbe-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="64bbe-113">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="64bbe-114">ACOS(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-114">ACOS(expression)</span></span>

<span data-ttu-id="64bbe-115">指定された式のアークコサイン (逆余弦) 値を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="64bbe-116">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-116">**Arguments**</span></span>

<span data-ttu-id="64bbe-117">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-118">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-118">**Return Value**</span></span>

<span data-ttu-id="64bbe-119">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-119">A `Double`.</span></span>

<span data-ttu-id="64bbe-120">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="64bbe-121">ASIN(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-121">ASIN(expression)</span></span>

<span data-ttu-id="64bbe-122">指定された式のアークサイン (逆正弦) 値を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="64bbe-123">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-123">**Arguments**</span></span>

<span data-ttu-id="64bbe-124">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-125">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-125">**Return Value**</span></span>

<span data-ttu-id="64bbe-126">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-126">A `Double`.</span></span>

<span data-ttu-id="64bbe-127">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="64bbe-128">ATAN(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-128">ATAN(expression)</span></span>

<span data-ttu-id="64bbe-129">指定された数値式のアークタンジェント (逆正接) 値を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="64bbe-130">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-130">**Arguments**</span></span>

<span data-ttu-id="64bbe-131">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-132">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-132">**Return Value**</span></span>

<span data-ttu-id="64bbe-133">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-133">A `Double`.</span></span>

<span data-ttu-id="64bbe-134">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="64bbe-135">ATN2(expression, expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="64bbe-136">指定された 2 つの数値式の商がタンジェント (正接) となる角度をラジアンで返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="64bbe-137">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-137">**Arguments**</span></span>

<span data-ttu-id="64bbe-138">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-139">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-139">**Return Value**</span></span>

<span data-ttu-id="64bbe-140">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-140">A `Double`.</span></span>

<span data-ttu-id="64bbe-141">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="64bbe-142">CEILING(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-142">CEILING(expression)</span></span>

<span data-ttu-id="64bbe-143">指定された式をその式以上の最小整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="64bbe-144">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-144">**Arguments**</span></span>

<span data-ttu-id="64bbe-145">`expression`:`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-146">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-146">**Return Value**</span></span>

<span data-ttu-id="64bbe-147">`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-148">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-148">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="64bbe-149">COS(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-149">COS(expression)</span></span>

<span data-ttu-id="64bbe-150">ラジアンで指定された角度のコサイン (余弦) を計算します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="64bbe-151">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-151">**Arguments**</span></span>

<span data-ttu-id="64bbe-152">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-152">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-153">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-153">**Return Value**</span></span>

<span data-ttu-id="64bbe-154">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-154">A `Double`.</span></span>

<span data-ttu-id="64bbe-155">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-155">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="64bbe-156">COT(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-156">COT(expression)</span></span>

<span data-ttu-id="64bbe-157">ラジアンで指定された角度のコタンジェント (余接) を計算します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="64bbe-158">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-158">**Arguments**</span></span>

<span data-ttu-id="64bbe-159">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-159">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-160">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-160">**Return Value**</span></span>

<span data-ttu-id="64bbe-161">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-161">A `Double`.</span></span>

<span data-ttu-id="64bbe-162">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-162">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="64bbe-163">DEGREES(radians)</span><span class="sxs-lookup"><span data-stu-id="64bbe-163">DEGREES(radians)</span></span>

<span data-ttu-id="64bbe-164">対応する角度を度数で返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-164">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="64bbe-165">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-165">**Arguments**</span></span>

<span data-ttu-id="64bbe-166">`expression`:`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-167">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-167">**Return Value**</span></span>

<span data-ttu-id="64bbe-168">`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-169">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-169">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="64bbe-170">EXP(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-170">EXP(expression)</span></span>

<span data-ttu-id="64bbe-171">指定された数値式の指数値を計算します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-171">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="64bbe-172">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-172">**Arguments**</span></span>

<span data-ttu-id="64bbe-173">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-173">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-174">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-174">**Return Value**</span></span>

<span data-ttu-id="64bbe-175">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-175">A `Double`.</span></span>

<span data-ttu-id="64bbe-176">**例** `SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="64bbe-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="64bbe-177">FLOOR(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-177">FLOOR(expression)</span></span>

<span data-ttu-id="64bbe-178">指定された式をその式以下の最大整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-178">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="64bbe-179">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-179">**Arguments**</span></span>

<span data-ttu-id="64bbe-180">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-180">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-181">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-181">**Return Value**</span></span>

<span data-ttu-id="64bbe-182">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-182">A `Double`.</span></span>

<span data-ttu-id="64bbe-183">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-183">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="64bbe-184">LOG(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-184">LOG(expression)</span></span>

<span data-ttu-id="64bbe-185">指定された `float` 型の式の自然対数を計算します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-185">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="64bbe-186">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-186">**Arguments**</span></span>

<span data-ttu-id="64bbe-187">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-187">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-188">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-188">**Return Value**</span></span>

<span data-ttu-id="64bbe-189">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-189">A `Double`.</span></span>

<span data-ttu-id="64bbe-190">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-190">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="64bbe-191">LOG10(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-191">LOG10(expression)</span></span>

<span data-ttu-id="64bbe-192">指定された `Double` 型の式の 10 を底とした対数を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="64bbe-193">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-193">**Arguments**</span></span>

<span data-ttu-id="64bbe-194">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-194">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-195">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-195">**Return Value**</span></span>

<span data-ttu-id="64bbe-196">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-196">A `Double`.</span></span>

<span data-ttu-id="64bbe-197">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-197">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="64bbe-198">PI()</span><span class="sxs-lookup"><span data-stu-id="64bbe-198">PI()</span></span>

<span data-ttu-id="64bbe-199">π の定数値を `Double` として返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-199">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="64bbe-200">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-200">**Return Value**</span></span>

<span data-ttu-id="64bbe-201">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-201">A `Double`.</span></span>

<span data-ttu-id="64bbe-202">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-202">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="64bbe-203">POWER(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="64bbe-204">指定された式の指定されたべき乗を計算します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="64bbe-205">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-205">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="64bbe-206">`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="64bbe-207">`numeric_expression` のべき乗値を表す `Double` 型の値。</span><span class="sxs-lookup"><span data-stu-id="64bbe-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="64bbe-208">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-208">**Return Value**</span></span>

<span data-ttu-id="64bbe-209">指定された `numeric_expression` を指定された `power_expression` でべき乗した値。</span><span class="sxs-lookup"><span data-stu-id="64bbe-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="64bbe-210">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-210">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="64bbe-211">RADIANS(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-211">RADIANS(expression)</span></span>

<span data-ttu-id="64bbe-212">角度をラジアンに変換します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-212">Converts degrees to radians.</span></span>

<span data-ttu-id="64bbe-213">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-213">**Arguments**</span></span>

<span data-ttu-id="64bbe-214">`expression`:`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-215">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-215">**Return Value**</span></span>

<span data-ttu-id="64bbe-216">`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-217">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-217">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="64bbe-218">RAND([seed])</span><span class="sxs-lookup"><span data-stu-id="64bbe-218">RAND([seed])</span></span>

<span data-ttu-id="64bbe-219">0 から 1 までの範囲の乱数を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-219">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="64bbe-220">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-220">**Arguments**</span></span>

<span data-ttu-id="64bbe-221">`Int32` としてのシード値。</span><span class="sxs-lookup"><span data-stu-id="64bbe-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="64bbe-222">シードを指定しない場合は、SQL Server データベース エンジンによってシード値がランダムに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="64bbe-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="64bbe-223">指定したシード値について、返される結果は常に同じです。</span><span class="sxs-lookup"><span data-stu-id="64bbe-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="64bbe-224">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-224">**Return Value**</span></span>

<span data-ttu-id="64bbe-225">0 から 1 までの範囲の `Double` 型の乱数。</span><span class="sxs-lookup"><span data-stu-id="64bbe-225">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="64bbe-226">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-226">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="64bbe-227">ROUND(numeric_expression, length[,function])</span><span class="sxs-lookup"><span data-stu-id="64bbe-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="64bbe-228">指定された長さまたは有効桁数に丸めた数値式を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-228">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="64bbe-229">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-229">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="64bbe-230">`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="64bbe-231">`Int32` を丸めた後の有効桁数を表す `numeric_expression`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="64bbe-232">`length` に正の値を指定した場合、`numeric_expression` は `length` で指定した小数点以下桁数に丸められます。</span><span class="sxs-lookup"><span data-stu-id="64bbe-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="64bbe-233">`length` に負の値を指定した場合、`numeric_expression` は `length` で指定した小数点の左側の位置で丸められます。</span><span class="sxs-lookup"><span data-stu-id="64bbe-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="64bbe-234">任意。</span><span class="sxs-lookup"><span data-stu-id="64bbe-234">Optional.</span></span> <span data-ttu-id="64bbe-235">実行する操作の種類を表す `Int32`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="64bbe-236">function を省略した場合、または 0 (既定値) を指定した場合、`numeric_expression` は丸められます。</span><span class="sxs-lookup"><span data-stu-id="64bbe-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="64bbe-237">0 以外の値を指定した場合、`numeric_expression` は切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="64bbe-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="64bbe-238">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-238">**Return Value**</span></span>

<span data-ttu-id="64bbe-239">指定された `numeric_expression` を指定された `power_expression` でべき乗した値。</span><span class="sxs-lookup"><span data-stu-id="64bbe-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="64bbe-240">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-240">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="64bbe-241">SIGN(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-241">SIGN(expression)</span></span>

<span data-ttu-id="64bbe-242">指定した式の符号として、正 (+1)、負 (-1)、ゼロ (0) のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="64bbe-243">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-243">**Arguments**</span></span>

<span data-ttu-id="64bbe-244">`expression`: `Int32`、`Int64`、`Double`、または `Decimal`</span><span class="sxs-lookup"><span data-stu-id="64bbe-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="64bbe-245">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-245">**Return Value**</span></span>

<span data-ttu-id="64bbe-246">`Int32`、`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="64bbe-247">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-247">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="64bbe-248">SIN(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-248">SIN(expression)</span></span>

<span data-ttu-id="64bbe-249">ラジアンで指定された角度のサイン (正弦) を計算し、`Double` 式を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="64bbe-250">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-250">**Arguments**</span></span>

<span data-ttu-id="64bbe-251">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-251">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-252">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-252">**Return Value**</span></span>

<span data-ttu-id="64bbe-253">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-253">A `Double`.</span></span>

<span data-ttu-id="64bbe-254">**例** `SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="64bbe-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="64bbe-255">SQRT(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-255">SQRT(expression)</span></span>

<span data-ttu-id="64bbe-256">指定された式の平方根を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-256">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="64bbe-257">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-257">**Arguments**</span></span>

<span data-ttu-id="64bbe-258">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-258">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-259">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-259">**Return Value**</span></span>

<span data-ttu-id="64bbe-260">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-260">A `Double`.</span></span>

<span data-ttu-id="64bbe-261">**例** `SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="64bbe-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="64bbe-262">SQUARE(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-262">SQUARE(expression)</span></span>

<span data-ttu-id="64bbe-263">指定された式の 2 乗値を返します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-263">Returns the square of the specified expression.</span></span>

<span data-ttu-id="64bbe-264">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-264">**Arguments**</span></span>

<span data-ttu-id="64bbe-265">`expression`:`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-265">`expression`: A `Double`.</span></span>

<span data-ttu-id="64bbe-266">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-266">**Return Value**</span></span>

<span data-ttu-id="64bbe-267">`Double`。</span><span class="sxs-lookup"><span data-stu-id="64bbe-267">A `Double`.</span></span>

<span data-ttu-id="64bbe-268">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-268">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="64bbe-269">TAN(expression)</span><span class="sxs-lookup"><span data-stu-id="64bbe-269">TAN(expression)</span></span>

<span data-ttu-id="64bbe-270">指定された式のタンジェントを計算します。</span><span class="sxs-lookup"><span data-stu-id="64bbe-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="64bbe-271">**引数**</span><span class="sxs-lookup"><span data-stu-id="64bbe-271">**Arguments**</span></span>

<span data-ttu-id="64bbe-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="64bbe-272">`expression`: `Double`</span></span>

<span data-ttu-id="64bbe-273">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="64bbe-273">**Return Value**</span></span>

`Double`

<span data-ttu-id="64bbe-274">**例**</span><span class="sxs-lookup"><span data-stu-id="64bbe-274">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="64bbe-275">関連項目</span><span class="sxs-lookup"><span data-stu-id="64bbe-275">See also</span></span>

- [<span data-ttu-id="64bbe-276">数学関数 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="64bbe-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="64bbe-277">Entity Framework 用 SqlClient 関数</span><span class="sxs-lookup"><span data-stu-id="64bbe-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
