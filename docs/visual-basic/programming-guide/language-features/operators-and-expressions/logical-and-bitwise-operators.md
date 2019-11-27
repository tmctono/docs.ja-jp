---
title: 論理演算子とビット処理演算子
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
ms.openlocfilehash: 55a246c0d56501a409ebbc7d0d0aa39ae9fa1770
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343595"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a><span data-ttu-id="23a33-102">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="23a33-102">Logical and Bitwise Operators in Visual Basic</span></span>
<span data-ttu-id="23a33-103">論理演算子は `Boolean` 式を比較し、`Boolean` の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-103">Logical operators compare `Boolean` expressions and return a `Boolean` result.</span></span> <span data-ttu-id="23a33-104">`And`、`Or`、`AndAlso`、`OrElse`、および `Xor` の各演算子は2つのオペランドを受け取りますが、`Not` 演算子は*単項*演算であるため、*二項*演算子です。</span><span class="sxs-lookup"><span data-stu-id="23a33-104">The `And`, `Or`, `AndAlso`, `OrElse`, and `Xor` operators are *binary* because they take two operands, while the `Not` operator is *unary* because it takes a single operand.</span></span> <span data-ttu-id="23a33-105">これらの演算子の一部では、整数値に対してビットごとの論理演算を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="23a33-105">Some of these operators can also perform bitwise logical operations on integral values.</span></span>  
  
## <a name="unary-logical-operator"></a><span data-ttu-id="23a33-106">単項論理演算子</span><span class="sxs-lookup"><span data-stu-id="23a33-106">Unary Logical Operator</span></span>  
 <span data-ttu-id="23a33-107">[Not 演算子](../../../../visual-basic/language-reference/operators/not-operator.md)は、`Boolean` 式の論理*否定*を実行します。</span><span class="sxs-lookup"><span data-stu-id="23a33-107">The [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md) performs logical *negation* on a `Boolean` expression.</span></span> <span data-ttu-id="23a33-108">これにより、オペランドの論理逆が生成されます。</span><span class="sxs-lookup"><span data-stu-id="23a33-108">It yields the logical opposite of its operand.</span></span> <span data-ttu-id="23a33-109">式が `True`に評価された場合、`Not` は `False`を返します。式が `False`に評価された場合、`Not` は `True`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-109">If the expression evaluates to `True`, then `Not` returns `False`; if the expression evaluates to `False`, then `Not` returns `True`.</span></span> <span data-ttu-id="23a33-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="23a33-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a><span data-ttu-id="23a33-111">二項論理演算子</span><span class="sxs-lookup"><span data-stu-id="23a33-111">Binary Logical Operators</span></span>  
 <span data-ttu-id="23a33-112">[And 演算子](../../../../visual-basic/language-reference/operators/and-operator.md)は、2つの `Boolean` 式の論理*積*を実行します。</span><span class="sxs-lookup"><span data-stu-id="23a33-112">The [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md) performs logical *conjunction* on two `Boolean` expressions.</span></span> <span data-ttu-id="23a33-113">両方の式が `True`に評価される場合、`And` は `True`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-113">If both expressions evaluate to `True`, then `And` returns `True`.</span></span> <span data-ttu-id="23a33-114">少なくとも1つの式が `False`に評価された場合、`And` は `False`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-114">If at least one of the expressions evaluates to `False`, then `And` returns `False`.</span></span>  
  
 <span data-ttu-id="23a33-115">[Or 演算子](../../../../visual-basic/language-reference/operators/or-operator.md)は、2つの `Boolean` 式に論理*和* *を実行*します。</span><span class="sxs-lookup"><span data-stu-id="23a33-115">The [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) performs logical *disjunction* or *inclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="23a33-116">いずれかの式が `True`に評価されるか、両方とも `True`に評価される場合、`Or` は `True`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-116">If either expression evaluates to `True`, or both evaluate to `True`, then `Or` returns `True`.</span></span> <span data-ttu-id="23a33-117">どちらの式も `True`に評価されない場合、`Or` は `False`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-117">If neither expression evaluates to `True`, `Or` returns `False`.</span></span>  
  
 <span data-ttu-id="23a33-118">[Xor 演算子](../../../../visual-basic/language-reference/operators/xor-operator.md)は、2つの `Boolean` 式に対して論理的な*除外*を実行します。</span><span class="sxs-lookup"><span data-stu-id="23a33-118">The [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md) performs logical *exclusion* on two `Boolean` expressions.</span></span> <span data-ttu-id="23a33-119">1つの式だけが `True`に評価され、両方ではない場合、`Xor` は `True`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-119">If exactly one expression evaluates to `True`, but not both, `Xor` returns `True`.</span></span> <span data-ttu-id="23a33-120">両方の式が `True` に評価されるか、両方とも `False`に評価される場合、`Xor` は `False`を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-120">If both expressions evaluate to `True` or both evaluate to `False`, `Xor` returns `False`.</span></span>  
  
 <span data-ttu-id="23a33-121">次の例は、`And`、`Or`、および `Xor` 演算子を示しています。</span><span class="sxs-lookup"><span data-stu-id="23a33-121">The following example illustrates the `And`, `Or`, and `Xor` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a><span data-ttu-id="23a33-122">ショートサーキット論理操作</span><span class="sxs-lookup"><span data-stu-id="23a33-122">Short-Circuiting Logical Operations</span></span>  
 <span data-ttu-id="23a33-123">[AndAlso 演算子](../../../../visual-basic/language-reference/operators/andalso-operator.md)は、2つの `Boolean` 式に対して論理積も実行するという点で、`And` 演算子と非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="23a33-123">The [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md) is very similar to the `And` operator, in that it also performs logical conjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="23a33-124">2つの間の主な違いは、`AndAlso` が*ショートサーキット*動作を示す点です。</span><span class="sxs-lookup"><span data-stu-id="23a33-124">The key difference between the two is that `AndAlso` exhibits *short-circuiting* behavior.</span></span> <span data-ttu-id="23a33-125">`AndAlso` 式の最初の式が `False`に評価される場合、最終的な結果を変更することはできず、`AndAlso` は `False`を返すため、2番目の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="23a33-125">If the first expression in an `AndAlso` expression evaluates to `False`, then the second expression is not evaluated because it cannot alter the final result, and `AndAlso` returns `False`.</span></span>  
  
 <span data-ttu-id="23a33-126">同様に、 [OrElse 演算子](../../../../visual-basic/language-reference/operators/orelse-operator.md)は、2つの `Boolean` 式のショートサーキット論理和を実行します。</span><span class="sxs-lookup"><span data-stu-id="23a33-126">Similarly, the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md) performs short-circuiting logical disjunction on two `Boolean` expressions.</span></span> <span data-ttu-id="23a33-127">`OrElse` 式の最初の式が `True`に評価される場合、最終的な結果を変更することはできず、`OrElse` は `True`を返すため、2番目の式は評価されません。</span><span class="sxs-lookup"><span data-stu-id="23a33-127">If the first expression in an `OrElse` expression evaluates to `True`, then the second expression is not evaluated because it cannot alter the final result, and `OrElse` returns `True`.</span></span>  
  
