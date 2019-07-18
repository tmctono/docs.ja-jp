---
title: 浮動小数点数値型 - C# リファレンス
description: Overview of the built-in C# floating-point types (組み込みの C# 浮動小数点型の概要)
ms.date: 06/30/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 738368abd9db75fbd97d1913324cab3b6e869c56
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67664192"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="43be1-103">浮動小数点数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="43be1-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="43be1-104">**浮動小数点型**は**単純型**のサブセットであり、[*リテラル*](#floating-point-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="43be1-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="43be1-105">すべての浮動小数点型は値の型でもあります。</span><span class="sxs-lookup"><span data-stu-id="43be1-105">All floating-point types are also value types.</span></span> <span data-ttu-id="43be1-106">すべての浮動小数点数値型は、[算術](../operators/arithmetic-operators.md)の[比較および等値](../operators/equality-operators.md)演算子をサポートします。</span><span class="sxs-lookup"><span data-stu-id="43be1-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md) [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

<span data-ttu-id="43be1-107">次の表では、浮動小数点型の有効桁数とおおよその範囲を示します。</span><span class="sxs-lookup"><span data-stu-id="43be1-107">The following table shows the precision and approximate ranges for the floating-point types:</span></span>
  
|<span data-ttu-id="43be1-108">型</span><span class="sxs-lookup"><span data-stu-id="43be1-108">Type</span></span>|<span data-ttu-id="43be1-109">おおよその範囲</span><span class="sxs-lookup"><span data-stu-id="43be1-109">Approximate range</span></span>|<span data-ttu-id="43be1-110">有効桁数</span><span class="sxs-lookup"><span data-stu-id="43be1-110">Precision</span></span>|  
|----------|-----------------------|---------------|  
|`float`|<span data-ttu-id="43be1-111">±1.5 x 10<sup>−45</sup> から ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="43be1-111">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="43be1-112">~6 ～9 桁</span><span class="sxs-lookup"><span data-stu-id="43be1-112">~6-9 digits</span></span>|  
|`double`|<span data-ttu-id="43be1-113">±5.0 × 10<sup>−324</sup> - ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="43be1-113">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="43be1-114">~15-17 桁</span><span class="sxs-lookup"><span data-stu-id="43be1-114">~15-17 digits</span></span>|  
|`decimal`|<span data-ttu-id="43be1-115">±1.0 x 10<sup>-28</sup> から ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="43be1-115">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="43be1-116">28 から 29 桁の数字</span><span class="sxs-lookup"><span data-stu-id="43be1-116">28-29 digits</span></span>|  

<span data-ttu-id="43be1-117">すべての浮動小数点型の既定値は `0` です。</span><span class="sxs-lookup"><span data-stu-id="43be1-117">The default value for all floating-point types is `0`.</span></span> <span data-ttu-id="43be1-118">各浮動小数点型には、その型の最小値と最大値に対する `MinValue` と `MaxValue` という名前の定数があります。</span><span class="sxs-lookup"><span data-stu-id="43be1-118">Each of the floating-point types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span> <span data-ttu-id="43be1-119">`float` 型と `double` 型には、さらに `PositiveInfinity`、`NegativeInfinity`、および `NaN` の定数 ("数値ではない" 場合) があります。</span><span class="sxs-lookup"><span data-stu-id="43be1-119">The `float` and `double` types have additional constants for `PositiveInfinity`, `NegativeInfinity`, and `NaN` (for "Not a Number").</span></span> <span data-ttu-id="43be1-120">`decimal` 型には、`Zero`、`One`、および`MinusOne` の定数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43be1-120">The `decimal` type includes constants for `Zero`, `One`, and `MinusOne`.</span></span>

<span data-ttu-id="43be1-121">`decimal` 型は、`float` と `double` の両方よりも有効桁数が多く、範囲が狭いため、財務や金融の計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="43be1-121">The `decimal` type has more precision and a smaller range than both `float` and `double`, which makes it appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="43be1-122">整数型と浮動小数点型を 1 つの式の中の混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="43be1-122">You can mix integral types and floating-point types in an expression.</span></span> <span data-ttu-id="43be1-123">この場合、整数型が浮動小数点型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-123">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="43be1-124">式の評価は、次の規則に従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-124">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="43be1-125">浮動小数点型の 1 つが `double` の場合、式は `double` または [bool](../keywords/bool.md) (リレーショナル比較または等価比較の場合) と評価されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-125">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="43be1-126">式に `double` 型が含まれない場合は、式は `float` または [bool](../keywords/bool.md) (リレーショナル比較または等価比較の場合) と評価されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-126">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="43be1-127">浮動小数点式は、次の値のセットを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="43be1-127">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="43be1-128">正および負のゼロ</span><span class="sxs-lookup"><span data-stu-id="43be1-128">Positive and negative zero</span></span>
- <span data-ttu-id="43be1-129">正および負の無限大</span><span class="sxs-lookup"><span data-stu-id="43be1-129">Positive and negative infinity</span></span>
- <span data-ttu-id="43be1-130">Not-a-Number (NaN) 値</span><span class="sxs-lookup"><span data-stu-id="43be1-130">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="43be1-131">ゼロ以外の値の有限のセット</span><span class="sxs-lookup"><span data-stu-id="43be1-131">The finite set of nonzero values</span></span>

<span data-ttu-id="43be1-132">これらの値について詳しくは、[IEEE](https://www.ieee.org) の Web サイトで入手できるバイナリ浮動小数点演算の IEEE 標準に関する資料をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="43be1-132">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="43be1-133">浮動小数点値の書式指定には、[標準の数値書式指定文字列](../../../standard/base-types/standard-numeric-format-strings.md)または[カスタムの数値書式指定文字列](../../../standard/base-types/custom-numeric-format-strings.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="43be1-133">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="43be1-134">浮動小数点リテラル</span><span class="sxs-lookup"><span data-stu-id="43be1-134">Floating-point literals</span></span>

<span data-ttu-id="43be1-135">既定では、代入演算子の右側にある浮動小数点数リテラルは `double` として扱われます。</span><span class="sxs-lookup"><span data-stu-id="43be1-135">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="43be1-136">サフィックスを使用して、浮動小数点リテラルまたは整数リテラルを特定の型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="43be1-136">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="43be1-137">`d` または `D` サフィックスによって、リテラルは `double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-137">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="43be1-138">`f` または `F` サフィックスによって、リテラルは `float` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-138">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="43be1-139">`m` または `M` サフィックスによって、リテラルは `decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="43be1-139">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="43be1-140">次の例は、各サフィックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="43be1-140">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="43be1-141">変換</span><span class="sxs-lookup"><span data-stu-id="43be1-141">Conversions</span></span>

<span data-ttu-id="43be1-142">`float` から `double` への暗黙の変換があります (*拡大変換*と呼ばれます)。`float` 値の範囲は `double` の真部分集合であり、`float` から `double` に有効桁数の損失はないためです。</span><span class="sxs-lookup"><span data-stu-id="43be1-142">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span> 

<span data-ttu-id="43be1-143">ソース型からターゲット型への暗黙の型変換が定義されていない場合、ある浮動小数点型を別の浮動小数点型に変換するには、明示的なキャストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43be1-143">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="43be1-144">これは*縮小変換*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="43be1-144">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="43be1-145">変換によりデータが失われる場合があるため、明示的なケースが必要となります。</span><span class="sxs-lookup"><span data-stu-id="43be1-145">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="43be1-146">`decimal` 型は `float` または `double` よりも有効桁数が多いため、他の浮動小数点型と `decimal` 型の間の暗黙の変換はありません。</span><span class="sxs-lookup"><span data-stu-id="43be1-146">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="43be1-147">暗黙的な数値変換の詳細については、「[暗黙的な数値変換の一覧表](../keywords/implicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43be1-147">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="43be1-148">明示的な数値変換の詳細については、「[明示的な数値変換の一覧表](../keywords/explicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43be1-148">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43be1-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="43be1-149">See also</span></span>

- [<span data-ttu-id="43be1-150">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="43be1-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="43be1-151">整数型</span><span class="sxs-lookup"><span data-stu-id="43be1-151">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="43be1-152">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="43be1-152">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="43be1-153">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="43be1-153">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="43be1-154">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="43be1-154">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="43be1-155">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="43be1-155">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="43be1-156">キャストと型変換</span><span class="sxs-lookup"><span data-stu-id="43be1-156">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="43be1-157">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="43be1-157">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="43be1-158">明示的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="43be1-158">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="43be1-159">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="43be1-159">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
