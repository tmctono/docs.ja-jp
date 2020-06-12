---
title: '方法: 数値を計算する'
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
ms.openlocfilehash: 94b02693f308dcfcfa6983f2750a26d9d419f7be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403460"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a><span data-ttu-id="cbb6b-102">方法: 数値を計算する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbb6b-102">How to: Calculate Numeric Values (Visual Basic)</span></span>
<span data-ttu-id="cbb6b-103">数式を使用して数値を計算できます。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-103">You can calculate numeric values through the use of numeric expressions.</span></span> <span data-ttu-id="cbb6b-104">*数式*は、数値を表すリテラル、定数、変数、およびそれらの値に対して作用する演算子を含む式です。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-104">A *numeric expression* is an expression that contains literals, constants, and variables representing numeric values, and operators that act on those values.</span></span>  
  
## <a name="calculating-numeric-values"></a><span data-ttu-id="cbb6b-105">数値の計算</span><span class="sxs-lookup"><span data-stu-id="cbb6b-105">Calculating Numeric Values</span></span>  
  
#### <a name="to-calculate-a-numeric-value"></a><span data-ttu-id="cbb6b-106">数値を計算するには</span><span class="sxs-lookup"><span data-stu-id="cbb6b-106">To calculate a numeric value</span></span>  
  
- <span data-ttu-id="cbb6b-107">1 つ以上の数値リテラル、定数、および変数を数式に組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-107">Combine one or more numeric literals, constants, and variables into a numeric expression.</span></span> <span data-ttu-id="cbb6b-108">次の例に、有効な数式をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-108">The following example shows some valid numeric expressions.</span></span>  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     <span data-ttu-id="cbb6b-109">最初の 3 行は、リテラル、定数、および変数を示しています。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-109">The first three lines show a literal, a constant, and a variable.</span></span> <span data-ttu-id="cbb6b-110">それぞれがそれだけで有効な数式を形成しています。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-110">Each one forms a valid numeric expression by itself.</span></span> <span data-ttu-id="cbb6b-111">最後の行は、2 つのリテラルを含む変数の組み合わせを示しています。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-111">The final line shows a combination of a variable with two literals.</span></span>  
  
     <span data-ttu-id="cbb6b-112">数式では、それだけで完全な Visual Basic ステートメントを形成するわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-112">Note that a numeric expression does not form a complete Visual Basic statement by itself.</span></span> <span data-ttu-id="cbb6b-113">式は、完全なステートメントの一部として使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-113">You must use the expression as part of a complete statement.</span></span>  
  
#### <a name="to-store-a-numeric-value"></a><span data-ttu-id="cbb6b-114">数値を格納するには</span><span class="sxs-lookup"><span data-stu-id="cbb6b-114">To store a numeric value</span></span>  
  
- <span data-ttu-id="cbb6b-115">次の例に示すように、代入ステートメントを使用して、数式で表される値を変数に代入することができます。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-115">You can use an assignment statement to assign the value represented by a numeric expression to a variable, as the following example demonstrates.</span></span>  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     <span data-ttu-id="cbb6b-116">前の例では、等号演算子 (`=`) の右側にある式の値が、演算子の左側にある変数 `j` に代入されているため、`j` は 276 に評価されます。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-116">In the preceding example, the value of the expression on the right side of the equal operator (`=`) is assigned to the variable `j` on the left side of the operator, so `j` evaluates to 276.</span></span>  
  
     <span data-ttu-id="cbb6b-117">詳細については、「[ステートメント](../../../language-reference/statements/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-117">For more information, see [Statements](../../../language-reference/statements/index.md).</span></span>  
  
## <a name="multiple-operators"></a><span data-ttu-id="cbb6b-118">複数の演算子</span><span class="sxs-lookup"><span data-stu-id="cbb6b-118">Multiple Operators</span></span>  
 <span data-ttu-id="cbb6b-119">数式に複数の演算子が含まれている場合、それらが評価される順序は、演算子の優先順位のルールによって決まります。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-119">If the numeric expression contains more than one operator, the order in which they are evaluated is determined by the rules of operator precedence.</span></span> <span data-ttu-id="cbb6b-120">演算子の優先順位のルールをオーバーライドするには、上の例のように、式をかっこで囲みます。囲まれた式は、最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-120">To override the rules of operator precedence, you enclose expressions in parentheses, as in the above example; the enclosed expressions are evaluated first.</span></span>  
  
#### <a name="to-override-normal-operator-precedence"></a><span data-ttu-id="cbb6b-121">通常の演算子の優先順位をオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="cbb6b-121">To override normal operator precedence</span></span>  
  
- <span data-ttu-id="cbb6b-122">かっこを使用して、最初に実行させる演算を囲みます。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-122">Use parentheses to enclose the operations you want to be performed first.</span></span> <span data-ttu-id="cbb6b-123">次の例は、同じオペランドと演算子による 2 つの異なる結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-123">The following example shows two different results with the same operands and operators.</span></span>  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     <span data-ttu-id="cbb6b-124">前の例では、`j` の計算で加算演算子 (`+`) が最初に実行されます。これは、`(67 + i)` を囲むかっこによって、通常の優先順位がオーバーライドされるためであり、`j` に代入される値は 276 (69 の 4 倍) になります。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-124">In the preceding example, the calculation for `j` performs the addition operator (`+`) first because the parentheses around `(67 + i)` override normal precedence, and the value assigned to `j` is 276 (4 times 69).</span></span> <span data-ttu-id="cbb6b-125">`k` の計算では、通常の優先順位 (`+` の前に `*`) で演算子が実行されるので、`k` に代入される値は 270 (268 + 2) になります。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-125">The calculation for `k` performs the operators in their normal precedence (`*` before `+`), and the value assigned to `k` is 270 (268 plus 2).</span></span>  
  
     <span data-ttu-id="cbb6b-126">詳細については、「[Visual Basic における演算子の優先順位](../../../language-reference/operators/operator-precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbb6b-126">For more information, see [Operator Precedence in Visual Basic](../../../language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb6b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbb6b-127">See also</span></span>

- [<span data-ttu-id="cbb6b-128">演算子および式</span><span class="sxs-lookup"><span data-stu-id="cbb6b-128">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="cbb6b-129">値の比較</span><span class="sxs-lookup"><span data-stu-id="cbb6b-129">Value Comparisons</span></span>](value-comparisons.md)
- [<span data-ttu-id="cbb6b-130">ステートメント</span><span class="sxs-lookup"><span data-stu-id="cbb6b-130">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="cbb6b-131">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="cbb6b-131">Operator Precedence in Visual Basic</span></span>](../../../language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="cbb6b-132">算術演算子</span><span class="sxs-lookup"><span data-stu-id="cbb6b-132">Arithmetic Operators</span></span>](../../../language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="cbb6b-133">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="cbb6b-133">Efficient Combination of Operators</span></span>](efficient-combination-of-operators.md)
