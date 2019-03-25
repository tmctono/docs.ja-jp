---
title: int - C# リファレンス
ms.custom: seodec18
ms.date: 03/14/2017
f1_keywords:
- int_CSharpKeyword
- int
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
ms.openlocfilehash: 6cabc2c6d4930c5d5fc88e76a17c1a6425ddd1bd
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185780"
---
# <a name="int-c-reference"></a><span data-ttu-id="c7227-102">int (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="c7227-102">int (C# Reference)</span></span>

<span data-ttu-id="c7227-103">`int` は、次の表に示されたサイズと範囲に従って値を格納する整数型を示します。</span><span class="sxs-lookup"><span data-stu-id="c7227-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>

|<span data-ttu-id="c7227-104">型</span><span class="sxs-lookup"><span data-stu-id="c7227-104">Type</span></span>|<span data-ttu-id="c7227-105">範囲</span><span class="sxs-lookup"><span data-stu-id="c7227-105">Range</span></span>|<span data-ttu-id="c7227-106">サイズ</span><span class="sxs-lookup"><span data-stu-id="c7227-106">Size</span></span>|<span data-ttu-id="c7227-107">.NET 型</span><span class="sxs-lookup"><span data-stu-id="c7227-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`int`|<span data-ttu-id="c7227-108">-2,147,483,648 ～ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="c7227-108">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="c7227-109">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="c7227-109">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="c7227-110">リテラル</span><span class="sxs-lookup"><span data-stu-id="c7227-110">Literals</span></span>

<span data-ttu-id="c7227-111">`int` 変数を宣言し、10 進リテラル、16 進リテラル、または (C# 7.0 以降) バイナリ リテラルを割り当てることによって初期化できます。</span><span class="sxs-lookup"><span data-stu-id="c7227-111">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="c7227-112">整数リテラルが `int` の範囲外にある場合 (つまり、<xref:System.Int32.MinValue?displayProperty=nameWithType> より小さいか、<xref:System.Int32.MaxValue?displayProperty=nameWithType> より大きい場合)、コンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c7227-112">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int32.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="c7227-113">次の例では、整数 90,946 を 10 進リテラル、16 進リテラル、バイナリ リテラルで表したものが、`int` 値に割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="c7227-113">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]

> [!NOTE]
> <span data-ttu-id="c7227-114">16 進リテラルを表すにはプレフィックス `0x` または `0X` を使い、バイナリ リテラルを表すにはプレフィックス `0b` または `0B` を使います。</span><span class="sxs-lookup"><span data-stu-id="c7227-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="c7227-115">10 進リテラルには、プレフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="c7227-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="c7227-116">C# 7.0 以降では、読みやすさを強化するためにいくつかの機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="c7227-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span>
- <span data-ttu-id="c7227-117">C# 7.0 では、桁区切り記号としてアンダースコア文字 (`_`) が使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7227-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
- <span data-ttu-id="c7227-118">C# 7.2 では、プレフィックスの後に、`_` をバイナリまたは 16 進リテラルの桁区切り記号として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c7227-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="c7227-119">10 進リテラルは先頭にアンダー スコアを持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="c7227-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="c7227-120">以下にいくつか例を示します。</span><span class="sxs-lookup"><span data-stu-id="c7227-120">Some examples are shown below.</span></span>

[!code-csharp[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]

<span data-ttu-id="c7227-121">整数リテラルでは型を示すサフィックスを含めることもできますが、`int` 型を示すサフィックスはありません。</span><span class="sxs-lookup"><span data-stu-id="c7227-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="c7227-122">サフィックスがない整数リテラルの型は、以下の型のうちその値を表すことができる最初のものになります。</span><span class="sxs-lookup"><span data-stu-id="c7227-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span>

1. `int`
2. [<span data-ttu-id="c7227-123">uint</span><span class="sxs-lookup"><span data-stu-id="c7227-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="c7227-124">long</span><span class="sxs-lookup"><span data-stu-id="c7227-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="c7227-125">ulong</span><span class="sxs-lookup"><span data-stu-id="c7227-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)

<span data-ttu-id="c7227-126">ここで示した例では、リテラル 90946 は `int` 型になります。</span><span class="sxs-lookup"><span data-stu-id="c7227-126">In these examples, the literal 90946 is of type `int`.</span></span>

## <a name="conversions"></a><span data-ttu-id="c7227-127">変換</span><span class="sxs-lookup"><span data-stu-id="c7227-127">Conversions</span></span>

<span data-ttu-id="c7227-128">`int` から [long](../../../csharp/language-reference/keywords/long.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md)、[decimal](../../../csharp/language-reference/keywords/decimal.md) への、定義済みの暗黙の型変換が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="c7227-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="c7227-129">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c7227-129">For example:</span></span>

```csharp
// '123' is an int, so an implicit conversion takes place here:
float f = 123;
```

<span data-ttu-id="c7227-130">[sbyte](../../../csharp/language-reference/keywords/sbyte.md)、[byte](../../../csharp/language-reference/keywords/byte.md)、[short](../../../csharp/language-reference/keywords/short.md)、[ushort](../../../csharp/language-reference/keywords/ushort.md)、[char](../../../csharp/language-reference/keywords/char.md) から `int` への、定義済みの暗黙の型変換が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="c7227-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="c7227-131">たとえば、次の代入ステートメントは、キャストを使用しない場合、コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="c7227-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>

```csharp
long aLong = 22;
int i1 = aLong;       // Error: no implicit conversion from long.
int i2 = (int)aLong;  // OK: explicit conversion.
```

<span data-ttu-id="c7227-132">浮動小数点型から `int` への暗黙的な変換が行われないことにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="c7227-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="c7227-133">たとえば、次のステートメントは、明示的なキャストを使用しない限り、コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="c7227-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>

```csharp
int x = 3.0;         // Error: no implicit conversion from double.
int y = (int)3.0;    // OK: explicit conversion.
```

<span data-ttu-id="c7227-134">浮動小数点型と整数型の混在する算術式の詳細については、「[float](../../../csharp/language-reference/keywords/float.md)」と「[double](../../../csharp/language-reference/keywords/double.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7227-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c7227-135">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="c7227-135">C# Language Specification</span></span>

<span data-ttu-id="c7227-136">詳細については、「[C# 言語仕様](../language-specification/index.md)」の[整数型](~/_csharplang/spec/types.md#integral-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7227-136">For more information, see [Integral types](~/_csharplang/spec/types.md#integral-types) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="c7227-137">言語仕様は、C# の構文と使用法に関する信頼性のある情報源です。</span><span class="sxs-lookup"><span data-stu-id="c7227-137">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7227-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7227-138">See also</span></span>

- <xref:System.Int32>
- [<span data-ttu-id="c7227-139">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="c7227-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="c7227-140">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c7227-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c7227-141">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="c7227-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="c7227-142">整数型の一覧表</span><span class="sxs-lookup"><span data-stu-id="c7227-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="c7227-143">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="c7227-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="c7227-144">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="c7227-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="c7227-145">明示的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="c7227-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
