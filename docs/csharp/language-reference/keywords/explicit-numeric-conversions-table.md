---
title: 明示的な数値変換の一覧表 - C# リファレンス
ms.custom: seodec18
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 24f7401538eb1eeb675e6c3de265688780d6b91a
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424205"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="1017a-102">明示的な数値変換の一覧表 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1017a-102">Explicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="1017a-103">次の表では、[暗黙的な変換](implicit-numeric-conversions-table.md)がない .NET 数値型間で事前定義されている明示的変換がまとめてあります。</span><span class="sxs-lookup"><span data-stu-id="1017a-103">The following table shows the predefined explicit conversions between .NET numeric types for which there is no [implicit conversion](implicit-numeric-conversions-table.md).</span></span>

|<span data-ttu-id="1017a-104">From</span><span class="sxs-lookup"><span data-stu-id="1017a-104">From</span></span>|<span data-ttu-id="1017a-105">終了</span><span class="sxs-lookup"><span data-stu-id="1017a-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="1017a-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="1017a-106">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-107">`byte`、`ushort`、`uint`、`ulong`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-107">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="1017a-108">byte</span><span class="sxs-lookup"><span data-stu-id="1017a-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-109">`sbyte` または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-109">`sbyte` or `char`</span></span>|  
|[<span data-ttu-id="1017a-110">short</span><span class="sxs-lookup"><span data-stu-id="1017a-110">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-111">`sbyte`、`byte`、`ushort`、`uint`、`ulong`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-111">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="1017a-112">ushort</span><span class="sxs-lookup"><span data-stu-id="1017a-112">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-113">`sbyte`、`byte`、`short`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-113">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="1017a-114">int</span><span class="sxs-lookup"><span data-stu-id="1017a-114">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-115">`sbyte`、`byte`、`short`、`ushort`、`uint`、`ulong`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-115">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="1017a-116">uint</span><span class="sxs-lookup"><span data-stu-id="1017a-116">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-117">`sbyte`、`byte`、`short`、`ushort`、`int`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-117">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="1017a-118">long</span><span class="sxs-lookup"><span data-stu-id="1017a-118">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-119">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`ulong`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-119">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="1017a-120">ulong</span><span class="sxs-lookup"><span data-stu-id="1017a-120">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="1017a-121">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、または `char`</span><span class="sxs-lookup"><span data-stu-id="1017a-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="1017a-122">char</span><span class="sxs-lookup"><span data-stu-id="1017a-122">char</span></span>](char.md)|<span data-ttu-id="1017a-123">`sbyte`、 `byte`、または `short`</span><span class="sxs-lookup"><span data-stu-id="1017a-123">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="1017a-124">float</span><span class="sxs-lookup"><span data-stu-id="1017a-124">float</span></span>](float.md)|<span data-ttu-id="1017a-125">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="1017a-125">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="1017a-126">double</span><span class="sxs-lookup"><span data-stu-id="1017a-126">double</span></span>](double.md)|<span data-ttu-id="1017a-127">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、または `decimal`</span><span class="sxs-lookup"><span data-stu-id="1017a-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="1017a-128">decimal</span><span class="sxs-lookup"><span data-stu-id="1017a-128">decimal</span></span>](decimal.md)|<span data-ttu-id="1017a-129">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、または `double`</span><span class="sxs-lookup"><span data-stu-id="1017a-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1017a-130">コメント</span><span class="sxs-lookup"><span data-stu-id="1017a-130">Remarks</span></span>  
  
- <span data-ttu-id="1017a-131">明示的な数値変換では、精度が失われたり、例外 (通常、<xref:System.OverflowException>) がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="1017a-131">The explicit numeric conversion may cause loss of precision or result in throwing an exception, typically an <xref:System.OverflowException>.</span></span>  

