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
ms.openlocfilehash: f99db4f1dc224e5f75ee67ba94c3745f28438724
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783891"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="cf526-102">Select...Case ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf526-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="cf526-103">式の値に応じて、ステートメントのグループをいくつかのいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf526-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf526-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf526-104">Syntax</span></span>  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="cf526-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="cf526-105">Parts</span></span>  
  
|<span data-ttu-id="cf526-106">用語</span><span class="sxs-lookup"><span data-stu-id="cf526-106">Term</span></span>|<span data-ttu-id="cf526-107">定義</span><span class="sxs-lookup"><span data-stu-id="cf526-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="cf526-108">必須。</span><span class="sxs-lookup"><span data-stu-id="cf526-108">Required.</span></span> <span data-ttu-id="cf526-109">式。</span><span class="sxs-lookup"><span data-stu-id="cf526-109">Expression.</span></span> <span data-ttu-id="cf526-110">基本データ型のいずれかを評価する必要があります (`Boolean`、 `Byte`、 `Char`、 `Date`、 `Double`、 `Decimal`、 `Integer`、 `Long`、 `Object`、 `SByte`、 `Short`、`Single`、 `String`、 `UInteger`、 `ULong`、および`UShort`)。</span><span class="sxs-lookup"><span data-stu-id="cf526-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="cf526-111">必要な`Case`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf526-111">Required in a `Case` statement.</span></span> <span data-ttu-id="cf526-112">一致した値を表す式の句のリスト`testexpression`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="cf526-113">複数の式の句は、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="cf526-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="cf526-114">各句には、次の形式のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf526-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="cf526-115">-   *expression1* `To` *expression2*</span><span class="sxs-lookup"><span data-stu-id="cf526-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="cf526-116">-   [ `Is` ] *comparisonoperator* *expression*</span><span class="sxs-lookup"><span data-stu-id="cf526-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="cf526-117">-   *expression*</span><span class="sxs-lookup"><span data-stu-id="cf526-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="cf526-118">使用して、`To`一致の範囲の境界を指定するキーワードの値を`testexpression`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="cf526-119">値`expression1`の値未満でなければなりません`expression2`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="cf526-120">使用して、`Is`比較演算子でキーワード (`=`、 `<>`、 `<`、 `<=`、 `>`、または`>=`)、一致した値に制限を指定する`testexpression`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="cf526-121">場合、`Is`キーワードが指定されていないが自動的にする前に挿入*comparisonoperator*します。</span><span class="sxs-lookup"><span data-stu-id="cf526-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="cf526-122">だけを指定してフォーム`expression`の特殊なケースとして扱われます、`Is`フォーム where *comparisonoperator*は等号 (=) (`=`)。</span><span class="sxs-lookup"><span data-stu-id="cf526-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="cf526-123">この形式は`testexpression`  = `expression`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="cf526-124">内の式`expressionlist`かの型に暗黙的に変換可能であれば、任意のデータ型のできる`testexpression`、適切な`comparisonoperator`はで使用されている 2 つの型に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="cf526-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="cf526-125">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cf526-125">Optional.</span></span> <span data-ttu-id="cf526-126">1 つまたは複数のステートメントの次`Case`実行されている場合`testexpression`で句と一致する`expressionlist`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="cf526-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cf526-127">Optional.</span></span> <span data-ttu-id="cf526-128">1 つまたは複数のステートメントの次`Case Else`実行されている場合`testexpression`で句と一致しません、`expressionlist`のいずれかの`Case`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf526-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="cf526-129">定義を終了、 `Select`.`Case`構築します。</span><span class="sxs-lookup"><span data-stu-id="cf526-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf526-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf526-130">Remarks</span></span>  
 <span data-ttu-id="cf526-131">場合`testexpression`と一致する`Case``expressionlist`句を次のステートメントでは、`Case`次ステートメントが実行`Case`、 `Case Else`、または`End Select`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf526-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="cf526-132">次のステートメントのパスを制御し、`End Select`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="cf526-133">場合`testexpression`と一致する、 `expressionlist` 1 つ以上の句`Case`句では、最初の一致の次のステートメントのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf526-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="cf526-134">`Case Else`ステートメントを使用して、導入、`elsestatements`間で一致が見つからない場合に実行する、`testexpression`と`expressionlist`で他の句`Case`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf526-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="cf526-135">良いアイデアですが必須ではありませんが、`Case Else`内のステートメント、`Select Case`の構築処理を予期しない`testexpression`値。</span><span class="sxs-lookup"><span data-stu-id="cf526-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="cf526-136">ない場合は`Case``expressionlist`句と一致する`testexpression`はない`Case Else`ステートメントでは、次のステートメントのコントロール パス`End Select`。</span><span class="sxs-lookup"><span data-stu-id="cf526-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="cf526-137">複数の式または範囲を使用するには各`Case`句。</span><span class="sxs-lookup"><span data-stu-id="cf526-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="cf526-138">たとえば、次の行は有効です。</span><span class="sxs-lookup"><span data-stu-id="cf526-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  <span data-ttu-id="cf526-139">`Is`で使用されるキーワード、`Case`と`Case Else`ステートメントがないと同じ、 [Is 演算子](../../../visual-basic/language-reference/operators/is-operator.md)、オブジェクト参照の比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf526-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="cf526-140">範囲と文字の文字列の複数の式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf526-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="cf526-141">次の例では、`Case`を"apples"に正確に一致、アルファベット順に「ナット」と「スープ」の間の値を持つ、またはの現在の値とまったく同じ値を格納する任意の文字列と一致する`testItem`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="cf526-142">設定は、`Option Compare`文字列比較に影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="cf526-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="cf526-143">`Option Compare Text`、Equal、として比較してが文字列"Apples"と"apples" `Option Compare Binary`、一致していないためです。</span><span class="sxs-lookup"><span data-stu-id="cf526-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf526-144">A`Case`句を指定して複数のステートメントと呼ばれる動作が発生することができます*ショート サーキット*します。</span><span class="sxs-lookup"><span data-stu-id="cf526-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="cf526-145">Visual Basic は、左から右への句を評価し、1 つの場合との一致を作成します。 `testexpression`、残りの句は評価されません。</span><span class="sxs-lookup"><span data-stu-id="cf526-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="cf526-146">ショート サーキットのパフォーマンスが向上するのすべての式が必要な場合、予期しない結果を生成できる`expressionlist`評価されます。</span><span class="sxs-lookup"><span data-stu-id="cf526-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="cf526-147">ショート サーキットの詳細については、次を参照してください。[ブール式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf526-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="cf526-148">場合内のコードを`Case`または`Case Else`ステートメント ブロックは、ブロックで以上のステートメントを実行する必要はありませんを使用して、ブロックを終了できますが、`Exit Select`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="cf526-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="cf526-149">ステートメントに制御を直ちに転送この`End Select`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="cf526-150">`Select Case` 構造を入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf526-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="cf526-151">入れ子になった`Select Case`構築の対応する必要がありますが`End Select`ステートメントを 1 回完全に含める必要があると`Case`または`Case Else`ステートメント ブロックの外側の`Select Case`構築を入れ子にします。</span><span class="sxs-lookup"><span data-stu-id="cf526-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf526-152">例</span><span class="sxs-lookup"><span data-stu-id="cf526-152">Example</span></span>  
 <span data-ttu-id="cf526-153">次の例では、`Select Case`構造を使用して、変数の値に対応する行も記述`number`します。</span><span class="sxs-lookup"><span data-stu-id="cf526-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="cf526-154">2 番目の`Case`ステートメントには、現在の値に一致する値が含まれています。 `number`"6 から 8 の包括的な"ステートメントを書き込むため、実行します。</span><span class="sxs-lookup"><span data-stu-id="cf526-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="cf526-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf526-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="cf526-156">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf526-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="cf526-157">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf526-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="cf526-158">Option Compare ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf526-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="cf526-159">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="cf526-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
