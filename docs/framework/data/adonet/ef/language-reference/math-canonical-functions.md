---
title: 数値演算正規関数
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 9417ff9836912017c9d88bb24a18849aaac2836a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250310"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="dd33d-102">数値演算正規関数</span><span class="sxs-lookup"><span data-stu-id="dd33d-102">Math Canonical Functions</span></span>

<span data-ttu-id="dd33d-103">Entity SQL には、次の数値演算正規関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd33d-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="dd33d-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="dd33d-104">Abs(value)</span></span>

<span data-ttu-id="dd33d-105">`value` の絶対値を返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="dd33d-106">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-106">**Arguments**</span></span>

<span data-ttu-id="dd33d-107">`Int16`、`Int32`、`Int64`、`Byte`、`Single`、`Double`、および `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="dd33d-108">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-108">**Return Value**</span></span>

<span data-ttu-id="dd33d-109">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-109">The type of `value`.</span></span>

<span data-ttu-id="dd33d-110">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="dd33d-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="dd33d-111">Ceiling(value)</span></span>

<span data-ttu-id="dd33d-112">`value` 以上で最小の整数値を返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="dd33d-113">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-113">**Arguments**</span></span>

<span data-ttu-id="dd33d-114">`Single`、`Double`、および `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="dd33d-115">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-115">**Return Value**</span></span>

<span data-ttu-id="dd33d-116">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-116">The type of `value`.</span></span>

<span data-ttu-id="dd33d-117">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="dd33d-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="dd33d-118">Floor(value)</span></span>

<span data-ttu-id="dd33d-119">`value` 以下で最大の整数値を返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="dd33d-120">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-120">**Arguments**</span></span>

<span data-ttu-id="dd33d-121">`Single`、`Double`、および `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="dd33d-122">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-122">**Return Value**</span></span>

<span data-ttu-id="dd33d-123">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-123">The type of `value`.</span></span>

<span data-ttu-id="dd33d-124">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="dd33d-125">Power(value, exponent)</span><span class="sxs-lookup"><span data-stu-id="dd33d-125">Power(value, exponent)</span></span>

<span data-ttu-id="dd33d-126">指定された `value` を指定された `exponent` でべき乗した結果を返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="dd33d-127">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="dd33d-128">`Int32, Int64, Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="dd33d-129">`Int64`、`Double`、または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="dd33d-130">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-130">**Return Value**</span></span>

<span data-ttu-id="dd33d-131">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-131">The type of `value`.</span></span>

<span data-ttu-id="dd33d-132">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="dd33d-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="dd33d-133">Round(value)</span></span>

<span data-ttu-id="dd33d-134">最も近い整数に丸められた `value` の整数部分を返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="dd33d-135">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-135">**Arguments**</span></span>

<span data-ttu-id="dd33d-136">`Single`、`Double`、および `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="dd33d-137">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-137">**Return Value**</span></span>

<span data-ttu-id="dd33d-138">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-138">The type of `value`.</span></span>

<span data-ttu-id="dd33d-139">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="dd33d-140">Round(value, digits)</span><span class="sxs-lookup"><span data-stu-id="dd33d-140">Round(value, digits)</span></span>

<span data-ttu-id="dd33d-141">`value` を指定された最も近い `digits` に丸めて返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="dd33d-142">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="dd33d-143">`Double` または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="dd33d-144">`Int16` または `Int32`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="dd33d-145">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-145">**Return Value**</span></span>

<span data-ttu-id="dd33d-146">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-146">The type of `value`.</span></span>

<span data-ttu-id="dd33d-147">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="dd33d-148">Truncate(value, digits)</span><span class="sxs-lookup"><span data-stu-id="dd33d-148">Truncate(value, digits)</span></span>

<span data-ttu-id="dd33d-149">`value` を指定された最も近い `digits` に切り詰めて返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="dd33d-150">**引数**</span><span class="sxs-lookup"><span data-stu-id="dd33d-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="dd33d-151">`Double` または `Decimal`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="dd33d-152">`Int16` または `Int32`。</span><span class="sxs-lookup"><span data-stu-id="dd33d-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="dd33d-153">**戻り値**</span><span class="sxs-lookup"><span data-stu-id="dd33d-153">**Return Value**</span></span>

<span data-ttu-id="dd33d-154">`value` の型。</span><span class="sxs-lookup"><span data-stu-id="dd33d-154">The type of `value`.</span></span>

<span data-ttu-id="dd33d-155">**例**</span><span class="sxs-lookup"><span data-stu-id="dd33d-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="dd33d-156">`null` が入力された場合、これらの関数は `null` を返します。</span><span class="sxs-lookup"><span data-stu-id="dd33d-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="dd33d-157">同等の機能は、Microsoft SQL クライアント マネージド プロバイダーでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="dd33d-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="dd33d-158">詳細については、「[Entity Framework 用 SqlClient 関数](../sqlclient-for-ef-functions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd33d-158">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd33d-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd33d-159">See also</span></span>

- [<span data-ttu-id="dd33d-160">正規関数</span><span class="sxs-lookup"><span data-stu-id="dd33d-160">Canonical Functions</span></span>](canonical-functions.md)
