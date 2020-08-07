---
title: リテラル
description: 'F # プログラミング言語のリテラル型について説明します。'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855024"
---
# <a name="literals"></a><span data-ttu-id="da0f6-103">リテラル</span><span class="sxs-lookup"><span data-stu-id="da0f6-103">Literals</span></span>

<span data-ttu-id="da0f6-104">この記事では、F # でリテラルの型を指定する方法を示す表を示します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

> [!NOTE]
> <span data-ttu-id="da0f6-105">F # の docs.microsoft.com API リファレンスが完全ではありません。</span><span class="sxs-lookup"><span data-stu-id="da0f6-105">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="da0f6-106">壊れたリンクが見つかった場合は、代わりに[F # コアライブラリのドキュメント](https://fsharp.github.io/fsharp-core-docs/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da0f6-106">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="literal-types"></a><span data-ttu-id="da0f6-107">リテラル型</span><span class="sxs-lookup"><span data-stu-id="da0f6-107">Literal types</span></span>

<span data-ttu-id="da0f6-108">F# のリテラル型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="da0f6-109">16 進表記で桁を表す文字は、大文字と小文字を区別しません。型を識別する文字は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="da0f6-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="da0f6-110">Type</span><span class="sxs-lookup"><span data-stu-id="da0f6-110">Type</span></span>|<span data-ttu-id="da0f6-111">説明</span><span class="sxs-lookup"><span data-stu-id="da0f6-111">Description</span></span>|<span data-ttu-id="da0f6-112">サフィックスまたはプリフィックス</span><span class="sxs-lookup"><span data-stu-id="da0f6-112">Suffix or prefix</span></span>|<span data-ttu-id="da0f6-113">例</span><span class="sxs-lookup"><span data-stu-id="da0f6-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="da0f6-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="da0f6-114">sbyte</span></span>|<span data-ttu-id="da0f6-115">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="da0f6-115">signed 8-bit integer</span></span>|<span data-ttu-id="da0f6-116">Y</span><span class="sxs-lookup"><span data-stu-id="da0f6-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="da0f6-117">byte</span><span class="sxs-lookup"><span data-stu-id="da0f6-117">byte</span></span>|<span data-ttu-id="da0f6-118">符号なし 8 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="da0f6-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="da0f6-119">uy</span><span class="sxs-lookup"><span data-stu-id="da0f6-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="da0f6-120">int16</span><span class="sxs-lookup"><span data-stu-id="da0f6-120">int16</span></span>|<span data-ttu-id="da0f6-121">符号付き16ビット整数</span><span class="sxs-lookup"><span data-stu-id="da0f6-121">signed 16-bit integer</span></span>|<span data-ttu-id="da0f6-122">s</span><span class="sxs-lookup"><span data-stu-id="da0f6-122">s</span></span>|`86s`|
|<span data-ttu-id="da0f6-123">uint16</span><span class="sxs-lookup"><span data-stu-id="da0f6-123">uint16</span></span>|<span data-ttu-id="da0f6-124">符号なし16ビット自然数</span><span class="sxs-lookup"><span data-stu-id="da0f6-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="da0f6-125">us</span><span class="sxs-lookup"><span data-stu-id="da0f6-125">us</span></span>|`86us`|
|<span data-ttu-id="da0f6-126">INT</span><span class="sxs-lookup"><span data-stu-id="da0f6-126">int</span></span><br /><br /><span data-ttu-id="da0f6-127">int32</span><span class="sxs-lookup"><span data-stu-id="da0f6-127">int32</span></span>|<span data-ttu-id="da0f6-128">符号付き32ビット整数</span><span class="sxs-lookup"><span data-stu-id="da0f6-128">signed 32-bit integer</span></span>|<span data-ttu-id="da0f6-129">l または none</span><span class="sxs-lookup"><span data-stu-id="da0f6-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="da0f6-130">uint</span><span class="sxs-lookup"><span data-stu-id="da0f6-130">uint</span></span><br /><br /><span data-ttu-id="da0f6-131">uint32</span><span class="sxs-lookup"><span data-stu-id="da0f6-131">uint32</span></span>|<span data-ttu-id="da0f6-132">符号なし32ビット自然数</span><span class="sxs-lookup"><span data-stu-id="da0f6-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="da0f6-133">u または ul</span><span class="sxs-lookup"><span data-stu-id="da0f6-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="da0f6-134">nativeint</span><span class="sxs-lookup"><span data-stu-id="da0f6-134">nativeint</span></span>|<span data-ttu-id="da0f6-135">符号付き自然数へのネイティブポインター</span><span class="sxs-lookup"><span data-stu-id="da0f6-135">native pointer to a signed natural number</span></span>|<span data-ttu-id="da0f6-136">n</span><span class="sxs-lookup"><span data-stu-id="da0f6-136">n</span></span>|`123n`|
|<span data-ttu-id="da0f6-137">unativeint</span><span class="sxs-lookup"><span data-stu-id="da0f6-137">unativeint</span></span>|<span data-ttu-id="da0f6-138">符号なし自然数としてのネイティブ ポインター</span><span class="sxs-lookup"><span data-stu-id="da0f6-138">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="da0f6-139">un</span><span class="sxs-lookup"><span data-stu-id="da0f6-139">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="da0f6-140">int64</span><span class="sxs-lookup"><span data-stu-id="da0f6-140">int64</span></span>|<span data-ttu-id="da0f6-141">符号付き64ビット整数</span><span class="sxs-lookup"><span data-stu-id="da0f6-141">signed 64-bit integer</span></span>|<span data-ttu-id="da0f6-142">L</span><span class="sxs-lookup"><span data-stu-id="da0f6-142">L</span></span>|`86L`|
|<span data-ttu-id="da0f6-143">uint64</span><span class="sxs-lookup"><span data-stu-id="da0f6-143">uint64</span></span>|<span data-ttu-id="da0f6-144">符号なし64ビット自然数</span><span class="sxs-lookup"><span data-stu-id="da0f6-144">unsigned 64-bit natural number</span></span>|<span data-ttu-id="da0f6-145">UL</span><span class="sxs-lookup"><span data-stu-id="da0f6-145">UL</span></span>|`86UL`|
|<span data-ttu-id="da0f6-146">single、float32</span><span class="sxs-lookup"><span data-stu-id="da0f6-146">single, float32</span></span>|<span data-ttu-id="da0f6-147">32 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="da0f6-147">32-bit floating point number</span></span>|<span data-ttu-id="da0f6-148">F または f</span><span class="sxs-lookup"><span data-stu-id="da0f6-148">F or f</span></span>|<span data-ttu-id="da0f6-149">`4.14F` または `4.14f`</span><span class="sxs-lookup"><span data-stu-id="da0f6-149">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="da0f6-150">lf</span><span class="sxs-lookup"><span data-stu-id="da0f6-150">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="da0f6-151">float、double</span><span class="sxs-lookup"><span data-stu-id="da0f6-151">float; double</span></span>|<span data-ttu-id="da0f6-152">64ビットの浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="da0f6-152">64-bit floating point number</span></span>|<span data-ttu-id="da0f6-153">なし</span><span class="sxs-lookup"><span data-stu-id="da0f6-153">none</span></span>|<span data-ttu-id="da0f6-154">`4.14` または `2.3E+32` または `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="da0f6-154">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="da0f6-155">LF</span><span class="sxs-lookup"><span data-stu-id="da0f6-155">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="da0f6-156">bigint</span><span class="sxs-lookup"><span data-stu-id="da0f6-156">bigint</span></span>|<span data-ttu-id="da0f6-157">64 ビット表現に制限されない整数</span><span class="sxs-lookup"><span data-stu-id="da0f6-157">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="da0f6-158">I</span><span class="sxs-lookup"><span data-stu-id="da0f6-158">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="da0f6-159">decimal</span><span class="sxs-lookup"><span data-stu-id="da0f6-159">decimal</span></span>|<span data-ttu-id="da0f6-160">固定小数点数または有理数として表現される小数</span><span class="sxs-lookup"><span data-stu-id="da0f6-160">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="da0f6-161">M または m</span><span class="sxs-lookup"><span data-stu-id="da0f6-161">M or m</span></span>|<span data-ttu-id="da0f6-162">`0.7833M` または `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="da0f6-162">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="da0f6-163">Char</span><span class="sxs-lookup"><span data-stu-id="da0f6-163">Char</span></span>|<span data-ttu-id="da0f6-164">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="da0f6-164">Unicode character</span></span>|<span data-ttu-id="da0f6-165">なし</span><span class="sxs-lookup"><span data-stu-id="da0f6-165">none</span></span>|<span data-ttu-id="da0f6-166">`'a'` または `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="da0f6-166">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="da0f6-167">String</span><span class="sxs-lookup"><span data-stu-id="da0f6-167">String</span></span>|<span data-ttu-id="da0f6-168">Unicode 文字列</span><span class="sxs-lookup"><span data-stu-id="da0f6-168">Unicode string</span></span>|<span data-ttu-id="da0f6-169">なし</span><span class="sxs-lookup"><span data-stu-id="da0f6-169">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="da0f6-170">or</span><span class="sxs-lookup"><span data-stu-id="da0f6-170">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="da0f6-171">or</span><span class="sxs-lookup"><span data-stu-id="da0f6-171">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="da0f6-172">or</span><span class="sxs-lookup"><span data-stu-id="da0f6-172">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="da0f6-173">「[文字列](Strings.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="da0f6-173">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="da0f6-174">byte</span><span class="sxs-lookup"><span data-stu-id="da0f6-174">byte</span></span>|<span data-ttu-id="da0f6-175">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="da0f6-175">ASCII character</span></span>|<span data-ttu-id="da0f6-176">B</span><span class="sxs-lookup"><span data-stu-id="da0f6-176">B</span></span>|`'a'B`|
|<span data-ttu-id="da0f6-177">byte[]</span><span class="sxs-lookup"><span data-stu-id="da0f6-177">byte[]</span></span>|<span data-ttu-id="da0f6-178">ASCII 文字列</span><span class="sxs-lookup"><span data-stu-id="da0f6-178">ASCII string</span></span>|<span data-ttu-id="da0f6-179">B</span><span class="sxs-lookup"><span data-stu-id="da0f6-179">B</span></span>|`"text"B`|
|<span data-ttu-id="da0f6-180">String または byte[]</span><span class="sxs-lookup"><span data-stu-id="da0f6-180">String or byte[]</span></span>|<span data-ttu-id="da0f6-181">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="da0f6-181">verbatim string</span></span>|<span data-ttu-id="da0f6-182">@ プリフィックス</span><span class="sxs-lookup"><span data-stu-id="da0f6-182">@ prefix</span></span>|<span data-ttu-id="da0f6-183">`@"\\server\share"`対応</span><span class="sxs-lookup"><span data-stu-id="da0f6-183">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="da0f6-184">`@"\\server\share"B`ASCII</span><span class="sxs-lookup"><span data-stu-id="da0f6-184">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="da0f6-185">名前付きリテラル</span><span class="sxs-lookup"><span data-stu-id="da0f6-185">Named literals</span></span>

<span data-ttu-id="da0f6-186">定数として使用する値は、[リテラル](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性でマークできます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-186">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="da0f6-187">この属性には、値が定数としてコンパイルされる効果があります。</span><span class="sxs-lookup"><span data-stu-id="da0f6-187">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="da0f6-188">パターン マッチ式では、小文字で始まる識別子は、リテラルとしてではなく常にバインドされる変数として扱われます。そのため、一般的に、リテラルを定義する場合は先頭大文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da0f6-188">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="da0f6-189">Remarks</span><span class="sxs-lookup"><span data-stu-id="da0f6-189">Remarks</span></span>

<span data-ttu-id="da0f6-190">Unicode 文字列には、を使用して指定できる明示的なエンコーディングを含めることができます。それに32は、の後に `\u` 16 ビットの16進コード (0000-FFFF)、またはを使用して指定することができ、その `\U` 後に unicode コードポイント (00000000-0010FFFF) を表す32ビットの16進コードを指定できます</span><span class="sxs-lookup"><span data-stu-id="da0f6-190">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="da0f6-191">以外のビットごとの演算子の使用は許可されていません `|||` 。</span><span class="sxs-lookup"><span data-stu-id="da0f6-191">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="da0f6-192">その他のベースの整数</span><span class="sxs-lookup"><span data-stu-id="da0f6-192">Integers in other bases</span></span>

<span data-ttu-id="da0f6-193">符号付き32ビット整数は `0x` 、、、またはプレフィックスを使用して、16進数、8進数、またはバイナリで指定することもでき `0o` `0b` ます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-193">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="da0f6-194">数値リテラルのアンダースコア</span><span class="sxs-lookup"><span data-stu-id="da0f6-194">Underscores in numeric literals</span></span>

<span data-ttu-id="da0f6-195">数字はアンダースコア文字 () で区切ることができ `_` ます。</span><span class="sxs-lookup"><span data-stu-id="da0f6-195">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="da0f6-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="da0f6-196">See also</span></span>

- [<span data-ttu-id="da0f6-197">LiteralAttribute クラス</span><span class="sxs-lookup"><span data-stu-id="da0f6-197">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
