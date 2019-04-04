---
title: Visual Basic における比較演算子
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: d08974a929a723d4037300f9d72ae03c072d47fa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826159"
---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="043df-102">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="043df-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="043df-103">比較演算子は 2 つの式を比較し、`Boolean`これらの値のリレーションシップを表す値。</span><span class="sxs-lookup"><span data-stu-id="043df-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="043df-104">数値、文字列、比較演算子、およびオブジェクトの比較演算子を比較するための演算子があります。</span><span class="sxs-lookup"><span data-stu-id="043df-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="043df-105">すべての 3 種類の演算子はここで説明します。</span><span class="sxs-lookup"><span data-stu-id="043df-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="043df-106">数値の値を比較します。</span><span class="sxs-lookup"><span data-stu-id="043df-106">Comparing Numeric Values</span></span>  
 <span data-ttu-id="043df-107">Visual Basic では、6 つの数値の比較演算子を使用して数値の値を比較します。</span><span class="sxs-lookup"><span data-stu-id="043df-107">Visual Basic compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="043df-108">各演算子はオペランドとして数値に評価される 2 つの式を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="043df-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="043df-109">次の表では、演算子の一覧し、それぞれの例を示します。</span><span class="sxs-lookup"><span data-stu-id="043df-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="043df-110">演算子</span><span class="sxs-lookup"><span data-stu-id="043df-110">Operator</span></span>|<span data-ttu-id="043df-111">テスト条件</span><span class="sxs-lookup"><span data-stu-id="043df-111">Condition tested</span></span>|<span data-ttu-id="043df-112">使用例</span><span class="sxs-lookup"><span data-stu-id="043df-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="043df-113">`=` (等価)</span><span class="sxs-lookup"><span data-stu-id="043df-113">`=` (Equality)</span></span>|<span data-ttu-id="043df-114">最初の式と等しい値を 2 番目の値とは</span><span class="sxs-lookup"><span data-stu-id="043df-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="043df-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="043df-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="043df-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="043df-118">`<>` (非等値)</span><span class="sxs-lookup"><span data-stu-id="043df-118">`<>` (Inequality)</span></span>|<span data-ttu-id="043df-119">最初の式の値と等しく、2 つ目の値か。</span><span class="sxs-lookup"><span data-stu-id="043df-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="043df-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="043df-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="043df-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="043df-123">`<` (より小さい)</span><span class="sxs-lookup"><span data-stu-id="043df-123">`<` (Less than)</span></span>|<span data-ttu-id="043df-124">最初の式の値より小さく、2 つ目の値とは</span><span class="sxs-lookup"><span data-stu-id="043df-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="043df-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="043df-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="043df-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="043df-128">`>` (より大きい)</span><span class="sxs-lookup"><span data-stu-id="043df-128">`>` (Greater than)</span></span>|<span data-ttu-id="043df-129">最初の式の値は、2 つ目の値よりも大きいですか。</span><span class="sxs-lookup"><span data-stu-id="043df-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="043df-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="043df-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="043df-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="043df-133">`<=` (に等しいまたはそれよりも小さい)</span><span class="sxs-lookup"><span data-stu-id="043df-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="043df-134">最初の式の値を 2 番目の値未満ですか。</span><span class="sxs-lookup"><span data-stu-id="043df-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="043df-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="043df-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="043df-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="043df-138">`>=` (より大きいまたは等しい)</span><span class="sxs-lookup"><span data-stu-id="043df-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="043df-139">最初の式の値が 2 番目の値以上か。</span><span class="sxs-lookup"><span data-stu-id="043df-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="043df-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="043df-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="043df-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="043df-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="043df-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="043df-143">文字列の比較</span><span class="sxs-lookup"><span data-stu-id="043df-143">Comparing Strings</span></span>  
 <span data-ttu-id="043df-144">Visual Basic を使用して文字列を比較し、 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)数値比較演算子とします。</span><span class="sxs-lookup"><span data-stu-id="043df-144">Visual Basic compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="043df-145">`Like`演算子を使用するパターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="043df-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="043df-146">文字列を比較し、パターンと一致した場合、結果は`True`します。</span><span class="sxs-lookup"><span data-stu-id="043df-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="043df-147">それ以外の場合、結果は `False` です。</span><span class="sxs-lookup"><span data-stu-id="043df-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="043df-148">数値演算子では、比較できます。`String`として次の例は、値が並べ替え順序に基づいています。</span><span class="sxs-lookup"><span data-stu-id="043df-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="043df-149">上記の例では、結果は`True`のため、2 番目の文字列の最初の文字の前に、最初の文字列の最初の文字を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="043df-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="043df-150">最初の文字と等しい場合は、比較は、両方の文字列では、次の文字を続けるし、などです。</span><span class="sxs-lookup"><span data-stu-id="043df-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="043df-151">次の例のように、等値演算子を使用して文字列の等価性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="043df-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="043df-152">1 つの文字列が"aa"と"aaa"など、別のプレフィックスである場合より長い文字列が短い文字列より大きいと見なされます。</span><span class="sxs-lookup"><span data-stu-id="043df-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="043df-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="043df-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="043df-154">並べ替え順序がバイナリの比較またはテキストの比較の設定に応じてのいずれかに基づいて`Option Compare`します。</span><span class="sxs-lookup"><span data-stu-id="043df-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="043df-155">詳細については、[Option Compare ステートメント](../../../../visual-basic/language-reference/statements/option-compare-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="043df-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="043df-156">オブジェクトの比較</span><span class="sxs-lookup"><span data-stu-id="043df-156">Comparing Objects</span></span>  
 <span data-ttu-id="043df-157">Visual Basic での 2 つのオブジェクト参照変数を比較し、 [Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)と[IsNot 演算子](../../../../visual-basic/language-reference/operators/isnot-operator.md)します。</span><span class="sxs-lookup"><span data-stu-id="043df-157">Visual Basic compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="043df-158">2 つの参照変数が同じオブジェクト インスタンスを参照している場合を判断するには、これらの演算子のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="043df-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="043df-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="043df-159">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 <span data-ttu-id="043df-160">前の例では、`x Is y`に評価される`True`、両方の変数が同じインスタンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="043df-160">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="043df-161">この結果を次の例と比較します。</span><span class="sxs-lookup"><span data-stu-id="043df-161">Contrast this result with the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 <span data-ttu-id="043df-162">前の例では、`x Is y`に評価される`False`、その型の異なるインスタンスに、同じ型のオブジェクトへの参照を変数が参照しているためです。</span><span class="sxs-lookup"><span data-stu-id="043df-162">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="043df-163">同じインスタンスを指していない 2 つのオブジェクトをテストする場合に、`IsNot`演算子の文法的に「不器用な組み合わせを回避しますできます。`Not`と`Is`します。</span><span class="sxs-lookup"><span data-stu-id="043df-163">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="043df-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="043df-164">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 <span data-ttu-id="043df-165">前の例では、`If a IsNot b`と等価`If Not a Is b`します。</span><span class="sxs-lookup"><span data-stu-id="043df-165">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="043df-166">オブジェクトの型の比較</span><span class="sxs-lookup"><span data-stu-id="043df-166">Comparing Object Type</span></span>  
 <span data-ttu-id="043df-167">特定の種類のオブジェクトがあるかどうかをテストすることができます、 `TypeOf`.`Is`式。</span><span class="sxs-lookup"><span data-stu-id="043df-167">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="043df-168">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="043df-168">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="043df-169">ときに`typename`インターフェイス型を指定します、 `TypeOf`.`Is`式を返します`True`オブジェクトがインターフェイス型を実装している場合。</span><span class="sxs-lookup"><span data-stu-id="043df-169">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="043df-170">ときに`typename`式を返しますが、クラス型`True`場合は、オブジェクトは、指定したクラスのまたは指定したクラスから派生したクラスのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="043df-170">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="043df-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="043df-171">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 <span data-ttu-id="043df-172">前の例では、`TypeOf x Is Control`式に評価されます`True`ための種類`x`は`Button`から継承される`Control`します。</span><span class="sxs-lookup"><span data-stu-id="043df-172">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="043df-173">詳細については、[TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="043df-173">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043df-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="043df-174">See also</span></span>

- [<span data-ttu-id="043df-175">値の比較</span><span class="sxs-lookup"><span data-stu-id="043df-175">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="043df-176">比較演算子</span><span class="sxs-lookup"><span data-stu-id="043df-176">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="043df-177">演算子</span><span class="sxs-lookup"><span data-stu-id="043df-177">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="043df-178">Visual Basic における算術演算子</span><span class="sxs-lookup"><span data-stu-id="043df-178">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="043df-179">Visual Basic の連結演算子</span><span class="sxs-lookup"><span data-stu-id="043df-179">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="043df-180">Visual Basic での論理とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="043df-180">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
