---
title: If...Then...Else ステートメント
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
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351163"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="cdcdb-102">If...Then...Else ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdcdb-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="cdcdb-103">式の値に応じてステートメント グループを条件付きで実行します。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="cdcdb-104">構文</span><span class="sxs-lookup"><span data-stu-id="cdcdb-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="cdcdb-105">コード例へのクイックリンク</span><span class="sxs-lookup"><span data-stu-id="cdcdb-105">Quick links to example code</span></span>

<span data-ttu-id="cdcdb-106">この記事には、`If`...`Then`...`Else` ステートメントの使用方法を示す例がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="cdcdb-107">複数行構文の例</span><span class="sxs-lookup"><span data-stu-id="cdcdb-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="cdcdb-108">入れ子になった構文の例</span><span class="sxs-lookup"><span data-stu-id="cdcdb-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="cdcdb-109">単一行構文の例</span><span class="sxs-lookup"><span data-stu-id="cdcdb-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="cdcdb-110">指定項目</span><span class="sxs-lookup"><span data-stu-id="cdcdb-110">Parts</span></span>

`condition` \
<span data-ttu-id="cdcdb-111">必須。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-111">Required.</span></span> <span data-ttu-id="cdcdb-112">条件.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-112">Expression.</span></span> <span data-ttu-id="cdcdb-113">は、`True` または `False`、または `Boolean`に暗黙的に変換できるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="cdcdb-114">式が[Nothing](../../../visual-basic/language-reference/nothing.md)に評価される[null 許容](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)型の `Boolean` 変数の場合、条件は式が `False`として扱われ、`ElseIf` ブロックが存在する場合は評価され、存在する場合は `Else` ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="cdcdb-115">単一行の構文では必須です。複数行の構文では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="cdcdb-116">省略可。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-116">Optional.</span></span> <span data-ttu-id="cdcdb-117">`condition` が `True`に評価された場合に実行される `If`...`Then` の後に続く1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="cdcdb-118">`ElseIf` が存在する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="cdcdb-119">条件.</span><span class="sxs-lookup"><span data-stu-id="cdcdb-119">Expression.</span></span> <span data-ttu-id="cdcdb-120">は、`True` または `False`、または `Boolean`に暗黙的に変換できるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="cdcdb-121">省略可。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-121">Optional.</span></span> <span data-ttu-id="cdcdb-122">`elseifcondition` が `True`に評価された場合に実行される `ElseIf`...`Then` の後に続く1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="cdcdb-123">省略可。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-123">Optional.</span></span> <span data-ttu-id="cdcdb-124">前の `condition` または `elseifcondition` 式が `True`に評価されなかった場合に実行される1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="cdcdb-125">複数行バージョンの `If`...`Then`...`Else` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdcdb-126">コメント</span><span class="sxs-lookup"><span data-stu-id="cdcdb-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="cdcdb-127">複数行の構文</span><span class="sxs-lookup"><span data-stu-id="cdcdb-127">Multiline syntax</span></span>

<span data-ttu-id="cdcdb-128">`If`...`Then`...`Else` ステートメントが検出されると、`condition` がテストされます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="cdcdb-129">`condition` が `True`場合、`Then` に続くステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="cdcdb-130">`condition` が `False`場合は、各 `ElseIf` ステートメント (存在する場合) が順番に評価されます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="cdcdb-131">`True` `elseifcondition` が見つかると、関連付けられた `ElseIf` の直後にあるステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="cdcdb-132">`elseifcondition` が `True`に評価されない場合、または `ElseIf` ステートメントが存在しない場合は、`Else` に続くステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="cdcdb-133">`Then`、`ElseIf`、または `Else`の後に続くステートメントを実行すると、次の `End If`に続くステートメントで実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="cdcdb-134">`ElseIf` 句と `Else` 句は両方とも省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="cdcdb-135">`If``Then`...`Else` ステートメントには、必要な数の `ElseIf` 句を指定できますが、`ElseIf` 句の後に `Else` 句を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="cdcdb-136">`If`...`Then`...`Else` ステートメントは、入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="cdcdb-137">複数行構文では、`If` ステートメントが1行目の唯一のステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="cdcdb-138">`ElseIf`、`Else`、および `End If` ステートメントの前には、行ラベルだけを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="cdcdb-139">`If`...`Then`...`Else` ブロックは、`End If` ステートメントで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="cdcdb-140">[選択...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)は、複数の可能な値を含む単一の式を評価する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="cdcdb-141">単一行の構文</span><span class="sxs-lookup"><span data-stu-id="cdcdb-141">Single-Line syntax</span></span>

<span data-ttu-id="cdcdb-142">単一行構文を使用すると、コードを含む単一の条件を使用して、true の場合に実行できます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="cdcdb-143">ただし、複数行の構文では、より多くの構造と柔軟性が提供され、読み取り、保守、デバッグが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="cdcdb-144">ステートメントが単一行の `If`であるかどうかを判断するために、`Then` キーワードの後に続くものは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="cdcdb-145">同じ行の `Then` の後にコメント以外のものがある場合、ステートメントは単一行の `If` ステートメントとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="cdcdb-146">`Then` が存在しない場合は、複数行の `If`.`Then`..`Else`を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="cdcdb-147">単一行構文では、`If`...`Then` 決定の結果として複数のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="cdcdb-148">すべてのステートメントは、同じ行にあり、コロンで区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="cdcdb-149">複数行構文の例</span><span class="sxs-lookup"><span data-stu-id="cdcdb-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="cdcdb-150">次の例では、`If`...`Then`...`Else` ステートメントの複数行構文の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="cdcdb-151">入れ子になった構文の例</span><span class="sxs-lookup"><span data-stu-id="cdcdb-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="cdcdb-152">次の例には、入れ子になった `If`...`Then`...`Else` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="cdcdb-153">単一行構文の例</span><span class="sxs-lookup"><span data-stu-id="cdcdb-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="cdcdb-154">単一行構文の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cdcdb-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="cdcdb-155">参照</span><span class="sxs-lookup"><span data-stu-id="cdcdb-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="cdcdb-156">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="cdcdb-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="cdcdb-157">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="cdcdb-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="cdcdb-158">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="cdcdb-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="cdcdb-159">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="cdcdb-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="cdcdb-160">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="cdcdb-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="cdcdb-161">If 演算子</span><span class="sxs-lookup"><span data-stu-id="cdcdb-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
