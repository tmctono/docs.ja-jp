---
title: リテラル
description: リテラルの型について説明します、F#プログラミング言語。
ms.date: 06/08/2019
ms.openlocfilehash: 93329cd868ff7a2daaffa1b87ba838bbbc98015c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816233"
---
# <a name="literals"></a><span data-ttu-id="89f27-103">リテラル</span><span class="sxs-lookup"><span data-stu-id="89f27-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="89f27-104">この記事の API 参照リンクに出ます msdn (現在のところ)。</span><span class="sxs-lookup"><span data-stu-id="89f27-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="89f27-105">このトピックでは、F# でリテラルの型を指定する方法を示す表を示します。</span><span class="sxs-lookup"><span data-stu-id="89f27-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="89f27-106">リテラル型</span><span class="sxs-lookup"><span data-stu-id="89f27-106">Literal Types</span></span>

<span data-ttu-id="89f27-107">F# のリテラル型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="89f27-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="89f27-108">16 進表記で桁を表す文字は、大文字と小文字を区別しません。型を識別する文字は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="89f27-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="89f27-109">型</span><span class="sxs-lookup"><span data-stu-id="89f27-109">Type</span></span>|<span data-ttu-id="89f27-110">説明</span><span class="sxs-lookup"><span data-stu-id="89f27-110">Description</span></span>|<span data-ttu-id="89f27-111">サフィックスまたはプリフィックス</span><span class="sxs-lookup"><span data-stu-id="89f27-111">Suffix or prefix</span></span>|<span data-ttu-id="89f27-112">使用例</span><span class="sxs-lookup"><span data-stu-id="89f27-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="89f27-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="89f27-113">sbyte</span></span>|<span data-ttu-id="89f27-114">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="89f27-114">signed 8-bit integer</span></span>|<span data-ttu-id="89f27-115">Y</span><span class="sxs-lookup"><span data-stu-id="89f27-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="89f27-116">byte</span><span class="sxs-lookup"><span data-stu-id="89f27-116">byte</span></span>|<span data-ttu-id="89f27-117">符号なし 8 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="89f27-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="89f27-118">uy</span><span class="sxs-lookup"><span data-stu-id="89f27-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="89f27-119">int16</span><span class="sxs-lookup"><span data-stu-id="89f27-119">int16</span></span>|<span data-ttu-id="89f27-120">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="89f27-120">signed 16-bit integer</span></span>|<span data-ttu-id="89f27-121">s</span><span class="sxs-lookup"><span data-stu-id="89f27-121">s</span></span>|`86s`|
|<span data-ttu-id="89f27-122">uint16</span><span class="sxs-lookup"><span data-stu-id="89f27-122">uint16</span></span>|<span data-ttu-id="89f27-123">符号なし 16 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="89f27-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="89f27-124">us</span><span class="sxs-lookup"><span data-stu-id="89f27-124">us</span></span>|`86us`|
|<span data-ttu-id="89f27-125">int</span><span class="sxs-lookup"><span data-stu-id="89f27-125">int</span></span><br /><br /><span data-ttu-id="89f27-126">int32</span><span class="sxs-lookup"><span data-stu-id="89f27-126">int32</span></span>|<span data-ttu-id="89f27-127">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="89f27-127">signed 32-bit integer</span></span>|<span data-ttu-id="89f27-128">l または none</span><span class="sxs-lookup"><span data-stu-id="89f27-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="89f27-129">uint</span><span class="sxs-lookup"><span data-stu-id="89f27-129">uint</span></span><br /><br /><span data-ttu-id="89f27-130">uint32</span><span class="sxs-lookup"><span data-stu-id="89f27-130">uint32</span></span>|<span data-ttu-id="89f27-131">符号なし 32 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="89f27-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="89f27-132">u または ul</span><span class="sxs-lookup"><span data-stu-id="89f27-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="89f27-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="89f27-133">nativeint</span></span>|<span data-ttu-id="89f27-134">符号付きの自然数へのネイティブ ポインター</span><span class="sxs-lookup"><span data-stu-id="89f27-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="89f27-135">n</span><span class="sxs-lookup"><span data-stu-id="89f27-135">n</span></span>|`123n`|
|<span data-ttu-id="89f27-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="89f27-136">unativeint</span></span>|<span data-ttu-id="89f27-137">符号なし自然数としてのネイティブ ポインター</span><span class="sxs-lookup"><span data-stu-id="89f27-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="89f27-138">un</span><span class="sxs-lookup"><span data-stu-id="89f27-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="89f27-139">int64</span><span class="sxs-lookup"><span data-stu-id="89f27-139">int64</span></span>|<span data-ttu-id="89f27-140">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="89f27-140">signed 64-bit integer</span></span>|<span data-ttu-id="89f27-141">L</span><span class="sxs-lookup"><span data-stu-id="89f27-141">L</span></span>|`86L`|
|<span data-ttu-id="89f27-142">uint64</span><span class="sxs-lookup"><span data-stu-id="89f27-142">uint64</span></span>|<span data-ttu-id="89f27-143">符号なし 64 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="89f27-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="89f27-144">UL</span><span class="sxs-lookup"><span data-stu-id="89f27-144">UL</span></span>|`86UL`|
|<span data-ttu-id="89f27-145">single、float32</span><span class="sxs-lookup"><span data-stu-id="89f27-145">single, float32</span></span>|<span data-ttu-id="89f27-146">32 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="89f27-146">32-bit floating point number</span></span>|<span data-ttu-id="89f27-147">F または f</span><span class="sxs-lookup"><span data-stu-id="89f27-147">F or f</span></span>|<span data-ttu-id="89f27-148">`4.14F` または `4.14f`</span><span class="sxs-lookup"><span data-stu-id="89f27-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="89f27-149">lf</span><span class="sxs-lookup"><span data-stu-id="89f27-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="89f27-150">float、double</span><span class="sxs-lookup"><span data-stu-id="89f27-150">float; double</span></span>|<span data-ttu-id="89f27-151">64 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="89f27-151">64-bit floating point number</span></span>|<span data-ttu-id="89f27-152">none</span><span class="sxs-lookup"><span data-stu-id="89f27-152">none</span></span>|<span data-ttu-id="89f27-153">`4.14` または `2.3E+32` または `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="89f27-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="89f27-154">LF</span><span class="sxs-lookup"><span data-stu-id="89f27-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="89f27-155">bigint</span><span class="sxs-lookup"><span data-stu-id="89f27-155">bigint</span></span>|<span data-ttu-id="89f27-156">64 ビット表現に制限されない整数</span><span class="sxs-lookup"><span data-stu-id="89f27-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="89f27-157">I</span><span class="sxs-lookup"><span data-stu-id="89f27-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="89f27-158">decimal</span><span class="sxs-lookup"><span data-stu-id="89f27-158">decimal</span></span>|<span data-ttu-id="89f27-159">固定小数点数または有理数として表現される小数</span><span class="sxs-lookup"><span data-stu-id="89f27-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="89f27-160">M または m</span><span class="sxs-lookup"><span data-stu-id="89f27-160">M or m</span></span>|<span data-ttu-id="89f27-161">`0.7833M` または `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="89f27-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="89f27-162">Char</span><span class="sxs-lookup"><span data-stu-id="89f27-162">Char</span></span>|<span data-ttu-id="89f27-163">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="89f27-163">Unicode character</span></span>|<span data-ttu-id="89f27-164">none</span><span class="sxs-lookup"><span data-stu-id="89f27-164">none</span></span>|`'a'`|
|<span data-ttu-id="89f27-165">String</span><span class="sxs-lookup"><span data-stu-id="89f27-165">String</span></span>|<span data-ttu-id="89f27-166">Unicode 文字列</span><span class="sxs-lookup"><span data-stu-id="89f27-166">Unicode string</span></span>|<span data-ttu-id="89f27-167">none</span><span class="sxs-lookup"><span data-stu-id="89f27-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="89f27-168">または</span><span class="sxs-lookup"><span data-stu-id="89f27-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="89f27-169">または</span><span class="sxs-lookup"><span data-stu-id="89f27-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="89f27-170">または</span><span class="sxs-lookup"><span data-stu-id="89f27-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="89f27-171">参照してください[文字列](Strings.md)します。</span><span class="sxs-lookup"><span data-stu-id="89f27-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="89f27-172">byte</span><span class="sxs-lookup"><span data-stu-id="89f27-172">byte</span></span>|<span data-ttu-id="89f27-173">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="89f27-173">ASCII character</span></span>|<span data-ttu-id="89f27-174">B</span><span class="sxs-lookup"><span data-stu-id="89f27-174">B</span></span>|`'a'B`|
|<span data-ttu-id="89f27-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="89f27-175">byte[]</span></span>|<span data-ttu-id="89f27-176">ASCII 文字列</span><span class="sxs-lookup"><span data-stu-id="89f27-176">ASCII string</span></span>|<span data-ttu-id="89f27-177">B</span><span class="sxs-lookup"><span data-stu-id="89f27-177">B</span></span>|`"text"B`|
|<span data-ttu-id="89f27-178">String または byte[]</span><span class="sxs-lookup"><span data-stu-id="89f27-178">String or byte[]</span></span>|<span data-ttu-id="89f27-179">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="89f27-179">verbatim string</span></span>|<span data-ttu-id="89f27-180">@ プリフィックス</span><span class="sxs-lookup"><span data-stu-id="89f27-180">@ prefix</span></span>|<span data-ttu-id="89f27-181">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="89f27-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="89f27-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="89f27-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="89f27-183">名前付きリテラル</span><span class="sxs-lookup"><span data-stu-id="89f27-183">Named literals</span></span>

