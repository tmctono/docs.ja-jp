---
title: 比較演算子
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
ms.openlocfilehash: e1feb08539e47ec6fda64aa1a1f8ec2cc19f7b62
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346067"
---
# <a name="comparison-operators-in-visual-basic"></a><span data-ttu-id="7d992-102">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-102">Comparison Operators in Visual Basic</span></span>
<span data-ttu-id="7d992-103">比較演算子は、2つの式を比較し、値の関係を表す `Boolean` 値を返します。</span><span class="sxs-lookup"><span data-stu-id="7d992-103">Comparison operators compare two expressions and return a `Boolean` value that represents the relationship of their values.</span></span> <span data-ttu-id="7d992-104">数値を比較するための演算子、文字列を比較するための演算子、およびオブジェクトを比較するための演算子があります。</span><span class="sxs-lookup"><span data-stu-id="7d992-104">There are operators for comparing numeric values, operators for comparing strings, and operators for comparing objects.</span></span> <span data-ttu-id="7d992-105">ここでは、3種類の演算子について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d992-105">All three types of operators are discussed herein.</span></span>  
  
## <a name="comparing-numeric-values"></a><span data-ttu-id="7d992-106">数値の比較</span><span class="sxs-lookup"><span data-stu-id="7d992-106">Comparing Numeric Values</span></span>  
 <span data-ttu-id="7d992-107">Visual Basic は、6つの数値比較演算子を使用して数値を比較します。</span><span class="sxs-lookup"><span data-stu-id="7d992-107">Visual Basic compares numeric values using six numeric comparison operators.</span></span> <span data-ttu-id="7d992-108">各演算子は、オペランドとして、数値に評価される2つの式を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7d992-108">Each operator takes as operands two expressions that evaluate to numeric values.</span></span> <span data-ttu-id="7d992-109">次の表に、演算子の一覧とそれぞれの例を示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-109">The following table lists the operators and shows examples of each.</span></span>  
  
|<span data-ttu-id="7d992-110">演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-110">Operator</span></span>|<span data-ttu-id="7d992-111">テストされた条件</span><span class="sxs-lookup"><span data-stu-id="7d992-111">Condition tested</span></span>|<span data-ttu-id="7d992-112">使用例</span><span class="sxs-lookup"><span data-stu-id="7d992-112">Examples</span></span>|  
|--------------|----------------------|--------------|  
|<span data-ttu-id="7d992-113">`=` (等しい)</span><span class="sxs-lookup"><span data-stu-id="7d992-113">`=` (Equality)</span></span>|<span data-ttu-id="7d992-114">最初の式の値が2番目の式の値と等しいかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-114">Is the value of the first expression equal to the value of the second?</span></span>|<span data-ttu-id="7d992-115">`23`   `=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-115">`23`   `=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="7d992-116">`23`   `=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-116">`23`   `=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="7d992-117">`23`   `=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-117">`23`   `=`   `12    ' False`</span></span>|  
|<span data-ttu-id="7d992-118">`<>` (非等値)</span><span class="sxs-lookup"><span data-stu-id="7d992-118">`<>` (Inequality)</span></span>|<span data-ttu-id="7d992-119">最初の式の値が2番目の式の値と等しくないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d992-119">Is the value of the first expression unequal to the value of the second?</span></span>|<span data-ttu-id="7d992-120">`23`   `<>`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-120">`23`   `<>`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="7d992-121">`23`   `<>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-121">`23`   `<>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="7d992-122">`23`   `<>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-122">`23`   `<>`   `12    ' True`</span></span>|  
|<span data-ttu-id="7d992-123">`<` (より小さい)</span><span class="sxs-lookup"><span data-stu-id="7d992-123">`<` (Less than)</span></span>|<span data-ttu-id="7d992-124">最初の式の値が2番目の式の値より小さいかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-124">Is the value of the first expression less than the value of the second?</span></span>|<span data-ttu-id="7d992-125">`23`   `<`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-125">`23`   `<`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="7d992-126">`23`   `<`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-126">`23`   `<`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="7d992-127">`23`   `<`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-127">`23`   `<`   `12    ' False`</span></span>|  
|<span data-ttu-id="7d992-128">`>` (より大きい)</span><span class="sxs-lookup"><span data-stu-id="7d992-128">`>` (Greater than)</span></span>|<span data-ttu-id="7d992-129">最初の式の値が2番目の式の値より大きいかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-129">Is the value of the first expression greater than the value of the second?</span></span>|<span data-ttu-id="7d992-130">`23`   `>`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-130">`23`   `>`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="7d992-131">`23`   `>`   `23    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-131">`23`   `>`   `23    ' False`</span></span><br /><br /> <span data-ttu-id="7d992-132">`23`   `>`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-132">`23`   `>`   `12    ' True`</span></span>|  
|<span data-ttu-id="7d992-133">`<=` (以下)</span><span class="sxs-lookup"><span data-stu-id="7d992-133">`<=` (Less than or equal to)</span></span>|<span data-ttu-id="7d992-134">最初の式の値が2番目の式の値以下であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-134">Is the value of the first expression less than or equal to the value of the second?</span></span>|<span data-ttu-id="7d992-135">`23`   `<=`   `33    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-135">`23`   `<=`   `33    ' True`</span></span><br /><br /> <span data-ttu-id="7d992-136">`23`   `<=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-136">`23`   `<=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="7d992-137">`23`   `<=`   `12    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-137">`23`   `<=`   `12    ' False`</span></span>|  
|<span data-ttu-id="7d992-138">`>=` (以上)</span><span class="sxs-lookup"><span data-stu-id="7d992-138">`>=` (Greater than or equal to)</span></span>|<span data-ttu-id="7d992-139">最初の式の値が2番目の式の値以上であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-139">Is the value of the first expression greater than or equal to the value of the second?</span></span>|<span data-ttu-id="7d992-140">`23`   `>=`   `33    ' False`</span><span class="sxs-lookup"><span data-stu-id="7d992-140">`23`   `>=`   `33    ' False`</span></span><br /><br /> <span data-ttu-id="7d992-141">`23`   `>=`   `23    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-141">`23`   `>=`   `23    ' True`</span></span><br /><br /> <span data-ttu-id="7d992-142">`23`   `>=`   `12    ' True`</span><span class="sxs-lookup"><span data-stu-id="7d992-142">`23`   `>=`   `12    ' True`</span></span>|  
  
