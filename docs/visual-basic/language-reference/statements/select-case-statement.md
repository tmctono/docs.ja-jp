---
title: Select...Case ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: d035118febc5ea9d1ea8e5cc0145cb030626b030
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583247"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="bff47-102">Select...Case ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bff47-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="bff47-103">式の値に応じて、いくつかのステートメントグループのうちの1つを実行します。</span><span class="sxs-lookup"><span data-stu-id="bff47-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bff47-104">構文</span><span class="sxs-lookup"><span data-stu-id="bff47-104">Syntax</span></span>  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="bff47-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="bff47-105">Parts</span></span>  
  
|<span data-ttu-id="bff47-106">用語</span><span class="sxs-lookup"><span data-stu-id="bff47-106">Term</span></span>|<span data-ttu-id="bff47-107">定義</span><span class="sxs-lookup"><span data-stu-id="bff47-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="bff47-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="bff47-108">Required.</span></span> <span data-ttu-id="bff47-109">条件.</span><span class="sxs-lookup"><span data-stu-id="bff47-109">Expression.</span></span> <span data-ttu-id="bff47-110">は、基本データ型 (`Boolean`、`Byte`、`Char`、`Date`、`Double`、`Decimal`、`Integer`、`Long`、`Object`、`SByte`、0、1 のいずれかに評価される必要があり 2、3、4、および 5)。</span><span class="sxs-lookup"><span data-stu-id="bff47-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="bff47-111">@No__t_0 ステートメントでは必須です。</span><span class="sxs-lookup"><span data-stu-id="bff47-111">Required in a `Case` statement.</span></span> <span data-ttu-id="bff47-112">@No__t_0 の一致値を表す式の句の一覧。</span><span class="sxs-lookup"><span data-stu-id="bff47-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="bff47-113">複数の式句は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="bff47-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="bff47-114">各句には、次のいずれかの形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bff47-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="bff47-115">-   *expression1* `To` *expression2*</span><span class="sxs-lookup"><span data-stu-id="bff47-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="bff47-116">-[`Is`] *comparisonoperator* *式*</span><span class="sxs-lookup"><span data-stu-id="bff47-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="bff47-117">-   *式*</span><span class="sxs-lookup"><span data-stu-id="bff47-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="bff47-118">@No__t_0 キーワードを使用して、`testexpression` の一致値の範囲の境界を指定します。</span><span class="sxs-lookup"><span data-stu-id="bff47-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="bff47-119">@No__t_0 の値は `expression2` の値以下である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bff47-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="bff47-120">比較演算子 (`=`、`<>`、`<`、`<=`、`>`、または `>=`) と共に `Is` キーワードを使用して、`testexpression` の一致値に制限を指定します。</span><span class="sxs-lookup"><span data-stu-id="bff47-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="bff47-121">@No__t_0 キーワードが指定されていない場合は、 *comparisonoperator*の前に自動的に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="bff47-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="bff47-122">@No__t_0 のみを指定するフォームは、`Is` 形式の特殊なケースとして扱われます。ここで、 *comparisonoperator*は等号 (`=`) です。</span><span class="sxs-lookup"><span data-stu-id="bff47-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="bff47-123">このフォームは `testexpression`  =  `expression` として評価されます。</span><span class="sxs-lookup"><span data-stu-id="bff47-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="bff47-124">@No__t_0 の式は、任意のデータ型にすることができます。 `testexpression` の型に暗黙的に変換可能であり、適切な `comparisonoperator` が使用されている2つの型に対して有効であることが条件となります。</span><span class="sxs-lookup"><span data-stu-id="bff47-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="bff47-125">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="bff47-125">Optional.</span></span> <span data-ttu-id="bff47-126">@No__t_1 が `expressionlist` 内のいずれかの句と一致する場合に実行される `Case` に続く1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="bff47-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="bff47-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="bff47-127">Optional.</span></span> <span data-ttu-id="bff47-128">@No__t_1 が `Case` ステートメントの `expressionlist` 内のどの句とも一致しない場合に実行される `Case Else` に続く1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="bff47-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="bff47-129">@No__t_0 の定義を終了します...`Case` 構築です。</span><span class="sxs-lookup"><span data-stu-id="bff47-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bff47-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="bff47-130">Remarks</span></span>  
 <span data-ttu-id="bff47-131">@No__t_0 が `Case` `expressionlist` 句と一致する場合、その `Case` ステートメントに続くステートメントは、次の `Case`、`Case Else`、または `End Select` ステートメントまで実行されます。</span><span class="sxs-lookup"><span data-stu-id="bff47-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="bff47-132">次に、コントロールは `End Select` に続くステートメントにを渡します。</span><span class="sxs-lookup"><span data-stu-id="bff47-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="bff47-133">@No__t_0 が1つ以上の `Case` 句の `expressionlist` 句と一致する場合、最初の一致を実行した後のステートメントのみが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bff47-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="bff47-134">@No__t_0 ステートメントを使用して、他の `Case` ステートメントで `testexpression` と `expressionlist` 句の間に一致が検出されなかった場合に実行する `elsestatements` を導入します。</span><span class="sxs-lookup"><span data-stu-id="bff47-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="bff47-135">必須ではありませんが、予期しない `testexpression` 値を処理するために、`Select Case` の構築に `Case Else` ステートメントを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bff47-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="bff47-136">@No__t_0 `expressionlist` 句が `testexpression` に一致せず、`Case Else` ステートメントが存在しない場合、制御は `End Select` に続くステートメントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bff47-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="bff47-137">各 `Case` 句では、複数の式または範囲を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bff47-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="bff47-138">たとえば、次の行は有効です。</span><span class="sxs-lookup"><span data-stu-id="bff47-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> <span data-ttu-id="bff47-139">@No__t_1 および `Case Else` ステートメントで使用されている `Is` キーワードは、オブジェクト参照の比較に使用される[Is 演算子](../../../visual-basic/language-reference/operators/is-operator.md)と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="bff47-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="bff47-140">文字列の範囲と複数の式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bff47-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="bff47-141">次の例では、`Case` は、"リンゴ" と完全に等価な任意の文字列と、アルファベット順の "ナット" と "スープ" の間の値を持つか、`testItem` の現在の値とまったく同じ値を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="bff47-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="bff47-142">@No__t_0 の設定は、文字列比較に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bff47-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="bff47-143">@No__t_0 では、文字列 "りんご" と "りんご" は等しいとして比較されますが、`Option Compare Binary` の下では、これらは等しくありません。</span><span class="sxs-lookup"><span data-stu-id="bff47-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bff47-144">複数の句を持つ `Case` ステートメントでは、*ショートサーキット*と呼ばれる動作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bff47-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="bff47-145">Visual Basic では、句が左から右に評価されます。一方が `testexpression` と一致する場合、残りの句は評価されません。</span><span class="sxs-lookup"><span data-stu-id="bff47-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="bff47-146">ショートサーキットはパフォーマンスを向上させることができますが、`expressionlist` 内のすべての式を評価する必要がある場合は、予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bff47-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="bff47-147">ショートサーキットの詳細については、「[ブール式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bff47-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="bff47-148">@No__t_0 または `Case Else` ステートメントブロック内のコードが、ブロック内のステートメントを実行する必要がない場合は、`Exit Select` ステートメントを使用してブロックを終了できます。</span><span class="sxs-lookup"><span data-stu-id="bff47-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="bff47-149">これにより、`End Select` に続くステートメントに制御が直ちに移ります。</span><span class="sxs-lookup"><span data-stu-id="bff47-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="bff47-150">`Select Case` の構造は入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bff47-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="bff47-151">入れ子になった `Select Case` 構築にはそれぞれ、一致する `End Select` ステートメントが必要です。また、入れ子になっている外側の `Select Case` 構築の1つの `Case` または `Case Else` ステートメントブロック内に完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bff47-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bff47-152">例</span><span class="sxs-lookup"><span data-stu-id="bff47-152">Example</span></span>  
 <span data-ttu-id="bff47-153">次の例では、`Select Case` 構築を使用して、変数 `number` の値に対応する行を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="bff47-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="bff47-154">2番目の `Case` ステートメントには、`number` の現在の値と一致する値が含まれています。そのため、"Between 6 ~ 8" を含むステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bff47-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="bff47-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="bff47-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="bff47-156">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="bff47-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="bff47-157">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="bff47-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="bff47-158">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="bff47-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="bff47-159">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="bff47-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
