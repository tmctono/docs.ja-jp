---
title: 10 進型 (Decimal)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 6d62bcc1d043b45c0fc30154d9dc633b998f97b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344043"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="89461-102">10 進型 (Decimal) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89461-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="89461-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span><span class="sxs-lookup"><span data-stu-id="89461-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="89461-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span><span class="sxs-lookup"><span data-stu-id="89461-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="89461-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span><span class="sxs-lookup"><span data-stu-id="89461-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="89461-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="89461-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="89461-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="89461-107">Remarks</span></span>

<span data-ttu-id="89461-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span><span class="sxs-lookup"><span data-stu-id="89461-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="89461-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span><span class="sxs-lookup"><span data-stu-id="89461-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="89461-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span><span class="sxs-lookup"><span data-stu-id="89461-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="89461-111">`Decimal` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="89461-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="89461-112">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="89461-112">Programming Tips</span></span>

- <span data-ttu-id="89461-113">**Precision.**</span><span class="sxs-lookup"><span data-stu-id="89461-113">**Precision.**</span></span> <span data-ttu-id="89461-114">`Decimal` is not a floating-point data type.</span><span class="sxs-lookup"><span data-stu-id="89461-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="89461-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span><span class="sxs-lookup"><span data-stu-id="89461-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="89461-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span><span class="sxs-lookup"><span data-stu-id="89461-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="89461-117">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="89461-117">**Performance.**</span></span> <span data-ttu-id="89461-118">The `Decimal` data type is the slowest of all the numeric types.</span><span class="sxs-lookup"><span data-stu-id="89461-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="89461-119">You should weigh the importance of precision against performance before choosing a data type.</span><span class="sxs-lookup"><span data-stu-id="89461-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="89461-120">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="89461-120">**Widening.**</span></span> <span data-ttu-id="89461-121">The `Decimal` data type widens to `Single` or `Double`.</span><span class="sxs-lookup"><span data-stu-id="89461-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="89461-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="89461-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="89461-123">**Trailing Zeros.**</span><span class="sxs-lookup"><span data-stu-id="89461-123">**Trailing Zeros.**</span></span> <span data-ttu-id="89461-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span><span class="sxs-lookup"><span data-stu-id="89461-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="89461-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span><span class="sxs-lookup"><span data-stu-id="89461-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="89461-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="89461-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="89461-127">The output of `MsgBox` in the preceding example is as follows:</span><span class="sxs-lookup"><span data-stu-id="89461-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="89461-128">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="89461-128">**Type Characters.**</span></span> <span data-ttu-id="89461-129">あるリテラルにリテラルの型文字 `D` を付けると、そのリテラルは `Decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="89461-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="89461-130">ある識別子に識別子の型文字 `@` を付けると、その識別子は整数型 (`Decimal`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="89461-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="89461-131">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="89461-131">**Framework Type.**</span></span> <span data-ttu-id="89461-132">.NET Framework において対応する型は、<xref:System.Decimal?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="89461-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="89461-133">範囲</span><span class="sxs-lookup"><span data-stu-id="89461-133">Range</span></span>

 <span data-ttu-id="89461-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span><span class="sxs-lookup"><span data-stu-id="89461-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="89461-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span><span class="sxs-lookup"><span data-stu-id="89461-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="89461-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span><span class="sxs-lookup"><span data-stu-id="89461-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="89461-137">The `Long` value can be assigned to the `Decimal` variable.</span><span class="sxs-lookup"><span data-stu-id="89461-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="89461-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span><span class="sxs-lookup"><span data-stu-id="89461-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="89461-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span><span class="sxs-lookup"><span data-stu-id="89461-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="89461-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span><span class="sxs-lookup"><span data-stu-id="89461-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="89461-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="89461-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="89461-142">データの種類</span><span class="sxs-lookup"><span data-stu-id="89461-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="89461-143">Single データ型</span><span class="sxs-lookup"><span data-stu-id="89461-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="89461-144">Double 型</span><span class="sxs-lookup"><span data-stu-id="89461-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="89461-145">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="89461-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="89461-146">変換の概要</span><span class="sxs-lookup"><span data-stu-id="89461-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="89461-147">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="89461-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