<span data-ttu-id="89f27-184">定数であることを意図した値でマークできる、[リテラル](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。</span><span class="sxs-lookup"><span data-stu-id="89f27-184">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="89f27-185">この属性には、値が定数としてコンパイルされる効果があります。</span><span class="sxs-lookup"><span data-stu-id="89f27-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="89f27-186">パターン マッチ式では、小文字で始まる識別子は、リテラルとしてではなく常にバインドされる変数として扱われます。そのため、一般的に、リテラルを定義する場合は先頭大文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89f27-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="89f27-187">Remarks</span><span class="sxs-lookup"><span data-stu-id="89f27-187">Remarks</span></span>

<span data-ttu-id="89f27-188">Unicode 文字列に明示的なエンコードを使用して指定することができますを含めることができます`\u`の後に 16 ビットの 16 進コードまたは utf-32 エンコーディングを使用して指定できる`\U`後に、Unicode を表す 32 ビットの 16 進コードサロゲート ペア。</span><span class="sxs-lookup"><span data-stu-id="89f27-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="89f27-189">以外の他のビットごとの演算子の使用`|||`は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="89f27-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="89f27-190">他の底の整数</span><span class="sxs-lookup"><span data-stu-id="89f27-190">Integers in other bases</span></span>

<span data-ttu-id="89f27-191">16 進数、8 進数、またはバイナリを使用して 32 ビット符号付き整数を指定することも、 `0x`、`0o`または`0b`それぞれプレフィックスします。</span><span class="sxs-lookup"><span data-stu-id="89f27-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="89f27-192">数値リテラルでのアンダー スコア</span><span class="sxs-lookup"><span data-stu-id="89f27-192">Underscores in numeric literals</span></span>

<span data-ttu-id="89f27-193">アンダー スコア文字は、桁を区切ることができます (`_`)。</span><span class="sxs-lookup"><span data-stu-id="89f27-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="89f27-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="89f27-194">See also</span></span>

- [<span data-ttu-id="89f27-195">Core.LiteralAttribute クラス</span><span class="sxs-lookup"><span data-stu-id="89f27-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
