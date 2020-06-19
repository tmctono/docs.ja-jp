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
ms.openlocfilehash: e9400b50a84522f87a9a2ea4cd05b479d7a4538e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371169"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="0a164-102">/ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a164-102">/ Operator (Visual Basic)</span></span>
<span data-ttu-id="0a164-103">2 つの数値の商を計算し、結果を浮動小数点で返します。</span><span class="sxs-lookup"><span data-stu-id="0a164-103">Divides two numbers and returns a floating-point result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a164-104">構文</span><span class="sxs-lookup"><span data-stu-id="0a164-104">Syntax</span></span>  
  
```vb  
expression1 / expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="0a164-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="0a164-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="0a164-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="0a164-106">Required.</span></span> <span data-ttu-id="0a164-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="0a164-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="0a164-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="0a164-108">Required.</span></span> <span data-ttu-id="0a164-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="0a164-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="0a164-110">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="0a164-110">Supported Types</span></span>  
 <span data-ttu-id="0a164-111">符号なし型、浮動小数点型、`Decimal` を含む、すべての数値型。</span><span class="sxs-lookup"><span data-stu-id="0a164-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="0a164-112">結果</span><span class="sxs-lookup"><span data-stu-id="0a164-112">Result</span></span>  
 <span data-ttu-id="0a164-113">結果は、`expression1` を `expression2` で除算した完全な商で、剰余も含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a164-113">The result is the full quotient of `expression1` divided by `expression2`, including any remainder.</span></span>  
  
 <span data-ttu-id="0a164-114">[\ 演算子 (Visual Basic)](integer-division-operator.md) では整数の商が返され、剰余は捨てられます。</span><span class="sxs-lookup"><span data-stu-id="0a164-114">The [\ Operator (Visual Basic)](integer-division-operator.md) returns the integer quotient, which drops the remainder.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a164-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="0a164-115">Remarks</span></span>  
 <span data-ttu-id="0a164-116">結果のデータ型は、オペランドの型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0a164-116">The data type of the result depends on the types of the operands.</span></span> <span data-ttu-id="0a164-117">次の表は、結果のデータ型がどのように決定されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="0a164-117">The following table shows how the data type of the result is determined.</span></span>  
  
|<span data-ttu-id="0a164-118">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="0a164-118">Operand data types</span></span>|<span data-ttu-id="0a164-119">結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="0a164-119">Result data type</span></span>|  
|------------------------|----------------------|  
|<span data-ttu-id="0a164-120">両方の式が整数データ型 ([SByte](../data-types/sbyte-data-type.md)、[Byte](../data-types/byte-data-type.md)、[Short](../data-types/short-data-type.md)、[UShort](../data-types/ushort-data-type.md)、[Integer](../data-types/integer-data-type.md)、[UInteger](../data-types/uinteger-data-type.md)、[Long](../data-types/long-data-type.md)、[ULong](../data-types/ulong-data-type.md)) である</span><span class="sxs-lookup"><span data-stu-id="0a164-120">Both expressions are integral data types ([SByte](../data-types/sbyte-data-type.md), [Byte](../data-types/byte-data-type.md), [Short](../data-types/short-data-type.md), [UShort](../data-types/ushort-data-type.md), [Integer](../data-types/integer-data-type.md), [UInteger](../data-types/uinteger-data-type.md), [Long](../data-types/long-data-type.md), [ULong](../data-types/ulong-data-type.md))</span></span>|`Double`|  
|<span data-ttu-id="0a164-121">一方の式が [Single](../data-types/single-data-type.md) データ型であり、もう一方が [Double](../data-types/double-data-type.md) でない</span><span class="sxs-lookup"><span data-stu-id="0a164-121">One expression is a [Single](../data-types/single-data-type.md) data type and the other is not a [Double](../data-types/double-data-type.md)</span></span>|`Single`|  
|<span data-ttu-id="0a164-122">一方の式が [Decimal](../data-types/decimal-data-type.md) データ型であり、もう一方が [Single](../data-types/single-data-type.md) でも [Double](../data-types/double-data-type.md) でもない</span><span class="sxs-lookup"><span data-stu-id="0a164-122">One expression is a [Decimal](../data-types/decimal-data-type.md) data type and the other is not a [Single](../data-types/single-data-type.md) or a [Double](../data-types/double-data-type.md)</span></span>|`Decimal`|  
|<span data-ttu-id="0a164-123">どちらか一方の式が [Double](../data-types/double-data-type.md) データ型である</span><span class="sxs-lookup"><span data-stu-id="0a164-123">Either expression is a [Double](../data-types/double-data-type.md) data type</span></span>|`Double`|  
  
 <span data-ttu-id="0a164-124">除算を実行する前に、整数の数値式はすべて `Double` に拡大変換されます。</span><span class="sxs-lookup"><span data-stu-id="0a164-124">Before division is performed, any integral numeric expressions are widened to `Double`.</span></span> <span data-ttu-id="0a164-125">結果を整数データ型に代入すると、結果は、Visual Basic により `Double` からその型への変換が試行されます。</span><span class="sxs-lookup"><span data-stu-id="0a164-125">If you assign the result to an integral data type, Visual Basic attempts to convert the result from `Double` to that type.</span></span> <span data-ttu-id="0a164-126">結果がその型に合わない場合、例外がスローされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a164-126">This can throw an exception if the result does not fit in that type.</span></span> <span data-ttu-id="0a164-127">特に、このヘルプ ページの「0 除算が試行された場合」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a164-127">In particular, see "Attempted Division by Zero" on this Help page.</span></span>  
  
 <span data-ttu-id="0a164-128">`expression1` または `expression2` が [Nothing](../nothing.md) に評価される場合、0 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="0a164-128">If `expression1` or `expression2` evaluates to [Nothing](../nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="0a164-129">0 除算が試行された場合</span><span class="sxs-lookup"><span data-stu-id="0a164-129">Attempted Division by Zero</span></span>  
 <span data-ttu-id="0a164-130">`expression2` が 0 に評価される場合、`/` 演算子の動作は、オペランドのデータ型によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0a164-130">If `expression2` evaluates to zero, the `/` operator behaves differently for different operand data types.</span></span> <span data-ttu-id="0a164-131">次の表に、起こりうる動作を示します。</span><span class="sxs-lookup"><span data-stu-id="0a164-131">The following table shows the possible behaviors.</span></span>  
  
|<span data-ttu-id="0a164-132">オペランドのデータ型</span><span class="sxs-lookup"><span data-stu-id="0a164-132">Operand data types</span></span>|<span data-ttu-id="0a164-133">`expression2` が 0 の場合の動作</span><span class="sxs-lookup"><span data-stu-id="0a164-133">Behavior if `expression2` is zero</span></span>|  
|------------------------|---------------------------------------|  
|<span data-ttu-id="0a164-134">浮動小数点 (`Single` または `Double`)</span><span class="sxs-lookup"><span data-stu-id="0a164-134">Floating-point (`Single` or `Double`)</span></span>|<span data-ttu-id="0a164-135">無限大 (<xref:System.Double.PositiveInfinity> または <xref:System.Double.NegativeInfinity>) を返し、`expression1` も 0 の場合は <xref:System.Double.NaN> (数値ではない) を返す</span><span class="sxs-lookup"><span data-stu-id="0a164-135">Returns infinity (<xref:System.Double.PositiveInfinity> or <xref:System.Double.NegativeInfinity>), or <xref:System.Double.NaN> (not a number) if `expression1` is also zero</span></span>|  
|`Decimal`|<span data-ttu-id="0a164-136"><xref:System.DivideByZeroException> をスローする</span><span class="sxs-lookup"><span data-stu-id="0a164-136">Throws <xref:System.DivideByZeroException></span></span>|  
|<span data-ttu-id="0a164-137">整数 (符号付きまたは符号なし)</span><span class="sxs-lookup"><span data-stu-id="0a164-137">Integral (signed or unsigned)</span></span>|<span data-ttu-id="0a164-138">整数型への変換を試行すると、整数型は <xref:System.Double.PositiveInfinity>、<xref:System.Double.NegativeInfinity>、または <xref:System.Double.NaN> を受け入れることができないため、<xref:System.OverflowException> をスローする</span><span class="sxs-lookup"><span data-stu-id="0a164-138">Attempted conversion back to integral type throws <xref:System.OverflowException> because integral types cannot accept <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity>, or <xref:System.Double.NaN></span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0a164-139">`/` 演算子は "*オーバーロード*" できます。つまり、オペランドの型がクラスまたは構造体であるとき、そのクラスまたは構造体で、演算子の動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="0a164-139">The `/` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0a164-140">コードで、そのようなクラスまたは構造体に対してこの演算子が使用される場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a164-140">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0a164-141">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a164-141">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a164-142">例</span><span class="sxs-lookup"><span data-stu-id="0a164-142">Example</span></span>  
 <span data-ttu-id="0a164-143">次の例では、`/` 演算子を使用して、浮動小数点除算を実行します。</span><span class="sxs-lookup"><span data-stu-id="0a164-143">This example uses the `/` operator to perform floating-point division.</span></span> <span data-ttu-id="0a164-144">結果は 2 つのオペランドの商になります。</span><span class="sxs-lookup"><span data-stu-id="0a164-144">The result is the quotient of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#16)]  
  
 <span data-ttu-id="0a164-145">この例の式では、2.5 と 3.333333 の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="0a164-145">The expressions in the preceding example return values of 2.5 and 3.333333.</span></span> <span data-ttu-id="0a164-146">両方のオペランドが整数定数でも、結果は常に浮動小数点 (`Double`) になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0a164-146">Note that the result is always floating-point (`Double`), even though both operands are integer constants.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a164-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a164-147">See also</span></span>

- [<span data-ttu-id="0a164-148">/= 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a164-148">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="0a164-149">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a164-149">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="0a164-150">演算子の結果のデータ型</span><span class="sxs-lookup"><span data-stu-id="0a164-150">Data Types of Operator Results</span></span>](data-types-of-operator-results.md)
- [<span data-ttu-id="0a164-151">算術演算子</span><span class="sxs-lookup"><span data-stu-id="0a164-151">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="0a164-152">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="0a164-152">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="0a164-153">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="0a164-153">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="0a164-154">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="0a164-154">Arithmetic Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
