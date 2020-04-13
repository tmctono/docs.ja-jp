---
title: 浮動小数点数値型 - C# リファレンス
description: 組み込みの C# 浮動小数点型 (float、double、decimal) について説明します
ms.date: 02/10/2020
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
ms.openlocfilehash: a277215d438b5f6b0bbbef72e5e0121b6ce41990
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121483"
---
# <a name="floating-point-numeric-types-c-reference"></a><span data-ttu-id="2b896-103">浮動小数点数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2b896-103">Floating-point numeric types (C# reference)</span></span>

<span data-ttu-id="2b896-104">"*浮動小数点数値型*" は実数を表します。</span><span class="sxs-lookup"><span data-stu-id="2b896-104">The *floating-point numeric types* represent real numbers.</span></span> <span data-ttu-id="2b896-105">浮動小数点数値型は、[値の型](value-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="2b896-105">All floating-point numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="2b896-106">また、[単純型](value-types.md#built-in-value-types)でもあり、[リテラル](#real-literals)を使用して初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="2b896-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#real-literals).</span></span> <span data-ttu-id="2b896-107">すべての浮動小数点数値型は、[算術](../operators/arithmetic-operators.md)、[比較](../operators/comparison-operators.md)、および[等値](../operators/equality-operators.md)演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2b896-107">All floating-point numeric types support [arithmetic](../operators/arithmetic-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-floating-point-types"></a><span data-ttu-id="2b896-108">浮動小数点型の特性</span><span class="sxs-lookup"><span data-stu-id="2b896-108">Characteristics of the floating-point types</span></span>

<span data-ttu-id="2b896-109">C# では、次の定義済みの浮動小数点型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2b896-109">C# supports the following predefined floating-point types:</span></span>
  
|<span data-ttu-id="2b896-110">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="2b896-110">C# type/keyword</span></span>|<span data-ttu-id="2b896-111">おおよその範囲</span><span class="sxs-lookup"><span data-stu-id="2b896-111">Approximate range</span></span>|<span data-ttu-id="2b896-112">Precision</span><span class="sxs-lookup"><span data-stu-id="2b896-112">Precision</span></span>|<span data-ttu-id="2b896-113">Size</span><span class="sxs-lookup"><span data-stu-id="2b896-113">Size</span></span>|<span data-ttu-id="2b896-114">.NET の種類</span><span class="sxs-lookup"><span data-stu-id="2b896-114">.NET type</span></span>|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|<span data-ttu-id="2b896-115">±1.5 x 10<sup>−45</sup> から ±3.4 x 10<sup>38</sup></span><span class="sxs-lookup"><span data-stu-id="2b896-115">±1.5 x 10<sup>−45</sup> to ±3.4 x 10<sup>38</sup></span></span>|<span data-ttu-id="2b896-116">~6 ～9 桁</span><span class="sxs-lookup"><span data-stu-id="2b896-116">~6-9 digits</span></span>|<span data-ttu-id="2b896-117">4 バイト</span><span class="sxs-lookup"><span data-stu-id="2b896-117">4 bytes</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|`double`|<span data-ttu-id="2b896-118">±5.0 × 10<sup>−324</sup> - ±1.7 × 10<sup>308</sup></span><span class="sxs-lookup"><span data-stu-id="2b896-118">±5.0 × 10<sup>−324</sup> to ±1.7 × 10<sup>308</sup></span></span>|<span data-ttu-id="2b896-119">~15-17 桁</span><span class="sxs-lookup"><span data-stu-id="2b896-119">~15-17 digits</span></span>|<span data-ttu-id="2b896-120">8 バイト</span><span class="sxs-lookup"><span data-stu-id="2b896-120">8 bytes</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|<span data-ttu-id="2b896-121">±1.0 x 10<sup>-28</sup> から ±7.9228 x 10<sup>28</sup></span><span class="sxs-lookup"><span data-stu-id="2b896-121">±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup></span></span>|<span data-ttu-id="2b896-122">28 から 29 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2b896-122">28-29 digits</span></span>|<span data-ttu-id="2b896-123">16 バイト</span><span class="sxs-lookup"><span data-stu-id="2b896-123">16 bytes</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|

<span data-ttu-id="2b896-124">上の表で、左端の列にある各 C# 型のキーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="2b896-124">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="2b896-125">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="2b896-125">They are interchangeable.</span></span> <span data-ttu-id="2b896-126">たとえば、次の宣言では同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="2b896-126">For example, the following declarations declare variables of the same type:</span></span>

```csharp
double a = 12.3;
System.Double b = 12.3;
```

<span data-ttu-id="2b896-127">各浮動小数点型の既定値はゼロ `0` です。</span><span class="sxs-lookup"><span data-stu-id="2b896-127">The default value of each floating-point type is zero, `0`.</span></span> <span data-ttu-id="2b896-128">各浮動小数点型には、その型の最小および最大有限値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="2b896-128">Each of the floating-point types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum finite value of that type.</span></span> <span data-ttu-id="2b896-129">`float` および `double` 型では、数字ではない値や無限値を表す定数も提供されています。</span><span class="sxs-lookup"><span data-stu-id="2b896-129">The `float` and `double` types also provide constants that represent not-a-number and infinity values.</span></span> <span data-ttu-id="2b896-130">たとえば、`double` 型では、定数 <xref:System.Double.NaN?displayProperty=nameWithType>、<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>、<xref:System.Double.PositiveInfinity?displayProperty=nameWithType> が提供されています。</span><span class="sxs-lookup"><span data-stu-id="2b896-130">For example, the `double` type provides the following constants: <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>, and <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="2b896-131">`decimal` 型は、`float` と `double` の両方よりも有効桁数が多く、範囲が狭いため、財務や金融の計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="2b896-131">Because the `decimal` type has more precision and a smaller range than both `float` and `double`, it's appropriate for financial and monetary calculations.</span></span>

<span data-ttu-id="2b896-132">[整数](integral-numeric-types.md)型と `float` および `double` 型を 1 つの式の中で混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="2b896-132">You can mix [integral](integral-numeric-types.md) types and the `float` and `double` types in an expression.</span></span> <span data-ttu-id="2b896-133">この場合、整数型は、浮動小数点型の 1 つに暗黙的に変換されます。また、必要に応じて、`float` 型は `double` に暗黙的に変換されます。</span><span class="sxs-lookup"><span data-stu-id="2b896-133">In this case, integral types are implicitly converted to one of the floating-point types and, if necessary, the `float` type is implicitly converted to `double`.</span></span> <span data-ttu-id="2b896-134">この式は、次のように評価されます。</span><span class="sxs-lookup"><span data-stu-id="2b896-134">The expression is evaluated as follows:</span></span>

- <span data-ttu-id="2b896-135">式に `double` 型がある場合、リレーショナル比較と等価比較で、式は `double`、または [`bool`](bool.md) に評価されます。</span><span class="sxs-lookup"><span data-stu-id="2b896-135">If there is `double` type in the expression, the expression evaluates to `double`, or to [`bool`](bool.md) in relational and equality comparisons.</span></span>
- <span data-ttu-id="2b896-136">式に `double` 型がない場合、リレーショナル比較と等価比較で、式は `float`、または `bool` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="2b896-136">If there is no `double` type in the expression, the expression evaluates to `float`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="2b896-137">また、整数型と `decimal` 型を 1 つの式の中で混在させることもできます。</span><span class="sxs-lookup"><span data-stu-id="2b896-137">You can also mix integral types and the `decimal` type in an expression.</span></span> <span data-ttu-id="2b896-138">この場合、整数型は `decimal` 型に暗黙的に変換され、リレーショナル比較と等価比較で、式は `decimal`、または `bool` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="2b896-138">In this case, integral types are implicitly converted to the `decimal` type and the expression evaluates to `decimal`, or to `bool` in relational and equality comparisons.</span></span>

<span data-ttu-id="2b896-139">`decimal` 型と `float` および `double` 型を 1 つの式の中で混在させることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b896-139">You cannot mix the `decimal` type with the `float` and `double` types in an expression.</span></span> <span data-ttu-id="2b896-140">この場合、算術演算、比較演算、または等値演算を実行するには、次の例に示すように、`decimal` 型との間でオペランドを明示的に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b896-140">In this case, if you want to perform arithmetic, comparison, or equality operations, you must explicitly convert the operands either from or to the `decimal` type, as the following example shows:</span></span>

```csharp-interactive
double a = 1.0;
decimal b = 2.1m;
Console.WriteLine(a + (double)b);
Console.WriteLine((decimal)a + b);
```

<span data-ttu-id="2b896-141">浮動小数点値の書式指定には、[標準の数値書式指定文字列](../../../standard/base-types/standard-numeric-format-strings.md)または[カスタムの数値書式指定文字列](../../../standard/base-types/custom-numeric-format-strings.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b896-141">You can use either [standard numeric format strings](../../../standard/base-types/standard-numeric-format-strings.md) or [custom numeric format strings](../../../standard/base-types/custom-numeric-format-strings.md) to format a floating-point value.</span></span>

## <a name="real-literals"></a><span data-ttu-id="2b896-142">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="2b896-142">Real literals</span></span>

<span data-ttu-id="2b896-143">実数リテラルの型は、サフィックスによって次のように決まります。</span><span class="sxs-lookup"><span data-stu-id="2b896-143">The type of a real literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="2b896-144">サフィックスがない、または `d` または `D` のリテラルは `double` 型です</span><span class="sxs-lookup"><span data-stu-id="2b896-144">The literal without suffix or with the `d` or `D` suffix is of type `double`</span></span>
- <span data-ttu-id="2b896-145">サフィックスが `f` または `F` のリテラルは `float` 型です</span><span class="sxs-lookup"><span data-stu-id="2b896-145">The literal with the `f` or `F` suffix is of type `float`</span></span>
- <span data-ttu-id="2b896-146">サフィックスが `m` または `M` のリテラルは `decimal` 型です</span><span class="sxs-lookup"><span data-stu-id="2b896-146">The literal with the `m` or `M` suffix is of type `decimal`</span></span>

<span data-ttu-id="2b896-147">次のコードは、それぞれの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b896-147">The following code demonstrates an example of each:</span></span>

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

<span data-ttu-id="2b896-148">前述の例は、C# 7.0 以降でサポートされている "`_`桁区切り記号 *" としての*  の使用法も示しています。</span><span class="sxs-lookup"><span data-stu-id="2b896-148">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="2b896-149">数字区切り記号は、あらゆる種類の数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b896-149">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="2b896-150">次の例に示すように、指数表記を使用して、実数リテラルの指数部を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b896-150">You also can use scientific notation, that is, specify an exponent part of a real literal, as the following example shows:</span></span>

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a><span data-ttu-id="2b896-151">コンバージョン</span><span class="sxs-lookup"><span data-stu-id="2b896-151">Conversions</span></span>

<span data-ttu-id="2b896-152">浮動小数点数値型の間には、`float` から `double` に対する暗黙的な変換が 1 つだけあります。</span><span class="sxs-lookup"><span data-stu-id="2b896-152">There is only one implicit conversion between floating-point numeric types: from `float` to `double`.</span></span> <span data-ttu-id="2b896-153">ただし、[明示的なキャスト](../operators/type-testing-and-cast.md#cast-expression)を使用して、任意の浮動小数点型を他の浮動小数点型に変換することはできます。</span><span class="sxs-lookup"><span data-stu-id="2b896-153">However, you can convert any floating-point type to any other floating-point type with the [explicit cast](../operators/type-testing-and-cast.md#cast-expression).</span></span> <span data-ttu-id="2b896-154">詳細については、「[Built-in numeric conversions](numeric-conversions.md)」(組み込みの数値変換) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b896-154">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2b896-155">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2b896-155">C# language specification</span></span>

<span data-ttu-id="2b896-156">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b896-156">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="2b896-157">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="2b896-157">Floating-point types</span></span>](~/_csharplang/spec/types.md#floating-point-types)
- [<span data-ttu-id="2b896-158">decimal 型</span><span class="sxs-lookup"><span data-stu-id="2b896-158">The decimal type</span></span>](~/_csharplang/spec/types.md#the-decimal-type)
- [<span data-ttu-id="2b896-159">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="2b896-159">Real literals</span></span>](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a><span data-ttu-id="2b896-160">参照</span><span class="sxs-lookup"><span data-stu-id="2b896-160">See also</span></span>

- [<span data-ttu-id="2b896-161">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2b896-161">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2b896-162">値型</span><span class="sxs-lookup"><span data-stu-id="2b896-162">Value types</span></span>](value-types.md)
- [<span data-ttu-id="2b896-163">整数型</span><span class="sxs-lookup"><span data-stu-id="2b896-163">Integral types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="2b896-164">標準の数値書式指定文字列</span><span class="sxs-lookup"><span data-stu-id="2b896-164">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="2b896-165">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="2b896-165">Numerics in .NET</span></span>](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
