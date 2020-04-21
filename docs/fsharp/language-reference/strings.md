---
title: 文字列
description: F# 'string' 型が、不変のテキストを Unicode 文字のシーケンスとして表す方法について説明します。
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739571"
---
# <a name="strings"></a><span data-ttu-id="ff1db-103">文字列</span><span class="sxs-lookup"><span data-stu-id="ff1db-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="ff1db-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="ff1db-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="ff1db-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="ff1db-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ff1db-106">この`string`型は、変更できないテキストを Unicode 文字のシーケンスとして表します。</span><span class="sxs-lookup"><span data-stu-id="ff1db-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="ff1db-107">`string` は、.NET Framework の `System.String` のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="ff1db-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff1db-108">解説</span><span class="sxs-lookup"><span data-stu-id="ff1db-108">Remarks</span></span>

<span data-ttu-id="ff1db-109">文字列リテラルは、引用符 (") 文字で区切られます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="ff1db-110">円記号 ( \\ ) は、特定の特殊文字をエンコードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="ff1db-111">バックスラッシュと次の文字はエスケープシーケンスと呼*ばれます*。</span><span class="sxs-lookup"><span data-stu-id="ff1db-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="ff1db-112">F# 文字列リテラルでサポートされているエスケープ シーケンスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ff1db-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="ff1db-113">文字</span><span class="sxs-lookup"><span data-stu-id="ff1db-113">Character</span></span>|<span data-ttu-id="ff1db-114">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="ff1db-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="ff1db-115">アラート:</span><span class="sxs-lookup"><span data-stu-id="ff1db-115">Alert</span></span>|`\a`|
|<span data-ttu-id="ff1db-116">バックスペース</span><span class="sxs-lookup"><span data-stu-id="ff1db-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="ff1db-117">改ページ</span><span class="sxs-lookup"><span data-stu-id="ff1db-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="ff1db-118">改行</span><span class="sxs-lookup"><span data-stu-id="ff1db-118">Newline</span></span>|`\n`|
|<span data-ttu-id="ff1db-119">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="ff1db-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="ff1db-120">タブ</span><span class="sxs-lookup"><span data-stu-id="ff1db-120">Tab</span></span>|`\t`|
|<span data-ttu-id="ff1db-121">垂直タブ</span><span class="sxs-lookup"><span data-stu-id="ff1db-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="ff1db-122">円記号</span><span class="sxs-lookup"><span data-stu-id="ff1db-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="ff1db-123">引用符</span><span class="sxs-lookup"><span data-stu-id="ff1db-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="ff1db-124">アポストロフィ</span><span class="sxs-lookup"><span data-stu-id="ff1db-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="ff1db-125">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ff1db-125">Unicode character</span></span>|<span data-ttu-id="ff1db-126">`\DDD`(ここで`D`、10 進数、000 から 255 の範囲`\231`、たとえば、="ç")</span><span class="sxs-lookup"><span data-stu-id="ff1db-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="ff1db-127">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ff1db-127">Unicode character</span></span>|<span data-ttu-id="ff1db-128">`\xHH`(ここで`H`、16 進数を示し、範囲は 00 から`\xE7`FF、例えば、"ç")</span><span class="sxs-lookup"><span data-stu-id="ff1db-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="ff1db-129">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ff1db-129">Unicode character</span></span>|<span data-ttu-id="ff1db-130">`\uHHHH`(UTF-16)(ここで`H`、16 進数を示し、0000 から FFFF の範囲を示します。 たとえば、="ç") `\u00E7`</span><span class="sxs-lookup"><span data-stu-id="ff1db-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="ff1db-131">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ff1db-131">Unicode character</span></span>|<span data-ttu-id="ff1db-132">`\U00HHHHHH`(UTF-32)(ここで`H`、16 進数を示し、000000 から 10FFFF の範囲を示します。 たとえば、= `\U0001F47D` "👽" "</span><span class="sxs-lookup"><span data-stu-id="ff1db-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ff1db-133">`\DDD`エスケープ シーケンスは 10 進数表記であり、他のほとんどの言語のように 8 進数表記ではありません。</span><span class="sxs-lookup"><span data-stu-id="ff1db-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="ff1db-134">したがって、数字`8`と`9`は有効であり、シーケンスは`\032`スペース(U+0020)を表しますが、8 進数表記の同じコードポイントは`\040`.</span><span class="sxs-lookup"><span data-stu-id="ff1db-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="ff1db-135">0 ~ 255 (0xFF) の範囲に`\DDD`制約`\x`されているエスケープ シーケンスとエスケープ シーケンスは、最初の 256 個の Unicode コード ポイントと一致するため、実質的には[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)文字セットになります。</span><span class="sxs-lookup"><span data-stu-id="ff1db-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="ff1db-136">逐語的な文字列</span><span class="sxs-lookup"><span data-stu-id="ff1db-136">Verbatim Strings</span></span>

<span data-ttu-id="ff1db-137">@ 記号が前に付いている場合、リテラルは逐語的な文字列です。</span><span class="sxs-lookup"><span data-stu-id="ff1db-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="ff1db-138">これは、2 つの引用符文字が 1 つの引用符文字として解釈されることを除いて、エスケープ・シーケンスはすべて無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ff1db-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="ff1db-139">三重引用符文字列</span><span class="sxs-lookup"><span data-stu-id="ff1db-139">Triple Quoted Strings</span></span>

<span data-ttu-id="ff1db-140">また、文字列は三重引用符で囲む場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff1db-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="ff1db-141">この場合、二重引用符文字を含め、すべてのエスケープ・シーケンスは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="ff1db-142">埋め込み引用符付き文字列を含む文字列を指定するには、逐語的文字列または三重引用符で囲まれた文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="ff1db-143">逐語的文字列を使用する場合は、単一引用符文字を示す 2 つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff1db-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="ff1db-144">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析されずに単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="ff1db-145">この方法は、XML や、引用符が埋め込まれた他の構造を操作する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="ff1db-146">コードでは、改行のある文字列は受け入れられ、改行文字は改行前の最後の文字でない限り、改行文字は改行として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="ff1db-147">円記号文字を使用する場合、次の行の先頭の空白は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="ff1db-148">次のコードは、値`str1`を持つ`"abc\ndef"`文字列と値`str2`を持つ`"abcdef"`文字列を生成します。</span><span class="sxs-lookup"><span data-stu-id="ff1db-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="ff1db-149">文字列のインデックス作成とスライス</span><span class="sxs-lookup"><span data-stu-id="ff1db-149">String Indexing and Slicing</span></span>

<span data-ttu-id="ff1db-150">次のように、配列のような構文を使用して、文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="ff1db-151">出力は `b`になります。</span><span class="sxs-lookup"><span data-stu-id="ff1db-151">The output is `b`.</span></span>

<span data-ttu-id="ff1db-152">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="ff1db-153">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ff1db-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="ff1db-154">ASCII 文字列は、符号なしバイトの配列で表すことができます`byte[]`。</span><span class="sxs-lookup"><span data-stu-id="ff1db-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="ff1db-155">文字列リテラルにサフィックス`B`を追加して、それが ASCII 文字列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="ff1db-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="ff1db-156">バイト配列で使用される ASCII 文字列リテラルは、Unicode エスケープ シーケンスを除き、Unicode 文字列と同じエスケープ シーケンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ff1db-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="ff1db-157">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="ff1db-157">String Operators</span></span>

<span data-ttu-id="ff1db-158">この`+`演算子を使用して文字列を連結し、.NET Framework の文字列処理機能との互換性を維持できます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="ff1db-159">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff1db-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="ff1db-160">文字列クラス</span><span class="sxs-lookup"><span data-stu-id="ff1db-160">String Class</span></span>

<span data-ttu-id="ff1db-161">F# の文字列型は実際には .NET `System.String` Framework 型であるため`System.String`、すべてのメンバーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="ff1db-162">これには、文字列`+`を連結するために使用される演算子、`Length`プロパティ、および Unicode 文字の`Chars`配列として文字列を返すプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="ff1db-163">文字列の詳細については、を参照`System.String`してください。</span><span class="sxs-lookup"><span data-stu-id="ff1db-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="ff1db-164">のプロパティを`Chars`使用すると`System.String`、次のコードに示すように、インデックスを指定して文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ff1db-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="ff1db-165">文字列モジュール</span><span class="sxs-lookup"><span data-stu-id="ff1db-165">String Module</span></span>

<span data-ttu-id="ff1db-166">文字列処理の追加機能は、名前空間の`String`モジュールに`FSharp.Core`含まれています。</span><span class="sxs-lookup"><span data-stu-id="ff1db-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="ff1db-167">詳細については、「 [Core.String モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff1db-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff1db-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff1db-168">See also</span></span>

- [<span data-ttu-id="ff1db-169">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="ff1db-169">F# Language Reference</span></span>](index.md)
