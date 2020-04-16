---
title: 整数数値型 - C# リファレンス
description: 各整数数値型の範囲、ストレージ サイズ、および使用方法について説明します。
ms.date: 10/22/2019
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
ms.openlocfilehash: 4b2506f48c3e72ff838a07087c8c5d9ea63bb46c
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121467"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="964e7-103">整数数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="964e7-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="964e7-104">"*整数数値型*" は、整数値を表します。</span><span class="sxs-lookup"><span data-stu-id="964e7-104">The *integral numeric types* represent integer numbers.</span></span> <span data-ttu-id="964e7-105">すべての整数数値型は、[値の型](value-types.md)です。</span><span class="sxs-lookup"><span data-stu-id="964e7-105">All integral numeric types are [value types](value-types.md).</span></span> <span data-ttu-id="964e7-106">また、[単純型](value-types.md#built-in-value-types)でもあり、[リテラル](#integer-literals)を使用して初期化することができます。</span><span class="sxs-lookup"><span data-stu-id="964e7-106">They are also [simple types](value-types.md#built-in-value-types) and can be initialized with [literals](#integer-literals).</span></span> <span data-ttu-id="964e7-107">すべての整数数値型では、[算術](../operators/arithmetic-operators.md)、[ビット論理](../operators/bitwise-and-shift-operators.md)、[比較](../operators/comparison-operators.md)、[等値](../operators/equality-operators.md)演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="964e7-107">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="964e7-108">整数型の特性</span><span class="sxs-lookup"><span data-stu-id="964e7-108">Characteristics of the integral types</span></span>

<span data-ttu-id="964e7-109">C# では、次の定義済みの整数型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="964e7-109">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="964e7-110">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="964e7-110">C# type/keyword</span></span>|<span data-ttu-id="964e7-111">範囲</span><span class="sxs-lookup"><span data-stu-id="964e7-111">Range</span></span>|<span data-ttu-id="964e7-112">サイズ</span><span class="sxs-lookup"><span data-stu-id="964e7-112">Size</span></span>|<span data-ttu-id="964e7-113">.NET 型</span><span class="sxs-lookup"><span data-stu-id="964e7-113">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="964e7-114">-128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="964e7-114">-128 to 127</span></span>|<span data-ttu-id="964e7-115">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-115">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="964e7-116">0 ～ 255</span><span class="sxs-lookup"><span data-stu-id="964e7-116">0 to 255</span></span>|<span data-ttu-id="964e7-117">符号なし 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-117">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="964e7-118">-32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="964e7-118">-32,768 to 32,767</span></span>|<span data-ttu-id="964e7-119">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-119">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="964e7-120">0 ～ 65,535</span><span class="sxs-lookup"><span data-stu-id="964e7-120">0 to 65,535</span></span>|<span data-ttu-id="964e7-121">符号なし 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-121">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="964e7-122">-2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="964e7-122">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="964e7-123">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-123">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="964e7-124">0 ～ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="964e7-124">0 to 4,294,967,295</span></span>|<span data-ttu-id="964e7-125">符号なし 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-125">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="964e7-126">-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="964e7-126">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="964e7-127">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-127">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="964e7-128">0 ～ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="964e7-128">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="964e7-129">符号なし 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="964e7-129">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="964e7-130">上の表で、左端の列にある各 C# 型のキーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="964e7-130">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="964e7-131">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="964e7-131">They are interchangeable.</span></span> <span data-ttu-id="964e7-132">たとえば、次の宣言では同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="964e7-132">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="964e7-133">各整数型の既定値はゼロ (`0`) です。</span><span class="sxs-lookup"><span data-stu-id="964e7-133">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="964e7-134">各整数型には、その型の最小値と最大値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="964e7-134">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="964e7-135"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 構造体を使用して、上限や下限のない符号付き整数を表します。</span><span class="sxs-lookup"><span data-stu-id="964e7-135">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="964e7-136">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="964e7-136">Integer literals</span></span>

<span data-ttu-id="964e7-137">次の整数リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="964e7-137">Integer literals can be</span></span>

- <span data-ttu-id="964e7-138">"*10 進*": プレフィックスなし</span><span class="sxs-lookup"><span data-stu-id="964e7-138">*decimal*: without any prefix</span></span>
- <span data-ttu-id="964e7-139">"*16 進*": `0x` または `0X` プレフィックスを使用します</span><span class="sxs-lookup"><span data-stu-id="964e7-139">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="964e7-140">"*バイナリ*": `0b` または `0B` プレフィックスを使用します (C# 7.0 以降で使用できます)</span><span class="sxs-lookup"><span data-stu-id="964e7-140">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="964e7-141">次のコードは、それぞれの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="964e7-141">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="964e7-142">前述の例は、C# 7.0 以降でサポートされている "*桁区切り記号*" としての `_` の使用法も示しています。</span><span class="sxs-lookup"><span data-stu-id="964e7-142">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="964e7-143">数字区切り記号は、あらゆる種類の数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="964e7-143">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="964e7-144">整数リテラルの型は、そのサフィックスによって次のように決まります。</span><span class="sxs-lookup"><span data-stu-id="964e7-144">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="964e7-145">サフィックスがないリテラルの型は、`int`、`uint`、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="964e7-145">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="964e7-146">リテラルのサフィックスが `U` または `u` の場合、その型は、`uint`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="964e7-146">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="964e7-147">リテラルのサフィックスが `L` または `l` の場合、その型は、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="964e7-147">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="964e7-148">小文字の `l` はサフィックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="964e7-148">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="964e7-149">ただし、文字の `l` は数字の `1` と混同しやすいため、コンパイラから警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="964e7-149">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="964e7-150">わかりやすくするために `L` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="964e7-150">Use `L` for clarity.</span></span>

- <span data-ttu-id="964e7-151">リテラルのサフィックスが `UL`、`Ul`、`uL`、`ul`、`LU`、`Lu`、`lU`、または `lu` の場合、その型は `ulong` です。</span><span class="sxs-lookup"><span data-stu-id="964e7-151">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="964e7-152">整数リテラルで表される値が <xref:System.UInt64.MaxValue?displayProperty=nameWithType> を超えると、コンパイル エラー [CS1021](../../misc/cs1021.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="964e7-152">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="964e7-153">整数リテラルの決定された型が `int` で、リテラルで表される値が変換先の型の範囲内にある場合、値を暗黙的に `sbyte`、`byte`、`short`、`ushort`、`uint`、または `ulong` に変換できます。</span><span class="sxs-lookup"><span data-stu-id="964e7-153">If the determined type of an integer literal is `int` and the value represented by the literal is within the range of the destination type, the value can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="964e7-154">前の例で示したように、リテラルの値が変換先の型の範囲内にない場合、コンパイラ エラー [CS0031](../../misc/cs0031.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="964e7-154">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="964e7-155">また、キャストを使用して、整数リテラルによって表される値を、指定された型のリテラル以外の型に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="964e7-155">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="964e7-156">変換</span><span class="sxs-lookup"><span data-stu-id="964e7-156">Conversions</span></span>

<span data-ttu-id="964e7-157">任意の整数数値型を他の整数数値型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="964e7-157">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="964e7-158">変換先の型に変換元の型のすべての値を格納できる場合、変換は暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="964e7-158">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="964e7-159">それ以外の場合は、[キャスト式](../operators/type-testing-and-cast.md#cast-expression)を使用して明示的な変換を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="964e7-159">Otherwise, you need to use a [cast expression](../operators/type-testing-and-cast.md#cast-expression) to perform an explicit conversion.</span></span> <span data-ttu-id="964e7-160">詳細については、「[組み込みの数値変換](numeric-conversions.md)」に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="964e7-160">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="964e7-161">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="964e7-161">C# language specification</span></span>

<span data-ttu-id="964e7-162">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="964e7-162">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="964e7-163">整数型</span><span class="sxs-lookup"><span data-stu-id="964e7-163">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="964e7-164">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="964e7-164">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="964e7-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="964e7-165">See also</span></span>

- [<span data-ttu-id="964e7-166">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="964e7-166">C# reference</span></span>](../index.md)
- [<span data-ttu-id="964e7-167">値型</span><span class="sxs-lookup"><span data-stu-id="964e7-167">Value types</span></span>](value-types.md)
- [<span data-ttu-id="964e7-168">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="964e7-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="964e7-169">標準の数値書式指定文字列</span><span class="sxs-lookup"><span data-stu-id="964e7-169">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="964e7-170">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="964e7-170">Numerics in .NET</span></span>](../../../standard/numerics.md)
