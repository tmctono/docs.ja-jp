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
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 17ae154780679dd1f42f43f1ec345cdc722815d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002196"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="f0b57-103">浮動小数点数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f0b57-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="f0b57-104">**浮動小数点型**は**単純型**のサブセットであり、[*リテラル*](#floating-point-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#floating-point-literals).</span></span> <span data-ttu-id="f0b57-105">すべての浮動小数点型は値の型でもあります。</span><span class="sxs-lookup"><span data-stu-id="f0b57-105">All floating-point types are also value types.</span></span> <span data-ttu-id="f0b57-106">すべての浮動小数点数値型では、[算術](../operators/arithmetic-operators.md)、[比較、および等値](../operators/equality-operators.md)演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="f0b57-107">浮動小数点型の特性</span><span class="sxs-lookup"><span data-stu-id="f0b57-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="f0b57-108">C# では、次の定義済みの浮動小数点型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="f0b57-109">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="f0b57-109">C# type/keyword</span></span>|<span data-ttu-id="f0b57-110">おおよその範囲</span><span class="sxs-lookup"><span data-stu-id="f0b57-110">Approximate range</span></span>|<span data-ttu-id="f0b57-111">Precision</span><span class="sxs-lookup"><span data-stu-id="f0b57-111">Precision</span></span>|<span data-ttu-id="f0b57-112">Size</span><span class="sxs-lookup"><span data-stu-id="f0b57-112">Size</span></span>|<span data-ttu-id="f0b57-113">.NET 型</span><span class="sxs-lookup"><span data-stu-id="f0b57-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="f0b57-114">±1.5 x 10<sup>−45</sup> から ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="f0b57-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="f0b57-115">~6 ～9 桁</span><span class="sxs-lookup"><span data-stu-id="f0b57-115">~6-9 digits</span></span>|<span data-ttu-id="f0b57-116">4 バイト</span><span class="sxs-lookup"><span data-stu-id="f0b57-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="f0b57-117">±5.0 × 10<sup>−324</sup> - ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="f0b57-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="f0b57-118">~15-17 桁</span><span class="sxs-lookup"><span data-stu-id="f0b57-118">~15-17 digits</span></span>|<span data-ttu-id="f0b57-119">8 バイト</span><span class="sxs-lookup"><span data-stu-id="f0b57-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="f0b57-120">±1.0 x 10<sup>-28</sup> から ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="f0b57-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="f0b57-121">28 から 29 桁の数字</span><span class="sxs-lookup"><span data-stu-id="f0b57-121">28-29 digits</span></span>|<span data-ttu-id="f0b57-122">16 バイト</span><span class="sxs-lookup"><span data-stu-id="f0b57-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="f0b57-123">上の表の左端の列にある各 C# 型/キーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="f0b57-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="f0b57-124">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="f0b57-124">They are interchangeable.</span></span> <span data-ttu-id="f0b57-125">たとえば、次の宣言では、同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="f0b57-126">各浮動小数点型の既定値はゼロ `0` です。</span><span class="sxs-lookup"><span data-stu-id="f0b57-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="f0b57-127">各浮動小数点型には、その型の最小および最大有限値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="f0b57-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="f0b57-128">`float` および `double` 型では、数字ではない値や無限値を表す定数も提供されています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="f0b57-129">たとえば、`double` 型では、定数 <xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>、<xref:System.Double.PositiveInfinity?displayProperty=nameWithType> が提供されています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="f0b57-130">`decimal` 型は、`float` と `double` の両方よりも有効桁数が多く、範囲が狭いため、財務や金融の計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="f0b57-131">[整数](integral-numeric-types.md)型と浮動小数点型を 1 つの式の中で混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="f0b57-132">この場合、整数型が浮動小数点型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="f0b57-133">式の評価は、次の規則に従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="f0b57-134">浮動小数点型の 1 つが `double` の場合、式は `double` または [bool](../keywords/bool.md) (リレーショナル比較または等価比較の場合) と評価されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>
- <span data-ttu-id="f0b57-135">式に `double` 型が含まれない場合は、式は `float` または [bool](../keywords/bool.md) (リレーショナル比較または等価比較の場合) と評価されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](../keywords/bool.md) in relational comparisons or comparisons for equality.</span></span>

<span data-ttu-id="f0b57-136">浮動小数点式は、次の値のセットを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="f0b57-137">正および負のゼロ</span><span class="sxs-lookup"><span data-stu-id="f0b57-137">Positive and negative zero</span></span>
- <span data-ttu-id="f0b57-138">正および負の無限大</span><span class="sxs-lookup"><span data-stu-id="f0b57-138">Positive and negative infinity</span></span>
- <span data-ttu-id="f0b57-139">Not-a-Number (NaN) 値</span><span class="sxs-lookup"><span data-stu-id="f0b57-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="f0b57-140">ゼロ以外の値の有限のセット</span><span class="sxs-lookup"><span data-stu-id="f0b57-140">The finite set of nonzero values</span></span>

