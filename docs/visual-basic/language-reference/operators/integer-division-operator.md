---
title: '\ 演算子'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 2b4cca99ed54195162530bb8eb950bd251bfbff9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347118"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="aa893-102">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa893-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="aa893-103">2つの数値を除算し、整数の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="aa893-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa893-104">構文</span><span class="sxs-lookup"><span data-stu-id="aa893-104">Syntax</span></span>  
  
```vb  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="aa893-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="aa893-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="aa893-106">必須。</span><span class="sxs-lookup"><span data-stu-id="aa893-106">Required.</span></span> <span data-ttu-id="aa893-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="aa893-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="aa893-108">必須。</span><span class="sxs-lookup"><span data-stu-id="aa893-108">Required.</span></span> <span data-ttu-id="aa893-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="aa893-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="aa893-110">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="aa893-110">Supported Types</span></span>  
 <span data-ttu-id="aa893-111">符号なしおよび浮動小数点型および `Decimal`を含むすべての数値型。</span><span class="sxs-lookup"><span data-stu-id="aa893-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="aa893-112">結果</span><span class="sxs-lookup"><span data-stu-id="aa893-112">Result</span></span>  
 <span data-ttu-id="aa893-113">結果として、`expression1` の商が `expression2`で除算され、余りが破棄され、整数部分のみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="aa893-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="aa893-114">これは*切り捨て*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="aa893-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="aa893-115">結果のデータ型は、`expression1` および `expression2`のデータ型に適した数値型です。</span><span class="sxs-lookup"><span data-stu-id="aa893-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="aa893-116">「[演算子の結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)」の「整数演算」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa893-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="aa893-117">[/演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)は、小数部の剰余を保持する完全な商を返します。</span><span class="sxs-lookup"><span data-stu-id="aa893-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa893-118">コメント</span><span class="sxs-lookup"><span data-stu-id="aa893-118">Remarks</span></span>  
 <span data-ttu-id="aa893-119">除算を実行する前に、Visual Basic 浮動小数点数値式を `Long`に変換しようとしています。</span><span class="sxs-lookup"><span data-stu-id="aa893-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="aa893-120">`Option Strict` が `On`場合は、コンパイラエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="aa893-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="aa893-121">`Option Strict` が `Off`場合、値が[Long データ型](../../../visual-basic/language-reference/data-types/long-data-type.md)の範囲外の場合は <xref:System.OverflowException> できます。</span><span class="sxs-lookup"><span data-stu-id="aa893-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="aa893-122">`Long` への変換は、*銀行の丸め*処理の対象にもなります。</span><span class="sxs-lookup"><span data-stu-id="aa893-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="aa893-123">詳細については、「[型変換関数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)」の「小数部」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa893-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="aa893-124">`expression1` または `expression2` が[Nothing](../../../visual-basic/language-reference/nothing.md)と評価された場合、0として扱われます。</span><span class="sxs-lookup"><span data-stu-id="aa893-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="aa893-125">0による除算を試行しました</span><span class="sxs-lookup"><span data-stu-id="aa893-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="aa893-126">`expression2` が0に評価される場合、`\` 演算子は <xref:System.DivideByZeroException> 例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="aa893-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="aa893-127">これは、オペランドのすべての数値データ型に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="aa893-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa893-128">`\` 演算子は*オーバーロード*することができます。つまり、クラスまたは構造体がそのクラスまたは構造体の型を持つ場合に、クラスまたは構造体がその動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="aa893-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="aa893-129">コードでこのようなクラスまたは構造体に対してこの演算子を使用する場合は、再定義された動作を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aa893-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="aa893-130">詳細については、「[演算子プロシージャ](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa893-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa893-131">例</span><span class="sxs-lookup"><span data-stu-id="aa893-131">Example</span></span>  
 <span data-ttu-id="aa893-132">次の例では、`\` 演算子を使用して、整数除算を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa893-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="aa893-133">結果は、2つのオペランドの整数の商を表す整数で、残りの部分は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="aa893-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="aa893-134">前の例の式では、それぞれ2、3、33、および-22 の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="aa893-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa893-135">参照</span><span class="sxs-lookup"><span data-stu-id="aa893-135">See also</span></span>

- [<span data-ttu-id="aa893-136">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="aa893-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="aa893-137">/演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa893-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="aa893-138">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="aa893-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="aa893-139">算術演算子</span><span class="sxs-lookup"><span data-stu-id="aa893-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="aa893-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="aa893-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="aa893-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="aa893-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="aa893-142">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="aa893-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
