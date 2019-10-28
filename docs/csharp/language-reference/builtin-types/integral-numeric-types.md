---
title: 整数数値型 - C# リファレンス
description: 各整数数値型の範囲、ストレージ サイズ、および使用方法について説明します。
ms.date: 10/18/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579193"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="12fe3-103">整数数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="12fe3-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="12fe3-104">**整数数値型**は**単純型**のサブセットであり、[*リテラル*](#integer-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="12fe3-105">すべての整数型は、値型でもあります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-105">All integral types are also value types.</span></span> <span data-ttu-id="12fe3-106">すべての整数数値型では、[算術](../operators/arithmetic-operators.md)、[ビット論理](../operators/bitwise-and-shift-operators.md)、[比較](../operators/comparison-operators.md)、[等値](../operators/equality-operators.md)演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="12fe3-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="12fe3-107">整数型の特性</span><span class="sxs-lookup"><span data-stu-id="12fe3-107">Characteristics of the integral types</span></span>

<span data-ttu-id="12fe3-108">C# では、次の定義済みの整数型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="12fe3-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="12fe3-109">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="12fe3-109">C# type/keyword</span></span>|<span data-ttu-id="12fe3-110">範囲</span><span class="sxs-lookup"><span data-stu-id="12fe3-110">Range</span></span>|<span data-ttu-id="12fe3-111">サイズ</span><span class="sxs-lookup"><span data-stu-id="12fe3-111">Size</span></span>|<span data-ttu-id="12fe3-112">.NET 型</span><span class="sxs-lookup"><span data-stu-id="12fe3-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="12fe3-113">-128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="12fe3-113">-128 to 127</span></span>|<span data-ttu-id="12fe3-114">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="12fe3-115">0 ～ 255</span><span class="sxs-lookup"><span data-stu-id="12fe3-115">0 to 255</span></span>|<span data-ttu-id="12fe3-116">符号なし 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="12fe3-117">-32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="12fe3-117">-32,768 to 32,767</span></span>|<span data-ttu-id="12fe3-118">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="12fe3-119">0 ～ 65,535</span><span class="sxs-lookup"><span data-stu-id="12fe3-119">0 to 65,535</span></span>|<span data-ttu-id="12fe3-120">符号なし 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="12fe3-121">-2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="12fe3-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="12fe3-122">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="12fe3-123">0 ～ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="12fe3-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="12fe3-124">符号なし 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="12fe3-125">-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="12fe3-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="12fe3-126">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="12fe3-127">0 ～ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="12fe3-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="12fe3-128">符号なし 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="12fe3-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="12fe3-129">上の表で、左端の列にある各 C# 型のキーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="12fe3-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="12fe3-130">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="12fe3-130">They are interchangeable.</span></span> <span data-ttu-id="12fe3-131">たとえば、次の宣言では同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="12fe3-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="12fe3-132">各整数型の既定値はゼロ (`0`) です。</span><span class="sxs-lookup"><span data-stu-id="12fe3-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="12fe3-133">各整数型には、その型の最小値と最大値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="12fe3-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 構造体を使用して、上限や下限のない符号付き整数を表します。</span><span class="sxs-lookup"><span data-stu-id="12fe3-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="12fe3-135">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="12fe3-135">Integer literals</span></span>

<span data-ttu-id="12fe3-136">次の整数リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-136">Integer literals can be</span></span>

- <span data-ttu-id="12fe3-137">"*10 進*": プレフィックスなし</span><span class="sxs-lookup"><span data-stu-id="12fe3-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="12fe3-138">"*16 進*": `0x` または `0X` プレフィックスを使用します</span><span class="sxs-lookup"><span data-stu-id="12fe3-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="12fe3-139">"*バイナリ*": `0b` または `0B` プレフィックスを使用します (C# 7.0 以降で使用できます)</span><span class="sxs-lookup"><span data-stu-id="12fe3-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="12fe3-140">次のコードは、それぞれの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="12fe3-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="12fe3-141">前述の例は、C# 7.0 以降でサポートされている "*桁区切り記号*" としての `_` の使用法も示しています。</span><span class="sxs-lookup"><span data-stu-id="12fe3-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="12fe3-142">数字区切り記号は、あらゆる種類の数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="12fe3-143">整数リテラルの型は、そのサフィックスによって次のように決まります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="12fe3-144">サフィックスがないリテラルの型は、`int`、`uint`、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="12fe3-145">リテラルのサフィックスが `U` または `u` の場合、その型は、`uint`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="12fe3-146">リテラルのサフィックスが `L` または `l` の場合、その型は、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="12fe3-147">小文字の `l` はサフィックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="12fe3-148">ただし、文字の `l` は数字の `1` と混同しやすいため、コンパイラから警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="12fe3-149">わかりやすくするために `L` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="12fe3-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="12fe3-150">リテラルのサフィックスが `UL`、`Ul`、`uL`、`ul`、`LU`、`Lu`、`lU`、または `lu` の場合、その型は `ulong` です。</span><span class="sxs-lookup"><span data-stu-id="12fe3-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="12fe3-151">整数リテラルで表される値が <xref:System.UInt64.MaxValue?displayProperty=nameWithType> を超えると、コンパイル エラー [CS1021](../../misc/cs1021.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="12fe3-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="12fe3-152">整数リテラルによって表される値は、リテラルの特定の型よりも範囲が狭い型に暗黙的に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-152">The value represented by an integer literal can be implicitly converted to a type with a smaller range than the determined type of the literal.</span></span> <span data-ttu-id="12fe3-153">これは、値が変換先の型の範囲内にある場合に実行できます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-153">That's possible when the value is within the range of the destination type:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="12fe3-154">前の例で示したように、リテラルの値が変換先の型の範囲内にない場合、コンパイラ エラー [CS0031](../../misc/cs0031.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="12fe3-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="12fe3-155">また、キャストを使用して、整数リテラルによって表される値を、指定された型のリテラル以外の型に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="12fe3-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="12fe3-156">変換</span><span class="sxs-lookup"><span data-stu-id="12fe3-156">Conversions</span></span>

<span data-ttu-id="12fe3-157">変換先の型に変換元の型のすべての値を格納可能な、任意の 2 つの整数型間の暗黙的な変換 (*拡大変換*と呼ばれます) があります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="12fe3-158">たとえば、`int` 値の範囲が `long` の適切なサブセットであるため、`int` から `long` への暗黙的な変換があります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="12fe3-159">小さな符号なし整数型から、大きな符号付き整数型への暗黙的な変換があります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="12fe3-160">任意の整数型から、任意の浮動小数点型への暗黙的な変換もあります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="12fe3-161">任意の符号付き整数型から、任意の符号なし整数型への暗黙的な変換はありません。</span><span class="sxs-lookup"><span data-stu-id="12fe3-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="12fe3-162">変換元の型から変換先の型への暗黙的な変換が定義されていない場合、明示的なキャストを使用して、1 つの整数型を別の整数型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="12fe3-163">これは*縮小変換*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="12fe3-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="12fe3-164">変換によりデータが失われる場合があるため、明示的なケースが必要となります。</span><span class="sxs-lookup"><span data-stu-id="12fe3-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12fe3-165">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="12fe3-165">C# language specification</span></span>

<span data-ttu-id="12fe3-166">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12fe3-166">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="12fe3-167">整数型</span><span class="sxs-lookup"><span data-stu-id="12fe3-167">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="12fe3-168">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="12fe3-168">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="12fe3-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="12fe3-169">See also</span></span>

- [<span data-ttu-id="12fe3-170">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="12fe3-170">C# reference</span></span>](../index.md)
- [<span data-ttu-id="12fe3-171">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="12fe3-171">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="12fe3-172">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="12fe3-172">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="12fe3-173">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="12fe3-173">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="12fe3-174">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="12fe3-174">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="12fe3-175">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="12fe3-175">Numerics in .NET</span></span>](../../../standard/numerics.md)
