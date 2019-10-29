---
title: リテラル
description: F#プログラミング言語のリテラル型について説明します。
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041038"
---
# <a name="literals"></a><span data-ttu-id="1a883-103">リテラル</span><span class="sxs-lookup"><span data-stu-id="1a883-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="1a883-104">この記事の API リファレンスリンクを使用すると、MSDN (現時点では) に移動します。</span><span class="sxs-lookup"><span data-stu-id="1a883-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="1a883-105">このトピックでは、F# でリテラルの型を指定する方法を示す表を示します。</span><span class="sxs-lookup"><span data-stu-id="1a883-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="1a883-106">リテラル型</span><span class="sxs-lookup"><span data-stu-id="1a883-106">Literal Types</span></span>

<span data-ttu-id="1a883-107">F# のリテラル型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1a883-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="1a883-108">16 進表記で桁を表す文字は、大文字と小文字を区別しません。型を識別する文字は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="1a883-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="1a883-109">[種類]</span><span class="sxs-lookup"><span data-stu-id="1a883-109">Type</span></span>|<span data-ttu-id="1a883-110">説明</span><span class="sxs-lookup"><span data-stu-id="1a883-110">Description</span></span>|<span data-ttu-id="1a883-111">サフィックスまたはプリフィックス</span><span class="sxs-lookup"><span data-stu-id="1a883-111">Suffix or prefix</span></span>|<span data-ttu-id="1a883-112">使用例</span><span class="sxs-lookup"><span data-stu-id="1a883-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="1a883-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="1a883-113">sbyte</span></span>|<span data-ttu-id="1a883-114">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="1a883-114">signed 8-bit integer</span></span>|<span data-ttu-id="1a883-115">Y</span><span class="sxs-lookup"><span data-stu-id="1a883-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="1a883-116">byte</span><span class="sxs-lookup"><span data-stu-id="1a883-116">byte</span></span>|<span data-ttu-id="1a883-117">符号なし 8 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="1a883-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="1a883-118">uy</span><span class="sxs-lookup"><span data-stu-id="1a883-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="1a883-119">int16</span><span class="sxs-lookup"><span data-stu-id="1a883-119">int16</span></span>|<span data-ttu-id="1a883-120">符号付き16ビット整数</span><span class="sxs-lookup"><span data-stu-id="1a883-120">signed 16-bit integer</span></span>|<span data-ttu-id="1a883-121">s</span><span class="sxs-lookup"><span data-stu-id="1a883-121">s</span></span>|`86s`|
|<span data-ttu-id="1a883-122">uint16</span><span class="sxs-lookup"><span data-stu-id="1a883-122">uint16</span></span>|<span data-ttu-id="1a883-123">符号なし16ビット自然数</span><span class="sxs-lookup"><span data-stu-id="1a883-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="1a883-124">us</span><span class="sxs-lookup"><span data-stu-id="1a883-124">us</span></span>|`86us`|
|<span data-ttu-id="1a883-125">int</span><span class="sxs-lookup"><span data-stu-id="1a883-125">int</span></span><br /><br /><span data-ttu-id="1a883-126">int32</span><span class="sxs-lookup"><span data-stu-id="1a883-126">int32</span></span>|<span data-ttu-id="1a883-127">符号付き32ビット整数</span><span class="sxs-lookup"><span data-stu-id="1a883-127">signed 32-bit integer</span></span>|<span data-ttu-id="1a883-128">l または none</span><span class="sxs-lookup"><span data-stu-id="1a883-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="1a883-129">uint</span><span class="sxs-lookup"><span data-stu-id="1a883-129">uint</span></span><br /><br /><span data-ttu-id="1a883-130">uint32</span><span class="sxs-lookup"><span data-stu-id="1a883-130">uint32</span></span>|<span data-ttu-id="1a883-131">符号なし32ビット自然数</span><span class="sxs-lookup"><span data-stu-id="1a883-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="1a883-132">u または ul</span><span class="sxs-lookup"><span data-stu-id="1a883-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="1a883-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="1a883-133">nativeint</span></span>|<span data-ttu-id="1a883-134">符号付き自然数へのネイティブポインター</span><span class="sxs-lookup"><span data-stu-id="1a883-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="1a883-135">n</span><span class="sxs-lookup"><span data-stu-id="1a883-135">n</span></span>|`123n`|
|<span data-ttu-id="1a883-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="1a883-136">unativeint</span></span>|<span data-ttu-id="1a883-137">符号なし自然数としてのネイティブ ポインター</span><span class="sxs-lookup"><span data-stu-id="1a883-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="1a883-138">un</span><span class="sxs-lookup"><span data-stu-id="1a883-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="1a883-139">int64</span><span class="sxs-lookup"><span data-stu-id="1a883-139">int64</span></span>|<span data-ttu-id="1a883-140">符号付き64ビット整数</span><span class="sxs-lookup"><span data-stu-id="1a883-140">signed 64-bit integer</span></span>|<span data-ttu-id="1a883-141">L</span><span class="sxs-lookup"><span data-stu-id="1a883-141">L</span></span>|`86L`|
|<span data-ttu-id="1a883-142">uint64</span><span class="sxs-lookup"><span data-stu-id="1a883-142">uint64</span></span>|<span data-ttu-id="1a883-143">符号なし64ビット自然数</span><span class="sxs-lookup"><span data-stu-id="1a883-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="1a883-144">UL</span><span class="sxs-lookup"><span data-stu-id="1a883-144">UL</span></span>|`86UL`|
|<span data-ttu-id="1a883-145">single、float32</span><span class="sxs-lookup"><span data-stu-id="1a883-145">single, float32</span></span>|<span data-ttu-id="1a883-146">32 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="1a883-146">32-bit floating point number</span></span>|<span data-ttu-id="1a883-147">F または f</span><span class="sxs-lookup"><span data-stu-id="1a883-147">F or f</span></span>|<span data-ttu-id="1a883-148">`4.14F` または `4.14f`</span><span class="sxs-lookup"><span data-stu-id="1a883-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="1a883-149">lf</span><span class="sxs-lookup"><span data-stu-id="1a883-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="1a883-150">float、double</span><span class="sxs-lookup"><span data-stu-id="1a883-150">float; double</span></span>|<span data-ttu-id="1a883-151">64ビットの浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="1a883-151">64-bit floating point number</span></span>|<span data-ttu-id="1a883-152">none</span><span class="sxs-lookup"><span data-stu-id="1a883-152">none</span></span>|<span data-ttu-id="1a883-153">`4.14` または `2.3E+32` または `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="1a883-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="1a883-154">LF</span><span class="sxs-lookup"><span data-stu-id="1a883-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="1a883-155">bigint</span><span class="sxs-lookup"><span data-stu-id="1a883-155">bigint</span></span>|<span data-ttu-id="1a883-156">64 ビット表現に制限されない整数</span><span class="sxs-lookup"><span data-stu-id="1a883-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="1a883-157">I</span><span class="sxs-lookup"><span data-stu-id="1a883-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="1a883-158">decimal</span><span class="sxs-lookup"><span data-stu-id="1a883-158">decimal</span></span>|<span data-ttu-id="1a883-159">固定小数点数または有理数として表現される小数</span><span class="sxs-lookup"><span data-stu-id="1a883-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="1a883-160">M または m</span><span class="sxs-lookup"><span data-stu-id="1a883-160">M or m</span></span>|<span data-ttu-id="1a883-161">`0.7833M` または `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="1a883-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="1a883-162">Char</span><span class="sxs-lookup"><span data-stu-id="1a883-162">Char</span></span>|<span data-ttu-id="1a883-163">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="1a883-163">Unicode character</span></span>|<span data-ttu-id="1a883-164">none</span><span class="sxs-lookup"><span data-stu-id="1a883-164">none</span></span>|<span data-ttu-id="1a883-165">`'a'` または `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="1a883-165">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="1a883-166">文字列型</span><span class="sxs-lookup"><span data-stu-id="1a883-166">String</span></span>|<span data-ttu-id="1a883-167">Unicode 文字列</span><span class="sxs-lookup"><span data-stu-id="1a883-167">Unicode string</span></span>|<span data-ttu-id="1a883-168">none</span><span class="sxs-lookup"><span data-stu-id="1a883-168">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="1a883-169">、または</span><span class="sxs-lookup"><span data-stu-id="1a883-169">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="1a883-170">、または</span><span class="sxs-lookup"><span data-stu-id="1a883-170">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="1a883-171">、または</span><span class="sxs-lookup"><span data-stu-id="1a883-171">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="1a883-172">「[文字列](Strings.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a883-172">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="1a883-173">byte</span><span class="sxs-lookup"><span data-stu-id="1a883-173">byte</span></span>|<span data-ttu-id="1a883-174">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="1a883-174">ASCII character</span></span>|<span data-ttu-id="1a883-175">B</span><span class="sxs-lookup"><span data-stu-id="1a883-175">B</span></span>|`'a'B`|
|<span data-ttu-id="1a883-176">byte[]</span><span class="sxs-lookup"><span data-stu-id="1a883-176">byte[]</span></span>|<span data-ttu-id="1a883-177">ASCII 文字列</span><span class="sxs-lookup"><span data-stu-id="1a883-177">ASCII string</span></span>|<span data-ttu-id="1a883-178">B</span><span class="sxs-lookup"><span data-stu-id="1a883-178">B</span></span>|`"text"B`|
|<span data-ttu-id="1a883-179">String または byte[]</span><span class="sxs-lookup"><span data-stu-id="1a883-179">String or byte[]</span></span>|<span data-ttu-id="1a883-180">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="1a883-180">verbatim string</span></span>|<span data-ttu-id="1a883-181">@ プリフィックス</span><span class="sxs-lookup"><span data-stu-id="1a883-181">@ prefix</span></span>|<span data-ttu-id="1a883-182">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="1a883-182">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="1a883-183">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="1a883-183">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="1a883-184">名前付きリテラル</span><span class="sxs-lookup"><span data-stu-id="1a883-184">Named literals</span></span>

