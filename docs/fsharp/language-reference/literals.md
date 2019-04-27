---
title: リテラル
description: リテラルの型について説明します、F#プログラミング言語。
ms.date: 02/08/2019
ms.openlocfilehash: 28ce34dee3c3c3d4d0cfd4107e8cbc375a23032c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904567"
---
# <a name="literals"></a><span data-ttu-id="ecd92-103">リテラル</span><span class="sxs-lookup"><span data-stu-id="ecd92-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="ecd92-104">この記事の API 参照リンクに出ます msdn (現在のところ)。</span><span class="sxs-lookup"><span data-stu-id="ecd92-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="ecd92-105">このトピックでは、F# でリテラルの型を指定する方法を示す表を示します。</span><span class="sxs-lookup"><span data-stu-id="ecd92-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="ecd92-106">リテラル型</span><span class="sxs-lookup"><span data-stu-id="ecd92-106">Literal Types</span></span>

<span data-ttu-id="ecd92-107">F# のリテラル型を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ecd92-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="ecd92-108">16 進表記で桁を表す文字は、大文字と小文字を区別しません。型を識別する文字は、大文字と小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="ecd92-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="ecd92-109">型</span><span class="sxs-lookup"><span data-stu-id="ecd92-109">Type</span></span>|<span data-ttu-id="ecd92-110">説明</span><span class="sxs-lookup"><span data-stu-id="ecd92-110">Description</span></span>|<span data-ttu-id="ecd92-111">サフィックスまたはプリフィックス</span><span class="sxs-lookup"><span data-stu-id="ecd92-111">Suffix or prefix</span></span>|<span data-ttu-id="ecd92-112">使用例</span><span class="sxs-lookup"><span data-stu-id="ecd92-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="ecd92-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="ecd92-113">sbyte</span></span>|<span data-ttu-id="ecd92-114">符号付き 8 ビット整数</span><span class="sxs-lookup"><span data-stu-id="ecd92-114">signed 8-bit integer</span></span>|<span data-ttu-id="ecd92-115">Y</span><span class="sxs-lookup"><span data-stu-id="ecd92-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="ecd92-116">byte</span><span class="sxs-lookup"><span data-stu-id="ecd92-116">byte</span></span>|<span data-ttu-id="ecd92-117">符号なし 8 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="ecd92-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="ecd92-118">uy</span><span class="sxs-lookup"><span data-stu-id="ecd92-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="ecd92-119">int16</span><span class="sxs-lookup"><span data-stu-id="ecd92-119">int16</span></span>|<span data-ttu-id="ecd92-120">符号付き 16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="ecd92-120">signed 16-bit integer</span></span>|<span data-ttu-id="ecd92-121">s</span><span class="sxs-lookup"><span data-stu-id="ecd92-121">s</span></span>|`86s`|
|<span data-ttu-id="ecd92-122">uint16</span><span class="sxs-lookup"><span data-stu-id="ecd92-122">uint16</span></span>|<span data-ttu-id="ecd92-123">符号なし 16 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="ecd92-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="ecd92-124">us</span><span class="sxs-lookup"><span data-stu-id="ecd92-124">us</span></span>|`86us`|
|<span data-ttu-id="ecd92-125">int</span><span class="sxs-lookup"><span data-stu-id="ecd92-125">int</span></span><br /><br /><span data-ttu-id="ecd92-126">int32</span><span class="sxs-lookup"><span data-stu-id="ecd92-126">int32</span></span>|<span data-ttu-id="ecd92-127">符号付き 32 ビット整数</span><span class="sxs-lookup"><span data-stu-id="ecd92-127">signed 32-bit integer</span></span>|<span data-ttu-id="ecd92-128">l または none</span><span class="sxs-lookup"><span data-stu-id="ecd92-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="ecd92-129">uint</span><span class="sxs-lookup"><span data-stu-id="ecd92-129">uint</span></span><br /><br /><span data-ttu-id="ecd92-130">uint32</span><span class="sxs-lookup"><span data-stu-id="ecd92-130">uint32</span></span>|<span data-ttu-id="ecd92-131">符号なし 32 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="ecd92-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="ecd92-132">u または ul</span><span class="sxs-lookup"><span data-stu-id="ecd92-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="ecd92-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="ecd92-133">unativeint</span></span>|<span data-ttu-id="ecd92-134">符号なし自然数としてのネイティブ ポインター</span><span class="sxs-lookup"><span data-stu-id="ecd92-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="ecd92-135">un</span><span class="sxs-lookup"><span data-stu-id="ecd92-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="ecd92-136">int64</span><span class="sxs-lookup"><span data-stu-id="ecd92-136">int64</span></span>|<span data-ttu-id="ecd92-137">符号付き 64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="ecd92-137">signed 64-bit integer</span></span>|<span data-ttu-id="ecd92-138">L</span><span class="sxs-lookup"><span data-stu-id="ecd92-138">L</span></span>|`86L`|
|<span data-ttu-id="ecd92-139">uint64</span><span class="sxs-lookup"><span data-stu-id="ecd92-139">uint64</span></span>|<span data-ttu-id="ecd92-140">符号なし 64 ビット自然数</span><span class="sxs-lookup"><span data-stu-id="ecd92-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="ecd92-141">UL</span><span class="sxs-lookup"><span data-stu-id="ecd92-141">UL</span></span>|`86UL`|
|<span data-ttu-id="ecd92-142">single、float32</span><span class="sxs-lookup"><span data-stu-id="ecd92-142">single, float32</span></span>|<span data-ttu-id="ecd92-143">32 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ecd92-143">32-bit floating point number</span></span>|<span data-ttu-id="ecd92-144">F または f</span><span class="sxs-lookup"><span data-stu-id="ecd92-144">F or f</span></span>|<span data-ttu-id="ecd92-145">`4.14F` または `4.14f`</span><span class="sxs-lookup"><span data-stu-id="ecd92-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="ecd92-146">lf</span><span class="sxs-lookup"><span data-stu-id="ecd92-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="ecd92-147">float、double</span><span class="sxs-lookup"><span data-stu-id="ecd92-147">float; double</span></span>|<span data-ttu-id="ecd92-148">64 ビット浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="ecd92-148">64-bit floating point number</span></span>|<span data-ttu-id="ecd92-149">none</span><span class="sxs-lookup"><span data-stu-id="ecd92-149">none</span></span>|<span data-ttu-id="ecd92-150">`4.14` または`2.3E+32`または `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="ecd92-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="ecd92-151">LF</span><span class="sxs-lookup"><span data-stu-id="ecd92-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="ecd92-152">bigint</span><span class="sxs-lookup"><span data-stu-id="ecd92-152">bigint</span></span>|<span data-ttu-id="ecd92-153">64 ビット表現に制限されない整数</span><span class="sxs-lookup"><span data-stu-id="ecd92-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="ecd92-154">I</span><span class="sxs-lookup"><span data-stu-id="ecd92-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="ecd92-155">decimal</span><span class="sxs-lookup"><span data-stu-id="ecd92-155">decimal</span></span>|<span data-ttu-id="ecd92-156">固定小数点数または有理数として表現される小数</span><span class="sxs-lookup"><span data-stu-id="ecd92-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="ecd92-157">M または m</span><span class="sxs-lookup"><span data-stu-id="ecd92-157">M or m</span></span>|<span data-ttu-id="ecd92-158">`0.7833M` または `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="ecd92-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="ecd92-159">Char</span><span class="sxs-lookup"><span data-stu-id="ecd92-159">Char</span></span>|<span data-ttu-id="ecd92-160">Unicode 文字</span><span class="sxs-lookup"><span data-stu-id="ecd92-160">Unicode character</span></span>|<span data-ttu-id="ecd92-161">none</span><span class="sxs-lookup"><span data-stu-id="ecd92-161">none</span></span>|`'a'`|
|<span data-ttu-id="ecd92-162">String</span><span class="sxs-lookup"><span data-stu-id="ecd92-162">String</span></span>|<span data-ttu-id="ecd92-163">Unicode 文字列</span><span class="sxs-lookup"><span data-stu-id="ecd92-163">Unicode string</span></span>|<span data-ttu-id="ecd92-164">none</span><span class="sxs-lookup"><span data-stu-id="ecd92-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="ecd92-165">または</span><span class="sxs-lookup"><span data-stu-id="ecd92-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="ecd92-166">または</span><span class="sxs-lookup"><span data-stu-id="ecd92-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="ecd92-167">または</span><span class="sxs-lookup"><span data-stu-id="ecd92-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="ecd92-168">参照してください[文字列](Strings.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecd92-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="ecd92-169">byte</span><span class="sxs-lookup"><span data-stu-id="ecd92-169">byte</span></span>|<span data-ttu-id="ecd92-170">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="ecd92-170">ASCII character</span></span>|<span data-ttu-id="ecd92-171">B</span><span class="sxs-lookup"><span data-stu-id="ecd92-171">B</span></span>|`'a'B`|
|<span data-ttu-id="ecd92-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="ecd92-172">byte[]</span></span>|<span data-ttu-id="ecd92-173">ASCII 文字列</span><span class="sxs-lookup"><span data-stu-id="ecd92-173">ASCII string</span></span>|<span data-ttu-id="ecd92-174">B</span><span class="sxs-lookup"><span data-stu-id="ecd92-174">B</span></span>|`"text"B`|
|<span data-ttu-id="ecd92-175">String または byte[]</span><span class="sxs-lookup"><span data-stu-id="ecd92-175">String or byte[]</span></span>|<span data-ttu-id="ecd92-176">逐語的文字列</span><span class="sxs-lookup"><span data-stu-id="ecd92-176">verbatim string</span></span>|<span data-ttu-id="ecd92-177">@ プリフィックス</span><span class="sxs-lookup"><span data-stu-id="ecd92-177">@ prefix</span></span>|<span data-ttu-id="ecd92-178">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="ecd92-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="ecd92-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="ecd92-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="ecd92-180">Remarks</span><span class="sxs-lookup"><span data-stu-id="ecd92-180">Remarks</span></span>

<span data-ttu-id="ecd92-181">Unicode 文字列に明示的なエンコードを使用して指定することができますを含めることができます`\u`の後に 16 ビットの 16 進コードまたは utf-32 エンコーディングを使用して指定できる`\U`後に、Unicode を表す 32 ビットの 16 進コードサロゲート ペア。</span><span class="sxs-lookup"><span data-stu-id="ecd92-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="ecd92-182">F# 3.1 を使用できます、`+`サインインすると、文字列リテラルを結合します。</span><span class="sxs-lookup"><span data-stu-id="ecd92-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="ecd92-183">ビットごとのこともできます。 または (`|||`) 列挙型フラグを結合する演算子。</span><span class="sxs-lookup"><span data-stu-id="ecd92-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="ecd92-184">たとえば、F# 3.1 では次のようなコードが有効です。</span><span class="sxs-lookup"><span data-stu-id="ecd92-184">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="ecd92-185">その他のビットごとの演算子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ecd92-185">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="ecd92-186">名前付きリテラル</span><span class="sxs-lookup"><span data-stu-id="ecd92-186">Named Literals</span></span>

<span data-ttu-id="ecd92-187">定数であることを意図した値でマークできる、[リテラル](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285)属性。</span><span class="sxs-lookup"><span data-stu-id="ecd92-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="ecd92-188">この属性には、値が定数としてコンパイルされる効果があります。</span><span class="sxs-lookup"><span data-stu-id="ecd92-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="ecd92-189">パターン マッチ式では、小文字で始まる識別子は、リテラルとしてではなく常にバインドされる変数として扱われます。そのため、一般的に、リテラルを定義する場合は先頭大文字を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecd92-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="ecd92-190">他の底の整数</span><span class="sxs-lookup"><span data-stu-id="ecd92-190">Integers In Other Bases</span></span>

<span data-ttu-id="ecd92-191">16 進数、8 進数、またはバイナリを使用して 32 ビット符号付き整数を指定することも、 `0x`、`0o`または`0b`それぞれプレフィックスします。</span><span class="sxs-lookup"><span data-stu-id="ecd92-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="ecd92-192">数値リテラルでのアンダー スコア</span><span class="sxs-lookup"><span data-stu-id="ecd92-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="ecd92-193">以降でF#4.1、アンダー スコア文字は、桁を区切ることができます (`_`)。</span><span class="sxs-lookup"><span data-stu-id="ecd92-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="ecd92-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecd92-194">See also</span></span>

- [<span data-ttu-id="ecd92-195">Core.LiteralAttribute クラス</span><span class="sxs-lookup"><span data-stu-id="ecd92-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