### <a name="short-circuiting-trade-offs"></a><span data-ttu-id="23a33-128">ショートサーキットトレードオフ</span><span class="sxs-lookup"><span data-stu-id="23a33-128">Short-Circuiting Trade-Offs</span></span>  
 <span data-ttu-id="23a33-129">ショートサーキットを使用すると、論理演算の結果を変更できない式を評価しないことで、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="23a33-129">Short-circuiting can improve performance by not evaluating an expression that cannot alter the result of the logical operation.</span></span> <span data-ttu-id="23a33-130">ただし、その式が追加のアクションを実行する場合、ショートサーキットはこれらのアクションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="23a33-130">However, if that expression performs additional actions, short-circuiting skips those actions.</span></span> <span data-ttu-id="23a33-131">たとえば、式に `Function` プロシージャへの呼び出しが含まれている場合、式がサーキットの場合、そのプロシージャは呼び出されず、`Function` に含まれる追加のコードは実行されません。</span><span class="sxs-lookup"><span data-stu-id="23a33-131">For example, if the expression includes a call to a `Function` procedure, that procedure is not called if the expression is short-circuited, and any additional code contained in the `Function` does not run.</span></span> <span data-ttu-id="23a33-132">このため、関数は、ときどき実行される場合があり、正しくテストされない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="23a33-132">Therefore, the function might run only occasionally, and might not be tested correctly.</span></span> <span data-ttu-id="23a33-133">または、プログラムロジックが `Function`のコードに依存している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="23a33-133">Or the program logic might depend on the code in the `Function`.</span></span>  
  
 <span data-ttu-id="23a33-134">次の例は、`And`、`Or`、および対応するショートサーキットの違いを示しています。</span><span class="sxs-lookup"><span data-stu-id="23a33-134">The following example illustrates the difference between `And`, `Or`, and their short-circuiting counterparts.</span></span>  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 <span data-ttu-id="23a33-135">前の例では、`checkIfValid()` 内のいくつかの重要なコードは、サーキットの呼び出しでは実行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="23a33-135">In the preceding example, note that some important code inside `checkIfValid()` does not run when the call is short-circuited.</span></span> <span data-ttu-id="23a33-136">最初の `If` ステートメントは、`And` がショートサーキットではないため、`12 > 45` が `False`を返す場合でも `checkIfValid()` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23a33-136">The first `If` statement calls `checkIfValid()` even though `12 > 45` returns `False`, because `And` does not short-circuit.</span></span> <span data-ttu-id="23a33-137">2番目の `If` ステートメントでは `checkIfValid()`が呼び出されません。これは、`12 > 45` が `False`を返し `AndAlso`、2番目の式をショートサーキットするためです。</span><span class="sxs-lookup"><span data-stu-id="23a33-137">The second `If` statement does not call `checkIfValid()`, because when `12 > 45` returns `False`, `AndAlso` short-circuits the second expression.</span></span> <span data-ttu-id="23a33-138">3番目の `If` ステートメントは、`Or` がショートサーキットではないため、`12 < 45` が `True`を返す場合でも `checkIfValid()` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="23a33-138">The third `If` statement calls `checkIfValid()` even though `12 < 45` returns `True`, because `Or` does not short-circuit.</span></span> <span data-ttu-id="23a33-139">4番目の `If` ステートメントでは `checkIfValid()`が呼び出されません。これは、`12 < 45` が `True`を返し `OrElse`、2番目の式をショートサーキットするためです。</span><span class="sxs-lookup"><span data-stu-id="23a33-139">The fourth `If` statement does not call `checkIfValid()`, because when `12 < 45` returns `True`, `OrElse` short-circuits the second expression.</span></span>  
  