<span data-ttu-id="1a883-185">定数として使用する値は、[リテラル](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性でマークできます。</span><span class="sxs-lookup"><span data-stu-id="1a883-185">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="1a883-186">この属性には、値が定数としてコンパイルされる効果があります。</span><span class="sxs-lookup"><span data-stu-id="1a883-186">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="1a883-187">パターン マッチ式では、小文字で始まる識別子は、リテラルとしてではなく常にバインドされる変数として扱われます。そのため、一般的に、リテラルを定義する場合は先頭大文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a883-187">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="1a883-188">Remarks</span><span class="sxs-lookup"><span data-stu-id="1a883-188">Remarks</span></span>

<span data-ttu-id="1a883-189">Unicode 文字列には、明示的なエンコーディングを含めることができます。これには、`\u` の後に16ビットの16進コード (0000-FFFF) を使用する32か、`\U` の後に Unicode を表す32ビットの16進コードを使用して指定することができます。コードポイント (00000000-0010FFFF)。</span><span class="sxs-lookup"><span data-stu-id="1a883-189">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="1a883-190">`|||` 以外の他のビットごとの演算子の使用は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="1a883-190">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="1a883-191">その他のベースの整数</span><span class="sxs-lookup"><span data-stu-id="1a883-191">Integers in other bases</span></span>

<span data-ttu-id="1a883-192">符号付き32ビット整数は、それぞれ `0x`、`0o`、または `0b` プレフィックスを使用して、16進数、8進数、またはバイナリで指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a883-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="1a883-193">数値リテラルのアンダースコア</span><span class="sxs-lookup"><span data-stu-id="1a883-193">Underscores in numeric literals</span></span>

<span data-ttu-id="1a883-194">数字はアンダースコア文字 (`_`) で区切ることができます。</span><span class="sxs-lookup"><span data-stu-id="1a883-194">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="1a883-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a883-195">See also</span></span>

- [<span data-ttu-id="1a883-196">LiteralAttribute クラス</span><span class="sxs-lookup"><span data-stu-id="1a883-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
