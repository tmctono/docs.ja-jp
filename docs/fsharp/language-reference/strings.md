---
title: 文字列
description: "' String ' F#型が Unicode 文字のシーケンスとして不変テキストを表す方法について説明します。"
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452819"
---
# <a name="strings"></a><span data-ttu-id="ef3f3-103">文字列</span><span class="sxs-lookup"><span data-stu-id="ef3f3-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="ef3f3-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="ef3f3-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ef3f3-106">`string` 型は、変更できないテキストを Unicode 文字のシーケンスとして表します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="ef3f3-107">`string` は、.NET Framework の `System.String` のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef3f3-108">コメント</span><span class="sxs-lookup"><span data-stu-id="ef3f3-108">Remarks</span></span>

<span data-ttu-id="ef3f3-109">文字列リテラルは引用符 (") で区切られます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="ef3f3-110">バックスラッシュ文字 (\\) は、特定の特殊文字をエンコードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="ef3f3-111">円記号と次の文字は、*エスケープシーケンス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="ef3f3-112">次の表にF# 、文字列リテラルでサポートされているエスケープシーケンスを示します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="ef3f3-113">文字</span><span class="sxs-lookup"><span data-stu-id="ef3f3-113">Character</span></span>|<span data-ttu-id="ef3f3-114">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="ef3f3-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="ef3f3-115">アラート</span><span class="sxs-lookup"><span data-stu-id="ef3f3-115">Alert</span></span>|`\a`|
|<span data-ttu-id="ef3f3-116">バックスペース</span><span class="sxs-lookup"><span data-stu-id="ef3f3-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="ef3f3-117">改ページ</span><span class="sxs-lookup"><span data-stu-id="ef3f3-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="ef3f3-118">改行</span><span class="sxs-lookup"><span data-stu-id="ef3f3-118">Newline</span></span>|`\n`|
|<span data-ttu-id="ef3f3-119">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="ef3f3-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="ef3f3-120">タブ</span><span class="sxs-lookup"><span data-stu-id="ef3f3-120">Tab</span></span>|`\t`|
|<span data-ttu-id="ef3f3-121">垂直タブ</span><span class="sxs-lookup"><span data-stu-id="ef3f3-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="ef3f3-122">円記号</span><span class="sxs-lookup"><span data-stu-id="ef3f3-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="ef3f3-123">引用符</span><span class="sxs-lookup"><span data-stu-id="ef3f3-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="ef3f3-124">単一</span><span class="sxs-lookup"><span data-stu-id="ef3f3-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="ef3f3-125">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ef3f3-125">Unicode character</span></span>|<span data-ttu-id="ef3f3-126">`\DDD` (`D` は10進数字、000-255 の範囲を示します。たとえば、`\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="ef3f3-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="ef3f3-127">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ef3f3-127">Unicode character</span></span>|<span data-ttu-id="ef3f3-128">`\xHH` (`H` は16進数字、00 ~ FF の範囲、たとえば `\xE7` = "ç") を示します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="ef3f3-129">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ef3f3-129">Unicode character</span></span>|<span data-ttu-id="ef3f3-130">`\uHHHH` (UTF-16) (`H` は16進数の数字、0000 ~ FFFF の範囲を示します。 たとえば、`\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="ef3f3-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="ef3f3-131">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ef3f3-131">Unicode character</span></span>|<span data-ttu-id="ef3f3-132">`\U00HHHHHH` (32) (`H` は16進数の数字、000000 ~ 10FFFF の範囲を示します。 たとえば、`\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="ef3f3-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ef3f3-133">`\DDD` エスケープシーケンスは、他のほとんどの言語のような8進数表記ではなく、10進表記です。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="ef3f3-134">したがって、`8` と `9` の数字は有効で、`\032` のシーケンスはスペース (U + 0020) を表しますが、8進数の同じコードポイントは `\040`されます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="ef3f3-135">0-255 (0xFF) の範囲に制限されている場合、`\DDD` と `\x` のエスケープシーケンスは、実際には、最初の 256 Unicode コードポイントと一致するため、 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)文字セットになります。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="ef3f3-136">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="ef3f3-136">Verbatim Strings</span></span>

<span data-ttu-id="ef3f3-137">前に @ 記号が付いている場合、リテラルは逐語的文字列になります。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="ef3f3-138">これは、2つの引用符文字が1つの引用符文字として解釈される点を除いて、すべてのエスケープシーケンスが無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="ef3f3-139">三重引用符で囲まれた文字列</span><span class="sxs-lookup"><span data-stu-id="ef3f3-139">Triple Quoted Strings</span></span>

<span data-ttu-id="ef3f3-140">さらに、文字列を三重引用符で囲むこともできます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="ef3f3-141">この場合、二重引用符文字を含め、すべてのエスケープシーケンスが無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="ef3f3-142">引用符で囲まれた埋め込み文字列を含む文字列を指定するには、逐語的文字列または三重引用符で囲んだ文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="ef3f3-143">逐語的文字列を使用する場合は、単一引用符文字を示す2つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="ef3f3-144">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析することなく、単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="ef3f3-145">この手法は、XML や、埋め込み引用符を含むその他の構造体を操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="ef3f3-146">コードでは、改行文字を含む文字列は改行文字として解釈されますが、バックスラッシュ文字が改行前の最後の文字である場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="ef3f3-147">円記号が使用されている場合、次の行の先頭の空白文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="ef3f3-148">次のコードでは、値 `"abc\ndef"` を持つ文字列 `str1` と、値 `"abcdef"`を持つ文字列 `str2` が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="ef3f3-149">文字列のインデックス作成とスライス</span><span class="sxs-lookup"><span data-stu-id="ef3f3-149">String Indexing and Slicing</span></span>

<span data-ttu-id="ef3f3-150">次のように、配列に似た構文を使用して、文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="ef3f3-151">出力は `b`になります。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-151">The output is `b`.</span></span>

<span data-ttu-id="ef3f3-152">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="ef3f3-153">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="ef3f3-154">ASCII 文字列は、符号なしバイトの配列で表すことができます `byte[]`型。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="ef3f3-155">文字列リテラルにサフィックス `B` を追加して、それが ASCII 文字列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="ef3f3-156">バイト配列で使用される ASCII 文字列リテラルでは、unicode エスケープシーケンスを除き、Unicode 文字列と同じエスケープシーケンスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="ef3f3-157">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="ef3f3-157">String Operators</span></span>

<span data-ttu-id="ef3f3-158">文字列を連結するには、`+` 演算子を使用する方法と `^` 演算子を使用する方法の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-158">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="ef3f3-159">`+` 演算子は、.NET Framework 文字列処理機能との互換性を維持します。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-159">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="ef3f3-160">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-160">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="ef3f3-161">String クラス</span><span class="sxs-lookup"><span data-stu-id="ef3f3-161">String Class</span></span>

<span data-ttu-id="ef3f3-162">のF#文字列型は実際には .NET Framework `System.String` 型であるため、すべての `System.String` メンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-162">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="ef3f3-163">これには、文字列を連結するために使用される `+` 演算子、`Length` プロパティ、および Unicode 文字の配列として文字列を返す `Chars` プロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-163">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="ef3f3-164">文字列の詳細については、「`System.String`」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-164">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="ef3f3-165">`System.String`の `Chars` プロパティを使用すると、次のコードに示すように、インデックスを指定することによって文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-165">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="ef3f3-166">文字列モジュール</span><span class="sxs-lookup"><span data-stu-id="ef3f3-166">String Module</span></span>

<span data-ttu-id="ef3f3-167">文字列処理の追加機能は、`FSharp.Core` 名前空間の `String` モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-167">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="ef3f3-168">詳細については、「 [Core. 文字列モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef3f3-168">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef3f3-169">参照</span><span class="sxs-lookup"><span data-stu-id="ef3f3-169">See also</span></span>

- [<span data-ttu-id="ef3f3-170">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ef3f3-170">F# Language Reference</span></span>](index.md)
