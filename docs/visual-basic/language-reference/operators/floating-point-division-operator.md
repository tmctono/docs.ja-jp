---
title: / 演算子
ms.date: 07/20/2015
f1_keywords:
- vb./
helpviewer_keywords:
- division operator [Visual Basic], floating point
- floating-point numbers [Visual Basic], division operator
- slash (/) operator
- zero, division by zero
- operators [Visual Basic], arithmetic
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- operators [Visual Basic], division
- division operator [Visual Basic], syntax
- / operator [Visual Basic]
- math operators [Visual Basic]
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
ms.openlocfilehash: 537d8b0c703b59743f1a7c531448118058707645
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331056"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7242d-102">/ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7242d-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="7242d-103">2つの数値を除算して、浮動小数点の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="7242d-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7242d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7242d-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7242d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7242d-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="7242d-106">必須。</span><span class="sxs-lookup"><span data-stu-id="7242d-106">Required.</span></span> <span data-ttu-id="7242d-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="7242d-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7242d-108">必須。</span><span class="sxs-lookup"><span data-stu-id="7242d-108">Required.</span></span> <span data-ttu-id="7242d-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="7242d-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7242d-110">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="7242d-110">Supported Types</span></span>  
 <span data-ttu-id="7242d-111">符号なしおよび浮動小数点型および `Decimal`を含むすべての数値型。</span><span class="sxs-lookup"><span data-stu-id="7242d-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7242d-112">結果</span><span class="sxs-lookup"><span data-stu-id="7242d-112">Result</span></span>  
 <span data-ttu-id="7242d-113">結果は、剰余を含め、`expression2`で割った `expression1` の完全な商です。</span><span class="sxs-lookup"><span data-stu-id="7242d-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="7242d-114">[\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)は、剰余を削除する整数の商を返します。</span><span class="sxs-lookup"><span data-stu-id="7242d-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7242d-115">コメント</span><span class="sxs-lookup"><span data-stu-id="7242d-115">Remarks</span></span>  
 <span data-ttu-id="7242d-116">結果のデータ型は、オペランドの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7242d-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="7242d-117">次の表は、結果のデータ型がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="7242d-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="7242d-118">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="7242d-118">Operand data types</span></span>|<span data-ttu-id="7242d-119">結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="7242d-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="7242d-120">両方の式は整数データ型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)、 [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)、 [Short](../../../visual-basic/language-reference/data-types/short-data-type.md)、 [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)、 [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)、 [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)、 [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)、 [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)) です。</span><span class="sxs-lookup"><span data-stu-id="7242d-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="7242d-121">1つの式が[1](../../../visual-basic/language-reference/data-types/single-data-type.md)つのデータ型で、もう一方が[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)ではない場合</span><span class="sxs-lookup"><span data-stu-id="7242d-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="7242d-122">一方の式は Decimal データ型で、もう一方は[単](../../../visual-basic/language-reference/data-types/single-data-type.md)[精度浮動](../../../visual-basic/language-reference/data-types/double-data-type.md)[小数点](../../../visual-basic/language-reference/data-types/decimal-data-type.md)型ではありません。</span><span class="sxs-lookup"><span data-stu-id="7242d-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="7242d-123">どちらの式も[Double](../../../visual-basic/language-reference/data-types/double-data-type.md)データ型です。</span><span class="sxs-lookup"><span data-stu-id="7242d-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="7242d-124">除算を実行する前に、整数の数値式はすべて `Double`に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="7242d-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="7242d-125">結果を整数データ型に代入すると、Visual Basic は `Double` の結果をその型に変換しようとします。</span><span class="sxs-lookup"><span data-stu-id="7242d-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="7242d-126">結果がその型に合わない場合、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7242d-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="7242d-127">特に、このヘルプページの「ゼロによる除算」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7242d-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="7242d-128">`expression1` または `expression2` が[Nothing](../../../visual-basic/language-reference/nothing.md)と評価された場合、0として扱われます。</span><span class="sxs-lookup"><span data-stu-id="7242d-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="7242d-129">0による除算を試行しました</span><span class="sxs-lookup"><span data-stu-id="7242d-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="7242d-130">`expression2` が0に評価された場合、オペランドのデータ型によって `/` 演算子の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="7242d-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="7242d-131">次の表に、考えられる動作を示します。</span><span class="sxs-lookup"><span data-stu-id="7242d-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="7242d-132">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="7242d-132">Operand data types</span></span>|<span data-ttu-id="7242d-133">`expression2` が0の場合の動作</span><span class="sxs-lookup"><span data-stu-id="7242d-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="7242d-134">浮動小数点 (`Single` または `Double`)</span><span class="sxs-lookup"><span data-stu-id="7242d-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="7242d-135">無限大 (<xref:System.Double.PositiveInfinity> または <xref:System.Double.NegativeInfinity>)、または `expression1` が0の場合は <xref:System.Double.NaN> (非数) を返します。</span><span class="sxs-lookup"><span data-stu-id="7242d-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="7242d-136">スロー <xref:System.DivideByZeroException></span><span class="sxs-lookup"><span data-stu-id="7242d-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="7242d-137">整数 (符号付きまたは符号なし)</span><span class="sxs-lookup"><span data-stu-id="7242d-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="7242d-138">整数型への変換 <xref:System.Double.NaN> は、<xref:System.Double.PositiveInfinity>、<xref:System.Double.NegativeInfinity>、またはを受け入れることができないため、<xref:System.OverflowException> をスローします</span><span class="sxs-lookup"><span data-stu-id="7242d-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7242d-139">`/` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="7242d-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7242d-140">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7242d-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7242d-141">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7242d-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7242d-142">例</span><span class="sxs-lookup"><span data-stu-id="7242d-142">Example</span></span>  
 <span data-ttu-id="7242d-143">この例では、`/` 演算子を使用して、浮動小数点除算を実行します。</span><span class="sxs-lookup"><span data-stu-id="7242d-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="7242d-144">結果は、2つのオペランドの商になります。</span><span class="sxs-lookup"><span data-stu-id="7242d-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="7242d-145">前の例の式では、2.5 と3.333333 の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="7242d-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="7242d-146">両方のオペランドが整数定数の場合でも、結果は常に浮動小数点 (`Double`) になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7242d-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7242d-147">参照</span><span class="sxs-lookup"><span data-stu-id="7242d-147">See also</span></span>

- [<span data-ttu-id="7242d-148">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7242d-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="7242d-149">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7242d-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="7242d-150">演算子の結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="7242d-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="7242d-151">算術演算子</span><span class="sxs-lookup"><span data-stu-id="7242d-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="7242d-152">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="7242d-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7242d-153">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="7242d-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7242d-154">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="7242d-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
