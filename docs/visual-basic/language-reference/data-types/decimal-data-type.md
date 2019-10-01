---
title: 10 進型 (Decimal) (Visual Basic)
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
ms.openlocfilehash: 892824b61cfb6a0172361d220c638cab0a78565d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700874"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="aa659-102">10 進型 (Decimal) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa659-102">Decimal Data Type (Visual Basic)</span></span>

<span data-ttu-id="aa659-103">10の可変指数でスケーリングされた96ビット (12 バイト) の整数値を表す、符号付き128ビット (16 バイト) の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="aa659-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="aa659-104">スケールファクターは、小数点の右側の桁数を指定します。0から28までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="aa659-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="aa659-105">小数点以下桁数が 0 (小数点以下桁数) の場合、有効な最大値は +/-79228162514264337593543950335 (+/-7.9228162514264337593543950335E + 28) です。</span><span class="sxs-lookup"><span data-stu-id="aa659-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="aa659-106">小数点以下を28桁にすると、最大値は +/-7.9228162514264337593543950335、0以外の最小値は +/-0.0000000000000000000000000001 (+/-1E-28) になります。</span><span class="sxs-lookup"><span data-stu-id="aa659-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>

## <a name="remarks"></a><span data-ttu-id="aa659-107">コメント</span><span class="sxs-lookup"><span data-stu-id="aa659-107">Remarks</span></span>

<span data-ttu-id="aa659-108">@No__t-0 データ型は、数値の最大有効桁数を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa659-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="aa659-109">最大29桁の有効桁数をサポートし、7.9228 x 10 ^ 28 を超える値を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="aa659-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="aa659-110">これは、多くの数字を必要とするが丸め誤差を許容できない財務などの計算に特に適しています。</span><span class="sxs-lookup"><span data-stu-id="aa659-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>

<span data-ttu-id="aa659-111">`Decimal` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="aa659-111">The default value of `Decimal` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="aa659-112">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="aa659-112">Programming Tips</span></span>

- <span data-ttu-id="aa659-113">**精度.**</span><span class="sxs-lookup"><span data-stu-id="aa659-113">**Precision.**</span></span> <span data-ttu-id="aa659-114">`Decimal` は浮動小数点データ型ではありません。</span><span class="sxs-lookup"><span data-stu-id="aa659-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="aa659-115">@No__t 0 構造体は、2進数の整数値を保持します。符号ビットと、値のどの部分が小数点であるかを指定する整数の拡大率です。</span><span class="sxs-lookup"><span data-stu-id="aa659-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="aa659-116">このため、@no__t 0 の数値は、浮動小数点型 (`Single` と `Double`) よりもメモリ内でより正確に表現されます。</span><span class="sxs-lookup"><span data-stu-id="aa659-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>

- <span data-ttu-id="aa659-117">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="aa659-117">**Performance.**</span></span> <span data-ttu-id="aa659-118">@No__t 0 のデータ型は、すべての数値型の中で最も低速なデータ型です。</span><span class="sxs-lookup"><span data-stu-id="aa659-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="aa659-119">データ型を選択する前に、精度の重要性をパフォーマンスと比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa659-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>

- <span data-ttu-id="aa659-120">**広げ.**</span><span class="sxs-lookup"><span data-stu-id="aa659-120">**Widening.**</span></span> <span data-ttu-id="aa659-121">@No__t 0 のデータ型は、`Single` または `Double` に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="aa659-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="aa659-122">つまり、<xref:System.OverflowException?displayProperty=nameWithType> のエラーが発生することなく、`Decimal` をこれらの型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="aa659-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="aa659-123">**後続のゼロ。**</span><span class="sxs-lookup"><span data-stu-id="aa659-123">**Trailing Zeros.**</span></span> <span data-ttu-id="aa659-124">Visual Basic は、末尾の0を @no__t 0 リテラルに格納しません。</span><span class="sxs-lookup"><span data-stu-id="aa659-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="aa659-125">ただし、@no__t 0 の変数は、計算を取得した後続のゼロを保持します。</span><span class="sxs-lookup"><span data-stu-id="aa659-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="aa659-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="aa659-126">The following example illustrates this.</span></span>

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  <span data-ttu-id="aa659-127">前の例の `MsgBox` の出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="aa659-127">The output of `MsgBox` in the preceding example is as follows:</span></span>

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- <span data-ttu-id="aa659-128">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="aa659-128">**Type Characters.**</span></span> <span data-ttu-id="aa659-129">あるリテラルにリテラルの型文字 `D` を付けると、そのリテラルは `Decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="aa659-129">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="aa659-130">ある識別子に識別子の型文字 `@` を付けると、その識別子は整数型 (`Decimal`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="aa659-130">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>

- <span data-ttu-id="aa659-131">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="aa659-131">**Framework Type.**</span></span> <span data-ttu-id="aa659-132">.NET Framework において対応する型は、<xref:System.Decimal?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="aa659-132">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>

## <a name="range"></a><span data-ttu-id="aa659-133">範囲</span><span class="sxs-lookup"><span data-stu-id="aa659-133">Range</span></span>
 <span data-ttu-id="aa659-134">@No__t-1 の変数または定数に大きな値を割り当てるには、@no__t 0 の型文字を使用することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa659-134">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="aa659-135">この要件は、次の例に示すように、リテラルの型文字がリテラルの後に続く場合を除き、コンパイラがリテラルを @no__t 0 として解釈するためです。</span><span class="sxs-lookup"><span data-stu-id="aa659-135">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

<span data-ttu-id="aa659-136">割り当てられた値が @no__t の範囲内にあるため、`bigDec1` の宣言はオーバーフローを生成しません。</span><span class="sxs-lookup"><span data-stu-id="aa659-136">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="aa659-137">@No__t-0 の値は、`Decimal` 変数に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="aa659-137">The `Long` value can be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="aa659-138">@No__t-0 の宣言では、割り当てられた値が `Long` に対して大きすぎるため、オーバーフローエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="aa659-138">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="aa659-139">数値リテラルは最初に @no__t 0 として解釈できないため、`Decimal` 変数に割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="aa659-139">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>

<span data-ttu-id="aa659-140">@No__t 0 の場合、リテラルの型文字 `D` は、コンパイラがリテラルを `Long` ではなく @no__t 2 として解釈するよう強制することによって問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="aa659-140">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa659-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa659-141">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="aa659-142">データの種類</span><span class="sxs-lookup"><span data-stu-id="aa659-142">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="aa659-143">Single データ型</span><span class="sxs-lookup"><span data-stu-id="aa659-143">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="aa659-144">Double 型</span><span class="sxs-lookup"><span data-stu-id="aa659-144">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="aa659-145">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="aa659-145">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="aa659-146">変換の概要</span><span class="sxs-lookup"><span data-stu-id="aa659-146">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="aa659-147">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="aa659-147">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
