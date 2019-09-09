---
title: '方法: 数値を計算する方法 (Visual Basic)。'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 3e367a10a3e703241c7417d3ea17068018becb5a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649728"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="f7b5f-102">方法: 数値を計算する方法 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="f7b5f-103">数値式を使用して数値を計算することができます。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="f7b5f-104">*数値式*リテラル、定数、および数値の値を表す変数を含む式とそれらの値に対して作用する演算子です。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="f7b5f-105">数値の計算</span><span class="sxs-lookup"><span data-stu-id="f7b5f-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="f7b5f-106">数値の値を計算するには</span><span class="sxs-lookup"><span data-stu-id="f7b5f-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="f7b5f-107">数値式に 1 つまたは複数の数値リテラル、定数、および変数を結合します。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="f7b5f-108">次の例は、いくつかの有効な数値式です。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="f7b5f-109">最初の 3 つの行では、リテラル、定数、および変数を示します。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="f7b5f-110">各 1 つは、単独で有効な数値式を形成します。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="f7b5f-111">最後の行は、2 つのリテラルと変数の組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="f7b5f-112">数値式を単独で、完全な Visual Basic ステートメントが形成されていませんことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="f7b5f-113">式は、完全なステートメントの一部として使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="f7b5f-114">数値の値を格納するには</span><span class="sxs-lookup"><span data-stu-id="f7b5f-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="f7b5f-115">代入ステートメントを使用して、次の例に示すように、変数に数値式で表される値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="f7b5f-116">前の例では、等値演算子の右側にある式の値 (`=`) 変数に割り当てられている`j`、演算子の左側にあるため、 `j` 276 に評価されます。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="f7b5f-117">詳細については、「[ステートメント](../../../../visual-basic/language-reference/statements/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-117">For more information, see [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="f7b5f-118">複数の演算子</span><span class="sxs-lookup"><span data-stu-id="f7b5f-118">Multiple Operators</span></span>  
 <span data-ttu-id="f7b5f-119">数値式には、複数の演算子が含まれている場合、演算子の優先順位のルールで評価される順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="f7b5f-120">演算子の優先順位のルールを無効にするには、; 上記の例のように、かっこで囲まれた式を囲みます。囲まれた式は、最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="f7b5f-121">標準の演算子の優先順位をオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="f7b5f-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="f7b5f-122">かっこを使用して、先に実行する操作を囲みます。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="f7b5f-123">次の例では、オペランドと演算子が同じで、2 つの異なる結果を示します。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="f7b5f-124">前の例では、計算で`j`加算演算子を実行します (`+`) 最初ので、かっこで囲んで`(67 + i)`通常の優先順位とに割り当てられた値をオーバーライド`j`276 (4 回 69) は、します。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="f7b5f-125">計算`k`、通常の優先順位の演算子を実行します (`*`する前に`+`) とに割り当てられた値`k`270 (268 および 2)。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="f7b5f-126">詳細については、次を参照してください。 [Visual Basic における演算子の優先順位](../../../../visual-basic/language-reference/operators/operator-precedence.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7b5f-126">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b5f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7b5f-127">See also</span></span>

- [<span data-ttu-id="f7b5f-128">演算子および式</span><span class="sxs-lookup"><span data-stu-id="f7b5f-128">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="f7b5f-129">値の比較</span><span class="sxs-lookup"><span data-stu-id="f7b5f-129">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="f7b5f-130">ステートメント</span><span class="sxs-lookup"><span data-stu-id="f7b5f-130">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="f7b5f-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="f7b5f-131">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f7b5f-132">算術演算子</span><span class="sxs-lookup"><span data-stu-id="f7b5f-132">Arithmetic Operators</span></span>](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f7b5f-133">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="f7b5f-133">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
