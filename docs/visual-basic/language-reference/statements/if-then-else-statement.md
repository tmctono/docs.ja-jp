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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404590"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="2e892-102">If...Then...Else ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e892-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="2e892-103">式の値に応じてステートメント グループを条件付きで実行します。</span><span class="sxs-lookup"><span data-stu-id="2e892-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e892-104">構文</span><span class="sxs-lookup"><span data-stu-id="2e892-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="2e892-105">コード例へのクイック リンク</span><span class="sxs-lookup"><span data-stu-id="2e892-105">Quick links to example code</span></span>

<span data-ttu-id="2e892-106">この記事には、`If`...`Then`...`Else` ステートメントの使用方法を示す例がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e892-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="2e892-107">複数行構文の例</span><span class="sxs-lookup"><span data-stu-id="2e892-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="2e892-108">入れ子になった構文の例</span><span class="sxs-lookup"><span data-stu-id="2e892-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="2e892-109">単一行構文の例</span><span class="sxs-lookup"><span data-stu-id="2e892-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="2e892-110">指定項目</span><span class="sxs-lookup"><span data-stu-id="2e892-110">Parts</span></span>

`condition` \
<span data-ttu-id="2e892-111">必須です。</span><span class="sxs-lookup"><span data-stu-id="2e892-111">Required.</span></span> <span data-ttu-id="2e892-112">式。</span><span class="sxs-lookup"><span data-stu-id="2e892-112">Expression.</span></span> <span data-ttu-id="2e892-113">`True` または `False`、または `Boolean` に暗黙的に変換できるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e892-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="2e892-114">式が [Nothing](../nothing.md) に評価される [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) の `Boolean` 変数の場合、条件は、式が `False` であるかのように処理され、`ElseIf` ブロックが存在する場合は評価されます。存在しない場合は、`Else` ブロックが実行されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="2e892-114">If the expression is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="2e892-115">単一行の構文では必須です。複数行の構文では省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2e892-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="2e892-116">任意。</span><span class="sxs-lookup"><span data-stu-id="2e892-116">Optional.</span></span> <span data-ttu-id="2e892-117">`condition` が `True` に評価された場合に実行される `If`...`Then` の後に続く 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="2e892-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="2e892-118">`ElseIf` が存在する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="2e892-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="2e892-119">式。</span><span class="sxs-lookup"><span data-stu-id="2e892-119">Expression.</span></span> <span data-ttu-id="2e892-120">`True` または `False`、または `Boolean` に暗黙的に変換できるデータ型に評価される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e892-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="2e892-121">任意。</span><span class="sxs-lookup"><span data-stu-id="2e892-121">Optional.</span></span> <span data-ttu-id="2e892-122">`elseifcondition` が `True` に評価された場合に実行される `ElseIf`...`Then` の後に続く 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="2e892-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="2e892-123">任意。</span><span class="sxs-lookup"><span data-stu-id="2e892-123">Optional.</span></span> <span data-ttu-id="2e892-124">前の `condition` または `elseifcondition` 式が `True` に評価されなかった場合に実行される 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="2e892-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="2e892-125">複数行バージョンの `If`...`Then`...`Else` ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="2e892-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e892-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="2e892-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="2e892-127">複数行の構文</span><span class="sxs-lookup"><span data-stu-id="2e892-127">Multiline syntax</span></span>

<span data-ttu-id="2e892-128">`If`...`Then`...`Else` ステートメントが検出されると、`condition` がテストされます。</span><span class="sxs-lookup"><span data-stu-id="2e892-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="2e892-129">`condition` が `True` の場合、`Then` に続くステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e892-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="2e892-130">`condition` が `False` の場合は、各 `ElseIf` ステートメント (存在する場合) が順番に評価されます。</span><span class="sxs-lookup"><span data-stu-id="2e892-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="2e892-131">`True` になる `elseifcondition` が見つかると、関連付けられた `ElseIf` の直後にあるステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e892-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="2e892-132">`True` に評価される `elseifcondition` がない場合、または `ElseIf` ステートメントが存在しない場合は、`Else` に続くステートメントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e892-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="2e892-133">`Then`、`ElseIf`、または `Else` の後に続くステートメントが実行されると、`End If` に続くステートメントが引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e892-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="2e892-134">`ElseIf` と `Else` の句は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2e892-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="2e892-135">`If`...`Then`...`Else` ステートメントには、必要な数の `ElseIf` 句を指定できますが、`Else` 句の後に `ElseIf` 句を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e892-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="2e892-136">`If`...`Then`...`Else` ステートメントは、入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e892-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="2e892-137">複数行の構文では、`If` ステートメントが 1 行目の唯一のステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e892-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="2e892-138">`ElseIf`、`Else`、および `End If` ステートメントの前には、行ラベルのみを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2e892-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="2e892-139">`If`...`Then`...`Else` ブロックは、`End If` ステートメントで終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e892-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="2e892-140">[Select...Case ステートメント](select-case-statement.md)は、複数の値が結果として得られる可能性がある単一の式を評価する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2e892-140">The [Select...Case Statement](select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="2e892-141">単一行の構文</span><span class="sxs-lookup"><span data-stu-id="2e892-141">Single-Line syntax</span></span>

<span data-ttu-id="2e892-142">単一行の構文は、単一の条件の場合に使用することができ、True の場合に実行するコードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e892-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="2e892-143">ただし、複数行の構文では、より多くの構造と柔軟性が提供され、読み取り、保守、デバッグが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="2e892-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="2e892-144">ステートメントが単一行の `If` であるかどうかを判別するために、`Then` キーワードの後に続くものが検査されます。</span><span class="sxs-lookup"><span data-stu-id="2e892-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="2e892-145">同じ行の `Then` の後にコメント以外のものがある場合、そのステートメントは単一行の `If` ステートメントとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="2e892-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="2e892-146">`Then` がない場合は、複数行の `If`...`Then`...`Else` が開始されたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="2e892-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="2e892-147">単一行の構文では、`If`...`Then` の判断の結果として複数のステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e892-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="2e892-148">すべてのステートメントは、同じ行にあり、コロンで区切られている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e892-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="2e892-149">複数行構文の例</span><span class="sxs-lookup"><span data-stu-id="2e892-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="2e892-150">次の例では、`If`...`Then`...`Else` ステートメントの複数行構文の使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2e892-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="2e892-151">入れ子になった構文の例</span><span class="sxs-lookup"><span data-stu-id="2e892-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="2e892-152">次の例には、入れ子になった `If`...`Then`...`Else` ステートメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e892-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="2e892-153">単一行構文の例</span><span class="sxs-lookup"><span data-stu-id="2e892-153">Single-Line syntax example</span></span>

<a name="single-line"></a> <span data-ttu-id="2e892-154">単一行構文の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2e892-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="2e892-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e892-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="2e892-156">#If...Then...#Else ディレクティブ</span><span class="sxs-lookup"><span data-stu-id="2e892-156">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
- [<span data-ttu-id="2e892-157">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="2e892-157">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="2e892-158">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="2e892-158">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="2e892-159">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="2e892-159">Decision Structures</span></span>](../../programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="2e892-160">Visual Basic の論理演算子とビット処理演算子</span><span class="sxs-lookup"><span data-stu-id="2e892-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="2e892-161">If 演算子</span><span class="sxs-lookup"><span data-stu-id="2e892-161">If Operator</span></span>](../operators/if-operator.md)