## <a name="bitwise-operations"></a><span data-ttu-id="23a33-140">ビットごとの演算</span><span class="sxs-lookup"><span data-stu-id="23a33-140">Bitwise Operations</span></span>  
 <span data-ttu-id="23a33-141">ビットごとの演算では、2つの整数値が binary (base 2) 形式で評価されます。</span><span class="sxs-lookup"><span data-stu-id="23a33-141">Bitwise operations evaluate two integral values in binary (base 2) form.</span></span> <span data-ttu-id="23a33-142">これらは、対応する位置のビットを比較し、比較に基づいて値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23a33-142">They compare the bits at corresponding positions and then assign values based on the comparison.</span></span> <span data-ttu-id="23a33-143">`And` 演算子の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="23a33-143">The following example illustrates the `And` operator.</span></span>  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 <span data-ttu-id="23a33-144">前の例では、`x` の値を1に設定しています。</span><span class="sxs-lookup"><span data-stu-id="23a33-144">The preceding example sets the value of `x` to 1.</span></span> <span data-ttu-id="23a33-145">これは、次の理由で発生します。</span><span class="sxs-lookup"><span data-stu-id="23a33-145">This happens for the following reasons:</span></span>  
  
- <span data-ttu-id="23a33-146">値はバイナリとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="23a33-146">The values are treated as binary:</span></span>  
  
     <span data-ttu-id="23a33-147">3バイナリ形式の 3 = 011</span><span class="sxs-lookup"><span data-stu-id="23a33-147">3 in binary form = 011</span></span>  
  
     <span data-ttu-id="23a33-148">5バイナリ形式 = 101</span><span class="sxs-lookup"><span data-stu-id="23a33-148">5 in binary form = 101</span></span>  
  