- <span data-ttu-id="1017a-132">ある整数型の値を別の整数型に変換するとき、その結果は、オーバーフロー [チェック コンテキスト](checked-and-unchecked.md)によって変わります。</span><span class="sxs-lookup"><span data-stu-id="1017a-132">When you convert a value of an integral type to another integral type, the result depends on the overflow [checking context](checked-and-unchecked.md).</span></span> <span data-ttu-id="1017a-133">checked コンテキストでは、変換元の値が変換先の型の範囲内にあるとき、変換に成功します。</span><span class="sxs-lookup"><span data-stu-id="1017a-133">In a checked context, the conversion succeeds if the source value is within the range of the destination type.</span></span> <span data-ttu-id="1017a-134">それ以外の場合は、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1017a-134">Otherwise, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="1017a-135">unchecked コンテキストでは、変換は常に成功し、次のように続行されます。</span><span class="sxs-lookup"><span data-stu-id="1017a-135">In an unchecked context, the conversion always succeeds, and proceeds as follows:</span></span>

  - <span data-ttu-id="1017a-136">変換元の型が変換先の型より大きい場合、変換元の値はその "余分な" 最上位ビットを破棄することで切り詰められます。</span><span class="sxs-lookup"><span data-stu-id="1017a-136">If the source type is larger than the destination type, then the source value is truncated by discarding its "extra" most significant bits.</span></span> <span data-ttu-id="1017a-137">結果は変換先の型の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="1017a-137">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="1017a-138">変換元の型が変換先の型より小さい場合、変換元の値は変換先の型と同じサイズになるように符号かゼロが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="1017a-138">If the source type is smaller than the destination type, then the source value is either sign-extended or zero-extended so that it is the same size as the destination type.</span></span> <span data-ttu-id="1017a-139">変換元の型に符号が付いている場合は符号拡張が利用され、符号が付いていない場合はゼロ拡張が利用されます。</span><span class="sxs-lookup"><span data-stu-id="1017a-139">Sign-extension is used if the source type is signed; zero-extension is used if the source type is unsigned.</span></span> <span data-ttu-id="1017a-140">結果は変換先の型の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="1017a-140">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="1017a-141">変換元の型が変換先の型と同じサイズの場合、変換元の値は変換先の型の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="1017a-141">If the source type is the same size as the destination type, then the source value is treated as a value of the destination type.</span></span>
  
- <span data-ttu-id="1017a-142">`decimal` 値を整数型に変換するとき、この値は 0 方向に最も近い整数値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1017a-142">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="1017a-143">結果的に生成される整数値が変換先の型の範囲外になった場合、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1017a-143">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
- <span data-ttu-id="1017a-144">`double` または `float` 値を整数型に変換するとき、この値は 0 方向に最も近い整数値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1017a-144">When you convert a `double` or `float` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="1017a-145">結果的に生成される整数値が変換先の型の範囲外になる場合、結果はオーバーフロー [チェック コンテキスト](checked-and-unchecked.md)によって変わります。</span><span class="sxs-lookup"><span data-stu-id="1017a-145">If the resulting integral value is outside the range of the destination type, the result depends on the overflow [checking context](checked-and-unchecked.md).</span></span> <span data-ttu-id="1017a-146">チェック済みコンテキストの場合、<xref:System.OverflowException> がスローされます。未チェック コンテキストの場合、結果は変換先の型の不特定な値になります。</span><span class="sxs-lookup"><span data-stu-id="1017a-146">In a checked context, an <xref:System.OverflowException> is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
- <span data-ttu-id="1017a-147">`double` を `float` に変換すると、`double` 値は最も近い `float` 値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1017a-147">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="1017a-148">`double` 値が小さすぎるか、大きすぎて変換先の型に合わない場合、結果は 0 か無限になります。</span><span class="sxs-lookup"><span data-stu-id="1017a-148">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
- <span data-ttu-id="1017a-149">`float` または `double` を `decimal` に変換するとき、変換元の値は `decimal` 表現に変換され、必要であれば、28 番目の小数位の後に最も近い数字に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1017a-149">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="1017a-150">変換元の値によっては、結果は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="1017a-150">Depending on the value of the source value, one of the following results may occur:</span></span>  

  - <span data-ttu-id="1017a-151">変換元の値が小さすぎて `decimal` として表現できない場合、結果は 0 になります。</span><span class="sxs-lookup"><span data-stu-id="1017a-151">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  

  - <span data-ttu-id="1017a-152">変換元の値が NaN (Not a Number/数字ではない) か、無限か、大きすぎて `decimal` として表現できない場合、<xref:System.OverflowException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1017a-152">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an <xref:System.OverflowException> is thrown.</span></span>  
  
- <span data-ttu-id="1017a-153">`decimal` を `float` または `double` に変換すると、`decimal` 値は最も近い `double` または `float` 値に丸められます。</span><span class="sxs-lookup"><span data-stu-id="1017a-153">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="1017a-154">明示的な変換に関する詳細については、[C# 言語仕様](../language-specification/index.md)に関するページの「[Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions)」(明示的な変換) セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1017a-154">For more information about explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1017a-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="1017a-155">See also</span></span>

- [<span data-ttu-id="1017a-156">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1017a-156">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1017a-157">キャストと型変換</span><span class="sxs-lookup"><span data-stu-id="1017a-157">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="1017a-158">() 演算子</span><span class="sxs-lookup"><span data-stu-id="1017a-158">() operator</span></span>](../operators/type-testing-and-conversion-operators.md#cast-operator-)
- [<span data-ttu-id="1017a-159">整数型</span><span class="sxs-lookup"><span data-stu-id="1017a-159">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="1017a-160">浮動小数点型の一覧表</span><span class="sxs-lookup"><span data-stu-id="1017a-160">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="1017a-161">組み込み型の一覧表</span><span class="sxs-lookup"><span data-stu-id="1017a-161">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="1017a-162">暗黙的な数値変換の一覧表</span><span class="sxs-lookup"><span data-stu-id="1017a-162">Implicit numeric conversions table</span></span>](implicit-numeric-conversions-table.md)
