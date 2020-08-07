---
title: 文字列
description: "F # の ' string ' 型が Unicode 文字のシーケンスとして不変テキストを表す方法について説明します。"
ms.date: 07/05/2019
ms.openlocfilehash: 67a6506b4b8c479da1022c069a7f53402f904b4d
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855414"
---
# <a name="strings"></a><span data-ttu-id="2aa40-103">文字列</span><span class="sxs-lookup"><span data-stu-id="2aa40-103">Strings</span></span>

<span data-ttu-id="2aa40-104">この `string` 型は、変更できないテキストを Unicode 文字のシーケンスとして表します。</span><span class="sxs-lookup"><span data-stu-id="2aa40-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="2aa40-105">`string` は .NET の `System.String` の別名です。</span><span class="sxs-lookup"><span data-stu-id="2aa40-105">`string` is an alias for `System.String` in .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="2aa40-106">F # の docs.microsoft.com API リファレンスが完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="2aa40-106">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="2aa40-107">壊れたリンクが見つかった場合は、代わりに[F # コアライブラリのドキュメント](https://fsharp.github.io/fsharp-core-docs/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa40-107">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="remarks"></a><span data-ttu-id="2aa40-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="2aa40-108">Remarks</span></span>

<span data-ttu-id="2aa40-109">文字列リテラルは引用符 (") で区切られます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="2aa40-110">バックスラッシュ文字 ( \\ ) は、特定の特殊文字をエンコードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="2aa40-111">円記号と次の文字は、*エスケープシーケンス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="2aa40-112">F # の文字列リテラルでサポートされているエスケープシーケンスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2aa40-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="2aa40-113">文字</span><span class="sxs-lookup"><span data-stu-id="2aa40-113">Character</span></span>|<span data-ttu-id="2aa40-114">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="2aa40-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="2aa40-115">アラート:</span><span class="sxs-lookup"><span data-stu-id="2aa40-115">Alert</span></span>|`\a`|
|<span data-ttu-id="2aa40-116">バックスペース</span><span class="sxs-lookup"><span data-stu-id="2aa40-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="2aa40-117">フォーム フィード</span><span class="sxs-lookup"><span data-stu-id="2aa40-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="2aa40-118">改行</span><span class="sxs-lookup"><span data-stu-id="2aa40-118">Newline</span></span>|`\n`|
|<span data-ttu-id="2aa40-119">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="2aa40-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="2aa40-120">タブ</span><span class="sxs-lookup"><span data-stu-id="2aa40-120">Tab</span></span>|`\t`|
|<span data-ttu-id="2aa40-121">垂直タブ</span><span class="sxs-lookup"><span data-stu-id="2aa40-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="2aa40-122">円記号</span><span class="sxs-lookup"><span data-stu-id="2aa40-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="2aa40-123">引用符</span><span class="sxs-lookup"><span data-stu-id="2aa40-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="2aa40-124">アポストロフィ</span><span class="sxs-lookup"><span data-stu-id="2aa40-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="2aa40-125">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="2aa40-125">Unicode character</span></span>|<span data-ttu-id="2aa40-126">`\DDD`(は `D` 10 進数字、000-255 の範囲、 `\231` = "ç" など)</span><span class="sxs-lookup"><span data-stu-id="2aa40-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="2aa40-127">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="2aa40-127">Unicode character</span></span>|<span data-ttu-id="2aa40-128">`\xHH`(は `H` 16 進数の数字、00 ~ FF の範囲、 `\xE7` = "ç" など)</span><span class="sxs-lookup"><span data-stu-id="2aa40-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="2aa40-129">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="2aa40-129">Unicode character</span></span>|<span data-ttu-id="2aa40-130">`\uHHHH`(UTF-16)(は `H` 16 進数の数字、0000 ~ FFFF の範囲を示します。 たとえば、 `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="2aa40-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="2aa40-131">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="2aa40-131">Unicode character</span></span>|<span data-ttu-id="2aa40-132">`\U00HHHHHH`(UTF-32)( `H` は16進数字、範囲 000000-10FFFF を示します。 たとえば、 `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="2aa40-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="2aa40-133">`\DDD`エスケープシーケンスは、他のほとんどの言語のような8進数表記ではなく、10進表記です。</span><span class="sxs-lookup"><span data-stu-id="2aa40-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="2aa40-134">したがって、桁数 `8` と `9` は有効であり、のシーケンスは `\032` 空白 (U + 0020) を表しますが、8進数表記では同じコードポイントが使用さ `\040` れます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="2aa40-135">0-255 (0xFF) の範囲に制限されている場合、とエスケープシーケンスは、実際には、 `\DDD` `\x` 最初の 256 Unicode コードポイントと一致するため、 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)文字セットになります。</span><span class="sxs-lookup"><span data-stu-id="2aa40-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="2aa40-136">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="2aa40-136">Verbatim Strings</span></span>

<span data-ttu-id="2aa40-137">前に @ 記号が付いている場合、リテラルは逐語的文字列になります。</span><span class="sxs-lookup"><span data-stu-id="2aa40-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="2aa40-138">これは、2つの引用符文字が1つの引用符文字として解釈される点を除いて、すべてのエスケープシーケンスが無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2aa40-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="2aa40-139">三重引用符で囲まれた文字列</span><span class="sxs-lookup"><span data-stu-id="2aa40-139">Triple Quoted Strings</span></span>

<span data-ttu-id="2aa40-140">さらに、文字列を三重引用符で囲むこともできます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="2aa40-141">この場合、二重引用符文字を含め、すべてのエスケープシーケンスが無視されます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="2aa40-142">引用符で囲まれた埋め込み文字列を含む文字列を指定するには、逐語的文字列または三重引用符で囲んだ文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="2aa40-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="2aa40-143">逐語的文字列を使用する場合は、単一引用符文字を示す2つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa40-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="2aa40-144">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析することなく、単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="2aa40-145">この手法は、XML や、埋め込み引用符を含むその他の構造体を操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2aa40-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="2aa40-146">コードでは、改行文字を含む文字列は改行文字として解釈されますが、バックスラッシュ文字が改行前の最後の文字である場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="2aa40-147">円記号が使用されている場合、次の行の先頭の空白文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="2aa40-148">次のコードでは、値を持つ文字列と値を持つ文字列が生成され `str1` `"abc\ndef"` `str2` `"abcdef"` ます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="2aa40-149">文字列のインデックス作成とスライス</span><span class="sxs-lookup"><span data-stu-id="2aa40-149">String Indexing and Slicing</span></span>

<span data-ttu-id="2aa40-150">次のように、配列に似た構文を使用して、文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="2aa40-151">出力は `b`になります。</span><span class="sxs-lookup"><span data-stu-id="2aa40-151">The output is `b`.</span></span>

<span data-ttu-id="2aa40-152">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="2aa40-153">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2aa40-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="2aa40-154">符号なしバイトの配列 (型) によって ASCII 文字列を表すことができ `byte[]` ます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="2aa40-155">文字列リテラルにサフィックスを追加し `B` て、ASCII 文字列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="2aa40-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="2aa40-156">バイト配列で使用される ASCII 文字列リテラルでは、unicode エスケープシーケンスを除き、Unicode 文字列と同じエスケープシーケンスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="2aa40-157">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="2aa40-157">String Operators</span></span>

<span data-ttu-id="2aa40-158">演算子を使用して文字列を `+` 連結し、文字列処理機能 .NET Framework との互換性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="2aa40-159">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="2aa40-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="2aa40-160">String クラス</span><span class="sxs-lookup"><span data-stu-id="2aa40-160">String Class</span></span>

<span data-ttu-id="2aa40-161">F # の文字列型は実際には .NET Framework 型であるため、 `System.String` すべての `System.String` メンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="2aa40-162">これには、文字列 `+` を連結するために使用される演算子、 `Length` プロパティ、および `Chars` Unicode 文字の配列として文字列を返すプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="2aa40-163">文字列の詳細については、「」を参照してください `System.String` 。</span><span class="sxs-lookup"><span data-stu-id="2aa40-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="2aa40-164">のプロパティを使用すると、 `Chars` `System.String` 次のコードに示すように、インデックスを指定することにより、文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="2aa40-165">文字列モジュール</span><span class="sxs-lookup"><span data-stu-id="2aa40-165">String Module</span></span>

<span data-ttu-id="2aa40-166">文字列処理の追加機能は、名前空間のモジュールに含まれてい `String` `FSharp.Core` ます。</span><span class="sxs-lookup"><span data-stu-id="2aa40-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="2aa40-167">詳細については、「 [Core. 文字列モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa40-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="2aa40-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="2aa40-168">See also</span></span>

- [<span data-ttu-id="2aa40-169">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="2aa40-169">F# Language Reference</span></span>](index.md)
