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
ms.openlocfilehash: bde0b7cea52951cd72bde6cfd7d8f1c7dbcb8f46
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425597"
---
# <a name="integral-numeric-types--c-reference"></a><span data-ttu-id="904b6-103">整数数値型 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="904b6-103">Integral numeric types  (C# reference)</span></span>

<span data-ttu-id="904b6-104">**整数数値型**は**単純型**のサブセットであり、[*リテラル*](#integral-literals)を使用して初期化できます。</span><span class="sxs-lookup"><span data-stu-id="904b6-104">The **integral numeric types** are a subset of the **simple types** and can be initialized with [*literals*](#integral-literals).</span></span> <span data-ttu-id="904b6-105">すべての整数型は、値型でもあります。</span><span class="sxs-lookup"><span data-stu-id="904b6-105">All integral types are also value types.</span></span>

<span data-ttu-id="904b6-106">すべての整数数値型では [arithmetic](../operators/arithmetic-operators.md)、[bitwise logical](../operators/bitwise-and-shift-operators.md)、[comparison、equality](../operators/equality-operators.md) 演算子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="904b6-106">All integral numeric types support [arithmetic](../operators/arithmetic-operators.md), [bitwise logical](../operators/bitwise-and-shift-operators.md), [comparison, and equality](../operators/equality-operators.md) operators.</span></span>

## <a name="sizes-and-ranges"></a><span data-ttu-id="904b6-107">サイズと範囲</span><span class="sxs-lookup"><span data-stu-id="904b6-107">Sizes and ranges</span></span>

<span data-ttu-id="904b6-108">次の表は、整数型のサイズと範囲を示しています。</span><span class="sxs-lookup"><span data-stu-id="904b6-108">The following table shows the sizes and ranges of the integral types:</span></span>

|<span data-ttu-id="904b6-109">型</span><span class="sxs-lookup"><span data-stu-id="904b6-109">Type</span></span>|<span data-ttu-id="904b6-110">範囲</span><span class="sxs-lookup"><span data-stu-id="904b6-110">Range</span></span>|<span data-ttu-id="904b6-111">サイズ</span><span class="sxs-lookup"><span data-stu-id="904b6-111">Size</span></span>|  
|----------|-----------|----------|  
|`sbyte`|<span data-ttu-id="904b6-112">-128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="904b6-112">-128 to 127</span></span>|<span data-ttu-id="904b6-113">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-113">Signed 8-bit integer</span></span>|  
|`byte`|<span data-ttu-id="904b6-114">0 ～ 255</span><span class="sxs-lookup"><span data-stu-id="904b6-114">0 to 255</span></span>|<span data-ttu-id="904b6-115">符号なし 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-115">Unsigned 8-bit integer</span></span>|  
|`short`|<span data-ttu-id="904b6-116">-32,768 ～ 32,767</span><span class="sxs-lookup"><span data-stu-id="904b6-116">-32,768 to 32,767</span></span>|<span data-ttu-id="904b6-117">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-117">Signed 16-bit integer</span></span>|  
|`ushort`|<span data-ttu-id="904b6-118">0 ～ 65,535</span><span class="sxs-lookup"><span data-stu-id="904b6-118">0 to 65,535</span></span>|<span data-ttu-id="904b6-119">符号なし 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-119">Unsigned 16-bit integer</span></span>|  
|`int`|<span data-ttu-id="904b6-120">-2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="904b6-120">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="904b6-121">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-121">Signed 32-bit integer</span></span>|  
|`uint`|<span data-ttu-id="904b6-122">0 ～ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="904b6-122">0 to 4,294,967,295</span></span>|<span data-ttu-id="904b6-123">符号なし 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-123">Unsigned 32-bit integer</span></span>|  
|`long`|<span data-ttu-id="904b6-124">-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="904b6-124">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="904b6-125">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-125">Signed 64-bit integer</span></span>|  
|`ulong`|<span data-ttu-id="904b6-126">0 ～ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="904b6-126">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="904b6-127">符号なし 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="904b6-127">Unsigned 64-bit integer</span></span>|  

<span data-ttu-id="904b6-128">すべての整数型の既定値は、`0` です。</span><span class="sxs-lookup"><span data-stu-id="904b6-128">The default value for all integral types is `0`.</span></span> <span data-ttu-id="904b6-129">各整数型には、型の最小値と最大値に対して、`MinValue` および `MaxValue` という名前の定数があります。</span><span class="sxs-lookup"><span data-stu-id="904b6-129">Each of the integral types has constants named `MinValue` and `MaxValue` for the minimum and maximum value for that type.</span></span>

<span data-ttu-id="904b6-130"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 構造体を使用して、上限や下限のない符号付き整数を表します。</span><span class="sxs-lookup"><span data-stu-id="904b6-130">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> structure to represent a signed integer with no upper or lower bounds.</span></span>

## <a name="integral-literals"></a><span data-ttu-id="904b6-131">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="904b6-131">Integral literals</span></span>

<span data-ttu-id="904b6-132">整数リテラルは、*10 進リテラル*、*16 進数リテラル*、または*バイナリ リテラル*として指定できます。</span><span class="sxs-lookup"><span data-stu-id="904b6-132">Integral literals can be specified as *decimal literals*, *hexadecimal literals*, or *binary literals*.</span></span> <span data-ttu-id="904b6-133">それぞれの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="904b6-133">An example of each is shown below:</span></span>

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

<span data-ttu-id="904b6-134">10 進リテラルには、プレフィックスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="904b6-134">Decimal literals don't require any prefix.</span></span> <span data-ttu-id="904b6-135">`x` または `X` プレフィックスは *16 進数リテラル*を意味します。</span><span class="sxs-lookup"><span data-stu-id="904b6-135">The `x` or `X` prefix signifies a *hexadecimal literal*.</span></span> <span data-ttu-id="904b6-136">`b` または `B` プレフィックスは*バイナリ リテラル*を意味します。</span><span class="sxs-lookup"><span data-stu-id="904b6-136">The `b` or `B` prefix signifies a *binary literal*.</span></span> <span data-ttu-id="904b6-137">`binaryLiteral` の宣言は、`_` を*桁区切り記号*として使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="904b6-137">The declaration of `binaryLiteral` demonstrates the use of `_` as a *digit separator*.</span></span> <span data-ttu-id="904b6-138">桁区切り記号は、すべての数値リテラルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="904b6-138">The digit separator can be used with all numeric literals.</span></span> <span data-ttu-id="904b6-139">バイナリ リテラルと桁区切り記号 `_` は、C# 7.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="904b6-139">Binary literals and the digit separator `_` are supported starting with C# 7.0.</span></span>

## <a name="literal-suffixes"></a><span data-ttu-id="904b6-140">リテラル サフィックス</span><span class="sxs-lookup"><span data-stu-id="904b6-140">Literal suffixes</span></span> 

<span data-ttu-id="904b6-141">`l` または `L` サフィックスは、整数リテラルが `long` 型である必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="904b6-141">The `l` or `L` suffix specifies that the integral literal should be of the `long` type.</span></span> <span data-ttu-id="904b6-142">`ul` または `UL` サフィックスは、`ulong` 型を示します。</span><span class="sxs-lookup"><span data-stu-id="904b6-142">The `ul` or `UL` suffix specifies the `ulong` type.</span></span> <span data-ttu-id="904b6-143">`L` サフィックスが 9,223,372,036,854,775,807 (`long` の最大値) より大きいリテラルで使用されている場合、値は `ulong` 型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="904b6-143">If the `L` suffix is used on a literal that is greater than 9,223,372,036,854,775,807 (the maximum value of `long`), the value is converted to the `ulong` type.</span></span> <span data-ttu-id="904b6-144">整数リテラルで表される値が <xref:System.UInt64.MaxValue?displayProperty=nameWithType> を超えると、コンパイル エラー [CS1021](../../misc/cs1021.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="904b6-144">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span> 

> [!NOTE]
> <span data-ttu-id="904b6-145">小文字の "l" はサフィックスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="904b6-145">You can use the lowercase letter "l" as a suffix.</span></span> <span data-ttu-id="904b6-146">ただし、文字の "l" は数字の "1" と混同しやすいため、コンパイラから警告が出されます。</span><span class="sxs-lookup"><span data-stu-id="904b6-146">However, this generates a compiler warning because the letter "l" is easily confused with the digit "1."</span></span> <span data-ttu-id="904b6-147">明確にするには、"L" を使用します。</span><span class="sxs-lookup"><span data-stu-id="904b6-147">Use "L" for clarity.</span></span>

## <a name="type-of-an-integral-literal"></a><span data-ttu-id="904b6-148">整数リテラルの型</span><span class="sxs-lookup"><span data-stu-id="904b6-148">Type of an integral literal</span></span>

<span data-ttu-id="904b6-149">サフィックスがない整数リテラルの型は、以下の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="904b6-149">If an integral literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
1. `uint`
1. `long`
1. `ulong`

<span data-ttu-id="904b6-150">整数リテラルは、割り当てまたはキャストのどちらかを使用して、既定よりも小さな範囲の型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="904b6-150">You can convert an integral literal to a type with a smaller range than the default using either an assignment or a cast:</span></span>

```csharp
byte byteVariable = 42; // type is byte
var signedByte = (sbyte)42; // type is sbyte.
```

<span data-ttu-id="904b6-151">整数リテラルは、割り当て、キャスト、またはリテラル上のサフィックスのいずれかを使用して、既定よりも大きな範囲の型に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="904b6-151">You can convert an integral literal to a type with a larger range than the default using either assignment, a cast, or a suffix on the literal:</span></span>

```csharp
var unsignedLong = 42UL;
var longVariable = 42L;
ulong anotherUnsignedLong = 42;
var anotherLong = (long)42;
```

## <a name="conversions"></a><span data-ttu-id="904b6-152">変換</span><span class="sxs-lookup"><span data-stu-id="904b6-152">Conversions</span></span>

<span data-ttu-id="904b6-153">変換先の型に変換元の型のすべての値を格納可能な、任意の 2 つの整数型間の暗黙的な変換 (*拡大変換*と呼ばれます) があります。</span><span class="sxs-lookup"><span data-stu-id="904b6-153">There's an implicit conversion (called a *widening conversion*) between any two integral types where the destination type can store all values of the source type.</span></span> <span data-ttu-id="904b6-154">たとえば、`int` 値の範囲が `long` の適切なサブセットであるため、`int` から `long` への暗黙的な変換があります。</span><span class="sxs-lookup"><span data-stu-id="904b6-154">For example, there's an implicit conversion from `int` to `long` because the range of `int` values is a proper subset of `long`.</span></span> <span data-ttu-id="904b6-155">小さな符号なし整数型から、大きな符号付き整数型への暗黙的な変換があります。</span><span class="sxs-lookup"><span data-stu-id="904b6-155">There are implicit conversions from a smaller unsigned integral type to a larger signed integral type.</span></span> <span data-ttu-id="904b6-156">任意の整数型から、任意の浮動小数点型への暗黙的な変換もあります。</span><span class="sxs-lookup"><span data-stu-id="904b6-156">There's also an implicit conversion from any integral type to any floating-point type.</span></span>  <span data-ttu-id="904b6-157">任意の符号付き整数型から、任意の符号なし整数型への暗黙的な変換はありません。</span><span class="sxs-lookup"><span data-stu-id="904b6-157">There's no implicit conversion from any signed integral type to any unsigned integral type.</span></span>

<span data-ttu-id="904b6-158">変換元の型から変換先の型への暗黙的な変換が定義されていない場合、明示的なキャストを使用して、1 つの整数型を別の整数型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="904b6-158">You must use an explicit cast to convert one integral type to another integral type when an implicit conversion is not defined from the source type to the destination type.</span></span> <span data-ttu-id="904b6-159">これは*縮小変換*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="904b6-159">This is called a *narrowing conversion*.</span></span> <span data-ttu-id="904b6-160">変換によりデータが失われる場合があるため、明示的なケースが必要となります。</span><span class="sxs-lookup"><span data-stu-id="904b6-160">The explicit case is required because the conversion can result in data loss.</span></span>

## <a name="see-also"></a><span data-ttu-id="904b6-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="904b6-161">See also</span></span>

- [<span data-ttu-id="904b6-162">C# 言語仕様 - 整数型</span><span class="sxs-lookup"><span data-stu-id="904b6-162">C# language specification - Integral types</span></span>](~/_csharplang/spec/types.md#integral-types)
- [<span data-ttu-id="904b6-163">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="904b6-163">C# reference</span></span>](../index.md)
- [<span data-ttu-id="904b6-164">浮動小数点型の一覧表</span><span class="sxs-lookup"><span data-stu-id="904b6-164">Floating-point types table</span></span>](../keywords/floating-point-types-table.md)
- [<span data-ttu-id="904b6-165">既定値の一覧表</span><span class="sxs-lookup"><span data-stu-id="904b6-165">Default values table</span></span>](../keywords/default-values-table.md)
- [<span data-ttu-id="904b6-166">数値結果テーブルの書式設定</span><span class="sxs-lookup"><span data-stu-id="904b6-166">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="904b6-167">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="904b6-167">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="904b6-168">.NET における数値</span><span class="sxs-lookup"><span data-stu-id="904b6-168">Numerics in .NET</span></span>](../../../standard/numerics.md)
