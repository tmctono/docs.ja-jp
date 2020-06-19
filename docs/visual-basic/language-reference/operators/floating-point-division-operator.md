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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331056"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="7444d-102">/ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7444d-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="7444d-103">2 つの数値の商を計算し、結果を浮動小数点で返します。</span><span class="sxs-lookup"><span data-stu-id="7444d-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7444d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7444d-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="7444d-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7444d-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="7444d-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="7444d-106">Required.</span></span> <span data-ttu-id="7444d-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="7444d-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="7444d-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="7444d-108">Required.</span></span> <span data-ttu-id="7444d-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="7444d-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7444d-110">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="7444d-110">Supported Types</span></span>  
 <span data-ttu-id="7444d-111">符号なし型、浮動小数点型、`Decimal` を含む、すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="7444d-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="7444d-112">結果</span><span class="sxs-lookup"><span data-stu-id="7444d-112">Result</span></span>  
 <span data-ttu-id="7444d-113">結果は、`expression1` を `expression2` で除算した完全な商で、剰余も含まれます。</span><span class="sxs-lookup"><span data-stu-id="7444d-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="7444d-114">[\ 演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) では整数の商が返され、剰余は捨てられます。</span><span class="sxs-lookup"><span data-stu-id="7444d-114">The [\ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7444d-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="7444d-115">Remarks</span></span>  
 <span data-ttu-id="7444d-116">結果のデータ型は、オペランドの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7444d-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="7444d-117">次の表は、結果のデータ型がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="7444d-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="7444d-118">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="7444d-118">Operand data types</span></span>|<span data-ttu-id="7444d-119">結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="7444d-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="7444d-120">両方の式が整数データ型 ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)、[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)、[Short](../../../visual-basic/language-reference/data-types/short-data-type.md)、[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)、[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)、[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)、[Long](../../../visual-basic/language-reference/data-types/long-data-type.md)、[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)) である</span><span class="sxs-lookup"><span data-stu-id="7444d-120">Both expressions are integral data types ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="7444d-121">一方の式が [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) データ型であり、もう一方が [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) でない</span><span class="sxs-lookup"><span data-stu-id="7444d-121">One expression is a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) data type and the other is not a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="7444d-122">一方の式が [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) データ型であり、もう一方が [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) でも [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) でもない</span><span class="sxs-lookup"><span data-stu-id="7444d-122">One expression is a [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) data type and the other is not a [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) or a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="7444d-123">どちらか一方の式が [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) データ型である</span><span class="sxs-lookup"><span data-stu-id="7444d-123">Either expression is a [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="7444d-124">除算を実行する前に、整数の数値式はすべて `Double` に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="7444d-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="7444d-125">結果を整数データ型に代入すると、結果は、Visual Basic により `Double` からその型への変換が試行されます。</span><span class="sxs-lookup"><span data-stu-id="7444d-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="7444d-126">結果がその型に合わない場合、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7444d-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="7444d-127">特に、このヘルプ ページの「0 除算が試行された場合」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7444d-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="7444d-128">`expression1` または `expression2` が [Nothing](../../../visual-basic/language-reference/nothing.md) に評価される場合、0 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="7444d-128">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="7444d-129">0 除算が試行された場合</span><span class="sxs-lookup"><span data-stu-id="7444d-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="7444d-130">`expression2` が 0 に評価される場合、`/` 演算子の動作は、オペランドのデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="7444d-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="7444d-131">次の表に、起こりうる動作を示します。</span><span class="sxs-lookup"><span data-stu-id="7444d-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="7444d-132">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="7444d-132">Operand data types</span></span>|<span data-ttu-id="7444d-133">`expression2` が 0 の場合の動作</span><span class="sxs-lookup"><span data-stu-id="7444d-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="7444d-134">浮動小数点 (`Single` または `Double`)</span><span class="sxs-lookup"><span data-stu-id="7444d-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="7444d-135">無限大 (<xref:System.Double.PositiveInfinity> または <xref:System.Double.NegativeInfinity>) を返し、`expression1` も 0 の場合は <xref:System.Double.NaN> (数値ではない) を返す</span><span class="sxs-lookup"><span data-stu-id="7444d-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="7444d-136"><xref:System.DivideByZeroException> をスローする</span><span class="sxs-lookup"><span data-stu-id="7444d-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="7444d-137">整数 (符号付きまたは符号なし)</span><span class="sxs-lookup"><span data-stu-id="7444d-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="7444d-138">整数型への変換を試行すると、整数型は <xref:System.Double.PositiveInfinity>、<xref:System.Double.NegativeInfinity>、または <xref:System.Double.NaN> を受け入れることができないため、<xref:System.OverflowException> をスローする</span><span class="sxs-lookup"><span data-stu-id="7444d-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7444d-139">`/` 演算子は "*オーバーロード*" できます。つまり、オペランドの型がクラスまたは構造体であるとき、そのクラスまたは構造体で、演算子の動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="7444d-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="7444d-140">コード内で、そのようなクラスまたは構造体でこの演算子を使用する場合は、再定義する動作を必ず理解してください。</span><span class="sxs-lookup"><span data-stu-id="7444d-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7444d-141">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7444d-141">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7444d-142">例</span><span class="sxs-lookup"><span data-stu-id="7444d-142">Example</span></span>  
 <span data-ttu-id="7444d-143">次の例では、`/` 演算子を使用して、浮動小数点除算を実行します。</span><span class="sxs-lookup"><span data-stu-id="7444d-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="7444d-144">結果は 2 つのオペランドの商になります。</span><span class="sxs-lookup"><span data-stu-id="7444d-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="7444d-145">この例の式では、2.5 と 3.333333 の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="7444d-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="7444d-146">両方のオペランドが整数定数でも、結果は常に浮動小数点 (`Double`) になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7444d-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7444d-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="7444d-147">See also</span></span>

- [<span data-ttu-id="7444d-148">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7444d-148">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [<span data-ttu-id="7444d-149">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7444d-149">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [<span data-ttu-id="7444d-150">演算子の結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="7444d-150">Data Types of Operator Results</span></span>](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)
- [<span data-ttu-id="7444d-151">算術演算子</span><span class="sxs-lookup"><span data-stu-id="7444d-151">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="7444d-152">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="7444d-152">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="7444d-153">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="7444d-153">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="7444d-154">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="7444d-154">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