## <a name="comparing-strings"></a><span data-ttu-id="7d992-143">文字列の比較</span><span class="sxs-lookup"><span data-stu-id="7d992-143">Comparing Strings</span></span>  
 <span data-ttu-id="7d992-144">Visual Basic は、 [Like 演算子](../../../../visual-basic/language-reference/operators/like-operator.md)および数値比較演算子を使用して文字列を比較します。</span><span class="sxs-lookup"><span data-stu-id="7d992-144">Visual Basic compares strings using the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md) as well as the numeric comparison operators.</span></span> <span data-ttu-id="7d992-145">`Like` 演算子を使用すると、パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7d992-145">The `Like` operator allows you to specify a pattern.</span></span> <span data-ttu-id="7d992-146">次に、文字列がパターンと比較され、一致する場合は結果が `True`されます。</span><span class="sxs-lookup"><span data-stu-id="7d992-146">The string is then compared against the pattern, and if it matches, the result is `True`.</span></span> <span data-ttu-id="7d992-147">それ以外の場合、結果は `False` です。</span><span class="sxs-lookup"><span data-stu-id="7d992-147">Otherwise, the result is `False`.</span></span> <span data-ttu-id="7d992-148">数値演算子を使用すると、次の例に示すように、並べ替え順序に基づいて `String` 値を比較できます。</span><span class="sxs-lookup"><span data-stu-id="7d992-148">The numeric operators allow you to compare `String` values based on their sort order, as the following example shows.</span></span>  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="7d992-149">最初の文字列の最初の文字が2番目の文字列の最初の文字の前にあるため、前の例の結果は `True` ます。</span><span class="sxs-lookup"><span data-stu-id="7d992-149">The result in the preceding example is `True` because the first character in the first string sorts before the first character in the second string.</span></span> <span data-ttu-id="7d992-150">最初の文字が等しい場合、比較は両方の文字列の次の文字に続きます。</span><span class="sxs-lookup"><span data-stu-id="7d992-150">If the first characters were equal, the comparison would continue to the next character in both strings, and so on.</span></span> <span data-ttu-id="7d992-151">次の例に示すように、等値演算子を使用して文字列の等価性をテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7d992-151">You can also test equality of strings using the equality operator, as the following example shows.</span></span>  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="7d992-152">1つの文字列が "aa" や "aaa" など、別の文字列のプレフィックスである場合、長い文字列は短い文字列よりも大きいと見なされます。</span><span class="sxs-lookup"><span data-stu-id="7d992-152">If one string is a prefix of another, such as "aa" and "aaa", the longer string is considered to be greater than the shorter string.</span></span> <span data-ttu-id="7d992-153">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-153">The following example illustrates this.</span></span>  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 <span data-ttu-id="7d992-154">並べ替え順序は、`Option Compare`の設定に応じて、バイナリ比較またはテキスト比較のいずれかに基づいています。</span><span class="sxs-lookup"><span data-stu-id="7d992-154">The sort order is based on either a binary comparison or a textual comparison depending on the setting of `Option Compare`.</span></span> <span data-ttu-id="7d992-155">詳細については、「 [Option Compare ステートメント](../../../../visual-basic/language-reference/statements/option-compare-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d992-155">For more information see [Option Compare Statement](../../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>  
  
## <a name="comparing-objects"></a><span data-ttu-id="7d992-156">オブジェクトの比較</span><span class="sxs-lookup"><span data-stu-id="7d992-156">Comparing Objects</span></span>  
 <span data-ttu-id="7d992-157">Visual Basic は、2つのオブジェクト参照変数を[Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)および[IsNot 演算子](../../../../visual-basic/language-reference/operators/isnot-operator.md)と比較します。</span><span class="sxs-lookup"><span data-stu-id="7d992-157">Visual Basic compares two object reference variables with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md).</span></span> <span data-ttu-id="7d992-158">これらの演算子のいずれかを使用して、2つの参照変数が同じオブジェクトインスタンスを参照しているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="7d992-158">You can use either of these operators to determine if two reference variables refer to the same object instance.</span></span> <span data-ttu-id="7d992-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-159">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 <span data-ttu-id="7d992-160">前の例では、両方の変数が同じインスタンスを参照しているため、`x Is y` は `True`に評価されます。</span><span class="sxs-lookup"><span data-stu-id="7d992-160">In the preceding example, `x Is y` evaluates to `True`, because both variables refer to the same instance.</span></span> <span data-ttu-id="7d992-161">次の例では、この結果を比較します。</span><span class="sxs-lookup"><span data-stu-id="7d992-161">Contrast this result with the following example.</span></span>  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 <span data-ttu-id="7d992-162">前の例では、`x Is y` は `False`に評価されます。これは、変数が同じ型のオブジェクトを参照しているにもかかわらず、その型の異なるインスタンスを参照しているためです。</span><span class="sxs-lookup"><span data-stu-id="7d992-162">In the preceding example, `x Is y` evaluates to `False`, because although the variables refer to objects of the same type, they refer to different instances of that type.</span></span>  
  
 <span data-ttu-id="7d992-163">同じインスタンスを指していない2つのオブジェクトをテストする場合、`IsNot` 演算子を使用すると、`Not` と `Is`の文法的ないくぶんの組み合わせを回避できます。</span><span class="sxs-lookup"><span data-stu-id="7d992-163">When you want to test for two objects not pointing to the same instance, the `IsNot` operator lets you avoid a grammatically clumsy combination of `Not` and `Is`.</span></span> <span data-ttu-id="7d992-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-164">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 <span data-ttu-id="7d992-165">前の例では、`If a IsNot b` は `If Not a Is b`と同じです。</span><span class="sxs-lookup"><span data-stu-id="7d992-165">In the preceding example, `If a IsNot b` is equivalent to `If Not a Is b`.</span></span>  
  
