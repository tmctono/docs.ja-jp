---
title: リテラル
description: 'F # プログラミング言語のリテラル型について説明します。'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559155"
---
# <a name="literals"></a><span data-ttu-id="cc9a3-103">リテラル</span><span class="sxs-lookup"><span data-stu-id="cc9a3-103">Literals</span></span>

<span data-ttu-id="cc9a3-104">この記事では、F # でリテラルの型を指定する方法を示す表を示します。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="cc9a3-105">リテラル型</span><span class="sxs-lookup"><span data-stu-id="cc9a3-105">Literal types</span></span>

<span data-ttu-id="cc9a3-106">F# のリテラル型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-106">The following table shows the literal types in F#.</span></span> <span data-ttu-id="cc9a3-107">16 進表記で桁を表す文字は、大文字と小文字を区別しません。型を識別する文字は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-107">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="cc9a3-108">Type</span><span class="sxs-lookup"><span data-stu-id="cc9a3-108">Type</span></span>|<span data-ttu-id="cc9a3-109">説明</span><span class="sxs-lookup"><span data-stu-id="cc9a3-109">Description</span></span>|<span data-ttu-id="cc9a3-110">サフィックスまたはプリフィックス</span><span class="sxs-lookup"><span data-stu-id="cc9a3-110">Suffix or prefix</span></span>|<span data-ttu-id="cc9a3-111">例</span><span class="sxs-lookup"><span data-stu-id="cc9a3-111">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="cc9a3-112">sbyte</span><span class="sxs-lookup"><span data-stu-id="cc9a3-112">sbyte</span></span>|<span data-ttu-id="cc9a3-113">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-113">signed 8-bit integer</span></span>|<span data-ttu-id="cc9a3-114">Y</span><span class="sxs-lookup"><span data-stu-id="cc9a3-114">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="cc9a3-115">byte</span><span class="sxs-lookup"><span data-stu-id="cc9a3-115">byte</span></span>|<span data-ttu-id="cc9a3-116">符号なし 8 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-116">unsigned 8-bit natural number</span></span>|<span data-ttu-id="cc9a3-117">uy</span><span class="sxs-lookup"><span data-stu-id="cc9a3-117">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="cc9a3-118">int16</span><span class="sxs-lookup"><span data-stu-id="cc9a3-118">int16</span></span>|<span data-ttu-id="cc9a3-119">符号付き16ビット整数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-119">signed 16-bit integer</span></span>|<span data-ttu-id="cc9a3-120">s</span><span class="sxs-lookup"><span data-stu-id="cc9a3-120">s</span></span>|`86s`|
|<span data-ttu-id="cc9a3-121">uint16</span><span class="sxs-lookup"><span data-stu-id="cc9a3-121">uint16</span></span>|<span data-ttu-id="cc9a3-122">符号なし16ビット自然数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-122">unsigned 16-bit natural number</span></span>|<span data-ttu-id="cc9a3-123">us</span><span class="sxs-lookup"><span data-stu-id="cc9a3-123">us</span></span>|`86us`|
|<span data-ttu-id="cc9a3-124">INT</span><span class="sxs-lookup"><span data-stu-id="cc9a3-124">int</span></span><br /><br /><span data-ttu-id="cc9a3-125">int32</span><span class="sxs-lookup"><span data-stu-id="cc9a3-125">int32</span></span>|<span data-ttu-id="cc9a3-126">符号付き32ビット整数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-126">signed 32-bit integer</span></span>|<span data-ttu-id="cc9a3-127">l または none</span><span class="sxs-lookup"><span data-stu-id="cc9a3-127">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="cc9a3-128">uint</span><span class="sxs-lookup"><span data-stu-id="cc9a3-128">uint</span></span><br /><br /><span data-ttu-id="cc9a3-129">uint32</span><span class="sxs-lookup"><span data-stu-id="cc9a3-129">uint32</span></span>|<span data-ttu-id="cc9a3-130">符号なし32ビット自然数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-130">unsigned 32-bit natural number</span></span>|<span data-ttu-id="cc9a3-131">u または ul</span><span class="sxs-lookup"><span data-stu-id="cc9a3-131">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="cc9a3-132">nativeint</span><span class="sxs-lookup"><span data-stu-id="cc9a3-132">nativeint</span></span>|<span data-ttu-id="cc9a3-133">符号付き自然数へのネイティブポインター</span><span class="sxs-lookup"><span data-stu-id="cc9a3-133">native pointer to a signed natural number</span></span>|<span data-ttu-id="cc9a3-134">n</span><span class="sxs-lookup"><span data-stu-id="cc9a3-134">n</span></span>|`123n`|
|<span data-ttu-id="cc9a3-135">unativeint</span><span class="sxs-lookup"><span data-stu-id="cc9a3-135">unativeint</span></span>|<span data-ttu-id="cc9a3-136">符号なし自然数としてのネイティブ ポインター</span><span class="sxs-lookup"><span data-stu-id="cc9a3-136">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="cc9a3-137">un</span><span class="sxs-lookup"><span data-stu-id="cc9a3-137">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="cc9a3-138">int64</span><span class="sxs-lookup"><span data-stu-id="cc9a3-138">int64</span></span>|<span data-ttu-id="cc9a3-139">符号付き64ビット整数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-139">signed 64-bit integer</span></span>|<span data-ttu-id="cc9a3-140">L</span><span class="sxs-lookup"><span data-stu-id="cc9a3-140">L</span></span>|`86L`|
|<span data-ttu-id="cc9a3-141">uint64</span><span class="sxs-lookup"><span data-stu-id="cc9a3-141">uint64</span></span>|<span data-ttu-id="cc9a3-142">符号なし64ビット自然数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-142">unsigned 64-bit natural number</span></span>|<span data-ttu-id="cc9a3-143">UL</span><span class="sxs-lookup"><span data-stu-id="cc9a3-143">UL</span></span>|`86UL`|
|<span data-ttu-id="cc9a3-144">single、float32</span><span class="sxs-lookup"><span data-stu-id="cc9a3-144">single, float32</span></span>|<span data-ttu-id="cc9a3-145">32 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-145">32-bit floating point number</span></span>|<span data-ttu-id="cc9a3-146">F または f</span><span class="sxs-lookup"><span data-stu-id="cc9a3-146">F or f</span></span>|<span data-ttu-id="cc9a3-147">`4.14F` または `4.14f`</span><span class="sxs-lookup"><span data-stu-id="cc9a3-147">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="cc9a3-148">lf</span><span class="sxs-lookup"><span data-stu-id="cc9a3-148">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="cc9a3-149">float、double</span><span class="sxs-lookup"><span data-stu-id="cc9a3-149">float; double</span></span>|<span data-ttu-id="cc9a3-150">64ビットの浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-150">64-bit floating point number</span></span>|<span data-ttu-id="cc9a3-151">なし</span><span class="sxs-lookup"><span data-stu-id="cc9a3-151">none</span></span>|<span data-ttu-id="cc9a3-152">`4.14` または `2.3E+32` または `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="cc9a3-152">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="cc9a3-153">LF</span><span class="sxs-lookup"><span data-stu-id="cc9a3-153">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="cc9a3-154">bigint</span><span class="sxs-lookup"><span data-stu-id="cc9a3-154">bigint</span></span>|<span data-ttu-id="cc9a3-155">64 ビット表現に制限されない整数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-155">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="cc9a3-156">I</span><span class="sxs-lookup"><span data-stu-id="cc9a3-156">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="cc9a3-157">decimal</span><span class="sxs-lookup"><span data-stu-id="cc9a3-157">decimal</span></span>|<span data-ttu-id="cc9a3-158">固定小数点数または有理数として表現される小数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-158">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="cc9a3-159">M または m</span><span class="sxs-lookup"><span data-stu-id="cc9a3-159">M or m</span></span>|<span data-ttu-id="cc9a3-160">`0.7833M` または `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="cc9a3-160">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="cc9a3-161">Char</span><span class="sxs-lookup"><span data-stu-id="cc9a3-161">Char</span></span>|<span data-ttu-id="cc9a3-162">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="cc9a3-162">Unicode character</span></span>|<span data-ttu-id="cc9a3-163">なし</span><span class="sxs-lookup"><span data-stu-id="cc9a3-163">none</span></span>|<span data-ttu-id="cc9a3-164">`'a'` または `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="cc9a3-164">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="cc9a3-165">String</span><span class="sxs-lookup"><span data-stu-id="cc9a3-165">String</span></span>|<span data-ttu-id="cc9a3-166">Unicode 文字列</span><span class="sxs-lookup"><span data-stu-id="cc9a3-166">Unicode string</span></span>|<span data-ttu-id="cc9a3-167">なし</span><span class="sxs-lookup"><span data-stu-id="cc9a3-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="cc9a3-168">or</span><span class="sxs-lookup"><span data-stu-id="cc9a3-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="cc9a3-169">or</span><span class="sxs-lookup"><span data-stu-id="cc9a3-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="cc9a3-170">or</span><span class="sxs-lookup"><span data-stu-id="cc9a3-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="cc9a3-171">「 [文字列](Strings.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="cc9a3-172">byte</span><span class="sxs-lookup"><span data-stu-id="cc9a3-172">byte</span></span>|<span data-ttu-id="cc9a3-173">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="cc9a3-173">ASCII character</span></span>|<span data-ttu-id="cc9a3-174">B</span><span class="sxs-lookup"><span data-stu-id="cc9a3-174">B</span></span>|`'a'B`|
|<span data-ttu-id="cc9a3-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="cc9a3-175">byte[]</span></span>|<span data-ttu-id="cc9a3-176">ASCII 文字列</span><span class="sxs-lookup"><span data-stu-id="cc9a3-176">ASCII string</span></span>|<span data-ttu-id="cc9a3-177">B</span><span class="sxs-lookup"><span data-stu-id="cc9a3-177">B</span></span>|`"text"B`|
|<span data-ttu-id="cc9a3-178">String または byte[]</span><span class="sxs-lookup"><span data-stu-id="cc9a3-178">String or byte[]</span></span>|<span data-ttu-id="cc9a3-179">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="cc9a3-179">verbatim string</span></span>|<span data-ttu-id="cc9a3-180">@ プリフィックス</span><span class="sxs-lookup"><span data-stu-id="cc9a3-180">@ prefix</span></span>|<span data-ttu-id="cc9a3-181">`@"\\server\share"` 対応</span><span class="sxs-lookup"><span data-stu-id="cc9a3-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="cc9a3-182">`@"\\server\share"B` ASCII</span><span class="sxs-lookup"><span data-stu-id="cc9a3-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="cc9a3-183">名前付きリテラル</span><span class="sxs-lookup"><span data-stu-id="cc9a3-183">Named literals</span></span>

<span data-ttu-id="cc9a3-184">定数として使用する値は、 [リテラル](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) 属性でマークできます。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-184">Values that are intended to be constants can be marked with the [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) attribute.</span></span> <span data-ttu-id="cc9a3-185">この属性には、値が定数としてコンパイルされる効果があります。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="cc9a3-186">パターン マッチ式では、小文字で始まる識別子は、リテラルとしてではなく常にバインドされる変数として扱われます。そのため、一般的に、リテラルを定義する場合は先頭大文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="cc9a3-187">注釈</span><span class="sxs-lookup"><span data-stu-id="cc9a3-187">Remarks</span></span>

<span data-ttu-id="cc9a3-188">Unicode 文字列には、を使用して指定できる明示的なエンコーディングを含めることができます。それに32は、の後に `\u` 16 ビットの16進コード (0000-FFFF)、またはを使用して指定することができ、その `\U` 後に unicode コードポイント (00000000-0010FFFF) を表す32ビットの16進コードを指定できます</span><span class="sxs-lookup"><span data-stu-id="cc9a3-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="cc9a3-189">以外のビットごとの演算子の使用は許可されていません `|||` 。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="cc9a3-190">その他のベースの整数</span><span class="sxs-lookup"><span data-stu-id="cc9a3-190">Integers in other bases</span></span>

<span data-ttu-id="cc9a3-191">符号付き32ビット整数は `0x` 、、、またはプレフィックスを使用して、16進数、8進数、またはバイナリで指定することもでき `0o` `0b` ます。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="cc9a3-192">数値リテラルのアンダースコア</span><span class="sxs-lookup"><span data-stu-id="cc9a3-192">Underscores in numeric literals</span></span>

<span data-ttu-id="cc9a3-193">数字はアンダースコア文字 () で区切ることができ `_` ます。</span><span class="sxs-lookup"><span data-stu-id="cc9a3-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
