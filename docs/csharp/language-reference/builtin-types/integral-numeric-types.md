---
title: 整数数値型 - C# リファレンス
description: 各整数数値型の範囲、ストレージ サイズ、および使用方法について説明します。
ms.date: 06/25/2019
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
ms.openlocfilehash: dfb1298abaff0cfe8eae7536f94511a30012a4a9
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68236077"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="bb668-103">整数数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="bb668-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="bb668-104">**整数数値型**は**単純型**のサブセットであり、[*リテラル*](#integral-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="bb668-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="bb668-105">すべての整数型は、値型でもあります。</span><span class="sxs-lookup"><span data-stu-id="bb668-105">All integral types are also value types.</span></span> <span data-ttu-id="bb668-106">すべての整数数値型では [arithmetic](../operators/arithmetic-operators.md)、[bitwise logical](../operators/bitwise-and-shift-operators.md)、[comparison、equality](../operators/equality-operators.md) 演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bb668-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="characteristics-of-the-integral-types"></a><span data-ttu-id="bb668-107">整数型の特性</span><span class="sxs-lookup"><span data-stu-id="bb668-107">Characteristics of the integral types</span></span>

<span data-ttu-id="bb668-108">C# では、次の定義済みの整数型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bb668-108">C# supports the following predefined integral types:</span></span>

|<span data-ttu-id="bb668-109">C# 型/キーワード</span><span class="sxs-lookup"><span data-stu-id="bb668-109">C# type/keyword</span></span>|<span data-ttu-id="bb668-110">範囲</span><span class="sxs-lookup"><span data-stu-id="bb668-110">Range</span></span>|<span data-ttu-id="bb668-111">サイズ</span><span class="sxs-lookup"><span data-stu-id="bb668-111">Size</span></span>|<span data-ttu-id="bb668-112">.NET 型</span><span class="sxs-lookup"><span data-stu-id="bb668-112">.NET type</span></span>|
|----------|-----------|----------|-------------|
|`sbyte`|<span data-ttu-id="bb668-113">-128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="bb668-113">-128 to 127</span></span>|<span data-ttu-id="bb668-114">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-114">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|<span data-ttu-id="bb668-115">0 ～ 255</span><span class="sxs-lookup"><span data-stu-id="bb668-115">0 to 255</span></span>|<span data-ttu-id="bb668-116">符号なし 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-116">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|<span data-ttu-id="bb668-117">-32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="bb668-117">-32,768 to 32,767</span></span>|<span data-ttu-id="bb668-118">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-118">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|<span data-ttu-id="bb668-119">0 ～ 65,535</span><span class="sxs-lookup"><span data-stu-id="bb668-119">0 to 65,535</span></span>|<span data-ttu-id="bb668-120">符号なし 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-120">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|<span data-ttu-id="bb668-121">-2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="bb668-121">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="bb668-122">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-122">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|<span data-ttu-id="bb668-123">0 ～ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="bb668-123">0 to 4,294,967,295</span></span>|<span data-ttu-id="bb668-124">符号なし 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-124">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|<span data-ttu-id="bb668-125">-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="bb668-125">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="bb668-126">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-126">Signed 64-bit integer</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|<span data-ttu-id="bb668-127">0 ～ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="bb668-127">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="bb668-128">符号なし 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="bb668-128">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|

<span data-ttu-id="bb668-129">上の表で、左端の列にある各 C# 型のキーワードは、対応する .NET 型の別名です。</span><span class="sxs-lookup"><span data-stu-id="bb668-129">In the preceding table, each C# type keyword from the leftmost column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="bb668-130">これらは交換可能です。</span><span class="sxs-lookup"><span data-stu-id="bb668-130">They are interchangeable.</span></span> <span data-ttu-id="bb668-131">たとえば、次の宣言では同じ型の変数が宣言されています。</span><span class="sxs-lookup"><span data-stu-id="bb668-131">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="bb668-132">各整数型の既定値はゼロ (`0`) です。</span><span class="sxs-lookup"><span data-stu-id="bb668-132">The default value of each integral type is zero, `0`.</span></span> <span data-ttu-id="bb668-133">各整数型には、その型の最小値と最大値を指定する `MinValue` および `MaxValue` 定数があります。</span><span class="sxs-lookup"><span data-stu-id="bb668-133">Each of the integral types has the `MinValue` and `MaxValue` constants that provide the minimum and maximum value of that type.</span></span>

<span data-ttu-id="bb668-134"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 構造体を使用して、上限や下限のない符号付き整数を表します。</span><span class="sxs-lookup"><span data-stu-id="bb668-134">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="bb668-135">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="bb668-135">Integral literals</span></span>

<span data-ttu-id="bb668-136">整数リテラルは、*10 進リテラル*、*16 進数リテラル*、または *バイナリ リテラル* として指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb668-136">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="bb668-137">それぞれの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb668-137">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="bb668-138">10 進リテラルには、プレフィックスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bb668-138">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="bb668-139">`x` または `X` プレフィックスは *16 進数リテラル*を意味します。</span><span class="sxs-lookup"><span data-stu-id="bb668-139">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="bb668-140">`b` または `B` プレフィックスは*バイナリ リテラル*を意味します。</span><span class="sxs-lookup"><span data-stu-id="bb668-140">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="bb668-141">`binaryLiteral` の宣言は、`_` を*桁区切り記号*として使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="bb668-141">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="bb668-142">桁区切り記号は、すべての数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb668-142">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="bb668-143">バイナリ リテラルと桁区切り記号 `_` は、C# 7.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bb668-143">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

### <a name="literal-suffixes"></a><span data-ttu-id="bb668-144">リテラル サフィックス</span><span class="sxs-lookup"><span data-stu-id="bb668-144">Literal suffixes</span></span>

<span data-ttu-id="bb668-145">`l` または `L` サフィックスは、整数リテラルが `long` 型である必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bb668-145">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="bb668-146">`ul` または `UL` サフィックスは、`ulong` 型を示します。</span><span class="sxs-lookup"><span data-stu-id="bb668-146">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="bb668-147">`L` サフィックスが 9,223,372,036,854,775,807 (`long` の最大値) より大きいリテラルで使用されている場合、値は `ulong` 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="bb668-147">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="bb668-148">整数リテラルで表される値が <xref:System.UInt64.MaxValue?displayProperty=nameWithType> を超えると、コンパイル エラー [CS1021](../../misc/cs1021.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="bb668-148">If the value represented by an integral literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="bb668-149">小文字の "l" はサフィックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb668-149">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="bb668-150">ただし、文字の "l" は数字の "1" と混同しやすいため、コンパイラから警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="bb668-150">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="bb668-151">明確にするには、"L" を使用します。</span><span class="sxs-lookup"><span data-stu-id="bb668-151">Use "L" for clarity.</span></span>

### <a name="type-of-an-integral-literal"></a><span data-ttu-id="bb668-152">整数リテラルの型</span><span class="sxs-lookup"><span data-stu-id="bb668-152">Type of an integral literal</span></span>

<span data-ttu-id="bb668-153">サフィックスがない整数リテラルの型は、次の型のうち、その値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="bb668-153">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="bb668-154">整数リテラルは、割り当てまたはキャストのどちらかを使用して、既定よりも小さな範囲の型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="bb668-154">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="bb668-155">整数リテラルは、割り当て、キャスト、またはリテラル上のサフィックスのいずれかを使用して、既定よりも大きな範囲の型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="bb668-155">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="bb668-156">変換</span><span class="sxs-lookup"><span data-stu-id="bb668-156">Conversions</span></span>

<span data-ttu-id="bb668-157">変換先の型に変換元の型のすべての値を格納可能な、任意の 2 つの整数型間の暗黙的な変換 (*拡大変換*と呼ばれます) があります。</span><span class="sxs-lookup"><span data-stu-id="bb668-157">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="bb668-158">たとえば、`int` 値の範囲が `long` の適切なサブセットであるため、`int` から `long` への暗黙的な変換があります。</span><span class="sxs-lookup"><span data-stu-id="bb668-158">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="bb668-159">小さな符号なし整数型から、大きな符号付き整数型への暗黙的な変換があります。</span><span class="sxs-lookup"><span data-stu-id="bb668-159">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="bb668-160">任意の整数型から、任意の浮動小数点型への暗黙的な変換もあります。</span><span class="sxs-lookup"><span data-stu-id="bb668-160">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="bb668-161">任意の符号付き整数型から、任意の符号なし整数型への暗黙的な変換はありません。</span><span class="sxs-lookup"><span data-stu-id="bb668-161">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="bb668-162">変換元の型から変換先の型への暗黙的な変換が定義されていない場合、明示的なキャストを使用して、1 つの整数型を別の整数型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb668-162">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="bb668-163">これは*縮小変換*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="bb668-163">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="bb668-164">変換によりデータが失われる場合があるため、明示的なケースが必要となります。</span><span class="sxs-lookup"><span data-stu-id="bb668-164">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb668-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb668-165">See also</span></span>

- [<span data-ttu-id="bb668-166">C# 言語仕様 - 整数型</span><span class="sxs-lookup"><span data-stu-id="bb668-166">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="bb668-167">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="bb668-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bb668-168">浮動小数点型</span><span class="sxs-lookup"><span data-stu-id="bb668-168">Floating-point types</span></span>](floating-point-numeric-types.md)
- [<span data-ttu-id="bb668-169">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="bb668-169">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="bb668-170">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="bb668-170">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="bb668-171">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="bb668-171">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="bb668-172">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="bb668-172">Numerics in .NET</span></span>](../../../standard/numerics.md)
