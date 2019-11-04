---
title: 数値結果テーブルの書式設定 - C# リファレンス
ms.custom: seodec18
description: C# の標準の数値書式指定文字列について説明します
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 2cba5e704787ae6368b2543c985babf2fde3b4dd
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422755"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="0c581-103">数値結果テーブルの書式設定 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="0c581-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="0c581-104">次の表は、数値結果の書式を設定するためにサポートされている書式指定子を示しています。</span><span class="sxs-lookup"><span data-stu-id="0c581-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="0c581-105">最後の列の書式設定後の結果は、"en-US"<xref:System.Globalization.CultureInfo> に対応します。</span><span class="sxs-lookup"><span data-stu-id="0c581-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="0c581-106">書式指定子</span><span class="sxs-lookup"><span data-stu-id="0c581-106">Format specifier</span></span>|<span data-ttu-id="0c581-107">説明</span><span class="sxs-lookup"><span data-stu-id="0c581-107">Description</span></span>|<span data-ttu-id="0c581-108">使用例</span><span class="sxs-lookup"><span data-stu-id="0c581-108">Examples</span></span>|<span data-ttu-id="0c581-109">結果</span><span class="sxs-lookup"><span data-stu-id="0c581-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="0c581-110">C または c</span><span class="sxs-lookup"><span data-stu-id="0c581-110">C or c</span></span>|<span data-ttu-id="0c581-111">通貨</span><span class="sxs-lookup"><span data-stu-id="0c581-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="0c581-112">$2.50</span><span class="sxs-lookup"><span data-stu-id="0c581-112">$2.50</span></span><br /><br /> <span data-ttu-id="0c581-113">($2.50)</span><span class="sxs-lookup"><span data-stu-id="0c581-113">($2.50)</span></span>|  
|<span data-ttu-id="0c581-114">D または d</span><span class="sxs-lookup"><span data-stu-id="0c581-114">D or d</span></span>|<span data-ttu-id="0c581-115">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="0c581-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="0c581-116">00025</span><span class="sxs-lookup"><span data-stu-id="0c581-116">00025</span></span>|  
|<span data-ttu-id="0c581-117">E または e</span><span class="sxs-lookup"><span data-stu-id="0c581-117">E or e</span></span>|<span data-ttu-id="0c581-118">指数</span><span class="sxs-lookup"><span data-stu-id="0c581-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="0c581-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="0c581-119">2.50E+005</span></span>|  
|<span data-ttu-id="0c581-120">F または f</span><span class="sxs-lookup"><span data-stu-id="0c581-120">F or f</span></span>|<span data-ttu-id="0c581-121">固定小数点</span><span class="sxs-lookup"><span data-stu-id="0c581-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="0c581-122">2.50</span><span class="sxs-lookup"><span data-stu-id="0c581-122">2.50</span></span><br /><br /> <span data-ttu-id="0c581-123">3</span><span class="sxs-lookup"><span data-stu-id="0c581-123">3</span></span>|  
|<span data-ttu-id="0c581-124">G または g</span><span class="sxs-lookup"><span data-stu-id="0c581-124">G or g</span></span>|<span data-ttu-id="0c581-125">全般</span><span class="sxs-lookup"><span data-stu-id="0c581-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="0c581-126">2.5</span><span class="sxs-lookup"><span data-stu-id="0c581-126">2.5</span></span>|  
|<span data-ttu-id="0c581-127">N または n</span><span class="sxs-lookup"><span data-stu-id="0c581-127">N or n</span></span>|<span data-ttu-id="0c581-128">数字</span><span class="sxs-lookup"><span data-stu-id="0c581-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="0c581-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="0c581-129">2,500,000.00</span></span>|  
|<span data-ttu-id="0c581-130">P または p</span><span class="sxs-lookup"><span data-stu-id="0c581-130">P or p</span></span>|<span data-ttu-id="0c581-131">パーセント</span><span class="sxs-lookup"><span data-stu-id="0c581-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="0c581-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="0c581-132">25.00%</span></span>|  
|<span data-ttu-id="0c581-133">R または r</span><span class="sxs-lookup"><span data-stu-id="0c581-133">R or r</span></span>|<span data-ttu-id="0c581-134">ラウンドトリップ</span><span class="sxs-lookup"><span data-stu-id="0c581-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="0c581-135">2.5</span><span class="sxs-lookup"><span data-stu-id="0c581-135">2.5</span></span>|  
|<span data-ttu-id="0c581-136">X または x</span><span class="sxs-lookup"><span data-stu-id="0c581-136">X or x</span></span>|<span data-ttu-id="0c581-137">16 進数</span><span class="sxs-lookup"><span data-stu-id="0c581-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="0c581-138">FA</span><span class="sxs-lookup"><span data-stu-id="0c581-138">FA</span></span><br /><br /> <span data-ttu-id="0c581-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="0c581-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="0c581-140">解説</span><span class="sxs-lookup"><span data-stu-id="0c581-140">Remarks</span></span>

<span data-ttu-id="0c581-141">書式指定子を使用して、書式設定文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c581-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="0c581-142">書式設定文字列は `Axx` 形式になります。</span><span class="sxs-lookup"><span data-stu-id="0c581-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="0c581-143">`A` は書式指定子であり、数値に適用される書式設定の種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="0c581-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="0c581-144">`xx` は精度指定子であり、書式設定後の結果の桁数に影響します。</span><span class="sxs-lookup"><span data-stu-id="0c581-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="0c581-145">精度指定子の値は 0 から 99 の範囲です。</span><span class="sxs-lookup"><span data-stu-id="0c581-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="0c581-146">10 進数 ("D"または"d") と 16 進数 ("X"または"x") の形式指定子は、整数型でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0c581-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="0c581-147">ラウンドト リップ ("R"または"r") 書式指定子は、<xref:System.Single>、 <xref:System.Double> 型と <xref:System.Numerics.BigInteger> 型でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0c581-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="0c581-148">標準の数値書式指定文字列は、以下をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0c581-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="0c581-149">全数値型の `ToString` メソッドの一部のオーバーロード。</span><span class="sxs-lookup"><span data-stu-id="0c581-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="0c581-150">たとえば、<xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> メソッドおよび <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> メソッドに数値書式指定文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0c581-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="0c581-151">.NET の[複合書式設定機能](../../../standard/base-types/composite-formatting.md)。たとえば <xref:System.String.Format%2A?displayProperty=nameWithType> メソッドでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0c581-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="0c581-152">[挿入文字列](../tokens/interpolated.md)。</span><span class="sxs-lookup"><span data-stu-id="0c581-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="0c581-153">詳細については、「[標準の数値書式指定文字列](../../../standard/base-types/standard-numeric-format-strings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c581-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c581-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c581-154">See also</span></span>

- [<span data-ttu-id="0c581-155">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="0c581-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0c581-156">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="0c581-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0c581-157">型の書式設定</span><span class="sxs-lookup"><span data-stu-id="0c581-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="0c581-158">複合書式指定</span><span class="sxs-lookup"><span data-stu-id="0c581-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="0c581-159">文字列補間</span><span class="sxs-lookup"><span data-stu-id="0c581-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="0c581-160">string</span><span class="sxs-lookup"><span data-stu-id="0c581-160">string</span></span>](../builtin-types/reference-types.md)
