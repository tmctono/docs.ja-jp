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
ms.openlocfilehash: c255711e4b165fdca27d50c6bd0f2debfe15ae25
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773867"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="55b0c-103">整数数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="55b0c-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="55b0c-104">**整数数値型**は**単純型**のサブセットであり、[*リテラル*](#integer-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integer-literals).</span></span> <span data-ttu-id="55b0c-105">すべての整数型は、値型でもあります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-105">All integral types are also value types.</span></span> <span data-ttu-id="55b0c-106">すべての整数数値型では、[算術](../operators/arithmetic-operators.md)、[ビット論理](../operators/bitwise-and-shift-operators.md)、[比較](../operators/comparison-operators.md)、[等値](../operators/equality-operators.md)演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55b0c-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison](../operators/comparison-operators.md), and [equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="55b0c-107">整数型の特性</span><span class="sxs-lookup"><span data-stu-id="55b0c-107">Characteristics of the integral types</span></span>

<span data-ttu-id="55b0c-108">C# では、次の定義済みの整数型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55b0c-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="55b0c-109">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="55b0c-109">C# type/keyword</span></span>|<span data-ttu-id="55b0c-110">範囲</span><span class="sxs-lookup"><span data-stu-id="55b0c-110">Range</span></span>|<span data-ttu-id="55b0c-111">サイズ</span><span class="sxs-lookup"><span data-stu-id="55b0c-111">Size</span></span>|<span data-ttu-id="55b0c-112">.NET 型</span><span class="sxs-lookup"><span data-stu-id="55b0c-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="55b0c-113">-128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="55b0c-113">-128 to 127</span></span>|<span data-ttu-id="55b0c-114">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="55b0c-115">0 ～ 255</span><span class="sxs-lookup"><span data-stu-id="55b0c-115">0 to 255</span></span>|<span data-ttu-id="55b0c-116">符号なし 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="55b0c-117">-32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="55b0c-117">-32,768 to 32,767</span></span>|<span data-ttu-id="55b0c-118">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="55b0c-119">0 ～ 65,535</span><span class="sxs-lookup"><span data-stu-id="55b0c-119">0 to 65,535</span></span>|<span data-ttu-id="55b0c-120">符号なし 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="55b0c-121">-2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="55b0c-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="55b0c-122">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="55b0c-123">0 ～ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="55b0c-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="55b0c-124">符号なし 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="55b0c-125">-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="55b0c-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="55b0c-126">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="55b0c-127">0 ～ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="55b0c-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="55b0c-128">符号なし 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="55b0c-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="55b0c-129">上の表で、左端の列にある各 C# 型のキーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="55b0c-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="55b0c-130">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="55b0c-130">They are interchangeable.</span></span> <span data-ttu-id="55b0c-131">たとえば、次の宣言では同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="55b0c-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="55b0c-132">各整数型の既定値はゼロ (`0`) です。</span><span class="sxs-lookup"><span data-stu-id="55b0c-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="55b0c-133">各整数型には、その型の最小値と最大値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="55b0c-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 構造体を使用して、上限や下限のない符号付き整数を表します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="55b0c-135">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="55b0c-135">Integer literals</span></span>

<span data-ttu-id="55b0c-136">次の整数リテラルがあります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-136">Integer literals can be</span></span>

- <span data-ttu-id="55b0c-137">"*10 進*": プレフィックスなし</span><span class="sxs-lookup"><span data-stu-id="55b0c-137">*decimal*: without any prefix</span></span>
- <span data-ttu-id="55b0c-138">"*16 進*": `0x` または `0X` プレフィックスを使用します</span><span class="sxs-lookup"><span data-stu-id="55b0c-138">*hexadecimal*: with the `0x` or `0X` prefix</span></span>
- <span data-ttu-id="55b0c-139">"*バイナリ*": `0b` または `0B` プレフィックスを使用します (C# 7.0 以降で使用できます)</span><span class="sxs-lookup"><span data-stu-id="55b0c-139">*binary*: with the `0b` or `0B` prefix (available in C# 7.0 and later)</span></span>

<span data-ttu-id="55b0c-140">次のコードは、それぞれの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="55b0c-140">The following code demonstrates an example of each:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="55b0c-141">前述の例は、C# 7.0 以降でサポートされている "*桁区切り記号*" としての `_` の使用法も示しています。</span><span class="sxs-lookup"><span data-stu-id="55b0c-141">The preceding example also shows the use of `_` as a *digit separator*, which is supported starting with C# 7.0.</span></span> <span data-ttu-id="55b0c-142">数字区切り記号は、あらゆる種類の数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-142">You can use the digit separator with all kinds of numeric literals.</span></span>

<span data-ttu-id="55b0c-143">整数リテラルの型は、そのサフィックスによって次のように決まります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-143">The type of an integer literal is determined by its suffix as follows:</span></span>

- <span data-ttu-id="55b0c-144">サフィックスがないリテラルの型は、`int`、`uint`、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-144">If the literal has no suffix, its type is the first of the following types in which its value can be represented: `int`, `uint`, `long`, `ulong`.</span></span>
- <span data-ttu-id="55b0c-145">リテラルのサフィックスが `U` または `u` の場合、その型は、`uint`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-145">If the literal is suffixed by `U` or `u`, its type is the first of the following types in which its value can be represented: `uint`, `ulong`.</span></span>
- <span data-ttu-id="55b0c-146">リテラルのサフィックスが `L` または `l` の場合、その型は、`long`、`ulong` の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-146">If the literal is suffixed by `L` or `l`, its type is the first of the following types in which its value can be represented: `long`, `ulong`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="55b0c-147">小文字の `l` はサフィックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-147">You can use the lowercase letter `l` as a suffix.</span></span> <span data-ttu-id="55b0c-148">ただし、文字の `l` は数字の `1` と混同しやすいため、コンパイラから警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-148">However, this generates a compiler warning because the letter `l` can be confused with the digit `1`.</span></span> <span data-ttu-id="55b0c-149">わかりやすくするために `L` を使用してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-149">Use `L` for clarity.</span></span>

- <span data-ttu-id="55b0c-150">リテラルのサフィックスが `UL`、`Ul`、`uL`、`ul`、`LU`、`Lu`、`lU`、または `lu` の場合、その型は `ulong` です。</span><span class="sxs-lookup"><span data-stu-id="55b0c-150">If the literal is suffixed by `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU`, or `lu`, its type is `ulong`.</span></span>

<span data-ttu-id="55b0c-151">整数リテラルで表される値が <xref:System.UInt64.MaxValue?displayProperty=nameWithType> を超えると、コンパイル エラー [CS1021](../../misc/cs1021.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-151">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="55b0c-152">整数リテラルの決定された型が `int` で、その値が変換先の型の範囲内にある場合、リテラルで表される値は暗黙的に `sbyte`、`byte`、`short`、`ushort`、`uint`、または `ulong` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-152">If the determined type of an integer literal is `int` and the value is within the range of the destination type, the value represented by the literal can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`:</span></span>

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

<span data-ttu-id="55b0c-153">前の例で示したように、リテラルの値が変換先の型の範囲内にない場合、コンパイラ エラー [CS0031](../../misc/cs0031.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-153">As the preceding example shows, if the literal's value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

<span data-ttu-id="55b0c-154">また、キャストを使用して、整数リテラルによって表される値を、指定された型のリテラル以外の型に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-154">You also can use a cast to convert the value represented by an integer literal to the type other than the determined type of the literal:</span></span>

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="55b0c-155">変換</span><span class="sxs-lookup"><span data-stu-id="55b0c-155">Conversions</span></span>

<span data-ttu-id="55b0c-156">任意の整数数値型を他の整数数値型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-156">You can convert any integral numeric type to any other integral numeric type.</span></span> <span data-ttu-id="55b0c-157">変換先の型に変換元の型のすべての値を格納できる場合、変換は暗黙的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-157">If the destination type can store all values of the source type, the conversion is implicit.</span></span> <span data-ttu-id="55b0c-158">それ以外の場合、明示的な変換を呼び出すには、[キャスト演算子 `()`](../operators/type-testing-and-cast.md#cast-operator-) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-158">Otherwise, you need to use the [cast operator `()`](../operators/type-testing-and-cast.md#cast-operator-) to invoke an explicit conversion.</span></span> <span data-ttu-id="55b0c-159">詳細については、「[Built-in numeric conversions](numeric-conversions.md)」(組み込みの数値変換) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-159">For more information, see [Built-in numeric conversions](numeric-conversions.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="55b0c-160">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="55b0c-160">C# language specification</span></span>

<span data-ttu-id="55b0c-161">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-161">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="55b0c-162">整数型</span><span class="sxs-lookup"><span data-stu-id="55b0c-162">Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="55b0c-163">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="55b0c-163">Integer literals</span></span>](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a><span data-ttu-id="55b0c-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="55b0c-164">See also</span></span>

- [<span data-ttu-id="55b0c-165">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="55b0c-165">C# reference</span></span>](../index.md)
- [<span data-ttu-id="55b0c-166">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="55b0c-166">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="55b0c-167">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="55b0c-167">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="55b0c-168">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="55b0c-168">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="55b0c-169">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="55b0c-169">Numerics in .NET</span></span>](../../../standard/numerics.md)
