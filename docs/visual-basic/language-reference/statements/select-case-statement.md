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
ms.openlocfilehash: 627318677270ba4ffa8ee430febea7ddf83bd245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957660"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="4e77f-102">Select...Case ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e77f-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="4e77f-103">式の値に応じて、いくつかのステートメントグループのうちの1つを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e77f-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e77f-104">構文</span><span class="sxs-lookup"><span data-stu-id="4e77f-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="4e77f-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="4e77f-105">Parts</span></span>  
  
|<span data-ttu-id="4e77f-106">用語</span><span class="sxs-lookup"><span data-stu-id="4e77f-106">Term</span></span>|<span data-ttu-id="4e77f-107">定義</span><span class="sxs-lookup"><span data-stu-id="4e77f-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="4e77f-108">必須。</span><span class="sxs-lookup"><span data-stu-id="4e77f-108">Required.</span></span> <span data-ttu-id="4e77f-109">条件.</span><span class="sxs-lookup"><span data-stu-id="4e77f-109">Expression.</span></span> <span data-ttu-id="4e77f-110">は、基本`Boolean`データ型 ( 、`Decimal`、、 `Date` `Char` `Double` 、、`Long`、、、、、 、)のいずれかに評価される必要があります。`Short` `Integer` `Byte` `Object` `SByte``Single` 、`String`、 、`ULong`、および)`UShort`。 `UInteger`</span><span class="sxs-lookup"><span data-stu-id="4e77f-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="4e77f-111">`Case`ステートメント内で必要です。</span><span class="sxs-lookup"><span data-stu-id="4e77f-111">Required in a `Case` statement.</span></span> <span data-ttu-id="4e77f-112">の`testexpression`一致値を表す式の句の一覧。</span><span class="sxs-lookup"><span data-stu-id="4e77f-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="4e77f-113">複数の式句は、コンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="4e77f-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="4e77f-114">各句には、次のいずれかの形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="4e77f-115">-   *expression1* `To` *expression2*</span><span class="sxs-lookup"><span data-stu-id="4e77f-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="4e77f-116">-   [ `Is` ] *comparisonoperator* *expression*</span><span class="sxs-lookup"><span data-stu-id="4e77f-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="4e77f-117">-   *条件*</span><span class="sxs-lookup"><span data-stu-id="4e77f-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="4e77f-118">キーワードを使用して、の`testexpression`一致値の範囲の境界を指定します。 `To`</span><span class="sxs-lookup"><span data-stu-id="4e77f-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="4e77f-119">の`expression1`値は、の`expression2`値以下である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e77f-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="4e77f-120">`=`比較演算子`<>`(、 `Is` `testexpression`、、 、、また`>=`は) でキーワードを使用して、の一致値に制限を指定します。 `>` `<=` `<`</span><span class="sxs-lookup"><span data-stu-id="4e77f-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="4e77f-121">キーワードが指定されていない場合は、comparisonoperator の前に自動的に挿入されます。 `Is`</span><span class="sxs-lookup"><span data-stu-id="4e77f-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="4e77f-122">のみ`expression`を指定するフォームは、 `Is`フォームの特殊なケースとして扱われます。ここ`=`で、 *comparisonoperator*は等号 () です。</span><span class="sxs-lookup"><span data-stu-id="4e77f-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="4e77f-123">このフォームはとし`testexpression`て =  `expression`評価されます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="4e77f-124">の式`expressionlist`は、任意のデータ型にすることができます。その場合、の`testexpression`型に暗黙的`comparisonoperator`に変換可能で、適切なが使用されている2つの型に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="4e77f-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="4e77f-125">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4e77f-125">Optional.</span></span> <span data-ttu-id="4e77f-126">が内の句に`Case` `expressionlist`一致する場合`testexpression` 、を実行する1つ以上のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e77f-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="4e77f-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="4e77f-127">Optional.</span></span> <span data-ttu-id="4e77f-128">に続く`Case Else` 1 つ以上のステートメントが`testexpression` 、 `Case`ステートメントの内`expressionlist`の句と一致しない場合に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="4e77f-129">`Select`... の定義を終了します。`Case`構築。</span><span class="sxs-lookup"><span data-stu-id="4e77f-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e77f-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="4e77f-130">Remarks</span></span>  
 <span data-ttu-id="4e77f-131">が`testexpression` any `Case` `Case Else` `Case` `End Select`句と一致する場合、そのステートメントの後に続くステートメントは、次の、、またはステートメントまで実行されます。 `Case` `expressionlist`</span><span class="sxs-lookup"><span data-stu-id="4e77f-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="4e77f-132">その後、制御は次`End Select`のステートメントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="4e77f-133">が`testexpression`複数の`expressionlist` `Case`句の句と一致する場合、最初の一致の後に続くステートメントだけが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="4e77f-134">`expressionlist` `elsestatements` `testexpression`ステートメントを使用すると、他の`Case`どのステートメントでも句と句の間に一致が検出されなかった場合に、実行するが導入されます。 `Case Else`</span><span class="sxs-lookup"><span data-stu-id="4e77f-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="4e77f-135">必須ではありませんが、予期`Case Else` `testexpression`しない値を処理する`Select Case`ためのステートメントを構築に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e77f-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="4e77f-136">に一致`Case`する`expressionlist` `Case Else`句がなく、ステートメントがない場合は、次`End Select`のステートメントに制御が渡されます。 `testexpression`</span><span class="sxs-lookup"><span data-stu-id="4e77f-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="4e77f-137">各`Case`句では、複数の式または範囲を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="4e77f-138">たとえば、次の行は有効です。</span><span class="sxs-lookup"><span data-stu-id="4e77f-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> <span data-ttu-id="4e77f-139">`Case`ステートメントおよびステートメント`Case Else`で使用されるキーワードは、オブジェクト参照の比較に使用される [is 演算子](../../../visual-basic/language-reference/operators/is-operator.md)と同じではありませ`Is`ん。</span><span class="sxs-lookup"><span data-stu-id="4e77f-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="4e77f-140">文字列の範囲と複数の式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="4e77f-141">次の例では`Case` 、は "りんご" と完全に等価な任意の文字列を、アルファベット順で "ナット" と "スープ" の間の値を持ちます。または、の現在`testItem`の値とまったく同じ値を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="4e77f-142">の`Option Compare`設定は、文字列比較に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e77f-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="4e77f-143">では、文字列 "りんご" と "りんご" は等しいものとして`Option Compare Binary`比較されますが、ではこれらの文字列は比較されません。 `Option Compare Text`</span><span class="sxs-lookup"><span data-stu-id="4e77f-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e77f-144">複数`Case`の句を持つステートメントでは、*ショートサーキット*と呼ばれる動作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="4e77f-145">Visual Basic は、句を左から右に評価し、一方がと`testexpression`一致する場合、残りの句は評価されません。</span><span class="sxs-lookup"><span data-stu-id="4e77f-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="4e77f-146">ショートサーキットはパフォーマンスを向上させることができますが、のすべての`expressionlist`式を評価する必要がある場合は、予期しない結果が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e77f-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="4e77f-147">ショートサーキットの詳細については、「[ブール式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e77f-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="4e77f-148">`Case`また`Exit Select`は`Case Else`ステートメントブロック内のコードが、ブロック内のステートメントを実行する必要がない場合は、ステートメントを使用してブロックを終了できます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="4e77f-149">これは、次`End Select`のステートメントに制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="4e77f-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="4e77f-150">`Select Case`構造は入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="4e77f-151">入れ子に`Select Case`なった各構築は`End Select` 、一致するステートメントを持つ必要があり`Case` 、入れ子になっている`Select Case`外側の構造体の1つまたは`Case Else`複数のステートメントブロック内に完全に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e77f-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e77f-152">例</span><span class="sxs-lookup"><span data-stu-id="4e77f-152">Example</span></span>  
 <span data-ttu-id="4e77f-153">次の例では`Select Case` 、構築を使用して、変数`number`の値に対応する行を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4e77f-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="4e77f-154">2番`Case`目のステートメントには、の現在の`number`値と一致する値が含まれています。そのため、"Between 6" ~ "8" を含むステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e77f-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="4e77f-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e77f-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="4e77f-156">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e77f-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="4e77f-157">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e77f-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="4e77f-158">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e77f-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="4e77f-159">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e77f-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
