---
title: Boolean 式
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- expressions [Visual Basic], Boolean
- expression evaluation [Visual Basic], Boolean expressions
- operators [Visual Basic], short-circuiting
- Visual Basic code, operators
- short-circuit evaluation
- logical operators [Visual Basic], short-circuiting
- operators [Visual Basic], Boolean
- Visual Basic code, expressions
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
ms.openlocfilehash: 1000ec6e4b35d0cb2c6232b50f9a9551cb0dfdcd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350810"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="9e79c-102">Boolean 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e79c-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="9e79c-103">*ブール式*は、[ブール データ型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` または `False`) の値に評価される式です。</span><span class="sxs-lookup"><span data-stu-id="9e79c-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="9e79c-104">`Boolean` 式では、複数の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="9e79c-105">最もシンプルなのは、次の例に示すように、`Boolean` 変数の値を `Boolean` リテラルに対して直接比較することです。</span><span class="sxs-lookup"><span data-stu-id="9e79c-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="9e79c-106">= 演算子の 2 つの意味</span><span class="sxs-lookup"><span data-stu-id="9e79c-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="9e79c-107">代入ステートメント `newCustomer = True` は、前の例の式と同じように見えますが、別の関数を実行し、使い方が異なります。</span><span class="sxs-lookup"><span data-stu-id="9e79c-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="9e79c-108">前の例では、式 `newCustomer = True` はブール値を表し、`=` 記号は比較演算子として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="9e79c-109">スタンドアロン ステートメントでは、`=` 記号は代入演算子として解釈され、右側の値が左側の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="9e79c-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e79c-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="9e79c-111">詳細については、「[値の比較](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)」と「[ステートメント](../../../../visual-basic/language-reference/statements/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e79c-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="9e79c-112">比較演算子</span><span class="sxs-lookup"><span data-stu-id="9e79c-112">Comparison Operators</span></span>  
 <span data-ttu-id="9e79c-113">`=`、`<`、`>`、`<>`、`<=`、`>=` などの比較演算子によって、演算子の左側の式が演算子の右側の式と比較され、結果が `True` または `False` として評価されることによって、ブール式が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="9e79c-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e79c-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="9e79c-115">42 は 81 未満であるため、前の例のブール式は `True` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="9e79c-116">この種類の式の詳細については、「[値の比較](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e79c-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="9e79c-117">論理演算子と組み合わせた比較演算子</span><span class="sxs-lookup"><span data-stu-id="9e79c-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="9e79c-118">論理演算子を使用して比較式を組み合わせると、より複雑なブール式を生成できます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="9e79c-119">次の例では、論理演算子と共に比較演算子を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e79c-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="9e79c-120">前の例では、式全体の値は、`And` 演算子の両側の式の値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="9e79c-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="9e79c-121">両方の式が `True` である場合、式全体が `True` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="9e79c-122">いずれかの式が `False` である場合、式全体が `False` に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="9e79c-123">ショートサーキット演算子</span><span class="sxs-lookup"><span data-stu-id="9e79c-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="9e79c-124">論理演算子 `AndAlso` および `OrElse` では、*ショートサーキット*と呼ばれる動作が見られます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="9e79c-125">ショートサーキット演算子では、左オペランドが最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="9e79c-126">左オペランドで式全体の値が判断された場合、右の式を評価せずにプログラムの実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="9e79c-127">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e79c-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="9e79c-128">前の例では、演算子によって左の式 `45 < 12` が評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="9e79c-129">左の式は `False` に評価されるため、論理式全体が `False` に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e79c-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="9e79c-130">このため、プログラムの実行では、右の式 `testFunction(3)` が評価されることなく、`If` ブロック内のコードの実行がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="9e79c-131">この例では、左の式によって式全体が False とされたため、`testFunction()` は呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="9e79c-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="9e79c-132">同様に、`OrElse` を使用する論理式の左の式が `True` に評価された場合、左の式で式全体が既に検証済みであるため、右の式が評価されずに、次のコード行に実行が進みます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="9e79c-133">非ショートサーキット演算子との比較</span><span class="sxs-lookup"><span data-stu-id="9e79c-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="9e79c-134">一方、論理演算子 `And` と `Or` が使用された場合、論理演算子の両側が評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="9e79c-135">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e79c-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="9e79c-136">前の例では、左の式が `False` に評価されても `testFunction()` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="9e79c-137">かっこで囲まれた式</span><span class="sxs-lookup"><span data-stu-id="9e79c-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="9e79c-138">かっこを使用して、ブール式の評価順序を制御できます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="9e79c-139">かっこで囲まれた式は最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="9e79c-140">複数レベルの入れ子の場合は、最も深い入れ子になった式が優先されます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="9e79c-141">かっこ内では、演算子の優先順位のルールに従って、評価が行われます。</span><span class="sxs-lookup"><span data-stu-id="9e79c-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="9e79c-142">詳細については、「[Visual Basic における演算子の優先順位](../../../../visual-basic/language-reference/operators/operator-precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e79c-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e79c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e79c-143">See also</span></span>

- [<span data-ttu-id="9e79c-144">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="9e79c-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="9e79c-145">値の比較</span><span class="sxs-lookup"><span data-stu-id="9e79c-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="9e79c-146">ステートメント</span><span class="sxs-lookup"><span data-stu-id="9e79c-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="9e79c-147">比較演算子</span><span class="sxs-lookup"><span data-stu-id="9e79c-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="9e79c-148">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="9e79c-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="9e79c-149">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="9e79c-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9e79c-150">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="9e79c-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
