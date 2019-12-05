---
title: char 型 - C# リファレンス
ms.date: 11/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: ab49b8cbddac2569d6063a5f312105bef3033e84
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552299"
---
# <a name="char-c-reference"></a><span data-ttu-id="2866c-102">char (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2866c-102">char (C# reference)</span></span>

<span data-ttu-id="2866c-103">`char` 型のキーワードは、Unicode UTF-16 文字を表す .NET <xref:System.Char?displayProperty=nameWithType> 構造体型のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="2866c-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character.</span></span>

|<span data-ttu-id="2866c-104">型</span><span class="sxs-lookup"><span data-stu-id="2866c-104">Type</span></span>|<span data-ttu-id="2866c-105">範囲</span><span class="sxs-lookup"><span data-stu-id="2866c-105">Range</span></span>|<span data-ttu-id="2866c-106">サイズ</span><span class="sxs-lookup"><span data-stu-id="2866c-106">Size</span></span>|<span data-ttu-id="2866c-107">.NET 型</span><span class="sxs-lookup"><span data-stu-id="2866c-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="2866c-108">U+0000 ～ U+FFFF</span><span class="sxs-lookup"><span data-stu-id="2866c-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="2866c-109">16 ビット</span><span class="sxs-lookup"><span data-stu-id="2866c-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

<span data-ttu-id="2866c-110">`char` 型の既定値は `\0` (つまり U+0000) です。</span><span class="sxs-lookup"><span data-stu-id="2866c-110">The default value of the `char` type is `\0`, that is, U+0000.</span></span>

<span data-ttu-id="2866c-111">[string](reference-types.md#the-string-type) 型では、`char` 値のシーケンスとしてテキストを表わします。</span><span class="sxs-lookup"><span data-stu-id="2866c-111">The [string](reference-types.md#the-string-type) type represents text as a sequence of `char` values.</span></span>

## <a name="literals"></a><span data-ttu-id="2866c-112">リテラル</span><span class="sxs-lookup"><span data-stu-id="2866c-112">Literals</span></span>

<span data-ttu-id="2866c-113">`char` 値は以下で指定できます。</span><span class="sxs-lookup"><span data-stu-id="2866c-113">You can specify a `char` value with:</span></span>

- <span data-ttu-id="2866c-114">文字リテラル。</span><span class="sxs-lookup"><span data-stu-id="2866c-114">a character literal.</span></span>
- <span data-ttu-id="2866c-115">Unicode エスケープシーケンス。これは `\u` の後に文字コードの 16 進数表現 (4 つの記号) を続けたものになります。</span><span class="sxs-lookup"><span data-stu-id="2866c-115">a Unicode escape sequence, which is `\u` followed by the four-symbol hexadecimal representation of a character code.</span></span>
- <span data-ttu-id="2866c-116">16 進数エスケープシーケンス。これは `\x` の後に文字コードの 16 進数表現を続けたものになります。</span><span class="sxs-lookup"><span data-stu-id="2866c-116">a hexadecimal escape sequence, which is `\x` followed by the hexadecimal representation of a character code.</span></span>

[!code-csharp-interactive[char literals](~/samples/csharp/language-reference/builtin-types/CharType.cs#Literals)]

<span data-ttu-id="2866c-117">前の例のように、文字コードの値をそれに対応する `char` 値に型変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="2866c-117">As the preceding example shows, you also can cast the value of a character code into the corresponding `char` value.</span></span>

> [!NOTE]
> <span data-ttu-id="2866c-118">Unicode エスケープ シーケンスの場合、4 つの 16 進数をすべて指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2866c-118">In the case of a Unicode escape sequence, you must specify all four hexadecimal digits.</span></span> <span data-ttu-id="2866c-119">つまり、`\u006A` は有効なエスケープ シーケンスであり、`\u06A` と `\u6A` は有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="2866c-119">That is, `\u006A` is a valid escape sequence, while `\u06A` and `\u6A` are not valid.</span></span>
>
> <span data-ttu-id="2866c-120">16 進数エスケープ シーケンスの場合、先頭のゼロを省略できます。</span><span class="sxs-lookup"><span data-stu-id="2866c-120">In the case of a hexadecimal escape sequence, you can omit the leading zeros.</span></span> <span data-ttu-id="2866c-121">つまり、エスケープ シーケンスの `\x006A`、`\x06A`、`\x6A` は有効であり、同じ文字に対応します。</span><span class="sxs-lookup"><span data-stu-id="2866c-121">That is, the `\x006A`, `\x06A`, and `\x6A` escape sequences are valid and correspond to the same character.</span></span>

## <a name="conversions"></a><span data-ttu-id="2866c-122">変換</span><span class="sxs-lookup"><span data-stu-id="2866c-122">Conversions</span></span>

<span data-ttu-id="2866c-123">`char` 型は、[整数](integral-numeric-types.md)型 (`ushort`、`int`、`uint`、`long`、`ulong`) に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="2866c-123">The `char` type is implicitly convertible to the following [integral](integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="2866c-124">また、組み込みの[浮動小数点](floating-point-numeric-types.md)数値型 (`float`、`double`、`decimal`) に暗黙的に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="2866c-124">It's also implicitly convertible to the built-in [floating-point](floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="2866c-125">`sbyte`、`byte`、`short` 整数型に明示的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="2866c-125">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="2866c-126">他の型から `char` 型へと暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="2866c-126">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="2866c-127">しかし、[整数](integral-numeric-types.md)または[浮動小数点](floating-point-numeric-types.md)の数値型は、`char` に明示的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="2866c-127">However, any [integral](integral-numeric-types.md) or [floating-point](floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2866c-128">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="2866c-128">C# language specification</span></span>

<span data-ttu-id="2866c-129">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[整数型](~/_csharplang/spec/types.md#integral-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2866c-129">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2866c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="2866c-130">See also</span></span>

- [<span data-ttu-id="2866c-131">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="2866c-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="2866c-132">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="2866c-132">Built-in types table</span></span>](../keywords/built-in-types-table.md)
- [<span data-ttu-id="2866c-133">文字列</span><span class="sxs-lookup"><span data-stu-id="2866c-133">Strings</span></span>](../../programming-guide/strings/index.md)
