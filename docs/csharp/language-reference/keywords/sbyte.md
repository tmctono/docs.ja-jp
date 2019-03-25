---
title: sbyte - C# リファレンス
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- sbyte_CSharpKeyword
- sbyte
helpviewer_keywords:
- sbyte keyword [C#]
ms.assetid: 1a9c7b48-73d1-4d33-b485-c4faf0a816bc
ms.openlocfilehash: 124ff282fc354699c68e0a17c64f911db2e25869
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185520"
---
# <a name="sbyte-c-reference"></a><span data-ttu-id="615fa-102">sbyte (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="615fa-102">sbyte (C# Reference)</span></span>

<span data-ttu-id="615fa-103">`sbyte` は、次の表に示されたサイズと範囲に従って値を格納する整数型を示します。</span><span class="sxs-lookup"><span data-stu-id="615fa-103">`sbyte` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="615fa-104">型</span><span class="sxs-lookup"><span data-stu-id="615fa-104">Type</span></span>|<span data-ttu-id="615fa-105">範囲</span><span class="sxs-lookup"><span data-stu-id="615fa-105">Range</span></span>|<span data-ttu-id="615fa-106">サイズ</span><span class="sxs-lookup"><span data-stu-id="615fa-106">Size</span></span>|<span data-ttu-id="615fa-107">.NET 型</span><span class="sxs-lookup"><span data-stu-id="615fa-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`sbyte`|<span data-ttu-id="615fa-108">-128 ～ 127</span><span class="sxs-lookup"><span data-stu-id="615fa-108">-128 to 127</span></span>|<span data-ttu-id="615fa-109">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="615fa-109">Signed 8-bit integer</span></span>|<xref:System.SByte?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="615fa-110">リテラル</span><span class="sxs-lookup"><span data-stu-id="615fa-110">Literals</span></span>

<span data-ttu-id="615fa-111">`sbyte` 変数を宣言し、10 進リテラル、16 進リテラル、または (C# 7.0 以降) バイナリ リテラルを割り当てることによって初期化できます。</span><span class="sxs-lookup"><span data-stu-id="615fa-111">You can declare and initialize an `sbyte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>

<span data-ttu-id="615fa-112">次の例では、整数 -102 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、[int](../../../csharp/language-reference/keywords/int.md) から `sbyte` 値に変換されています。</span><span class="sxs-lookup"><span data-stu-id="615fa-112">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are converted from [int](../../../csharp/language-reference/keywords/int.md) to `sbyte` values.</span></span>

[!code-csharp[SByte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByte)]

> [!NOTE]
> <span data-ttu-id="615fa-113">16 進リテラルを表すにはプレフィックス `0x` または `0X` を使い、バイナリ リテラルを表すにはプレフィックス `0b` または `0B` を使います。</span><span class="sxs-lookup"><span data-stu-id="615fa-113">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="615fa-114">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="615fa-114">Decimal literals have no prefix.</span></span>

<span data-ttu-id="615fa-115">C# 7.0 以降では、読みやすさを強化するためにいくつかの機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="615fa-115">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>
- <span data-ttu-id="615fa-116">C# 7.0 では、桁区切り記号としてアンダースコア文字 (`_`) が使用できます。</span><span class="sxs-lookup"><span data-stu-id="615fa-116">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="615fa-117">C# 7.2 では、プレフィックスの後に、`_` をバイナリまたは 16 進リテラルの桁区切り記号として使用できます。</span><span class="sxs-lookup"><span data-stu-id="615fa-117">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="615fa-118">10 進リテラルは先頭にアンダー スコアを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="615fa-118">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="615fa-119">以下にいくつか例を示します。</span><span class="sxs-lookup"><span data-stu-id="615fa-119">Some examples are shown below.</span></span>

[!code-csharp[SByteSeparator](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#SByteS)]

<span data-ttu-id="615fa-120">整数リテラルが `sbyte` の範囲外にある場合 (つまり、<xref:System.SByte.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.SByte.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="615fa-120">If the integer literal is outside the range of `sbyte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="615fa-121">サフィックスがない整数リテラルの場合、整数リテラルの型は、[int](int.md)、[uint](uint.md)、[long](long.md)、[ulong](ulong.md) のうち、その値を表すことができる最初の型になります。</span><span class="sxs-lookup"><span data-stu-id="615fa-121">When an integer literal has no suffix, its type is the first of these types in which its value can be represented: [int](int.md), [uint](uint.md), [long](long.md), [ulong](ulong.md).</span></span> <span data-ttu-id="615fa-122">つまり、この例では、数値リテラル `0x9A` と `0b10011010` は値が 156 の 32 ビット符号付き整数として解釈され、これは <xref:System.SByte.MaxValue?displayProperty=nameWithType> を超えています。</span><span class="sxs-lookup"><span data-stu-id="615fa-122">This means that, in this example, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="615fa-123">このため、キャスト演算子が必要であり、割り当ては [unchecked](unchecked.md) コンテキストで行われる必要があります。</span><span class="sxs-lookup"><span data-stu-id="615fa-123">Because of this, the casting operator is needed, and the assignment must occur in an [unchecked](unchecked.md) context.</span></span>

## <a name="compiler-overload-resolution"></a><span data-ttu-id="615fa-124">コンパイラのオーバーロード解決</span><span class="sxs-lookup"><span data-stu-id="615fa-124">Compiler overload resolution</span></span>

<span data-ttu-id="615fa-125">オーバーロードされたメソッドを呼び出すときは、キャストを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="615fa-125">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="615fa-126">たとえば、`sbyte` パラメーターと [int](../../../csharp/language-reference/keywords/int.md) パラメーターを使用したオーバーロードされたメソッドがあるとします。</span><span class="sxs-lookup"><span data-stu-id="615fa-126">Consider, for example, the following overloaded methods that use `sbyte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>

```csharp
public static void SampleMethod(int i) {}
public static void SampleMethod(sbyte b) {}
```

<span data-ttu-id="615fa-127">`sbyte` キャストを使用すると、正しい型が呼び出されます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="615fa-127">Using the `sbyte` cast guarantees that the correct type is called, for example:</span></span>

```csharp
// Calling the method with the int parameter:
SampleMethod(5);
// Calling the method with the sbyte parameter:
SampleMethod((sbyte)5);
```

## <a name="conversions"></a><span data-ttu-id="615fa-128">変換</span><span class="sxs-lookup"><span data-stu-id="615fa-128">Conversions</span></span>

<span data-ttu-id="615fa-129">`sbyte` から [short](../../../csharp/language-reference/keywords/short.md)、[int](../../../csharp/language-reference/keywords/int.md)、[long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md)、[decimal](../../../csharp/language-reference/keywords/decimal.md) への、定義済みの暗黙的な変換が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="615fa-129">There is a predefined implicit conversion from `sbyte` to [short](../../../csharp/language-reference/keywords/short.md), [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>

<span data-ttu-id="615fa-130">記憶領域が大きなリテラル以外の数値型を暗黙的に `sbyte` に変換することはできません (整数型の記憶領域については、「[整数型の一覧表](../../../csharp/language-reference/keywords/integral-types-table.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="615fa-130">You cannot implicitly convert nonliteral numeric types of larger storage size to `sbyte` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="615fa-131">たとえば、2 つの `sbyte` 変数 `x` と `y` があるとします。</span><span class="sxs-lookup"><span data-stu-id="615fa-131">Consider, for example, the following two `sbyte` variables `x` and `y`:</span></span>

```csharp
sbyte x = 10, y = 20;
```

<span data-ttu-id="615fa-132">次の代入ステートメントは、代入演算子の右側にある算術式が既定で [int](../../../csharp/language-reference/keywords/int.md) に評価されるため、コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="615fa-132">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>

```csharp
sbyte z = x + y;   // Error: conversion from int to sbyte
```

<span data-ttu-id="615fa-133">この問題を解決するには、次の例のように式をキャストします。</span><span class="sxs-lookup"><span data-stu-id="615fa-133">To fix this problem, cast the expression as in the following example:</span></span>

```csharp
sbyte z = (sbyte)(x + y);   // OK: explicit conversion
```

<span data-ttu-id="615fa-134">ただし、次のステートメントは使用できます。このステートメントでは、変換先の変数の記憶領域サイズは元のサイズ以上になります。</span><span class="sxs-lookup"><span data-stu-id="615fa-134">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>

```csharp
sbyte x = 10, y = 20;
int m = x + y;
long n = x + y;
```

<span data-ttu-id="615fa-135">浮動小数点型から `sbyte` への暗黙的な変換が行われないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="615fa-135">Notice also that there is no implicit conversion from floating-point types to `sbyte`.</span></span> <span data-ttu-id="615fa-136">たとえば、次のステートメントは、明示的なキャストを使用しない場合、コンパイラ エラーになります。</span><span class="sxs-lookup"><span data-stu-id="615fa-136">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
sbyte x = 3.0;         // Error: no implicit conversion from double
sbyte y = (sbyte)3.0;  // OK: explicit conversion
```

<span data-ttu-id="615fa-137">浮動小数点型と整数型の混在する算術式の詳細については、「[float](../../../csharp/language-reference/keywords/float.md)」および「[double](../../../csharp/language-reference/keywords/double.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="615fa-137">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>

<span data-ttu-id="615fa-138">暗黙的な数値変換規則の詳細については、「[暗黙的な数値変換の一覧表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="615fa-138">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="615fa-139">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="615fa-139">C# Language Specification</span></span>

<span data-ttu-id="615fa-140">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[整数型](~/_csharplang/spec/types.md#integral-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="615fa-140">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="615fa-141">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="615fa-141">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="615fa-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="615fa-142">See also</span></span>

- <xref:System.SByte>
- [<span data-ttu-id="615fa-143">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="615fa-143">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="615fa-144">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="615fa-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="615fa-145">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="615fa-145">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="615fa-146">整数型の一覧表</span><span class="sxs-lookup"><span data-stu-id="615fa-146">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="615fa-147">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="615fa-147">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="615fa-148">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="615fa-148">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="615fa-149">明示的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="615fa-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
