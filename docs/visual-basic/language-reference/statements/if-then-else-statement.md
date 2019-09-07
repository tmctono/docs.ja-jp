---
title: If...Then...Else ステートメント (Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: db81a1c41809b563d5f9d0777c3feb064c5e540b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400709"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="03d10-102">If...Then...Else ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03d10-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="03d10-103">式の値に応じてステートメント グループを条件付きで実行します。</span><span class="sxs-lookup"><span data-stu-id="03d10-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="03d10-104">構文</span><span class="sxs-lookup"><span data-stu-id="03d10-104">Syntax</span></span>

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a><span data-ttu-id="03d10-105">コード例へのクイックリンク</span><span class="sxs-lookup"><span data-stu-id="03d10-105">Quick links to example code</span></span>

<span data-ttu-id="03d10-106">この記事には、 `If`...`Then`...`Else`ステートメント:</span><span class="sxs-lookup"><span data-stu-id="03d10-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="03d10-107">複数行構文の例</span><span class="sxs-lookup"><span data-stu-id="03d10-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="03d10-108">入れ子になった構文の例</span><span class="sxs-lookup"><span data-stu-id="03d10-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="03d10-109">単一行構文の例</span><span class="sxs-lookup"><span data-stu-id="03d10-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="03d10-110">指定項目</span><span class="sxs-lookup"><span data-stu-id="03d10-110">Parts</span></span>

`condition` \
<span data-ttu-id="03d10-111">必須。</span><span class="sxs-lookup"><span data-stu-id="03d10-111">Required.</span></span> <span data-ttu-id="03d10-112">条件.</span><span class="sxs-lookup"><span data-stu-id="03d10-112">Expression.</span></span> <span data-ttu-id="03d10-113">`True`は`Boolean`、、、またはに暗黙的に変換可能なデータ型に評価される必要があります。 `False`</span><span class="sxs-lookup"><span data-stu-id="03d10-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="03d10-114">式が[Nothing](../../../visual-basic/language-reference/nothing.md)に`False`評価される[null 許容](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean`変数である場合、条件は式がで`ElseIf`あるかのように処理され、ブロックが存在する場合`Else`は評価され、ブロックは存在する場合は実行されます。</span><span class="sxs-lookup"><span data-stu-id="03d10-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="03d10-115">単一行の構文では必須です。複数行の構文では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="03d10-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="03d10-116">任意。</span><span class="sxs-lookup"><span data-stu-id="03d10-116">Optional.</span></span> <span data-ttu-id="03d10-117">次の1つまた`If`は複数のステートメントをフォローしています...`Then`が`condition`に評価`True`される場合に実行される。</span><span class="sxs-lookup"><span data-stu-id="03d10-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="03d10-118">が存在`ElseIf`する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="03d10-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="03d10-119">条件.</span><span class="sxs-lookup"><span data-stu-id="03d10-119">Expression.</span></span> <span data-ttu-id="03d10-120">`True`は`Boolean`、、、またはに暗黙的に変換可能なデータ型に評価される必要があります。 `False`</span><span class="sxs-lookup"><span data-stu-id="03d10-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="03d10-121">任意。</span><span class="sxs-lookup"><span data-stu-id="03d10-121">Optional.</span></span> <span data-ttu-id="03d10-122">次の1つまた`ElseIf`は複数のステートメントをフォローしています...`Then`が`elseifcondition`に評価`True`される場合に実行される。</span><span class="sxs-lookup"><span data-stu-id="03d10-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="03d10-123">任意。</span><span class="sxs-lookup"><span data-stu-id="03d10-123">Optional.</span></span> <span data-ttu-id="03d10-124">前`condition`のまたは`elseifcondition`式がと評価`True`されなかった場合に実行される1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="03d10-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="03d10-125">の`If`複数行バージョンを終了します...`Then`...`Else`ブロック。</span><span class="sxs-lookup"><span data-stu-id="03d10-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="03d10-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="03d10-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="03d10-127">複数行の構文</span><span class="sxs-lookup"><span data-stu-id="03d10-127">Multiline syntax</span></span>

<span data-ttu-id="03d10-128">`If`When...`Then`...ステートメントが検出されました。がテストされています。`condition` `Else`</span><span class="sxs-lookup"><span data-stu-id="03d10-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="03d10-129">`Then`が`condition` の`True`場合は、次のステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="03d10-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="03d10-130">`ElseIf`が`condition` の場合、各ステートメント(存在する場合)は順番に評価されます。`False`</span><span class="sxs-lookup"><span data-stu-id="03d10-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="03d10-131">が見つかると、関連付けられ`ElseIf`たの直後にあるステートメントが実行されます。 `True` `elseifcondition`</span><span class="sxs-lookup"><span data-stu-id="03d10-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="03d10-132">`ElseIf`がに`elseifcondition`評価されない場合、またはステートメントが存在しない`Else`場合は、次のステートメントが実行されます。 `True`</span><span class="sxs-lookup"><span data-stu-id="03d10-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="03d10-133">、 `Then` `End If`、または`Else`に続くステートメントを実行すると、次のステートメントで実行が続行されます。 `ElseIf`</span><span class="sxs-lookup"><span data-stu-id="03d10-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="03d10-134">句`ElseIf` と`Else`句はどちらも省略可能です。</span><span class="sxs-lookup"><span data-stu-id="03d10-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="03d10-135">必要な数`ElseIf` `If`の句を含めることができます...`Then`...ステートメントですが、句の後に`Else`句を記述することはできません`ElseIf`。 `Else`</span><span class="sxs-lookup"><span data-stu-id="03d10-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="03d10-136">`If`...`Then`...`Else`ステートメントは、入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="03d10-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="03d10-137">複数行構文`If`では、ステートメントが1行目の唯一のステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="03d10-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="03d10-138">、 `ElseIf` 、`Else`および`End If`の各ステートメントの前には、行ラベルだけを指定できます。</span><span class="sxs-lookup"><span data-stu-id="03d10-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="03d10-139">`If`...`Then`...ブロックは`End If`ステートメントで終了する必要があります。 `Else`</span><span class="sxs-lookup"><span data-stu-id="03d10-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="03d10-140">[Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)をいくつかの値を持つ 1 つの式を評価するときにさらに便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="03d10-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="03d10-141">単一行の構文</span><span class="sxs-lookup"><span data-stu-id="03d10-141">Single-Line syntax</span></span>

<span data-ttu-id="03d10-142">単一行構文を使用すると、コードを含む単一の条件を使用して、true の場合に実行できます。</span><span class="sxs-lookup"><span data-stu-id="03d10-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="03d10-143">ただし、複数行の構文では、より多くの構造と柔軟性が提供され、読み取り、保守、デバッグが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="03d10-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="03d10-144">ステートメントが単`Then`一行`If`であるかどうかを判断するために、キーワードの後に続く内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="03d10-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="03d10-145">コメント以外のものが`Then`同じ行にある場合、ステートメントは単一行`If`のステートメントとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="03d10-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="03d10-146">が`Then`存在しない場合は、複数行`If`の先頭にする必要があります...`Then`...`Else`.</span><span class="sxs-lookup"><span data-stu-id="03d10-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="03d10-147">単一行構文では、... の結果として複数の`If`ステートメントを実行できます。`Then`決定。</span><span class="sxs-lookup"><span data-stu-id="03d10-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="03d10-148">すべてのステートメントは、同じ行にあり、コロンで区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="03d10-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="03d10-149">複数行構文の例</span><span class="sxs-lookup"><span data-stu-id="03d10-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="03d10-150">次の例では、 `If`... の複数行構文の使用方法を示しています。`Then`...`Else`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="03d10-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="03d10-151">入れ子になった構文の例</span><span class="sxs-lookup"><span data-stu-id="03d10-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="03d10-152">次の例には`If`、入れ子になった...`Then`...`Else`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="03d10-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="03d10-153">単一行構文の例</span><span class="sxs-lookup"><span data-stu-id="03d10-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="03d10-154">単一行構文の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="03d10-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="03d10-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="03d10-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="03d10-156">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="03d10-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="03d10-157">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="03d10-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="03d10-158">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="03d10-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="03d10-159">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="03d10-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="03d10-160">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="03d10-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="03d10-161">If 演算子</span><span class="sxs-lookup"><span data-stu-id="03d10-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
