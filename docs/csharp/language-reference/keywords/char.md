---
title: char キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 10/22/2019
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 1b9f8d1bb205a6cbfe521830a11bd8878ccde991
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771798"
---
# <a name="char-c-reference"></a><span data-ttu-id="d9bb6-102">char (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="d9bb6-102">char (C# reference)</span></span>

<span data-ttu-id="d9bb6-103">`char` 型のキーワードは、Unicode UTF-16 文字を表す .NET <xref:System.Char?displayProperty=nameWithType> 構造体型のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-103">The `char` type keyword is an alias for the .NET <xref:System.Char?displayProperty=nameWithType> structure type that represents a Unicode UTF-16 character:</span></span>

|<span data-ttu-id="d9bb6-104">型</span><span class="sxs-lookup"><span data-stu-id="d9bb6-104">Type</span></span>|<span data-ttu-id="d9bb6-105">範囲</span><span class="sxs-lookup"><span data-stu-id="d9bb6-105">Range</span></span>|<span data-ttu-id="d9bb6-106">サイズ</span><span class="sxs-lookup"><span data-stu-id="d9bb6-106">Size</span></span>|<span data-ttu-id="d9bb6-107">.NET 型</span><span class="sxs-lookup"><span data-stu-id="d9bb6-107">.NET type</span></span>|
|----------|-----------|----------|-------------------------|
|`char`|<span data-ttu-id="d9bb6-108">U+0000 ～ U+FFFF</span><span class="sxs-lookup"><span data-stu-id="d9bb6-108">U+0000 to U+FFFF</span></span>|<span data-ttu-id="d9bb6-109">16 ビット</span><span class="sxs-lookup"><span data-stu-id="d9bb6-109">16 bit</span></span>|<xref:System.Char?displayProperty=nameWithType>|

## <a name="literals"></a><span data-ttu-id="d9bb6-110">リテラル</span><span class="sxs-lookup"><span data-stu-id="d9bb6-110">Literals</span></span>

<span data-ttu-id="d9bb6-111">`char` 型の定数は、文字リテラル、16 進数のエスケープ シーケンス、または Unicode 表現として記述できます。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-111">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="d9bb6-112">また、整数の文字コードを対応する `char` 値にキャストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-112">You can also cast an integral character code into the corresponding `char` value.</span></span> <span data-ttu-id="d9bb6-113">次の例では、`char` の配列の 4 つの要素が同じ文字 `X` を使用して初期化されています。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-113">In the following example, the four elements of an array of `char` are initialized with the same character `X`:</span></span>

[!code-csharp[csrefKeywordsTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#19)]

## <a name="conversions"></a><span data-ttu-id="d9bb6-114">変換</span><span class="sxs-lookup"><span data-stu-id="d9bb6-114">Conversions</span></span>

<span data-ttu-id="d9bb6-115">`char` 型は、[整数](../builtin-types/integral-numeric-types.md)型 (`ushort`、`int`、`uint`、`long`、`ulong`) に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-115">The `char` type is implicitly convertible to the following [integral](../builtin-types/integral-numeric-types.md) types: `ushort`, `int`, `uint`, `long`, and `ulong`.</span></span> <span data-ttu-id="d9bb6-116">また、組み込みの[浮動小数点](../builtin-types/floating-point-numeric-types.md)数値型 (`float`、`double`、`decimal`) に暗黙的に変換することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-116">It's also implicitly convertible to the built-in [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types: `float`, `double`, and `decimal`.</span></span> <span data-ttu-id="d9bb6-117">`sbyte`、`byte`、`short` 整数型に明示的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-117">It's explicitly convertible to `sbyte`, `byte`, and `short` integral types.</span></span>

<span data-ttu-id="d9bb6-118">他の型から `char` 型へと暗黙的に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-118">There are no implicit conversions from other types to the `char` type.</span></span> <span data-ttu-id="d9bb6-119">しかし、[整数](../builtin-types/integral-numeric-types.md)または[浮動小数点](../builtin-types/floating-point-numeric-types.md)の数値型は、`char` に明示的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-119">However, any [integral](../builtin-types/integral-numeric-types.md) or [floating-point](../builtin-types/floating-point-numeric-types.md) numeric type is explicitly convertible to `char`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d9bb6-120">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="d9bb6-120">C# language specification</span></span>

<span data-ttu-id="d9bb6-121">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[整数型](~/_csharplang/spec/types.md#integral-types)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9bb6-121">For more information, see the [Integral types](~/_csharplang/spec/types.md#integral-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9bb6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9bb6-122">See also</span></span>

- [<span data-ttu-id="d9bb6-123">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="d9bb6-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d9bb6-124">C# キーワード</span><span class="sxs-lookup"><span data-stu-id="d9bb6-124">C# keywords</span></span>](./index.md)
- [<span data-ttu-id="d9bb6-125">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="d9bb6-125">Built-in types table</span></span>](./built-in-types-table.md)
- [<span data-ttu-id="d9bb6-126">文字列</span><span class="sxs-lookup"><span data-stu-id="d9bb6-126">Strings</span></span>](../../programming-guide/strings/index.md)
- <xref:System.Char?displayProperty=nameWithType>