### <a name="comparing-object-type"></a><span data-ttu-id="7d992-166">オブジェクトの種類の比較</span><span class="sxs-lookup"><span data-stu-id="7d992-166">Comparing Object Type</span></span>  
 <span data-ttu-id="7d992-167">`TypeOf`...`Is` 式を使用して、オブジェクトが特定の型であるかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="7d992-167">You can test whether an object is of a particular type with the `TypeOf`...`Is` expression.</span></span> <span data-ttu-id="7d992-168">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7d992-168">The syntax is as follows:</span></span>  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 <span data-ttu-id="7d992-169">`typename` がインターフェイス型を指定する場合、オブジェクトがインターフェイス型を実装している場合、`TypeOf`...`Is` 式は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="7d992-169">When `typename` specifies an interface type, then the `TypeOf`...`Is` expression returns `True` if the object implements the interface type.</span></span> <span data-ttu-id="7d992-170">`typename` がクラス型の場合、オブジェクトが指定されたクラスのインスタンスであるか、または指定されたクラスから派生したクラスのインスタンスである場合、式は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="7d992-170">When `typename` is a class type, then the expression returns `True` if the object is an instance of the specified class or of a class that derives from the specified class.</span></span> <span data-ttu-id="7d992-171">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7d992-171">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 <span data-ttu-id="7d992-172">前の例では、`TypeOf x Is Control` 式が `True` に評価されます。これは、`x` の型が `Button`であり、`Control`から継承されているためです。</span><span class="sxs-lookup"><span data-stu-id="7d992-172">In the preceding example, the `TypeOf x Is Control` expression evaluates to `True` because the type of `x` is `Button`, which inherits from `Control`.</span></span>  
  
 <span data-ttu-id="7d992-173">詳細については、「 [TypeOf 演算子](../../../../visual-basic/language-reference/operators/typeof-operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d992-173">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d992-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d992-174">See also</span></span>

- [<span data-ttu-id="7d992-175">値の比較</span><span class="sxs-lookup"><span data-stu-id="7d992-175">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="7d992-176">比較演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-176">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="7d992-177">演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-177">Operators</span></span>](../../../../visual-basic/language-reference/operators/index.md)
- [<span data-ttu-id="7d992-178">Visual Basic の算術演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-178">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
- [<span data-ttu-id="7d992-179">Visual Basic での連結演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-179">Concatenation Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
- [<span data-ttu-id="7d992-180">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="7d992-180">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
