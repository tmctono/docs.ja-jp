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
ms.openlocfilehash: 4d530a8c1f85d2f0045184c05df63849047a8204
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971770"
---
# <a name="decimal-data-type-visual-basic"></a><span data-ttu-id="bfb3b-102">10 進型 (Decimal) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfb3b-102">Decimal Data Type (Visual Basic)</span></span>
<span data-ttu-id="bfb3b-103">符号付き 10 の累乗によってスケーリング 96 ビット (12 バイト) の整数値を表す 128 ビット (16 バイト) 値を保持します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-103">Holds signed 128-bit (16-byte) values representing 96-bit (12-byte) integer numbers scaled by a variable power of 10.</span></span> <span data-ttu-id="bfb3b-104">スケール ファクターは小数点の右側にある数字の数を指定します。その範囲は 0 から 28 です。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-104">The scaling factor specifies the number of digits to the right of the decimal point; it ranges from 0 through 28.</span></span> <span data-ttu-id="bfb3b-105">最大有効値は 0 (数値) の小数点以下桁数、79,228,162,514,264,337,593,543,950,335 +/-(7 +/-.9228162514264337593543950335E + 28)。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-105">With a scale of 0 (no decimal places), the largest possible value is +/-79,228,162,514,264,337,593,543,950,335 (+/-7.9228162514264337593543950335E+28).</span></span> <span data-ttu-id="bfb3b-106">小数点以下桁数が 28 7.9228162514264337593543950335 については、最大値は、および 0 以外の最小値は、(1 e ~ 28) +/-+/-0.0000000000000000000000000001。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-106">With 28 decimal places, the largest value is +/-7.9228162514264337593543950335, and the smallest nonzero value is +/-0.0000000000000000000000000001 (+/-1E-28).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfb3b-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bfb3b-107">Remarks</span></span>  
 <span data-ttu-id="bfb3b-108">`Decimal`データ型有効桁数の最大数を提供しています。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-108">The `Decimal` data type provides the greatest number of significant digits for a number.</span></span> <span data-ttu-id="bfb3b-109">最大 29 桁をサポートし、7.9228 x 10 を超える値を表すことができます ^28。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-109">It supports up to 29 significant digits and can represent values in excess of 7.9228 x 10^28.</span></span> <span data-ttu-id="bfb3b-110">など、計算に特に適しています金融機関、多くの桁数が必要ですが、丸めエラーを許容することはできません。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-110">It is particularly suitable for calculations, such as financial, that require a large number of digits but cannot tolerate rounding errors.</span></span>  
  
 <span data-ttu-id="bfb3b-111">`Decimal` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-111">The default value of `Decimal` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="bfb3b-112">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="bfb3b-112">Programming Tips</span></span>  
  
- <span data-ttu-id="bfb3b-113">**有効桁数です。**</span><span class="sxs-lookup"><span data-stu-id="bfb3b-113">**Precision.**</span></span> <span data-ttu-id="bfb3b-114">`Decimal` 浮動小数点データ型はありません。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-114">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="bfb3b-115">`Decimal`構造体は、符号ビットとスケール ファクターがどの程度の値が 10 進数の割合を指定する整数値のバイナリ整数値を保持します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-115">The `Decimal` structure holds a binary integer value, together with a sign bit and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span> <span data-ttu-id="bfb3b-116">このため、`Decimal`番号は、浮動小数点型よりもメモリ内でより正確な表現を持ち (`Single`と`Double`)。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-116">Because of this, `Decimal` numbers have a more precise representation in memory than floating-point types (`Single` and `Double`).</span></span>  
  
- <span data-ttu-id="bfb3b-117">**パフォーマンス。**</span><span class="sxs-lookup"><span data-stu-id="bfb3b-117">**Performance.**</span></span> <span data-ttu-id="bfb3b-118">`Decimal`データ型はすべての数値型の最も遅い。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-118">The `Decimal` data type is the slowest of all the numeric types.</span></span> <span data-ttu-id="bfb3b-119">データ型を選択する前にパフォーマンスと精度の重要性を比較検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-119">You should weigh the importance of precision against performance before choosing a data type.</span></span>  
  
