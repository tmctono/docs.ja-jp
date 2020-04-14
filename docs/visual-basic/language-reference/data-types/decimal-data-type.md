---
title: Decimal データ型
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
ms.openlocfilehash: d4d868ba7c05cf3c2d538de1217231df91d4f43d
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243324"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="5b860-102">10 進型 (Decimal) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b860-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="5b860-103">可変 10 の累乗によってスケーリングされた 96 ビット (12 バイト) 整数値を表す符号付き 128 ビット (16 バイト) 値を保持します。</span><span class="sxs-lookup"><span data-stu-id="5b860-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="5b860-104">スケール ファクターは、小数点の右側の桁数を指定します。0 から 28 までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="5b860-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="5b860-105">0 (小数点以下の桁数なし) の場合、最大の値は +/-79,228,162,514,264,337,593,543,950,335 (+/-7.92816251422643375935335335E+28) です。</span><span class="sxs-lookup"><span data-stu-id="5b860-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="5b860-106">小数点以下 28 桁の最大値は +/-7.92281625142643375935439393955555555530335 で、ゼロ以外の最小値は +/-0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000</span><span class="sxs-lookup"><span data-stu-id="5b860-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="5b860-107">解説</span><span class="sxs-lookup"><span data-stu-id="5b860-107">Remarks</span></span>

<span data-ttu-id="5b860-108">データ`Decimal`型は、数値の有効桁数の最大数を提供します。</span><span class="sxs-lookup"><span data-stu-id="5b860-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="5b860-109">最大 29 桁の有効桁数をサポートし、7.9228 x 10^28 を超える値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="5b860-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="5b860-110">特に、財務計算など、桁数が多く必要な場合でも、丸め誤差を許容できない計算に適しています。</span><span class="sxs-lookup"><span data-stu-id="5b860-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="5b860-111">`Decimal` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="5b860-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="5b860-112">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="5b860-112">Programming Tips</span></span>

- <span data-ttu-id="5b860-113">**精度。**</span><span class="sxs-lookup"><span data-stu-id="5b860-113">**Precision.**</span></span> <span data-ttu-id="5b860-114">`Decimal`は浮動小数点データ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="5b860-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="5b860-115">この`Decimal`構造体には、2 進整数値と、符号ビットと、値のどの部分が小数であるかを指定する整数のスケーリング係数が格納されます。</span><span class="sxs-lookup"><span data-stu-id="5b860-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="5b860-116">このため、`Decimal`数値は浮動小数点型 ( および`Single``Double`) よりも正確なメモリ表現を持ちます。</span><span class="sxs-lookup"><span data-stu-id="5b860-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="5b860-117">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="5b860-117">**Performance.**</span></span> <span data-ttu-id="5b860-118">データ`Decimal`型は、すべての数値型の中で最も低速です。</span><span class="sxs-lookup"><span data-stu-id="5b860-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="5b860-119">データ型を選択する前に、精度の重要性とパフォーマンスの比較を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b860-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="5b860-120">**拡大。**</span><span class="sxs-lookup"><span data-stu-id="5b860-120">**Widening.**</span></span> <span data-ttu-id="5b860-121">データ`Decimal`型が、 または`Single``Double`に拡大されます。</span><span class="sxs-lookup"><span data-stu-id="5b860-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="5b860-122">つまり、<xref:System.OverflowException?displayProperty=nameWithType>エラーが発生`Decimal`することなく、これらの型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="5b860-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="5b860-123">**末尾のゼロ。**</span><span class="sxs-lookup"><span data-stu-id="5b860-123">**Trailing Zeros.**</span></span> <span data-ttu-id="5b860-124">Visual Basic では、末尾のゼロは`Decimal`リテラルに格納されません。</span><span class="sxs-lookup"><span data-stu-id="5b860-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="5b860-125">ただし、変数`Decimal`は計算上、取得した後続のゼロを保持します。</span><span class="sxs-lookup"><span data-stu-id="5b860-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="5b860-126">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="5b860-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="5b860-127">上記の`MsgBox`例の出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5b860-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="5b860-128">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="5b860-128">**Type Characters.**</span></span> <span data-ttu-id="5b860-129">あるリテラルにリテラルの型文字 `D` を付けると、そのリテラルは `Decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5b860-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="5b860-130">ある識別子に識別子の型文字 `@` を付けると、その識別子は整数型 (`Decimal`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5b860-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="5b860-131">**Framework のデータ型**</span><span class="sxs-lookup"><span data-stu-id="5b860-131">**Framework Type.**</span></span> <span data-ttu-id="5b860-132">.NET Framework において対応する型は、<xref:System.Decimal?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="5b860-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="5b860-133">範囲</span><span class="sxs-lookup"><span data-stu-id="5b860-133">Range</span></span>

 <span data-ttu-id="5b860-134">変数または定数に大きな`D`値を割り当てるには、型`Decimal`文字を使用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b860-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="5b860-135">この要件は、次の例に示すように、`Long`リテラルの型文字がリテラルの後に続く場合を除き、コンパイラがリテラルを解釈するためです。</span><span class="sxs-lookup"><span data-stu-id="5b860-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="5b860-136">に割り`bigDec1`当てられた値が の範囲内にあるため、 の宣言ではオーバーフローが発生しません`Long`。</span><span class="sxs-lookup"><span data-stu-id="5b860-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="5b860-137">値`Long`は変数に`Decimal`割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5b860-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="5b860-138">に割り`bigDec2`当てられた値が大きすぎるため、 の宣言はオーバーフロー エラーを`Long`生成します。</span><span class="sxs-lookup"><span data-stu-id="5b860-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="5b860-139">数値リテラルは、 として`Long`解釈できないため、 変数に`Decimal`代入することはできません。</span><span class="sxs-lookup"><span data-stu-id="5b860-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="5b860-140">リテラル`bigDec3`型文字`D`は、リテラルを の`Decimal`代わりに a として解釈するようにコンパイラに強制することによって、この問題`Long`を解決します。</span><span class="sxs-lookup"><span data-stu-id="5b860-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b860-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="5b860-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5b860-142">データ型</span><span class="sxs-lookup"><span data-stu-id="5b860-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5b860-143">Single データ型</span><span class="sxs-lookup"><span data-stu-id="5b860-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="5b860-144">Double データ型</span><span class="sxs-lookup"><span data-stu-id="5b860-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="5b860-145">CString</span><span class="sxs-lookup"><span data-stu-id="5b860-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5b860-146">変換の概要</span><span class="sxs-lookup"><span data-stu-id="5b860-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5b860-147">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="5b860-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
