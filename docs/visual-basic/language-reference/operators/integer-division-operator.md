---
title: '\ 演算子 (Visual Basic)'
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
ms.openlocfilehash: 1753199e2ecf3f156b90d8c0a5cacd672397260d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013557"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="bea80-102">\ 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bea80-102">\ Operator (Visual Basic)</span></span>
<span data-ttu-id="bea80-103">2 つの数値を除算し、整数の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="bea80-103">Divides two numbers and returns an integer result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea80-104">構文</span><span class="sxs-lookup"><span data-stu-id="bea80-104">Syntax</span></span>  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="bea80-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="bea80-105">Parts</span></span>  
 `expression1`  
 <span data-ttu-id="bea80-106">必須。</span><span class="sxs-lookup"><span data-stu-id="bea80-106">Required.</span></span> <span data-ttu-id="bea80-107">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="bea80-107">Any numeric expression.</span></span>  
  
 `expression2`  
 <span data-ttu-id="bea80-108">必須。</span><span class="sxs-lookup"><span data-stu-id="bea80-108">Required.</span></span> <span data-ttu-id="bea80-109">任意の数式。</span><span class="sxs-lookup"><span data-stu-id="bea80-109">Any numeric expression.</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="bea80-110">サポートされている型</span><span class="sxs-lookup"><span data-stu-id="bea80-110">Supported Types</span></span>  
 <span data-ttu-id="bea80-111">符号なしと浮動小数点型を含め、すべての数値型と`Decimal`します。</span><span class="sxs-lookup"><span data-stu-id="bea80-111">All numeric types, including the unsigned and floating-point types and `Decimal`.</span></span>  
  
## <a name="result"></a><span data-ttu-id="bea80-112">結果</span><span class="sxs-lookup"><span data-stu-id="bea80-112">Result</span></span>  
 <span data-ttu-id="bea80-113">結果は整数の商`expression1`で割った値`expression2`余りはすべて破棄され、整数部分だけが保持されます。</span><span class="sxs-lookup"><span data-stu-id="bea80-113">The result is the integer quotient of `expression1` divided by `expression2`, which discards any remainder and retains only the integer portion.</span></span> <span data-ttu-id="bea80-114">これと呼ばれます*切り捨て*します。</span><span class="sxs-lookup"><span data-stu-id="bea80-114">This is known as *truncation*.</span></span>  
  
 <span data-ttu-id="bea80-115">結果のデータ型が数値型のデータ型に適した`expression1`と`expression2`します。</span><span class="sxs-lookup"><span data-stu-id="bea80-115">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="bea80-116">「整数の算術演算による」のテーブルを参照してください。[演算子結果のデータ型](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)します。</span><span class="sxs-lookup"><span data-stu-id="bea80-116">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>  
  
 <span data-ttu-id="bea80-117">[/演算子 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)小数部分の残りの部分を保持する、完全な商を返します。</span><span class="sxs-lookup"><span data-stu-id="bea80-117">The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) returns the full quotient, which retains the remainder in the fractional portion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bea80-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="bea80-118">Remarks</span></span>  
 <span data-ttu-id="bea80-119">除算を実行する前に、Visual Basic に任意の浮動小数点の数値式の変換を試みます`Long`します。</span><span class="sxs-lookup"><span data-stu-id="bea80-119">Before performing the division, Visual Basic attempts to convert any floating-point numeric expression to `Long`.</span></span> <span data-ttu-id="bea80-120">場合`Option Strict`は`On`、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bea80-120">If `Option Strict` is `On`, a compiler error occurs.</span></span> <span data-ttu-id="bea80-121">場合`Option Strict`は`Off`、<xref:System.OverflowException>値の範囲外の場合は、 [Long データ型](../../../visual-basic/language-reference/data-types/long-data-type.md)します。</span><span class="sxs-lookup"><span data-stu-id="bea80-121">If `Option Strict` is `Off`, an <xref:System.OverflowException> is possible if the value is outside the range of the [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md).</span></span> <span data-ttu-id="bea80-122">変換`Long`対象にも*銀行型丸め*します。</span><span class="sxs-lookup"><span data-stu-id="bea80-122">The conversion to `Long` is also subject to *banker's rounding*.</span></span> <span data-ttu-id="bea80-123">詳細については、「部分の小数部」を参照してください[型変換関数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)します。</span><span class="sxs-lookup"><span data-stu-id="bea80-123">For more information, see "Fractional Parts" in [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="bea80-124">場合`expression1`または`expression2`に評価される[Nothing](../../../visual-basic/language-reference/nothing.md)、0 として扱われます。</span><span class="sxs-lookup"><span data-stu-id="bea80-124">If `expression1` or `expression2` evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), it is treated as zero.</span></span>  
  
## <a name="attempted-division-by-zero"></a><span data-ttu-id="bea80-125">0 による除算</span><span class="sxs-lookup"><span data-stu-id="bea80-125">Attempted Division by Zero</span></span>  
 <span data-ttu-id="bea80-126">場合`expression2`を 0 に評価される、`\`演算子がスローされます、<xref:System.DivideByZeroException>例外。</span><span class="sxs-lookup"><span data-stu-id="bea80-126">If `expression2` evaluates to zero, the `\` operator throws a <xref:System.DivideByZeroException> exception.</span></span> <span data-ttu-id="bea80-127">これは、すべての数値データ型のオペランドの場合は true。</span><span class="sxs-lookup"><span data-stu-id="bea80-127">This is true for all numeric data types of the operands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bea80-128">`\`演算子は、*オーバー ロードされた*、つまり、ことクラスまたは構造体を再定義できますその動作はそのクラスまたは構造体の型。</span><span class="sxs-lookup"><span data-stu-id="bea80-128">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bea80-129">コードは、このようなクラスまたは構造体に、この演算子を使用する場合は、再定義された動作を確認ください。</span><span class="sxs-lookup"><span data-stu-id="bea80-129">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bea80-130">詳細については、「 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bea80-130">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bea80-131">例</span><span class="sxs-lookup"><span data-stu-id="bea80-131">Example</span></span>  
 <span data-ttu-id="bea80-132">次の例では、`\`整数除算を実行する演算子。</span><span class="sxs-lookup"><span data-stu-id="bea80-132">The following example uses the `\` operator to perform integer division.</span></span> <span data-ttu-id="bea80-133">結果は、破棄された残りの部分を 2 つのオペランドの商の整数を表す整数です。</span><span class="sxs-lookup"><span data-stu-id="bea80-133">The result is an integer that represents the integer quotient of the two operands, with the remainder discarded.</span></span>  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 <span data-ttu-id="bea80-134">前の例の式では、それぞれ 2、3、33、および ~ 22 日の値を返します。</span><span class="sxs-lookup"><span data-stu-id="bea80-134">The expressions in the preceding example return values of 2, 3, 33, and -22, respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea80-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="bea80-135">See also</span></span>

- [<span data-ttu-id="bea80-136">\\= 演算子</span><span class="sxs-lookup"><span data-stu-id="bea80-136">\\= Operator</span></span>](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [<span data-ttu-id="bea80-137">/演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bea80-137">/ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [<span data-ttu-id="bea80-138">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="bea80-138">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="bea80-139">算術演算子</span><span class="sxs-lookup"><span data-stu-id="bea80-139">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="bea80-140">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="bea80-140">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="bea80-141">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="bea80-141">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="bea80-142">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="bea80-142">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
