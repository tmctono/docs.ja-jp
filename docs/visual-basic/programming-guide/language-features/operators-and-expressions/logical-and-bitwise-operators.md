---
title: Visual Basic の論理演算子とビット処理演算子
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 40076b2ad6606b4c565bcd39dbeea9e55da47211
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963319"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="d53c0-102">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="d53c0-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="d53c0-103">論理演算子は`Boolean` 、式を比較`Boolean`し、結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="d53c0-104">`And` 、`Or`、 `Not` 、 、およびの各演算子は2つのオペランドを受け取りますが、演算子は単項演算であるため、二項演算子`AndAlso`です。 `OrElse` `Xor`</span><span class="sxs-lookup"><span data-stu-id="d53c0-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="d53c0-105">これらの演算子の一部では、整数値に対してビットごとの論理演算を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="d53c0-106">単項論理演算子</span><span class="sxs-lookup"><span data-stu-id="d53c0-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="d53c0-107">[Not 演算子](../../../../visual-basic/language-reference/operators/not-operator.md)は、 `Boolean`式の論理*否定*を実行します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="d53c0-108">これにより、オペランドの論理逆が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="d53c0-109">式がと`True`評価された場合`False` `Not` 、はを返します。 `False`式がと`True`評価された場合、 `Not`はを返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="d53c0-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="d53c0-111">二項論理演算子</span><span class="sxs-lookup"><span data-stu-id="d53c0-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="d53c0-112">[And 演算子](../../../../visual-basic/language-reference/operators/and-operator.md)は、2 `Boolean`つの式の論理積を実行します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="d53c0-113">両方`True`の式がに`True`評価される場合、はを返します。`And`</span><span class="sxs-lookup"><span data-stu-id="d53c0-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="d53c0-114">少なくとも1つの式がに`False`評価さ`And`れる`False`場合、はを返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="d53c0-115">[Or 演算子](../../../../visual-basic/language-reference/operators/or-operator.md)は、2 `Boolean`つの式の論理*和*を実行します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="d53c0-116">いずれかの式が`True`に評価された`True`場合、また`True`は両方がと評価された場合、 `Or`はを返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="d53c0-117">どちらの式もに`True`評価`Or`さ`False`れない場合、はを返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="d53c0-118">[Xor 演算子](../../../../visual-basic/language-reference/operators/xor-operator.md)は、2 `Boolean`つの式に対して論理的な除外を実行します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="d53c0-119">1つの式だけがと`True`評価される場合、 `Xor`両方`True`ではなく、が返されます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="d53c0-120">両方`True`の式がと評価されるか、両方`False`がに`False`評価される場合、 `Xor`はを返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="d53c0-121">次の例は、 `And`、 `Or`、および`Xor`の各演算子を示しています。</span><span class="sxs-lookup"><span data-stu-id="d53c0-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="d53c0-122">ショートサーキット論理操作</span><span class="sxs-lookup"><span data-stu-id="d53c0-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="d53c0-123">[AndAlso 演算子](../../../../visual-basic/language-reference/operators/andalso-operator.md)は、2 `And` `Boolean`つの式に対して論理積も実行するという点で、演算子と非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="d53c0-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="d53c0-124">2つの間の主な違い`AndAlso`は、が*ショートサーキット*動作を示す点です。</span><span class="sxs-lookup"><span data-stu-id="d53c0-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="d53c0-125">`AndAlso`式の最初の式がに`False`評価される場合、2番目の式は評価されません。これは`AndAlso` 、 `False`最終的な結果を変更できず、がを返すためです。</span><span class="sxs-lookup"><span data-stu-id="d53c0-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="d53c0-126">同様に、 [OrElse 演算子](../../../../visual-basic/language-reference/operators/orelse-operator.md)は、2 `Boolean`つの式の短絡論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="d53c0-127">`OrElse`式の最初の式がに`True`評価される場合、2番目の式は評価されません。これは`OrElse` 、 `True`最終的な結果を変更できず、がを返すためです。</span><span class="sxs-lookup"><span data-stu-id="d53c0-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="d53c0-128">ショートサーキットトレードオフ</span><span class="sxs-lookup"><span data-stu-id="d53c0-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="d53c0-129">ショートサーキットを使用すると、論理演算の結果を変更できない式を評価しないことで、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="d53c0-130">ただし、その式が追加のアクションを実行する場合、ショートサーキットはこれらのアクションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="d53c0-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="d53c0-131">たとえば、式に`Function`プロシージャへの呼び出しが含まれている場合、式が短いサーキットの場合、そのプロシージャは呼び出されず、に含まれる追加の`Function`コードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d53c0-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="d53c0-132">このため、関数は、ときどき実行される場合があり、正しくテストされない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d53c0-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="d53c0-133">または、プログラムロジックがの`Function`コードに依存している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d53c0-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="d53c0-134">次の例は、 `And`、 `Or`、および対応するショートサーキットの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="d53c0-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="d53c0-135">前の例では、の一部の重要な`checkIfValid()`コードは、サーキットの呼び出しでは実行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d53c0-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="d53c0-136">はショート`If`サーキットで`checkIfValid()`はない`12 > 45`ため`False` 、`And`最初のステートメントはを返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="d53c0-137">2番`If`目のステートメントは`checkIfValid()`を呼び出しません`False`。 `AndAlso`がを返した場合`12 > 45` 、2番目の式がショートサーキットされるためです。</span><span class="sxs-lookup"><span data-stu-id="d53c0-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="d53c0-138">3番`If`目のステートメントは`12 < 45`を`True`返します`Or`が、はショートサーキットではないため、を呼び出し`checkIfValid()`ます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="d53c0-139">4 `If`番目のステートメントは`checkIfValid()`を呼び出しません`True`。 `OrElse`がを返した場合`12 < 45` 、2番目の式がショートサーキットされるためです。</span><span class="sxs-lookup"><span data-stu-id="d53c0-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="d53c0-140">ビットごとの演算</span><span class="sxs-lookup"><span data-stu-id="d53c0-140">Bitwise Operations</span></span>  
 <span data-ttu-id="d53c0-141">ビットごとの演算では、2つの整数値が binary (base 2) 形式で評価されます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="d53c0-142">これらは、対応する位置のビットを比較し、比較に基づいて値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="d53c0-143">次の例は、 `And`演算子を示しています。</span><span class="sxs-lookup"><span data-stu-id="d53c0-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="d53c0-144">前の例では、の`x`値を1に設定しています。</span><span class="sxs-lookup"><span data-stu-id="d53c0-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="d53c0-145">これは、次の理由で発生します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-145">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="d53c0-146">値はバイナリとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="d53c0-147">3バイナリ形式の 3 = 011</span><span class="sxs-lookup"><span data-stu-id="d53c0-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="d53c0-148">5バイナリ形式 = 101</span><span class="sxs-lookup"><span data-stu-id="d53c0-148">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="d53c0-149">演算子`And`は、一度に1つのバイナリ位置 (ビット) をバイナリ表現と比較します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="d53c0-150">指定された位置にある両方のビットが1の場合、結果内のその位置に1が配置されます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="d53c0-151">どちらかのビットが0の場合は、結果内のその位置に0が配置されます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="d53c0-152">前の例では、これは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="d53c0-153">011 (バイナリ形式の場合は 3)</span><span class="sxs-lookup"><span data-stu-id="d53c0-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="d53c0-154">101 (バイナリ形式で 5)</span><span class="sxs-lookup"><span data-stu-id="d53c0-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="d53c0-155">001 (バイナリ形式の結果)</span><span class="sxs-lookup"><span data-stu-id="d53c0-155">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="d53c0-156">結果は decimal として扱われます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-156">The result is treated as decimal.</span></span> <span data-ttu-id="d53c0-157">値001は 1 `x`のバイナリ表現であり、= 1 です。</span><span class="sxs-lookup"><span data-stu-id="d53c0-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="d53c0-158">ビットごと`Or`の演算は似ていますが、比較対象のビットのいずれかまたは両方が1の場合、結果ビットに1が割り当てられる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="d53c0-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="d53c0-159">`Xor`比較されたビットの1つ (両方ではない) が1の場合、結果のビットに1を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="d53c0-160">`Not`1つのオペランドを受け取り、符号ビットを含むすべてのビットを反転し、その値を結果に代入します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="d53c0-161">つまり、符号付き正の数値の`Not`場合、は常に負の値を返し、 `Not`負の数値の場合は正の値または0を返します。</span><span class="sxs-lookup"><span data-stu-id="d53c0-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="d53c0-162">演算子`AndAlso` と`OrElse`演算子は、ビットごとの演算をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="d53c0-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d53c0-163">ビットごとの演算は、整数型に対してのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="d53c0-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="d53c0-164">浮動小数点値は、ビットごとの演算を続行する前に、整数型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d53c0-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53c0-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="d53c0-165">See also</span></span>

- [<span data-ttu-id="d53c0-166">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d53c0-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="d53c0-167">ブール式</span><span class="sxs-lookup"><span data-stu-id="d53c0-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="d53c0-168">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="d53c0-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="d53c0-169">Visual Basic の比較演算子</span><span class="sxs-lookup"><span data-stu-id="d53c0-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="d53c0-170">Visual Basic での連結演算子</span><span class="sxs-lookup"><span data-stu-id="d53c0-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="d53c0-171">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="d53c0-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
