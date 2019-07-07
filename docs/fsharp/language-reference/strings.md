---
title: 文字列
description: について説明しますが、どのようにF#'string' 型では、変更不可のテキストを表す Unicode 文字のシーケンスとして。
ms.date: 07/05/2019
ms.openlocfilehash: b252aef7d7e6e299df8282407198714971e80cd5
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610160"
---
# <a name="strings"></a><span data-ttu-id="eada8-103">文字列</span><span class="sxs-lookup"><span data-stu-id="eada8-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="eada8-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="eada8-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="eada8-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="eada8-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="eada8-106">`string`型が Unicode 文字のシーケンスとして変更不可のテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="eada8-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="eada8-107">`string` は、.NET Framework の `System.String` のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="eada8-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="eada8-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="eada8-108">Remarks</span></span>

<span data-ttu-id="eada8-109">文字列リテラルは引用符 (") 文字で区切られます。</span><span class="sxs-lookup"><span data-stu-id="eada8-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="eada8-110">円記号 ( \\ ) 特定の特殊文字をエンコードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="eada8-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="eada8-111">円記号と、次の文字の組み合わせと呼ばれる、*エスケープ シーケンス*します。</span><span class="sxs-lookup"><span data-stu-id="eada8-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="eada8-112">エスケープ シーケンスが F# 文字列リテラルは、次の表に示すでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eada8-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="eada8-113">文字</span><span class="sxs-lookup"><span data-stu-id="eada8-113">Character</span></span>|<span data-ttu-id="eada8-114">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="eada8-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="eada8-115">警告</span><span class="sxs-lookup"><span data-stu-id="eada8-115">Alert</span></span>|`\a`|
|<span data-ttu-id="eada8-116">バックスペース</span><span class="sxs-lookup"><span data-stu-id="eada8-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="eada8-117">フォーム フィード</span><span class="sxs-lookup"><span data-stu-id="eada8-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="eada8-118">改行</span><span class="sxs-lookup"><span data-stu-id="eada8-118">Newline</span></span>|`\n`|
|<span data-ttu-id="eada8-119">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="eada8-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="eada8-120">タブ</span><span class="sxs-lookup"><span data-stu-id="eada8-120">Tab</span></span>|`\t`|
|<span data-ttu-id="eada8-121">垂直タブ</span><span class="sxs-lookup"><span data-stu-id="eada8-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="eada8-122">円記号</span><span class="sxs-lookup"><span data-stu-id="eada8-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="eada8-123">引用符</span><span class="sxs-lookup"><span data-stu-id="eada8-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="eada8-124">アポストロフィ</span><span class="sxs-lookup"><span data-stu-id="eada8-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="eada8-125">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="eada8-125">Unicode character</span></span>|<span data-ttu-id="eada8-126">`\DDD` (場所`D`10 進数を示す数字です - 000 の範囲 255 は、たとえば`\231`="ç")。</span><span class="sxs-lookup"><span data-stu-id="eada8-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; e.g. `\231` = "ç")</span></span>|
|<span data-ttu-id="eada8-127">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="eada8-127">Unicode character</span></span>|<span data-ttu-id="eada8-128">`\xHH` (場所`H`の 16 進数値です 00 ~ FF; の範囲を示しますたとえば`\xE7`="ç")。</span><span class="sxs-lookup"><span data-stu-id="eada8-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; e.g. `\xE7` = "ç")</span></span>|
|<span data-ttu-id="eada8-129">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="eada8-129">Unicode character</span></span>|<span data-ttu-id="eada8-130">`\uHHHH` (UTF-16)(場所`H`の 16 進数値です 0000 - FFFF; の範囲を示します。 例: `\u00E7` =「ç」)</span><span class="sxs-lookup"><span data-stu-id="eada8-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  e.g. `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="eada8-131">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="eada8-131">Unicode character</span></span>|<span data-ttu-id="eada8-132">`\U00HHHHHH` (UTF-32)(場所`H`の 16 進数値です 000000 - 10 ffff; の範囲を示します。 例: `\U0001F47D` ="👽")</span><span class="sxs-lookup"><span data-stu-id="eada8-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  e.g. `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="eada8-133">`\DDD`エスケープ シーケンスは、その他のほとんどの言語でなどのない 8 進数表記の 10 進表記。</span><span class="sxs-lookup"><span data-stu-id="eada8-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="eada8-134">したがって、桁`8`と`9`有効では、一連の`\032`空白を表します (u+0020)、8 進数表記で同じコード ポイントになりますが、`\040`します。</span><span class="sxs-lookup"><span data-stu-id="eada8-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="eada8-135">0 の範囲に制約されている - 255 (0 xff)、`\DDD`と`\x`エスケープ シーケンスは、実質的に、 [ISO 8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout)文字セットの最初の 256 個の Unicode コード ポイントと一致するためです。</span><span class="sxs-lookup"><span data-stu-id="eada8-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="eada8-136">前にある場合、@ 記号、リテラルには、逐語的文字列。</span><span class="sxs-lookup"><span data-stu-id="eada8-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="eada8-137">つまり、2 つの引用符文字が 1 つの引用符文字として解釈される点が異なりますエスケープ シーケンスが無視します。</span><span class="sxs-lookup"><span data-stu-id="eada8-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="eada8-138">さらに、文字列の場合は、三重引用符で囲まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eada8-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="eada8-139">この場合、すべてのエスケープ シーケンスは無視されます、二重引用符文字も含まれます。</span><span class="sxs-lookup"><span data-stu-id="eada8-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="eada8-140">埋め込まれた文字列を引用符で囲まれたを含む文字列を指定するには、逐語的文字列または三重引用符で囲まれた文字列か、使用できます。</span><span class="sxs-lookup"><span data-stu-id="eada8-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="eada8-141">逐語的文字列を使用する場合は、一重引用符文字を示す 2 つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eada8-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="eada8-142">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析することがなく、単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="eada8-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="eada8-143">この方法は、XML または埋め込まれた引用符を含むその他の構造を操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="eada8-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="eada8-144">コードでは、文字列は、改行が受け入れられ、改行以外として解釈されますとして改行、円記号が改行の前に最後の文字。</span><span class="sxs-lookup"><span data-stu-id="eada8-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="eada8-145">次の行の先頭の空白文字には、円記号を使用する場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="eada8-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="eada8-146">次のコードには、文字列が生成されます。`str1`値を持つ`"abc\ndef"`と文字列`str2`値を持つ`"abcdef"`します。</span><span class="sxs-lookup"><span data-stu-id="eada8-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="eada8-147">文字列の個々 の文字は、次のように配列に似た構文を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eada8-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="eada8-148">出力は `b`になります。</span><span class="sxs-lookup"><span data-stu-id="eada8-148">The output is `b`.</span></span>

<span data-ttu-id="eada8-149">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="eada8-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="eada8-150">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eada8-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="eada8-151">ASCII 文字列型の符号なしバイトの配列で表現できます`byte[]`します。</span><span class="sxs-lookup"><span data-stu-id="eada8-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="eada8-152">サフィックスを追加する`B`を ASCII 文字列であることを示すリテラル文字列にします。</span><span class="sxs-lookup"><span data-stu-id="eada8-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="eada8-153">ASCII 文字列リテラルのバイト配列を使用では、Unicode のエスケープ シーケンスを除く、Unicode 文字列として同じエスケープ シーケンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="eada8-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="eada8-154">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="eada8-154">String Operators</span></span>

<span data-ttu-id="eada8-155">文字列を連結する 2 つの方法があります: を使用して、`+`演算子またはを使用して、`^`演算子。</span><span class="sxs-lookup"><span data-stu-id="eada8-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="eada8-156">`+`演算子が、.NET Framework の文字列処理機能との互換性を維持します。</span><span class="sxs-lookup"><span data-stu-id="eada8-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="eada8-157">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="eada8-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="eada8-158">String クラス</span><span class="sxs-lookup"><span data-stu-id="eada8-158">String Class</span></span>

<span data-ttu-id="eada8-159">文字列を入力するためF#.NET Framework では実際には、`System.String`すべての入力、`System.String`メンバーが使用可能です。</span><span class="sxs-lookup"><span data-stu-id="eada8-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="eada8-160">これが含まれています、`+`演算子、文字列の連結に使用される、`Length`プロパティ、および`Chars`プロパティで、文字列を Unicode 文字の配列として返します。</span><span class="sxs-lookup"><span data-stu-id="eada8-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="eada8-161">文字列の詳細については、次を参照してください。`System.String`します。</span><span class="sxs-lookup"><span data-stu-id="eada8-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="eada8-162">使用して、`Chars`プロパティの`System.String`文字列の個々 の文字の次のコードに示すように、インデックスを指定することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eada8-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="eada8-163">文字列のモジュール</span><span class="sxs-lookup"><span data-stu-id="eada8-163">String Module</span></span>

<span data-ttu-id="eada8-164">含まれている文字列の処理の追加機能、`String`でモジュール、`FSharp.Core`名前空間。</span><span class="sxs-lookup"><span data-stu-id="eada8-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="eada8-165">詳細については、次を参照してください。 [Core.String モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="eada8-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="eada8-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="eada8-166">See also</span></span>

- [<span data-ttu-id="eada8-167">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="eada8-167">F# Language Reference</span></span>](index.md)