- <span data-ttu-id="bfb3b-120">**拡大します。**</span><span class="sxs-lookup"><span data-stu-id="bfb3b-120">**Widening.**</span></span> <span data-ttu-id="bfb3b-121">`Decimal`拡大変換後のデータ型`Single`または`Double`します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-121">The `Decimal` data type widens to `Single` or `Double`.</span></span> <span data-ttu-id="bfb3b-122">つまり、変換できる`Decimal`遭遇することがなくこれらの型のいずれかに、<xref:System.OverflowException?displayProperty=nameWithType>エラー。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-122">This means you can convert `Decimal` to either of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="bfb3b-123">**後続のゼロ。**</span><span class="sxs-lookup"><span data-stu-id="bfb3b-123">**Trailing Zeros.**</span></span> <span data-ttu-id="bfb3b-124">Visual Basic では後続の 0 を格納しません、`Decimal`リテラル。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-124">Visual Basic does not store trailing zeros in a `Decimal` literal.</span></span> <span data-ttu-id="bfb3b-125">ただし、`Decimal`変数には、計算に必要なすべての後続のゼロが保持されます。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-125">However, a `Decimal` variable preserves any trailing zeros acquired computationally.</span></span> <span data-ttu-id="bfb3b-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-126">The following example illustrates this.</span></span>  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     <span data-ttu-id="bfb3b-127">出力`MsgBox`前の例では、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-127">The output of `MsgBox` in the preceding example is as follows:</span></span>  
  
     <span data-ttu-id="bfb3b-128">d1 2.375、d2 の = = 1.625、d3 4.000、d4 を = = 4</span><span class="sxs-lookup"><span data-stu-id="bfb3b-128">d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4</span></span>  
  
- <span data-ttu-id="bfb3b-129">**型宣言文字。**</span><span class="sxs-lookup"><span data-stu-id="bfb3b-129">**Type Characters.**</span></span> <span data-ttu-id="bfb3b-130">あるリテラルにリテラルの型文字 `D` を付けると、そのリテラルは `Decimal` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-130">Appending the literal type character `D` to a literal forces it to the `Decimal` data type.</span></span> <span data-ttu-id="bfb3b-131">ある識別子に識別子の型文字 `@` を付けると、その識別子は整数型 (`Decimal`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-131">Appending the identifier type character `@` to any identifier forces it to `Decimal`.</span></span>  
  
- <span data-ttu-id="bfb3b-132">**フレームワークの型。**</span><span class="sxs-lookup"><span data-stu-id="bfb3b-132">**Framework Type.**</span></span> <span data-ttu-id="bfb3b-133">.NET Framework において対応する型は、<xref:System.Decimal?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-133">The corresponding type in the .NET Framework is the <xref:System.Decimal?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="range"></a><span data-ttu-id="bfb3b-134">範囲</span><span class="sxs-lookup"><span data-stu-id="bfb3b-134">Range</span></span>  
 <span data-ttu-id="bfb3b-135">使用する必要があります、`D`文字入力すると大きな値を割り当てる、`Decimal`変数または定数。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-135">You might need to use the `D` type character to assign a large value to a `Decimal` variable or constant.</span></span> <span data-ttu-id="bfb3b-136">この要件は、コンパイラがリテラルとして解釈されるので`Long`しない限り、リテラルの型文字以下、リテラルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-136">This requirement is because the compiler interprets a literal as `Long` unless a literal type character follows the literal, as the following example shows.</span></span>  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 <span data-ttu-id="bfb3b-137">宣言`bigDec1`に割り当てられている値の範囲内に収まるために、オーバーフローを生成しない`Long`します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-137">The declaration for `bigDec1` doesn't produce an overflow because the value that's assigned to it falls within the range for `Long`.</span></span> <span data-ttu-id="bfb3b-138">`Long`に値を割り当てることができます、`Decimal`変数。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-138">The `Long` value can be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="bfb3b-139">宣言`bigDec2`用に割り当てられている値が大きすぎるために、オーバーフロー エラーが発生`Long`します。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-139">The declaration for `bigDec2` generates an overflow error because the value that's assigned to it is too large for `Long`.</span></span> <span data-ttu-id="bfb3b-140">数値リテラルとしてまず解釈できないため、`Long`に割り当てることができない、`Decimal`変数。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-140">Because the numeric literal can't first be interpreted as a `Long`, it can't be assigned to the `Decimal` variable.</span></span>  
  
 <span data-ttu-id="bfb3b-141">`bigDec3`、リテラルの型文字`D`としてリテラルを解釈するコンパイラを強制することで、問題を解決する`Decimal`の代わりとして、 `Long`。</span><span class="sxs-lookup"><span data-stu-id="bfb3b-141">For `bigDec3`, the literal type character `D` solves the problem by forcing the compiler to interpret the literal as a `Decimal` instead of as a `Long`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfb3b-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="bfb3b-142">See also</span></span>

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bfb3b-143">データの種類</span><span class="sxs-lookup"><span data-stu-id="bfb3b-143">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="bfb3b-144">Single データ型</span><span class="sxs-lookup"><span data-stu-id="bfb3b-144">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="bfb3b-145">Double 型</span><span class="sxs-lookup"><span data-stu-id="bfb3b-145">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="bfb3b-146">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="bfb3b-146">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="bfb3b-147">変換の概要</span><span class="sxs-lookup"><span data-stu-id="bfb3b-147">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="bfb3b-148">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="bfb3b-148">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
