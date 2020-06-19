---
title: 比較演算子
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: bcd51d70c5c7bd08991c7433e244316a82daa9da
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371792"
---
# <a name="comparison-operators-visual-basic"></a><span data-ttu-id="d6448-102">比較演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6448-102">Comparison Operators (Visual Basic)</span></span>
<span data-ttu-id="d6448-103">次に示すのは、Visual Basic で定義されている比較演算子です。</span><span class="sxs-lookup"><span data-stu-id="d6448-103">The following are the comparison operators defined in Visual Basic.</span></span>

 <span data-ttu-id="d6448-104">`<` 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-104">`<` operator</span></span>

 <span data-ttu-id="d6448-105">`<=` 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-105">`<=` operator</span></span>

 <span data-ttu-id="d6448-106">`>` 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-106">`>` operator</span></span>

 <span data-ttu-id="d6448-107">`>=` 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-107">`>=` operator</span></span>

 <span data-ttu-id="d6448-108">`=` 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-108">`=` operator</span></span>

 <span data-ttu-id="d6448-109">`<>` 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-109">`<>` operator</span></span>

 [<span data-ttu-id="d6448-110">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-110">Is Operator</span></span>](is-operator.md)

 [<span data-ttu-id="d6448-111">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-111">IsNot Operator</span></span>](isnot-operator.md)

 [<span data-ttu-id="d6448-112">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-112">Like Operator</span></span>](like-operator.md)

 <span data-ttu-id="d6448-113">これらの演算子は、2 つの式を比較して、両者が等しいかどうかを判断します。等しくない場合は、両者がどのように異なるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d6448-113">These operators compare two expressions to determine whether or not they are equal, and if not, how they differ.</span></span> <span data-ttu-id="d6448-114">`Is`、`IsNot`、`Like` の詳細については、それぞれのヘルプ ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6448-114">`Is`, `IsNot`, and `Like` are discussed in detail on separate Help pages.</span></span> <span data-ttu-id="d6448-115">このページでは、関係比較演算子について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d6448-115">The relational comparison operators are discussed in detail on this page.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6448-116">構文</span><span class="sxs-lookup"><span data-stu-id="d6448-116">Syntax</span></span>
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="d6448-117">指定項目</span><span class="sxs-lookup"><span data-stu-id="d6448-117">Parts</span></span>
 `result`  
 <span data-ttu-id="d6448-118">必須です。</span><span class="sxs-lookup"><span data-stu-id="d6448-118">Required.</span></span> <span data-ttu-id="d6448-119">比較の結果を表す `Boolean` 値です。</span><span class="sxs-lookup"><span data-stu-id="d6448-119">A `Boolean` value representing the result of the comparison.</span></span>

 <span data-ttu-id="d6448-120">`expression1`、`expression2`</span><span class="sxs-lookup"><span data-stu-id="d6448-120">`expression1`, `expression2`</span></span>  
 <span data-ttu-id="d6448-121">必須です。</span><span class="sxs-lookup"><span data-stu-id="d6448-121">Required.</span></span> <span data-ttu-id="d6448-122">任意の式。</span><span class="sxs-lookup"><span data-stu-id="d6448-122">Any expression.</span></span>

 `comparisonoperator`  
 <span data-ttu-id="d6448-123">必須です。</span><span class="sxs-lookup"><span data-stu-id="d6448-123">Required.</span></span> <span data-ttu-id="d6448-124">いずれかの関係比較演算子です。</span><span class="sxs-lookup"><span data-stu-id="d6448-124">Any relational comparison operator.</span></span>

 <span data-ttu-id="d6448-125">`object1`、`object2`</span><span class="sxs-lookup"><span data-stu-id="d6448-125">`object1`, `object2`</span></span>  
 <span data-ttu-id="d6448-126">必須です。</span><span class="sxs-lookup"><span data-stu-id="d6448-126">Required.</span></span> <span data-ttu-id="d6448-127">いずれかの参照オブジェクト名です。</span><span class="sxs-lookup"><span data-stu-id="d6448-127">Any reference object names.</span></span>

 `string`  
 <span data-ttu-id="d6448-128">必須です。</span><span class="sxs-lookup"><span data-stu-id="d6448-128">Required.</span></span> <span data-ttu-id="d6448-129">任意のブール型 ( `String` ) の式を指定します。</span><span class="sxs-lookup"><span data-stu-id="d6448-129">Any `String` expression.</span></span>

 `pattern`  
 <span data-ttu-id="d6448-130">必須です。</span><span class="sxs-lookup"><span data-stu-id="d6448-130">Required.</span></span> <span data-ttu-id="d6448-131">いずれかの `String` 式または文字の範囲です。</span><span class="sxs-lookup"><span data-stu-id="d6448-131">Any `String` expression or range of characters.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6448-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="d6448-132">Remarks</span></span>
 <span data-ttu-id="d6448-133">次の表に、関係比較演算子と、`result` が `True` か `False` かを決定する条件の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d6448-133">The following table contains a list of the relational comparison operators and the conditions that determine whether `result` is `True` or `False`.</span></span>

|<span data-ttu-id="d6448-134">演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-134">Operator</span></span>|<span data-ttu-id="d6448-135">`True`:</span><span class="sxs-lookup"><span data-stu-id="d6448-135">`True` if</span></span>|<span data-ttu-id="d6448-136">`False`:</span><span class="sxs-lookup"><span data-stu-id="d6448-136">`False` if</span></span>|
|--------------|---------------|----------------|
|<span data-ttu-id="d6448-137">`<` (より小さい)</span><span class="sxs-lookup"><span data-stu-id="d6448-137">`<` (Less than)</span></span>|`expression1` < `expression2`|`expression1` >= `expression2`|
|<span data-ttu-id="d6448-138">`<=` (以下)</span><span class="sxs-lookup"><span data-stu-id="d6448-138">`<=` (Less than or equal to)</span></span>|`expression1` <= `expression2`|`expression1` > `expression2`|
|<span data-ttu-id="d6448-139">`>` (より大きい)</span><span class="sxs-lookup"><span data-stu-id="d6448-139">`>` (Greater than)</span></span>|`expression1` > `expression2`|`expression1` <= `expression2`|
|<span data-ttu-id="d6448-140">`>=` (以上)</span><span class="sxs-lookup"><span data-stu-id="d6448-140">`>=` (Greater than or equal to)</span></span>|`expression1` >= `expression2`|`expression1` < `expression2`|
|<span data-ttu-id="d6448-141">`=` (等しい)</span><span class="sxs-lookup"><span data-stu-id="d6448-141">`=` (Equal to)</span></span>|`expression1` = `expression2`|`expression1` <> `expression2`|
|<span data-ttu-id="d6448-142">`<>` (等しくない)</span><span class="sxs-lookup"><span data-stu-id="d6448-142">`<>` (Not equal to)</span></span>|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> <span data-ttu-id="d6448-143">[= 演算子](assignment-operator.md)は、代入演算子としても使用されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-143">The [= Operator](assignment-operator.md) is also used as an assignment operator.</span></span>

 <span data-ttu-id="d6448-144">`Is` 演算子、`IsNot` 演算子、および `Like` 演算子には、前の表の演算子とは異なる特定の比較機能があります。</span><span class="sxs-lookup"><span data-stu-id="d6448-144">The `Is` operator, the `IsNot` operator, and the `Like` operator have specific comparison functionalities that differ from the operators in the preceding table.</span></span>

## <a name="comparing-numbers"></a><span data-ttu-id="d6448-145">数値の比較</span><span class="sxs-lookup"><span data-stu-id="d6448-145">Comparing Numbers</span></span>
 <span data-ttu-id="d6448-146">`Single` 型の式を `Double` 型のいずれかと比較すると、`Single` 式が `Double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-146">When you compare an expression of type `Single` to one of type `Double`, the `Single` expression is converted to `Double`.</span></span> <span data-ttu-id="d6448-147">この動作は Visual Basic 6 で見られる動作とは逆です。</span><span class="sxs-lookup"><span data-stu-id="d6448-147">This behavior is opposite to the behavior found in Visual Basic 6.</span></span>

 <span data-ttu-id="d6448-148">同様に、`Decimal` 型の式を `Single` 型、または `Double` 型の式と比較すると、`Decimal` 式が `Single` または `Double` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-148">Similarly, when you compare an expression of type `Decimal` to an expression of type `Single` or `Double`, the `Decimal` expression is converted to `Single` or `Double`.</span></span> <span data-ttu-id="d6448-149">`Decimal` 式の場合、1E-28 未満の小数値は失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6448-149">For `Decimal` expressions, any fractional value less than 1E-28 might be lost.</span></span> <span data-ttu-id="d6448-150">このような小数値の損失によって、2 つの値が等しくない場合でも等しいと見なされることがあります。</span><span class="sxs-lookup"><span data-stu-id="d6448-150">Such fractional value loss may cause two values to compare as equal when they are not.</span></span> <span data-ttu-id="d6448-151">このため、等値 (`=`) を使用して 2 つの浮動小数点変数を比較する場合は注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="d6448-151">For this reason, you should take care when using equality (`=`) to compare two floating-point variables.</span></span> <span data-ttu-id="d6448-152">2 つの数値の差の絶対値が許容範囲の最小値より小さいかどうかをテストする方が安全です。</span><span class="sxs-lookup"><span data-stu-id="d6448-152">It is safer to test whether the absolute value of the difference between the two numbers is less than a small acceptable tolerance.</span></span>

### <a name="floating-point-imprecision"></a><span data-ttu-id="d6448-153">浮動小数点おける誤差</span><span class="sxs-lookup"><span data-stu-id="d6448-153">Floating-point Imprecision</span></span>
 <span data-ttu-id="d6448-154">浮動小数点数を操作する場合、それらがメモリ内で常に正確な表現が使用されているとは限らないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d6448-154">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="d6448-155">これにより、値の比較や [Mod 演算子](mod-operator.md)などの特定の演算によって、予期しない結果につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6448-155">This could lead to unexpected results from certain operations, such as value comparison and the [Mod Operator](mod-operator.md).</span></span> <span data-ttu-id="d6448-156">詳細については、「[データ型のトラブルシューティング](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6448-156">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

## <a name="comparing-strings"></a><span data-ttu-id="d6448-157">文字列の比較</span><span class="sxs-lookup"><span data-stu-id="d6448-157">Comparing Strings</span></span>
 <span data-ttu-id="d6448-158">文字列を比較すると、文字列式はアルファベット順の並べ替え順序に基づいて評価されます。これは、`Option Compare` の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6448-158">When you compare strings, the string expressions are evaluated based on their alphabetical sort order, which depends on the `Option Compare` setting.</span></span>

 <span data-ttu-id="d6448-159">`Option Compare Binary` の文字列比較は、文字の内部バイナリ表現から派生した並べ替え順序に基づきます。</span><span class="sxs-lookup"><span data-stu-id="d6448-159">`Option Compare Binary` bases string comparisons on a sort order derived from the internal binary representations of the characters.</span></span> <span data-ttu-id="d6448-160">並べ替え順序はコード ページによって決まります。</span><span class="sxs-lookup"><span data-stu-id="d6448-160">The sort order is determined by the code page.</span></span> <span data-ttu-id="d6448-161">次の例は、一般的なバイナリの並べ替え順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="d6448-161">The following example shows a typical binary sort order.</span></span>

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 <span data-ttu-id="d6448-162">`Option Compare Text` の文字列比較は、アプリケーションのロケールによって決まる、大文字と小文字を区別しないテキストの並べ替え順序に基づきます。</span><span class="sxs-lookup"><span data-stu-id="d6448-162">`Option Compare Text` bases string comparisons on a case-insensitive, textual sort order determined by your application's locale.</span></span> <span data-ttu-id="d6448-163">前の例で `Option Compare Text` を設定して文字を並べ替えると、次のテキストの並べ替え順序が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-163">When you set `Option Compare Text` and sort the characters in the preceding example, the following text sort order applies:</span></span>

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a><span data-ttu-id="d6448-164">ロケール依存性</span><span class="sxs-lookup"><span data-stu-id="d6448-164">Locale Dependence</span></span>
 <span data-ttu-id="d6448-165">`Option Compare Text` を設定すると、文字列比較の結果が、アプリケーションが実行されているロケールによって変わる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6448-165">When you set `Option Compare Text`, the result of a string comparison can depend on the locale in which the application is running.</span></span> <span data-ttu-id="d6448-166">2 文字の比較では、あるロケールで等しくても、別のロケールでは等しくならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d6448-166">Two characters might compare as equal in one locale but not in another.</span></span> <span data-ttu-id="d6448-167">ログオン試行を受け入れるかどうかなど、重要な決定を行うために文字列比較を使用している場合は、ロケールの感度に関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-167">If you are using a string comparison to make important decisions, such as whether to accept an attempt to log on, you should be alert to locale sensitivity.</span></span> <span data-ttu-id="d6448-168">`Option Compare Binary` を設定するか、ロケールを考慮する <xref:Microsoft.VisualBasic.Strings.StrComp%2A> を呼び出すことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d6448-168">Consider either setting `Option Compare Binary` or calling the <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, which takes the locale into account.</span></span>

## <a name="typeless-programming-with-relational-comparison-operators"></a><span data-ttu-id="d6448-169">関係比較演算子を使用した型宣言を省略したプログラミング</span><span class="sxs-lookup"><span data-stu-id="d6448-169">Typeless Programming with Relational Comparison Operators</span></span>
 <span data-ttu-id="d6448-170">`Object` 式での関係比較演算子の使用は、`Option Strict On` では許可されていません。</span><span class="sxs-lookup"><span data-stu-id="d6448-170">The use of relational comparison operators with `Object` expressions is not allowed under `Option Strict On`.</span></span> <span data-ttu-id="d6448-171">`Option Strict` が `Off` であり、`expression1` または `expression2` が `Object` 式の場合、実行時の型によって比較方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="d6448-171">When `Option Strict` is `Off`, and either `expression1` or `expression2` is an `Object` expression, the run-time types determine how they are compared.</span></span> <span data-ttu-id="d6448-172">次の表に、オペランドの実行時の型に応じた、式の比較方法と比較結果を示します。</span><span class="sxs-lookup"><span data-stu-id="d6448-172">The following table shows how the expressions are compared and the result from the comparison, depending on the runtime type of the operands.</span></span>

|<span data-ttu-id="d6448-173">オペランドが次の場合</span><span class="sxs-lookup"><span data-stu-id="d6448-173">If operands are</span></span>|<span data-ttu-id="d6448-174">比較</span><span class="sxs-lookup"><span data-stu-id="d6448-174">Comparison is</span></span>|
|---------------------|-------------------|
|<span data-ttu-id="d6448-175">両方とも `String`</span><span class="sxs-lookup"><span data-stu-id="d6448-175">Both `String`</span></span>|<span data-ttu-id="d6448-176">文字列の並べ替え特性に基づいて比較を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d6448-176">Sort comparison based on string sorting characteristics.</span></span>|
|<span data-ttu-id="d6448-177">両方とも数値</span><span class="sxs-lookup"><span data-stu-id="d6448-177">Both numeric</span></span>|<span data-ttu-id="d6448-178">オブジェクトが `Double` に変換され、数値比較が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-178">Objects converted to `Double`, numeric comparison.</span></span>|
|<span data-ttu-id="d6448-179">1 つが数値、1 つが `String`</span><span class="sxs-lookup"><span data-stu-id="d6448-179">One numeric and one `String`</span></span>|<span data-ttu-id="d6448-180">`String` は `Double` に変換され、数値比較が実行されます。</span><span class="sxs-lookup"><span data-stu-id="d6448-180">The `String` is converted to a `Double` and numeric comparison is performed.</span></span> <span data-ttu-id="d6448-181">`String` を `Double` に変換できない場合、<xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d6448-181">If the `String` cannot be converted to `Double`, an <xref:System.InvalidCastException> is thrown.</span></span>|
|<span data-ttu-id="d6448-182">一方または両方が `String` 以外の参照型</span><span class="sxs-lookup"><span data-stu-id="d6448-182">Either or both are reference types other than `String`</span></span>|<span data-ttu-id="d6448-183"><xref:System.InvalidCastException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d6448-183">An <xref:System.InvalidCastException> is thrown.</span></span>|

 <span data-ttu-id="d6448-184">数値比較では、`Nothing` を 0 として扱います。</span><span class="sxs-lookup"><span data-stu-id="d6448-184">Numeric comparisons treat `Nothing` as 0.</span></span> <span data-ttu-id="d6448-185">文字列比較では、`Nothing` を `""` (空の文字列) として扱います。</span><span class="sxs-lookup"><span data-stu-id="d6448-185">String comparisons treat `Nothing` as `""` (an empty string).</span></span>

## <a name="overloading"></a><span data-ttu-id="d6448-186">オーバーロード</span><span class="sxs-lookup"><span data-stu-id="d6448-186">Overloading</span></span>
 <span data-ttu-id="d6448-187">関係比較演算子 (`<`、</span><span class="sxs-lookup"><span data-stu-id="d6448-187">The relational comparison operators (`<`.</span></span> <span data-ttu-id="d6448-188">`<=`、`>`、`>=`、`=`、`<>`) は "*オーバーロード*" できます。つまり、オペランドがクラスまたは構造体の型を持っているときに、そのクラスまたは構造体は動作を再定義できます。</span><span class="sxs-lookup"><span data-stu-id="d6448-188">`<=`, `>`, `>=`, `=`, `<>`) can be *overloaded*, which means that a class or structure can redefine their behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="d6448-189">コードで、そのようなクラスまたは構造体に対してこれらの演算子が使用される場合は、再定義された動作を理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="d6448-189">If your code uses any of these operators on such a class or structure, be sure you understand the redefined behavior.</span></span> <span data-ttu-id="d6448-190">詳細については、「 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6448-190">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>

 <span data-ttu-id="d6448-191">[= 演算子](assignment-operator.md)は、代入演算子としてではなく、関係比較演算子としてのみオーバーロードできます。</span><span class="sxs-lookup"><span data-stu-id="d6448-191">Notice that the [= Operator](assignment-operator.md) can be overloaded only as a relational comparison operator, not as an assignment operator.</span></span>

## <a name="example"></a><span data-ttu-id="d6448-192">例</span><span class="sxs-lookup"><span data-stu-id="d6448-192">Example</span></span>
 <span data-ttu-id="d6448-193">次の例は、式を比較するために使用する関係比較演算子のさまざまな用途を示します。</span><span class="sxs-lookup"><span data-stu-id="d6448-193">The following example shows various uses of relational comparison operators, which you use to compare expressions.</span></span> <span data-ttu-id="d6448-194">関係比較演算子は、記述された式が `True` に評価されるかどうかを表す `Boolean` の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d6448-194">Relational comparison operators return a `Boolean` result that represents whether or not the stated expression evaluates to `True`.</span></span> <span data-ttu-id="d6448-195">文字列に `>` 演算子と `<` 演算子を適用すると、文字列の通常のアルファベット順の並べ替え順序を使用して比較が行われます。</span><span class="sxs-lookup"><span data-stu-id="d6448-195">When you apply the `>` and `<` operators to strings, the comparison is made using the normal alphabetical sorting order of the strings.</span></span> <span data-ttu-id="d6448-196">この順序は、ロケールの設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6448-196">This order can be dependent on your locale setting.</span></span> <span data-ttu-id="d6448-197">並べ替えで大文字と小文字を区別するかどうかは、[Option Compare](../statements/option-compare-statement.md) の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d6448-197">Whether the sort is case-sensitive or not depends on the [Option Compare](../statements/option-compare-statement.md) setting.</span></span>

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 <span data-ttu-id="d6448-198">前の例では、最初の比較によって `False` が返され、残りの比較で `True` が返されています。</span><span class="sxs-lookup"><span data-stu-id="d6448-198">In the preceding example, the first comparison returns `False` and the remaining comparisons return `True`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6448-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="d6448-199">See also</span></span>

- <xref:System.InvalidCastException>
- [<span data-ttu-id="d6448-200">= 演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-200">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="d6448-201">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="d6448-201">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="d6448-202">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="d6448-202">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="d6448-203">トラブルシューティング (データ型)</span><span class="sxs-lookup"><span data-stu-id="d6448-203">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="d6448-204">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="d6448-204">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
