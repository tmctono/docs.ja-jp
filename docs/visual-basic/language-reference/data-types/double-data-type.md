---
title: 倍精度浮動小数点数型 (Double) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 92adb26702d94dee08e51decd845d019c797e195
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630099"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="8c746-102">倍精度浮動小数点数型 (Double) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c746-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="8c746-103">負の値に対して-1.79769313486231570 E + 308 から-4.94065645841246544 E-324 までの値を範囲とする、符号付き IEEE 64 ビット (8 バイト) の倍精度浮動小数点数を保持します。 4.94065645841246544 E-324 から 1.79769313486231570 E + 308 まで正の値。</span><span class="sxs-lookup"><span data-stu-id="8c746-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="8c746-104">倍精度数値は、実数の概数を格納します。</span><span class="sxs-lookup"><span data-stu-id="8c746-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c746-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="8c746-105">Remarks</span></span>

<span data-ttu-id="8c746-106">データ`Double`型は、数値に使用できる最大の大きくなりを提供します。</span><span class="sxs-lookup"><span data-stu-id="8c746-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="8c746-107">`Double` の既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="8c746-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="8c746-108">プログラミングのヒント</span><span class="sxs-lookup"><span data-stu-id="8c746-108">Programming Tips</span></span>

- <span data-ttu-id="8c746-109">**精度.**</span><span class="sxs-lookup"><span data-stu-id="8c746-109">**Precision.**</span></span> <span data-ttu-id="8c746-110">浮動小数点数を使用する場合は、メモリ内に常に正確な表現がないという点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="8c746-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="8c746-111">これにより、値の比較や`Mod`演算子など、特定の操作によって予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8c746-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="8c746-112">詳細については、「[データ型のトラブルシューティング](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c746-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="8c746-113">**後続のゼロ。**</span><span class="sxs-lookup"><span data-stu-id="8c746-113">**Trailing Zeros.**</span></span> <span data-ttu-id="8c746-114">浮動小数点データ型には、後続のゼロ文字の内部表現がありません。</span><span class="sxs-lookup"><span data-stu-id="8c746-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="8c746-115">たとえば、4.2000 と4.2 を区別しません。</span><span class="sxs-lookup"><span data-stu-id="8c746-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="8c746-116">そのため、浮動小数点値を表示または印刷するときに、後続のゼロ文字は表示されません。</span><span class="sxs-lookup"><span data-stu-id="8c746-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="8c746-117">**文字を入力します。**</span><span class="sxs-lookup"><span data-stu-id="8c746-117">**Type Characters.**</span></span> <span data-ttu-id="8c746-118">あるリテラルにリテラルの型文字 `R` を付けると、そのリテラルは `Double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8c746-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="8c746-119">たとえば、整数値の後に`R`を指定した場合、値はに変更`Double`されます。</span><span class="sxs-lookup"><span data-stu-id="8c746-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="8c746-120">ある識別子に識別子の型文字 `#` を付けると、その識別子は整数型 (`Double`) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="8c746-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="8c746-121">次の例では、変数`num`は`Double`として型指定されています。</span><span class="sxs-lookup"><span data-stu-id="8c746-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="8c746-122">**フレームワークの種類。**</span><span class="sxs-lookup"><span data-stu-id="8c746-122">**Framework Type.**</span></span> <span data-ttu-id="8c746-123">.NET Framework において対応する型は、<xref:System.Double?displayProperty=nameWithType> 構造体です。</span><span class="sxs-lookup"><span data-stu-id="8c746-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c746-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c746-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="8c746-125">データの種類</span><span class="sxs-lookup"><span data-stu-id="8c746-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8c746-126">Decimal データ型</span><span class="sxs-lookup"><span data-stu-id="8c746-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="8c746-127">Single データ型</span><span class="sxs-lookup"><span data-stu-id="8c746-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="8c746-128">データ型変換関数</span><span class="sxs-lookup"><span data-stu-id="8c746-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8c746-129">変換の概要</span><span class="sxs-lookup"><span data-stu-id="8c746-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8c746-130">データ型の有効な使用方法</span><span class="sxs-lookup"><span data-stu-id="8c746-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="8c746-131">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="8c746-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="8c746-132">型文字</span><span class="sxs-lookup"><span data-stu-id="8c746-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
