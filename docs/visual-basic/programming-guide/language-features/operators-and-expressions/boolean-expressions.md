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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350810"
---
# <a name="boolean-expressions-visual-basic"></a><span data-ttu-id="c9317-102">Boolean 式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9317-102">Boolean Expressions (Visual Basic)</span></span>
<span data-ttu-id="c9317-103">*ブール式*は、`True` または `False`[ブールデータ型](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)の値に評価される式です。</span><span class="sxs-lookup"><span data-stu-id="c9317-103">A *Boolean expression* is an expression that evaluates to a value of the [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md): `True` or `False`.</span></span> <span data-ttu-id="c9317-104">`Boolean` 式には、複数の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9317-104">`Boolean` expressions can take several forms.</span></span> <span data-ttu-id="c9317-105">最も単純なのは、次の例に示すように、`Boolean` 変数の値を `Boolean` リテラルに直接比較することです。</span><span class="sxs-lookup"><span data-stu-id="c9317-105">The simplest is the direct comparison of the value of a `Boolean` variable to a `Boolean` literal, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#87)]  
  
## <a name="two-meanings-of-the--operator"></a><span data-ttu-id="c9317-106">= 演算子の2つの意味</span><span class="sxs-lookup"><span data-stu-id="c9317-106">Two Meanings of the = Operator</span></span>  
 <span data-ttu-id="c9317-107">代入ステートメント `newCustomer = True` は、前の例の式と同じように見えますが、別の関数を実行し、異なる方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="c9317-107">Notice that the assignment statement `newCustomer = True` looks the same as the expression in the preceding example, but it performs a different function and is used differently.</span></span> <span data-ttu-id="c9317-108">前の例では、式 `newCustomer = True` はブール値を表し、`=` 符号は比較演算子として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-108">In the preceding example, the expression `newCustomer = True` represents a Boolean value, and the `=` sign is interpreted as a comparison operator.</span></span> <span data-ttu-id="c9317-109">スタンドアロンのステートメントでは、`=` 記号は代入演算子として解釈され、右側の値が左側の変数に代入されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-109">In a stand-alone statement, the `=` sign is interpreted as an assignment operator and assigns the value on the right to the variable on the left.</span></span> <span data-ttu-id="c9317-110">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c9317-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#88)]  
  
 <span data-ttu-id="c9317-111">詳細については、「[値の比較](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)と[ステートメント](../../../../visual-basic/language-reference/statements/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9317-111">For further information, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) and [Statements](../../../../visual-basic/language-reference/statements/index.md).</span></span>  
  
## <a name="comparison-operators"></a><span data-ttu-id="c9317-112">比較演算子</span><span class="sxs-lookup"><span data-stu-id="c9317-112">Comparison Operators</span></span>  
 <span data-ttu-id="c9317-113">`=`、`<`、`>`、`<>`、`<=`、`>=` などの比較演算子は、演算子の左辺の式を演算子の右辺の式と比較し、結果を `True` または `False`として評価することによって、ブール式を生成します。</span><span class="sxs-lookup"><span data-stu-id="c9317-113">Comparison operators such as `=`, `<`, `>`, `<>`, `<=`, and `>=` produce Boolean expressions by comparing the expression on the left side of the operator to the expression on the right side of the operator and evaluating the result as `True` or `False`.</span></span> <span data-ttu-id="c9317-114">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c9317-114">The following example illustrates this.</span></span>  
  
 `42 < 81`  
  
 <span data-ttu-id="c9317-115">42は81未満であるため、前の例のブール式は `True`に評価されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-115">Because 42 is less than 81, the Boolean expression in the preceding example evaluates to `True`.</span></span> <span data-ttu-id="c9317-116">この種類の式の詳細については、「[値の比較](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9317-116">For more information on this kind of expression, see [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md).</span></span>  
  
### <a name="comparison-operators-combined-with-logical-operators"></a><span data-ttu-id="c9317-117">論理演算子と組み合わせた比較演算子</span><span class="sxs-lookup"><span data-stu-id="c9317-117">Comparison Operators Combined with Logical Operators</span></span>  
 <span data-ttu-id="c9317-118">論理演算子を使用して比較式を組み合わせると、より複雑なブール式を生成できます。</span><span class="sxs-lookup"><span data-stu-id="c9317-118">Comparison expressions can be combined using logical operators to produce more complex Boolean expressions.</span></span> <span data-ttu-id="c9317-119">次の例では、論理演算子と共に比較演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c9317-119">The following example demonstrates the use of comparison operators in conjunction with a logical operator.</span></span>  
  
 `x > y And x < 1000`  
  
 <span data-ttu-id="c9317-120">前の例では、式全体の値は、`And` 演算子の各辺の式の値によって決まります。</span><span class="sxs-lookup"><span data-stu-id="c9317-120">In the preceding example, the value of the overall expression depends on the values of the expressions on each side of the `And` operator.</span></span> <span data-ttu-id="c9317-121">両方の式が `True`場合、全体の式が `True`に評価されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-121">If both expressions are `True`, then the overall expression evaluates to `True`.</span></span> <span data-ttu-id="c9317-122">いずれかの式が `False`場合、式全体が `False`に評価されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-122">If either expression is `False`, then the entire expression evaluates to `False`.</span></span>  
  
## <a name="short-circuiting-operators"></a><span data-ttu-id="c9317-123">ショートサーキット演算子</span><span class="sxs-lookup"><span data-stu-id="c9317-123">Short-Circuiting Operators</span></span>  
 <span data-ttu-id="c9317-124">論理演算子 `AndAlso` と `OrElse`*ショートサーキット*と呼ばれる動作を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="c9317-124">The logical operators `AndAlso` and `OrElse` exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="c9317-125">ショートサーキット演算子は、左オペランドを最初に評価します。</span><span class="sxs-lookup"><span data-stu-id="c9317-125">A short-circuiting operator evaluates the left operand first.</span></span> <span data-ttu-id="c9317-126">左側のオペランドで式全体の値が決定された場合、プログラムの実行は正しい式を評価せずに続行されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-126">If the left operand determines the value of the entire expression, then program execution proceeds without evaluating the right expression.</span></span> <span data-ttu-id="c9317-127">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c9317-127">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#89)]  
  
 <span data-ttu-id="c9317-128">前の例では、演算子は左の式の `45 < 12`を評価します。</span><span class="sxs-lookup"><span data-stu-id="c9317-128">In the preceding example, the operator evaluates the left expression, `45 < 12`.</span></span> <span data-ttu-id="c9317-129">左の式は `False`と評価されるため、論理式全体が `False`に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9317-129">Because the left expression evaluates to `False`, the entire logical expression must evaluate to `False`.</span></span> <span data-ttu-id="c9317-130">このため、プログラムを実行すると、正しい式 `testFunction(3)`を評価せずに `If` ブロック内のコードの実行がスキップされます。</span><span class="sxs-lookup"><span data-stu-id="c9317-130">Program execution thus skips execution of the code within the `If` block without evaluating the right expression, `testFunction(3)`.</span></span> <span data-ttu-id="c9317-131">この例では `testFunction()` は呼び出されません。左の式が式全体を falsifies ためです。</span><span class="sxs-lookup"><span data-stu-id="c9317-131">This example does not call `testFunction()` because the left expression falsifies the entire expression.</span></span>  
  
 <span data-ttu-id="c9317-132">同様に、`OrElse` を使用する論理式の左式が `True`に評価される場合、左の式では式全体が検証済みであるため、右の式を評価せずに次のコード行に実行が進みます。</span><span class="sxs-lookup"><span data-stu-id="c9317-132">Similarly, if the left expression in a logical expression using `OrElse` evaluates to `True`, execution proceeds to the next line of code without evaluating the right expression, because the left expression has already validated the entire expression.</span></span>  
  
### <a name="comparison-with-non-short-circuiting-operators"></a><span data-ttu-id="c9317-133">非ショートサーキット演算子との比較</span><span class="sxs-lookup"><span data-stu-id="c9317-133">Comparison with Non-Short-Circuiting Operators</span></span>  
 <span data-ttu-id="c9317-134">一方、論理演算子の両側は、論理演算子 `And` と `Or` が使用されるときに評価されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-134">By contrast, both sides of the logical operator are evaluated when the logical operators `And` and `Or` are used.</span></span> <span data-ttu-id="c9317-135">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="c9317-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#90)]  
  
 <span data-ttu-id="c9317-136">前の例では、左の式が `False`に評価された場合でも `testFunction()` が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-136">The preceding example calls `testFunction()` even though the left expression evaluates to `False`.</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="c9317-137">かっこで囲まれる式</span><span class="sxs-lookup"><span data-stu-id="c9317-137">Parenthetical Expressions</span></span>  
 <span data-ttu-id="c9317-138">かっこを使用して、ブール式の評価順序を制御できます。</span><span class="sxs-lookup"><span data-stu-id="c9317-138">You can use parentheses to control the order of evaluation of Boolean expressions.</span></span> <span data-ttu-id="c9317-139">かっこで囲まれた式は最初に評価されます。</span><span class="sxs-lookup"><span data-stu-id="c9317-139">Expressions enclosed by parentheses evaluate first.</span></span> <span data-ttu-id="c9317-140">入れ子のレベルが複数ある場合は、最も深い入れ子になった式に優先順位が与えられます。</span><span class="sxs-lookup"><span data-stu-id="c9317-140">For multiple levels of nesting, precedence is granted to the most deeply nested expressions.</span></span> <span data-ttu-id="c9317-141">かっこ内で、評価は演算子の優先順位の規則に従って行われます。</span><span class="sxs-lookup"><span data-stu-id="c9317-141">Within parentheses, evaluation proceeds according to the rules of operator precedence.</span></span> <span data-ttu-id="c9317-142">詳細については、「 [Visual Basic での演算子の優先順位](../../../../visual-basic/language-reference/operators/operator-precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9317-142">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9317-143">参照</span><span class="sxs-lookup"><span data-stu-id="c9317-143">See also</span></span>

- [<span data-ttu-id="c9317-144">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="c9317-144">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="c9317-145">値の比較</span><span class="sxs-lookup"><span data-stu-id="c9317-145">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="c9317-146">ステートメント</span><span class="sxs-lookup"><span data-stu-id="c9317-146">Statements</span></span>](../../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="c9317-147">比較演算子</span><span class="sxs-lookup"><span data-stu-id="c9317-147">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="c9317-148">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c9317-148">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
- [<span data-ttu-id="c9317-149">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c9317-149">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c9317-150">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="c9317-150">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)