<span data-ttu-id="f0b57-141">これらの値について詳しくは、[IEEE](https://www.ieee.org) の Web サイトで入手できるバイナリ浮動小数点演算の IEEE 標準に関する資料をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f0b57-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="f0b57-142">浮動小数点値の書式指定には、[標準の数値書式指定文字列](../../../standard/base-types/standard-numeric-format-strings.md)または[カスタムの数値書式指定文字列](../../../standard/base-types/custom-numeric-format-strings.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="floating-point-literals"></a><span data-ttu-id="f0b57-143">浮動小数点リテラル</span><span class="sxs-lookup"><span data-stu-id="f0b57-143">Floating-point literals</span></span>

<span data-ttu-id="f0b57-144">既定では、代入演算子の右側にある浮動小数点数リテラルは `double` として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-144">By default, a floating-point numeric literal on the right side of the assignment operator is treated as `double`.</span></span> <span data-ttu-id="f0b57-145">サフィックスを使用して、浮動小数点リテラルまたは整数リテラルを特定の型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-145">You can use suffixes to convert a floating-point or integral literal to a specific type:</span></span>

- <span data-ttu-id="f0b57-146">`d` または `D` サフィックスによって、リテラルは `double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-146">The `d` or `D` suffix converts a literal to a `double`.</span></span>
- <span data-ttu-id="f0b57-147">`f` または `F` サフィックスによって、リテラルは `float` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-147">The `f` or `F` suffix converts a literal to a `float`.</span></span>
- <span data-ttu-id="f0b57-148">`m` または `M` サフィックスによって、リテラルは `decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="f0b57-148">The `m` or `M` suffix converts a literal to a `decimal`.</span></span>

<span data-ttu-id="f0b57-149">次の例は、各サフィックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-149">The following examples show each suffix:</span></span>

```csharp
double d = 3D;
d = 4d;
float f = 3.5F;
f = 5.4f;
decimal myMoney = 300.5m;
myMoney = 400.75M;
```

## <a name="conversions"></a><span data-ttu-id="f0b57-150">変換</span><span class="sxs-lookup"><span data-stu-id="f0b57-150">Conversions</span></span>

<span data-ttu-id="f0b57-151">`float` から `double` への暗黙の変換があります (*拡大変換*と呼ばれます)。`float` 値の範囲は `double` の真部分集合であり、`float` から `double` に有効桁数の損失はないためです。</span><span class="sxs-lookup"><span data-stu-id="f0b57-151">There's an implicit conversion (called a *widening conversion*) from `float` to `double` because the range of `float` values is a proper subset of `double` and there is no loss of precision from `float` to `double`.</span></span>

<span data-ttu-id="f0b57-152">ソース型からターゲット型への暗黙の型変換が定義されていない場合、ある浮動小数点型を別の浮動小数点型に変換するには、明示的なキャストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0b57-152">You must use an explicit cast to convert one floating-point type to another floating-point type when an implicit conversion isn't defined from the source type to the destination type.</span></span> <span data-ttu-id="f0b57-153">これは*縮小変換*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="f0b57-153">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="f0b57-154">変換によりデータが失われる場合があるため、明示的なケースが必要となります。</span><span class="sxs-lookup"><span data-stu-id="f0b57-154">The explicit case is required because the conversion can result in data loss.</span></span> <span data-ttu-id="f0b57-155">`decimal` 型は `float` または `double` よりも有効桁数が多いため、他の浮動小数点型と `decimal` 型の間の暗黙の変換はありません。</span><span class="sxs-lookup"><span data-stu-id="f0b57-155">There's no implicit conversion between other floating-point types and the `decimal` type because the `decimal` type has greater precision than either `float` or `double`.</span></span>

<span data-ttu-id="f0b57-156">暗黙的な数値変換の詳細については、「[暗黙的な数値変換の一覧表](../keywords/implicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b57-156">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../keywords/implicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="f0b57-157">明示的な数値変換の詳細については、「[明示的な数値変換の一覧表](../keywords/explicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0b57-157">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../keywords/explicit-numeric-conversions-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0b57-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0b57-158">See also</span></span>

- [<span data-ttu-id="f0b57-159">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f0b57-159">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f0b57-160">整数型</span><span class="sxs-lookup"><span data-stu-id="f0b57-160">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="f0b57-161">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="f0b57-161">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="f0b57-162">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="f0b57-162">Numerics in .NET</span></span>](../../../standard/numerics.md)
- [<span data-ttu-id="f0b57-163">キャストと型変換</span><span class="sxs-lookup"><span data-stu-id="f0b57-163">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="f0b57-164">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="f0b57-164">Implicit Numeric Conversions Table</span></span>](../keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="f0b57-165">明示的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="f0b57-165">Explicit Numeric Conversions Table</span></span>](../keywords/explicit-numeric-conversions-table.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- [<span data-ttu-id="f0b57-166">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="f0b57-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="f0b57-167">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="f0b57-167">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