- <span data-ttu-id="23a33-149">`And` 演算子は、一度に1つのバイナリ位置 (ビット) をバイナリ表現と比較します。</span><span class="sxs-lookup"><span data-stu-id="23a33-149">The `And` operator compares the binary representations, one binary position (bit) at a time.</span></span> <span data-ttu-id="23a33-150">指定された位置にある両方のビットが1の場合、結果内のその位置に1が配置されます。</span><span class="sxs-lookup"><span data-stu-id="23a33-150">If both bits at a given position are 1, then a 1 is placed in that position in the result.</span></span> <span data-ttu-id="23a33-151">どちらかのビットが0の場合は、結果内のその位置に0が配置されます。</span><span class="sxs-lookup"><span data-stu-id="23a33-151">If either bit is 0, then a 0 is placed in that position in the result.</span></span> <span data-ttu-id="23a33-152">前の例では、これは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="23a33-152">In the preceding example this works out as follows:</span></span>  
  
     <span data-ttu-id="23a33-153">011 (バイナリ形式の場合は 3)</span><span class="sxs-lookup"><span data-stu-id="23a33-153">011 (3 in binary form)</span></span>  
  
     <span data-ttu-id="23a33-154">101 (バイナリ形式で 5)</span><span class="sxs-lookup"><span data-stu-id="23a33-154">101 (5 in binary form)</span></span>  
  
     <span data-ttu-id="23a33-155">001 (バイナリ形式の結果)</span><span class="sxs-lookup"><span data-stu-id="23a33-155">001 (The result, in binary form)</span></span>  
  
- <span data-ttu-id="23a33-156">結果は decimal として扱われます。</span><span class="sxs-lookup"><span data-stu-id="23a33-156">The result is treated as decimal.</span></span> <span data-ttu-id="23a33-157">値001は1のバイナリ表現であるため、`x` = 1 です。</span><span class="sxs-lookup"><span data-stu-id="23a33-157">The value 001 is the binary representation of 1, so `x` = 1.</span></span>  
  
 <span data-ttu-id="23a33-158">ビットごとの `Or` 演算は似ていますが、比較対象のビットのいずれかまたは両方が1の場合、結果ビットに1が割り当てられる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="23a33-158">The bitwise `Or` operation is similar, except that a 1 is assigned to the result bit if either or both of the compared bits is 1.</span></span> <span data-ttu-id="23a33-159">比較したビットの1つ (両方ではない) が1の場合、`Xor` は結果ビットに1を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23a33-159">`Xor` assigns a 1 to the result bit if exactly one of the compared bits (not both) is 1.</span></span> <span data-ttu-id="23a33-160">`Not` は1つのオペランドを受け取り、符号ビットを含むすべてのビットを反転し、その値を結果に代入します。</span><span class="sxs-lookup"><span data-stu-id="23a33-160">`Not` takes a single operand and inverts all the bits, including the sign bit, and assigns that value to the result.</span></span> <span data-ttu-id="23a33-161">つまり、符号付き正の数値の場合、`Not` は常に負の値を返します。負の数値の場合、`Not` は常に正の値または0を返します。</span><span class="sxs-lookup"><span data-stu-id="23a33-161">This means that for signed positive numbers, `Not` always returns a negative value, and for negative numbers, `Not` always returns a positive or zero value.</span></span>  
  
 <span data-ttu-id="23a33-162">`AndAlso` 演算子と `OrElse` 演算子では、ビットごとの演算がサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23a33-162">The `AndAlso` and `OrElse` operators do not support bitwise operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23a33-163">ビットごとの演算は、整数型に対してのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="23a33-163">Bitwise operations can be performed on integral types only.</span></span> <span data-ttu-id="23a33-164">浮動小数点値は、ビットごとの演算を続行する前に、整数型に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23a33-164">Floating-point values must be converted to integral types before bitwise operation can proceed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a33-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="23a33-165">See also</span></span>

- [<span data-ttu-id="23a33-166">論理/ビット演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23a33-166">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [<span data-ttu-id="23a33-167">ブール式</span><span class="sxs-lookup"><span data-stu-id="23a33-167">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="23a33-168">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="23a33-168">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="23a33-169">Visual Basic の比較演算子</span><span class="sxs-lookup"><span data-stu-id="23a33-169">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="23a33-170">Visual Basic での連結演算子</span><span class="sxs-lookup"><span data-stu-id="23a33-170">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="23a33-171">演算子の効率のよい組み合わせ</span><span class="sxs-lookup"><span data-stu-id="23a33-171">Efficient Combination of Operators</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
