---
title: 浮動小数点数値型 - C# リファレンス
description: Overview of the built-in C# floating-point types (組み込みの C# 浮動小数点型の概要)
ms.date: 10/22/2019
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
ms.openlocfilehash: 23aa33c6887db48a12f995efc5e1e2220d30216c
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552280"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="56027-103">浮動小数点数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="56027-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="56027-104">**浮動小数点型**は**単純型**のサブセットであり、[*リテラル*](#real-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="56027-104">The **floating-point types** are a subset of the **simple types** and can be initialized with [*literals*](#real-literals).</span></span> <span data-ttu-id="56027-105">すべての浮動小数点型は値の型でもあります。</span><span class="sxs-lookup"><span data-stu-id="56027-105">All floating-point types are also value types.</span></span> <span data-ttu-id="56027-106">すべての浮動小数点数値型は、[算術](../operators/arithmetic-operators.md)、[比較](../operators/comparison-operators.md)、および[等値](../operators/equality-operators.md)演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="56027-106">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="56027-107">浮動小数点型の特性</span><span class="sxs-lookup"><span data-stu-id="56027-107">Characteristics of the floating-point types</span></span>

<span data-ttu-id="56027-108">C# では、次の定義済みの浮動小数点型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="56027-108">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="56027-109">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="56027-109">C# type/keyword</span></span>|<span data-ttu-id="56027-110">おおよその範囲</span><span class="sxs-lookup"><span data-stu-id="56027-110">Approximate range</span></span>|<span data-ttu-id="56027-111">有効桁数</span><span class="sxs-lookup"><span data-stu-id="56027-111">Precision</span></span>|<span data-ttu-id="56027-112">サイズ</span><span class="sxs-lookup"><span data-stu-id="56027-112">Size</span></span>|<span data-ttu-id="56027-113">.NET 型</span><span class="sxs-lookup"><span data-stu-id="56027-113">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="56027-114">±1.5 x 10<sup>−45</sup> から ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="56027-114">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="56027-115">~6 ～9 桁</span><span class="sxs-lookup"><span data-stu-id="56027-115">~6-9 digits</span></span>|<span data-ttu-id="56027-116">4 バイト</span><span class="sxs-lookup"><span data-stu-id="56027-116">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="56027-117">±5.0 × 10<sup>−324</sup> - ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="56027-117">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="56027-118">~15-17 桁</span><span class="sxs-lookup"><span data-stu-id="56027-118">~15-17 digits</span></span>|<span data-ttu-id="56027-119">8 バイト</span><span class="sxs-lookup"><span data-stu-id="56027-119">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="56027-120">±1.0 x 10<sup>-28</sup> から ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="56027-120">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="56027-121">28 から 29 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56027-121">28-29 digits</span></span>|<span data-ttu-id="56027-122">16 バイト</span><span class="sxs-lookup"><span data-stu-id="56027-122">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="56027-123">上の表の左端の列にある各 C# 型/キーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="56027-123">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="56027-124">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="56027-124">They are interchangeable.</span></span> <span data-ttu-id="56027-125">たとえば、次の宣言では、同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="56027-125">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="56027-126">各浮動小数点型の既定値はゼロ `0` です。</span><span class="sxs-lookup"><span data-stu-id="56027-126">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="56027-127">各浮動小数点型には、その型の最小および最大有限値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="56027-127">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="56027-128">`float` および `double` 型では、数字ではない値や無限値を表す定数も提供されています。</span><span class="sxs-lookup"><span data-stu-id="56027-128">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="56027-129">たとえば、`double` 型では、定数 <xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>、<xref:System.Double.PositiveInfinity?displayProperty=nameWithType> が提供されています。</span><span class="sxs-lookup"><span data-stu-id="56027-129">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="56027-130">`decimal` 型は、`float` と `double` の両方よりも有効桁数が多く、範囲が狭いため、財務や金融の計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="56027-130">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="56027-131">[整数](integral-numeric-types.md)型と浮動小数点型を 1 つの式の中で混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="56027-131">You can mix [integral](integral-numeric-types.md) types and floating-point types in an expression.</span></span> <span data-ttu-id="56027-132">この場合、整数型が浮動小数点型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="56027-132">In this case, the integral types are converted to floating-point types.</span></span> <span data-ttu-id="56027-133">式の評価は、次の規則に従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="56027-133">The evaluation of the expression is performed according to the following rules:</span></span>

- <span data-ttu-id="56027-134">浮動小数点型のいずれかが `double` の場合、リレーショナル比較と等価比較で、式は `double`、または[ブール](bool.md)に評価されます。</span><span class="sxs-lookup"><span data-stu-id="56027-134">If one of the floating-point types is `double`, the expression evaluates to `double`, or to [bool](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="56027-135">式に `double` 型がない場合、リレーショナル比較と等価比較で、式は `float`、または[ブール](bool.md)に評価されます。</span><span class="sxs-lookup"><span data-stu-id="56027-135">If there is no `double` type in the expression, the expression evaluates to `float`, or to [bool](bool.md) in relational and equality comparisons.</span></span>

<span data-ttu-id="56027-136">浮動小数点式は、次の値のセットを含むことができます。</span><span class="sxs-lookup"><span data-stu-id="56027-136">A floating-point expression can contain the following sets of values:</span></span>

- <span data-ttu-id="56027-137">正および負のゼロ</span><span class="sxs-lookup"><span data-stu-id="56027-137">Positive and negative zero</span></span>
- <span data-ttu-id="56027-138">正および負の無限大</span><span class="sxs-lookup"><span data-stu-id="56027-138">Positive and negative infinity</span></span>
- <span data-ttu-id="56027-139">Not-a-Number (NaN) 値</span><span class="sxs-lookup"><span data-stu-id="56027-139">Not-a-Number value (NaN)</span></span>
- <span data-ttu-id="56027-140">ゼロ以外の値の有限のセット</span><span class="sxs-lookup"><span data-stu-id="56027-140">The finite set of nonzero values</span></span>

<span data-ttu-id="56027-141">これらの値について詳しくは、[IEEE](https://www.ieee.org) の Web サイトで入手できるバイナリ浮動小数点演算の IEEE 標準に関する資料をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="56027-141">For more information about these values, see IEEE Standard for Binary Floating-Point Arithmetic, available on the [IEEE](https://www.ieee.org) website.</span></span>

<span data-ttu-id="56027-142">浮動小数点値の書式指定には、[標準の数値書式指定文字列](../../../standard/base-types/standard-numeric-format-strings.md)または[カスタムの数値書式指定文字列](../../../standard/base-types/custom-numeric-format-strings.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="56027-142">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="56027-143">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="56027-143">Real literals</span></span>

<span data-ttu-id="56027-144">実数リテラルの型は、サフィックスによって次のように決まります。</span><span class="sxs-lookup"><span data-stu-id="56027-144">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="56027-145">サフィックスがない、または `d` または `D` のリテラルは `double` 型です</span><span class="sxs-lookup"><span data-stu-id="56027-145">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="56027-146">サフィックスが `f` または `F` のリテラルは `float` 型です</span><span class="sxs-lookup"><span data-stu-id="56027-146">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="56027-147">サフィックスが `m` または `M` のリテラルは `decimal` 型です</span><span class="sxs-lookup"><span data-stu-id="56027-147">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="56027-148">次のコードは、それぞれの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="56027-148">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="56027-149">前述の例は、C# 7.0 以降でサポートされている "*桁区切り記号*" としての `_` の使用法も示しています。</span><span class="sxs-lookup"><span data-stu-id="56027-149">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="56027-150">数字区切り記号は、あらゆる種類の数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="56027-150">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="56027-151">次の例に示すように、指数表記を使用して、実数リテラルの指数部を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="56027-151">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="56027-152">変換</span><span class="sxs-lookup"><span data-stu-id="56027-152">Conversions</span></span>

<span data-ttu-id="56027-153">浮動小数点数値型の間には、`float` から `double` に対する暗黙的な変換が 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="56027-153">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="56027-154">ただし、[明示的なキャスト](../operators/type-testing-and-cast.md#cast-operator-)を使用して、任意の浮動小数点型を他の浮動小数点型に変換することはできます。</span><span class="sxs-lookup"><span data-stu-id="56027-154">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-operator-).</span></span> <span data-ttu-id="56027-155">詳細については、「[組み込みの数値変換](numeric-conversions.md)」に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56027-155">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="56027-156">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="56027-156">C# language specification</span></span>

<span data-ttu-id="56027-157">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="56027-157">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="56027-158">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="56027-158">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="56027-159">decimal 型</span><span class="sxs-lookup"><span data-stu-id="56027-159">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="56027-160">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="56027-160">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="56027-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="56027-161">See also</span></span>

- [<span data-ttu-id="56027-162">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="56027-162">C# reference</span></span>](../index.md)
- [<span data-ttu-id="56027-163">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="56027-163">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="56027-164">整数型</span><span class="sxs-lookup"><span data-stu-id="56027-164">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="56027-165">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="56027-165">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="56027-166">標準の数値書式指定文字列</span><span class="sxs-lookup"><span data-stu-id="56027-166">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="56027-167">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="56027-167">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
