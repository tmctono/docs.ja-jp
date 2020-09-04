---
description: C# の組み込みの数値型間での暗黙的および明示的な変換について
title: 組み込みの数値変換 - C# リファレンス
ms.date: 10/22/2019
helpviewer_keywords:
- implicit numeric conversions [C#]
- explicit numeric conversion [C#]
- numeric conversions [C#], implicit
- numeric conversions [C#], explicit
- conversions [C#], implicit numeric
- conversions [C#], explicit numeric
ms.openlocfilehash: ee5def3b5e0e067919a8c8335db701dbb6dd4d88
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142246"
---
# <a name="built-in-numeric-conversions-c-reference"></a><span data-ttu-id="f7646-103">組み込みの数値変換 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f7646-103">Built-in numeric conversions (C# reference)</span></span>

<span data-ttu-id="f7646-104">C# では、[整数](integral-numeric-types.md)数値型と[浮動小数点](floating-point-numeric-types.md)数値型のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7646-104">C# provides a set of [integral](integral-numeric-types.md) and [floating-point](floating-point-numeric-types.md) numeric types.</span></span> <span data-ttu-id="f7646-105">任意の 2 つの数値型の間で、暗黙的または明示的のいずれかの変換が存在します。</span><span class="sxs-lookup"><span data-stu-id="f7646-105">There exists a conversion between any two numeric types, either implicit or explicit.</span></span> <span data-ttu-id="f7646-106">明示的な変換を実行するには、[キャスト式](../operators/type-testing-and-cast.md#cast-expression)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7646-106">You must use a [cast expression](../operators/type-testing-and-cast.md#cast-expression) to perform an explicit conversion.</span></span>

## <a name="implicit-numeric-conversions"></a><span data-ttu-id="f7646-107">暗黙の数値変換</span><span class="sxs-lookup"><span data-stu-id="f7646-107">Implicit numeric conversions</span></span>

<span data-ttu-id="f7646-108">組み込みの数値型間の定義済みの暗黙的な変換を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="f7646-108">The following table shows the predefined implicit conversions between the built-in numeric types:</span></span>

|<span data-ttu-id="f7646-109">From</span><span class="sxs-lookup"><span data-stu-id="f7646-109">From</span></span>|<span data-ttu-id="f7646-110">終了</span><span class="sxs-lookup"><span data-stu-id="f7646-110">To</span></span>|
|----------|--------|
|[<span data-ttu-id="f7646-111">sbyte</span><span class="sxs-lookup"><span data-stu-id="f7646-111">sbyte</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-112">`short`、`int`、`long`、`float`、`double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-112">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-113">byte</span><span class="sxs-lookup"><span data-stu-id="f7646-113">byte</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-114">`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-114">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-115">short</span><span class="sxs-lookup"><span data-stu-id="f7646-115">short</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-116">`int`、`long`、`float`、`double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-116">`int`, `long`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-117">ushort</span><span class="sxs-lookup"><span data-stu-id="f7646-117">ushort</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-118">`int`、`uint`、`long`、`ulong`、`float`、`double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-118">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-119">int</span><span class="sxs-lookup"><span data-stu-id="f7646-119">int</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-120">`long`、`float`、`double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-120">`long`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-121">uint</span><span class="sxs-lookup"><span data-stu-id="f7646-121">uint</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-122">`long`、`ulong`、`float`、`double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-122">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-123">long</span><span class="sxs-lookup"><span data-stu-id="f7646-123">long</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-124">`float`、 `double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-124">`float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-125">ulong</span><span class="sxs-lookup"><span data-stu-id="f7646-125">ulong</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-126">`float`、 `double`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-126">`float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-127">float</span><span class="sxs-lookup"><span data-stu-id="f7646-127">float</span></span>](floating-point-numeric-types.md)|`double`|

> [!NOTE]
> <span data-ttu-id="f7646-128">`int`、`uint`、`long`、または `ulong` から `float` および `long` または `ulong` から `double` への暗黙的な変換では、精度が失われる可能性がありますが、桁違いの損失は発生しません。</span><span class="sxs-lookup"><span data-stu-id="f7646-128">The implicit conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double` may cause a loss of precision, but never a loss of an order of magnitude.</span></span> <span data-ttu-id="f7646-129">その他の暗黙的な数値変換では、情報が失われることはありません。</span><span class="sxs-lookup"><span data-stu-id="f7646-129">The other implicit numeric conversions never lose any information.</span></span>

<span data-ttu-id="f7646-130">次の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7646-130">Also note that</span></span>

- <span data-ttu-id="f7646-131">[整数数値型](integral-numeric-types.md)はすべて、あらゆる[浮動小数点数値型](floating-point-numeric-types.md)に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f7646-131">Any [integral numeric type](integral-numeric-types.md) is implicitly convertible to any [floating-point numeric type](floating-point-numeric-types.md).</span></span>

- <span data-ttu-id="f7646-132">`byte` および `sbyte` 型への暗黙的な変換はありません。</span><span class="sxs-lookup"><span data-stu-id="f7646-132">There are no implicit conversions to the `byte` and `sbyte` types.</span></span> <span data-ttu-id="f7646-133">`double` および `decimal` 型からの暗黙的な変換はありません。</span><span class="sxs-lookup"><span data-stu-id="f7646-133">There are no implicit conversions from the `double` and `decimal` types.</span></span>

- <span data-ttu-id="f7646-134">`decimal` 型と `float` 型または `double` 型の間に暗黙的な変換はありません。</span><span class="sxs-lookup"><span data-stu-id="f7646-134">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>

- <span data-ttu-id="f7646-135">型 `int` の定数式の値 (整数リテラルで表される値など) は、それが変換先の型の範囲内にある場合、`sbyte`、`byte`、`short`、`ushort`、`uint`、または `ulong` に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f7646-135">A value of a constant expression of type `int` (for example, a value represented by an integer literal) can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, if it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;
  byte b = 300;  // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

  <span data-ttu-id="f7646-136">前の例で示したように、定数値が変換先の型の範囲内にない場合、コンパイラ エラー [CS0031](../../misc/cs0031.md) が発生します。</span><span class="sxs-lookup"><span data-stu-id="f7646-136">As the preceding example shows, if the constant value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

## <a name="explicit-numeric-conversions"></a><span data-ttu-id="f7646-137">明示的な数値変換</span><span class="sxs-lookup"><span data-stu-id="f7646-137">Explicit numeric conversions</span></span>

<span data-ttu-id="f7646-138">次の表では、[暗黙的な変換](#implicit-numeric-conversions)がない組み込みの数値型間で事前定義されている明示的変換を示しています。</span><span class="sxs-lookup"><span data-stu-id="f7646-138">The following table shows the predefined explicit conversions between the built-in numeric types for which there is no [implicit conversion](#implicit-numeric-conversions):</span></span>

|<span data-ttu-id="f7646-139">From</span><span class="sxs-lookup"><span data-stu-id="f7646-139">From</span></span>|<span data-ttu-id="f7646-140">終了</span><span class="sxs-lookup"><span data-stu-id="f7646-140">To</span></span>|
|----------|--------|
|[<span data-ttu-id="f7646-141">sbyte</span><span class="sxs-lookup"><span data-stu-id="f7646-141">sbyte</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-142">`byte`、`ushort`、`uint`、または `ulong`</span><span class="sxs-lookup"><span data-stu-id="f7646-142">`byte`, `ushort`, `uint`, or `ulong`</span></span>|
|[<span data-ttu-id="f7646-143">byte</span><span class="sxs-lookup"><span data-stu-id="f7646-143">byte</span></span>](integral-numeric-types.md)|`sbyte`|
|[<span data-ttu-id="f7646-144">short</span><span class="sxs-lookup"><span data-stu-id="f7646-144">short</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-145">`sbyte`、`byte`、`ushort`、`uint`、または `ulong`</span><span class="sxs-lookup"><span data-stu-id="f7646-145">`sbyte`, `byte`, `ushort`, `uint`, or `ulong`</span></span>|
|[<span data-ttu-id="f7646-146">ushort</span><span class="sxs-lookup"><span data-stu-id="f7646-146">ushort</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-147">`sbyte`、 `byte`、または `short`</span><span class="sxs-lookup"><span data-stu-id="f7646-147">`sbyte`, `byte`, or `short`</span></span>|
|[<span data-ttu-id="f7646-148">int</span><span class="sxs-lookup"><span data-stu-id="f7646-148">int</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-149">`sbyte`、`byte`、`short`、`ushort`、`uint`、または `ulong`</span><span class="sxs-lookup"><span data-stu-id="f7646-149">`sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`</span></span>|
|[<span data-ttu-id="f7646-150">uint</span><span class="sxs-lookup"><span data-stu-id="f7646-150">uint</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-151">`sbyte`、`byte`、`short`、`ushort`、または `int`</span><span class="sxs-lookup"><span data-stu-id="f7646-151">`sbyte`, `byte`, `short`, `ushort`, or `int`</span></span>|
|[<span data-ttu-id="f7646-152">long</span><span class="sxs-lookup"><span data-stu-id="f7646-152">long</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-153">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、または `ulong`</span><span class="sxs-lookup"><span data-stu-id="f7646-153">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, or `ulong`</span></span>|
|[<span data-ttu-id="f7646-154">ulong</span><span class="sxs-lookup"><span data-stu-id="f7646-154">ulong</span></span>](integral-numeric-types.md)|<span data-ttu-id="f7646-155">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、または `long`</span><span class="sxs-lookup"><span data-stu-id="f7646-155">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, or `long`</span></span>|
|[<span data-ttu-id="f7646-156">float</span><span class="sxs-lookup"><span data-stu-id="f7646-156">float</span></span>](floating-point-numeric-types.md)|<span data-ttu-id="f7646-157">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-157">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-158">double</span><span class="sxs-lookup"><span data-stu-id="f7646-158">double</span></span>](floating-point-numeric-types.md)|<span data-ttu-id="f7646-159">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="f7646-159">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, or `decimal`</span></span>|
|[<span data-ttu-id="f7646-160">decimal</span><span class="sxs-lookup"><span data-stu-id="f7646-160">decimal</span></span>](floating-point-numeric-types.md)|<span data-ttu-id="f7646-161">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、または `double`</span><span class="sxs-lookup"><span data-stu-id="f7646-161">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, or `double`</span></span>|

> [!NOTE]
> <span data-ttu-id="f7646-162">明示的な数値変換によって、データが失われたり、例外がスローされたりすることがあります (通常は <xref:System.OverflowException>)。</span><span class="sxs-lookup"><span data-stu-id="f7646-162">An explicit numeric conversion might result in data loss or throw an exception, typically an <xref:System.OverflowException>.</span></span>

<span data-ttu-id="f7646-163">次の点にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7646-163">Also note that</span></span>

- <span data-ttu-id="f7646-164">ある整数型の値を別の整数型に変換するとき、その結果は、オーバーフロー [チェック コンテキスト](../keywords/checked-and-unchecked.md)によって変わります。</span><span class="sxs-lookup"><span data-stu-id="f7646-164">When you convert a value of an integral type to another integral type, the result depends on the overflow [checking context](../keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="f7646-165">checked コンテキストでは、変換元の値が変換先の型の範囲内にあるとき、変換に成功します。</span><span class="sxs-lookup"><span data-stu-id="f7646-165">In a checked context, the conversion succeeds if the source value is within the range of the destination type.</span></span> <span data-ttu-id="f7646-166">それ以外の場合は、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f7646-166">Otherwise, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="f7646-167">unchecked コンテキストでは、変換は常に成功し、次のように続行されます。</span><span class="sxs-lookup"><span data-stu-id="f7646-167">In an unchecked context, the conversion always succeeds, and proceeds as follows:</span></span>

  - <span data-ttu-id="f7646-168">変換元の型が変換先の型より大きい場合、変換元の値はその "余分な" 最上位ビットを破棄することで切り詰められます。</span><span class="sxs-lookup"><span data-stu-id="f7646-168">If the source type is larger than the destination type, then the source value is truncated by discarding its "extra" most significant bits.</span></span> <span data-ttu-id="f7646-169">結果は変換先の型の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f7646-169">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="f7646-170">変換元の型が変換先の型より小さい場合、変換元の値は変換先の型と同じサイズになるように、符号拡張またはゼロ拡張されます。</span><span class="sxs-lookup"><span data-stu-id="f7646-170">If the source type is smaller than the destination type, then the source value is either sign-extended or zero-extended so that it's of the same size as the destination type.</span></span> <span data-ttu-id="f7646-171">変換元の型に符号が付いている場合は符号拡張が利用され、符号が付いていない場合はゼロ拡張が利用されます。</span><span class="sxs-lookup"><span data-stu-id="f7646-171">Sign-extension is used if the source type is signed; zero-extension is used if the source type is unsigned.</span></span> <span data-ttu-id="f7646-172">結果は変換先の型の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f7646-172">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="f7646-173">変換元の型が変換先の型と同じサイズの場合、変換元の値は変換先の型の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="f7646-173">If the source type is the same size as the destination type, then the source value is treated as a value of the destination type.</span></span>

- <span data-ttu-id="f7646-174">`decimal` 値を整数型に変換するとき、この値は 0 方向に最も近い整数値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="f7646-174">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="f7646-175">結果的に生成される整数値が変換先の型の範囲外になった場合、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f7646-175">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>

- <span data-ttu-id="f7646-176">`double` または `float` 値を整数型に変換するとき、この値は 0 方向に最も近い整数値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="f7646-176">When you convert a `double` or `float` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="f7646-177">結果的に生成される整数値が変換先の型の範囲外になる場合、結果はオーバーフロー [チェック コンテキスト](../keywords/checked-and-unchecked.md)によって変わります。</span><span class="sxs-lookup"><span data-stu-id="f7646-177">If the resulting integral value is outside the range of the destination type, the result depends on the overflow [checking context](../keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="f7646-178">チェック済みコンテキストの場合、<xref:System.OverflowException> がスローされます。未チェック コンテキストの場合、結果は変換先の型の不特定な値になります。</span><span class="sxs-lookup"><span data-stu-id="f7646-178">In a checked context, an <xref:System.OverflowException> is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>

- <span data-ttu-id="f7646-179">`double` を `float` に変換すると、`double` 値は最も近い `float` 値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="f7646-179">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="f7646-180">`double` 値が小さすぎるか、大きすぎて `float` 型に合わない場合、結果は 0 か無限になります。</span><span class="sxs-lookup"><span data-stu-id="f7646-180">If the `double` value is too small or too large to fit into the `float` type, the result is zero or infinity.</span></span>

- <span data-ttu-id="f7646-181">`float` または `double` を `decimal` に変換するとき、変換元の値は `decimal` 表現に変換され、必要であれば、28 番目の小数位の後に最も近い数字に丸められます。</span><span class="sxs-lookup"><span data-stu-id="f7646-181">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="f7646-182">変換元の値によっては、結果は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="f7646-182">Depending on the value of the source value, one of the following results may occur:</span></span>

  - <span data-ttu-id="f7646-183">変換元の値が小さすぎて `decimal` として表現できない場合、結果は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="f7646-183">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>

  - <span data-ttu-id="f7646-184">変換元の値が NaN (Not a Number/数字ではない) か、無限か、大きすぎて `decimal` として表現できない場合、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f7646-184">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an <xref:System.OverflowException> is thrown.</span></span>

- <span data-ttu-id="f7646-185">`decimal` を `float` または `double` に変換すると、変換元の値はそれぞれ最も近い `float` または `double` 値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="f7646-185">When you convert `decimal` to `float` or `double`, the source value is rounded to the nearest `float` or `double` value, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f7646-186">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f7646-186">C# language specification</span></span>

<span data-ttu-id="f7646-187">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7646-187">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="f7646-188">暗黙の数値変換</span><span class="sxs-lookup"><span data-stu-id="f7646-188">Implicit numeric conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-numeric-conversions)
- [<span data-ttu-id="f7646-189">明示的な数値変換</span><span class="sxs-lookup"><span data-stu-id="f7646-189">Explicit numeric conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-numeric-conversions)

## <a name="see-also"></a><span data-ttu-id="f7646-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7646-190">See also</span></span>

- [<span data-ttu-id="f7646-191">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f7646-191">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f7646-192">キャストと型変換</span><span class="sxs-lookup"><span data-stu-id="f7646-192">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
