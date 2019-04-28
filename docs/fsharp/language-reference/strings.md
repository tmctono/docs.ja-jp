---
title: 文字列
description: について説明しますが、どのようにF#'string' 型では、変更不可のテキストを表す Unicode 文字のシーケンスとして。
ms.date: 05/16/2016
ms.openlocfilehash: 5b55b0c87b6636346677b973e093e7bcba324e98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755351"
---
# <a name="strings"></a><span data-ttu-id="0efbe-103">文字列</span><span class="sxs-lookup"><span data-stu-id="0efbe-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="0efbe-104">この記事の API リファレンスのリンクをクリックすると MSDN に移動します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="0efbe-105">docs.microsoft.com API リファレンスは完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="0efbe-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="0efbe-106">`string`型が Unicode 文字のシーケンスとして変更不可のテキストを表します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="0efbe-107">`string` は、.NET Framework の `System.String` のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="0efbe-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="0efbe-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0efbe-108">Remarks</span></span>

<span data-ttu-id="0efbe-109">文字列リテラルは引用符 (") 文字で区切られます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="0efbe-110">円記号 ( \\ ) 特定の特殊文字をエンコードするために使用します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="0efbe-111">円記号と、次の文字の組み合わせと呼ばれる、*エスケープ シーケンス*します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="0efbe-112">エスケープ シーケンスが F# 文字列リテラルは、次の表に示すでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0efbe-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="0efbe-113">文字</span><span class="sxs-lookup"><span data-stu-id="0efbe-113">Character</span></span>|<span data-ttu-id="0efbe-114">エスケープ シーケンス</span><span class="sxs-lookup"><span data-stu-id="0efbe-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="0efbe-115">バックスペース</span><span class="sxs-lookup"><span data-stu-id="0efbe-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="0efbe-116">改行</span><span class="sxs-lookup"><span data-stu-id="0efbe-116">Newline</span></span>|`\n`|
|<span data-ttu-id="0efbe-117">キャリッジ リターン</span><span class="sxs-lookup"><span data-stu-id="0efbe-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="0efbe-118">タブ</span><span class="sxs-lookup"><span data-stu-id="0efbe-118">Tab</span></span>|`\t`|
|<span data-ttu-id="0efbe-119">円記号</span><span class="sxs-lookup"><span data-stu-id="0efbe-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="0efbe-120">引用符</span><span class="sxs-lookup"><span data-stu-id="0efbe-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="0efbe-121">アポストロフィ</span><span class="sxs-lookup"><span data-stu-id="0efbe-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="0efbe-122">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="0efbe-122">Unicode character</span></span>|<span data-ttu-id="0efbe-123">`\uXXXX` または`\UXXXX`(場所`X`16 進数の数字を示します)</span><span class="sxs-lookup"><span data-stu-id="0efbe-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="0efbe-124">前にある場合、@ 記号、リテラルには、逐語的文字列。</span><span class="sxs-lookup"><span data-stu-id="0efbe-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="0efbe-125">つまり、2 つの引用符文字が 1 つの引用符文字として解釈される点が異なりますエスケープ シーケンスが無視します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="0efbe-126">さらに、文字列の場合は、三重引用符で囲まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0efbe-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="0efbe-127">この場合、すべてのエスケープ シーケンスは無視されます、二重引用符文字も含まれます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="0efbe-128">埋め込まれた文字列を引用符で囲まれたを含む文字列を指定するには、逐語的文字列または三重引用符で囲まれた文字列か、使用できます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="0efbe-129">逐語的文字列を使用する場合は、一重引用符文字を示す 2 つの引用符文字を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0efbe-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="0efbe-130">三重引用符で囲まれた文字列を使用する場合は、文字列の末尾として解析することがなく、単一引用符文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="0efbe-131">この方法は、XML または埋め込まれた引用符を含むその他の構造を操作する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="0efbe-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="0efbe-132">コードでは、文字列は、改行が受け入れられ、改行以外として解釈されますとして改行、円記号が改行の前に最後の文字。</span><span class="sxs-lookup"><span data-stu-id="0efbe-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="0efbe-133">次の行の先頭の空白文字には、円記号を使用する場合は無視されます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="0efbe-134">次のコードには、文字列が生成されます。`str1`値を持つ`"abc\ndef"`と文字列`str2`値を持つ`"abcdef"`します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="0efbe-135">文字列の個々 の文字は、次のように配列に似た構文を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="0efbe-136">出力は `b`になります。</span><span class="sxs-lookup"><span data-stu-id="0efbe-136">The output is `b`.</span></span>

<span data-ttu-id="0efbe-137">または、次のコードに示すように、配列スライス構文を使用して部分文字列を抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="0efbe-138">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0efbe-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="0efbe-139">ASCII 文字列型の符号なしバイトの配列で表現できます`byte[]`します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="0efbe-140">サフィックスを追加する`B`を ASCII 文字列であることを示すリテラル文字列にします。</span><span class="sxs-lookup"><span data-stu-id="0efbe-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="0efbe-141">ASCII 文字列リテラルのバイト配列を使用では、Unicode のエスケープ シーケンスを除く、Unicode 文字列として同じエスケープ シーケンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0efbe-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="0efbe-142">文字列演算子</span><span class="sxs-lookup"><span data-stu-id="0efbe-142">String Operators</span></span>

<span data-ttu-id="0efbe-143">文字列を連結する 2 つの方法があります: を使用して、`+`演算子またはを使用して、`^`演算子。</span><span class="sxs-lookup"><span data-stu-id="0efbe-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="0efbe-144">`+`演算子が、.NET Framework の文字列処理機能との互換性を維持します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="0efbe-145">次の例は、文字列の連結を示しています。</span><span class="sxs-lookup"><span data-stu-id="0efbe-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="0efbe-146">String クラス</span><span class="sxs-lookup"><span data-stu-id="0efbe-146">String Class</span></span>

<span data-ttu-id="0efbe-147">文字列を入力するためF#.NET Framework では実際には、`System.String`すべての入力、`System.String`メンバーが使用可能です。</span><span class="sxs-lookup"><span data-stu-id="0efbe-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="0efbe-148">これが含まれています、`+`演算子、文字列の連結に使用される、`Length`プロパティ、および`Chars`プロパティで、文字列を Unicode 文字の配列として返します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="0efbe-149">文字列の詳細については、次を参照してください。`System.String`します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="0efbe-150">使用して、`Chars`プロパティの`System.String`文字列の個々 の文字の次のコードに示すように、インデックスを指定することでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0efbe-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="0efbe-151">文字列のモジュール</span><span class="sxs-lookup"><span data-stu-id="0efbe-151">String Module</span></span>

<span data-ttu-id="0efbe-152">含まれている文字列の処理の追加機能、`String`でモジュール、`FSharp.Core`名前空間。</span><span class="sxs-lookup"><span data-stu-id="0efbe-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="0efbe-153">詳細については、次を参照してください。 [Core.String モジュール](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)します。</span><span class="sxs-lookup"><span data-stu-id="0efbe-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="0efbe-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="0efbe-154">See also</span></span>

- [<span data-ttu-id="0efbe-155">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="0efbe-155">F# Language Reference</span></span>](index.md)