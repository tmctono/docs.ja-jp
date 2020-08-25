---
title: 文字列
description: "F # の ' string ' 型が Unicode 文字のシーケンスとして不変テキストを表す方法について説明します。"
ms.date: 08/15/2020
ms.openlocfilehash: f6ec36feeb197bf785c702e7b626cf5cf80696ab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812212"
---
# <a name="strings"></a><span data-ttu-id="c49e2-103">文字列</span><span class="sxs-lookup"><span data-stu-id="c49e2-103">Strings</span></span>

<span data-ttu-id="c49e2-104">この `string` 型は、変更できないテキストを Unicode 文字のシーケンスとして表します。</span><span class="sxs-lookup"><span data-stu-id="c49e2-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="c49e2-105">`string` は .NET の `System.String` の別名です。</span><span class="sxs-lookup"><span data-stu-id="c49e2-105">`string` is an alias for `System.String` in .NET.</span></span>

## <a name="remarks"></a><span data-ttu-id="c49e2-106">注釈</span><span class="sxs-lookup"><span data-stu-id="c49e2-106">Remarks</span></span>

<span data-ttu-id="c49e2-107">文字列リテラルは引用符 (") で区切られます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-107">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="c49e2-108">バックスラッシュ文字 ( \\ ) は、特定の特殊文字をエンコードするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-108">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="c49e2-109">円記号と次の文字は、 *エスケープシーケンス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-109">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="c49e2-110">F # の文字列リテラルでサポートされているエスケープシーケンスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="c49e2-110">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="c49e2-111">文字</span><span class="sxs-lookup"><span data-stu-id="c49e2-111">Character</span></span>|<span data-ttu-id="c49e2-112">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="c49e2-112">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="c49e2-113">アラート:</span><span class="sxs-lookup"><span data-stu-id="c49e2-113">Alert</span></span>|`\a`|
|<span data-ttu-id="c49e2-114">バックスペース</span><span class="sxs-lookup"><span data-stu-id="c49e2-114">Backspace</span></span>|`\b`|
|<span data-ttu-id="c49e2-115">フォーム フィード</span><span class="sxs-lookup"><span data-stu-id="c49e2-115">Form feed</span></span>|`\f`|
|<span data-ttu-id="c49e2-116">改行</span><span class="sxs-lookup"><span data-stu-id="c49e2-116">Newline</span></span>|`\n`|
|<span data-ttu-id="c49e2-117">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="c49e2-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="c49e2-118">タブ</span><span class="sxs-lookup"><span data-stu-id="c49e2-118">Tab</span></span>|`\t`|
|<span data-ttu-id="c49e2-119">垂直タブ</span><span class="sxs-lookup"><span data-stu-id="c49e2-119">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="c49e2-120">円記号</span><span class="sxs-lookup"><span data-stu-id="c49e2-120">Backslash</span></span>|`\\`|
|<span data-ttu-id="c49e2-121">引用符</span><span class="sxs-lookup"><span data-stu-id="c49e2-121">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="c49e2-122">アポストロフィ</span><span class="sxs-lookup"><span data-stu-id="c49e2-122">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="c49e2-123">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="c49e2-123">Unicode character</span></span>|<span data-ttu-id="c49e2-124">`\DDD` (は `D` 10 進数字、000-255 の範囲、 `\231` = "ç" など)</span><span class="sxs-lookup"><span data-stu-id="c49e2-124">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="c49e2-125">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="c49e2-125">Unicode character</span></span>|<span data-ttu-id="c49e2-126">`\xHH` (は `H` 16 進数の数字、00 ~ FF の範囲、 `\xE7` = "ç" など)</span><span class="sxs-lookup"><span data-stu-id="c49e2-126">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="c49e2-127">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="c49e2-127">Unicode character</span></span>|<span data-ttu-id="c49e2-128">`\uHHHH` (UTF-16)(は `H` 16 進数の数字、0000 ~ FFFF の範囲を示します。 たとえば、 `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="c49e2-128">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="c49e2-129">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="c49e2-129">Unicode character</span></span>|<span data-ttu-id="c49e2-130">`\U00HHHHHH` (UTF-32)( `H` は16進数字、範囲 000000-10FFFF を示します。 たとえば、 `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="c49e2-130">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="c49e2-131">`\DDD`エスケープシーケンスは、他のほとんどの言語のような8進数表記ではなく、10進表記です。</span><span class="sxs-lookup"><span data-stu-id="c49e2-131">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="c49e2-132">したがって、桁数 `8` と `9` は有効であり、のシーケンスは `\032` 空白 (U + 0020) を表しますが、8進数表記では同じコードポイントが使用さ `\040` れます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-132">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="c49e2-133">0-255 (0xFF) の範囲に制限されている場合、とエスケープシーケンスは、実際には、 `\DDD` `\x` 最初の 256 Unicode コードポイントと一致するため、 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 文字セットになります。</span><span class="sxs-lookup"><span data-stu-id="c49e2-133">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="c49e2-134">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="c49e2-134">Verbatim Strings</span></span>

<span data-ttu-id="c49e2-135">前に @ 記号が付いている場合、リテラルは逐語的文字列になります。</span><span class="sxs-lookup"><span data-stu-id="c49e2-135">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="c49e2-136">これは、2つの引用符文字が1つの引用符文字として解釈される点を除いて、すべてのエスケープシーケンスが無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c49e2-136">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="c49e2-137">三重引用符で囲まれた文字列</span><span class="sxs-lookup"><span data-stu-id="c49e2-137">Triple Quoted Strings</span></span>

<span data-ttu-id="c49e2-138">さらに、文字列を三重引用符で囲むこともできます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="c49e2-139">この場合、二重引用符文字を含め、すべてのエスケープシーケンスが無視されます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="c49e2-140">引用符で囲まれた埋め込み文字列を含む文字列を指定するには、逐語的文字列または三重引用符で囲んだ文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="c49e2-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="c49e2-141">逐語的文字列を使用する場合は、単一引用符文字を示す2つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c49e2-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="c49e2-142">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析することなく、単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="c49e2-143">この手法は、XML や、埋め込み引用符を含むその他の構造体を操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c49e2-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="c49e2-144">コードでは、改行文字を含む文字列は改行文字として解釈されますが、バックスラッシュ文字が改行前の最後の文字である場合は除きます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="c49e2-145">円記号が使用されている場合、次の行の先頭の空白文字は無視されます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="c49e2-146">次のコードでは、値を持つ文字列と値を持つ文字列が生成され `str1` `"abc\ndef"` `str2` `"abcdef"` ます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="c49e2-147">文字列のインデックス作成とスライス</span><span class="sxs-lookup"><span data-stu-id="c49e2-147">String Indexing and Slicing</span></span>

<span data-ttu-id="c49e2-148">次のように、配列に似た構文を使用して、文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-148">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="c49e2-149">出力は `b` になります。</span><span class="sxs-lookup"><span data-stu-id="c49e2-149">The output is `b`.</span></span>

<span data-ttu-id="c49e2-150">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出することもできます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-150">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="c49e2-151">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c49e2-151">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="c49e2-152">符号なしバイトの配列 (型) によって ASCII 文字列を表すことができ `byte[]` ます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-152">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="c49e2-153">文字列リテラルにサフィックスを追加し `B` て、ASCII 文字列であることを示します。</span><span class="sxs-lookup"><span data-stu-id="c49e2-153">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="c49e2-154">バイト配列で使用される ASCII 文字列リテラルでは、unicode エスケープシーケンスを除き、Unicode 文字列と同じエスケープシーケンスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-154">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="c49e2-155">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="c49e2-155">String Operators</span></span>

<span data-ttu-id="c49e2-156">演算子を使用して文字列を `+` 連結し、文字列処理機能 .NET Framework との互換性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-156">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="c49e2-157">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="c49e2-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="c49e2-158">String クラス</span><span class="sxs-lookup"><span data-stu-id="c49e2-158">String Class</span></span>

<span data-ttu-id="c49e2-159">F # の文字列型は実際には .NET Framework 型であるため、 `System.String` すべての `System.String` メンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="c49e2-160">これには、文字列 `+` を連結するために使用される演算子、 `Length` プロパティ、および `Chars` Unicode 文字の配列として文字列を返すプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="c49e2-161">文字列の詳細については、「」を参照してください `System.String` 。</span><span class="sxs-lookup"><span data-stu-id="c49e2-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="c49e2-162">のプロパティを使用すると、 `Chars` `System.String` 次のコードに示すように、インデックスを指定することにより、文字列内の個々の文字にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="c49e2-163">文字列モジュール</span><span class="sxs-lookup"><span data-stu-id="c49e2-163">String Module</span></span>

<span data-ttu-id="c49e2-164">文字列処理の追加機能は、名前空間のモジュールに含まれてい `String` `FSharp.Core` ます。</span><span class="sxs-lookup"><span data-stu-id="c49e2-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="c49e2-165">詳細については、「 [文字列モジュール](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c49e2-165">For more information, see [String Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="c49e2-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="c49e2-166">See also</span></span>

- [<span data-ttu-id="c49e2-167">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="c49e2-167">F# Language Reference</span></span>](index.md)
