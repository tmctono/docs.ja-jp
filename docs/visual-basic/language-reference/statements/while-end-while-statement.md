---
title: While...End While ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 87f6fbd6147b6dbfbe08c93e862d58b9868f9201
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352753"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="37ca4-102">While...End While ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37ca4-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="37ca4-103">Runs a series of statements as long as a given condition is `True`.</span><span class="sxs-lookup"><span data-stu-id="37ca4-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ca4-104">構文</span><span class="sxs-lookup"><span data-stu-id="37ca4-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="37ca4-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="37ca4-105">Parts</span></span>  
  
|<span data-ttu-id="37ca4-106">用語</span><span class="sxs-lookup"><span data-stu-id="37ca4-106">Term</span></span>|<span data-ttu-id="37ca4-107">定義</span><span class="sxs-lookup"><span data-stu-id="37ca4-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="37ca4-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="37ca4-108">Required.</span></span> <span data-ttu-id="37ca4-109">`Boolean` expression.</span><span class="sxs-lookup"><span data-stu-id="37ca4-109">`Boolean` expression.</span></span> <span data-ttu-id="37ca4-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span><span class="sxs-lookup"><span data-stu-id="37ca4-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="37ca4-111">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="37ca4-111">Optional.</span></span> <span data-ttu-id="37ca4-112">One or more statements following `While`, which run every time `condition` is `True`.</span><span class="sxs-lookup"><span data-stu-id="37ca4-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="37ca4-113">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="37ca4-113">Optional.</span></span> <span data-ttu-id="37ca4-114">Transfers control to the next iteration of the `While` block.</span><span class="sxs-lookup"><span data-stu-id="37ca4-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="37ca4-115">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="37ca4-115">Optional.</span></span> <span data-ttu-id="37ca4-116">Transfers control out of the `While` block.</span><span class="sxs-lookup"><span data-stu-id="37ca4-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="37ca4-117">必須です。</span><span class="sxs-lookup"><span data-stu-id="37ca4-117">Required.</span></span> <span data-ttu-id="37ca4-118">`While` ブロックの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="37ca4-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37ca4-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="37ca4-119">Remarks</span></span>  
 <span data-ttu-id="37ca4-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span><span class="sxs-lookup"><span data-stu-id="37ca4-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="37ca4-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="37ca4-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="37ca4-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span><span class="sxs-lookup"><span data-stu-id="37ca4-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37ca4-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span><span class="sxs-lookup"><span data-stu-id="37ca4-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="37ca4-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span><span class="sxs-lookup"><span data-stu-id="37ca4-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="37ca4-125">Control then returns to the `While` statement, and `condition` is again checked.</span><span class="sxs-lookup"><span data-stu-id="37ca4-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="37ca4-126">If `condition` is still `True`, the process is repeated.</span><span class="sxs-lookup"><span data-stu-id="37ca4-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="37ca4-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span><span class="sxs-lookup"><span data-stu-id="37ca4-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="37ca4-128">The `While` statement always checks the condition before it starts the loop.</span><span class="sxs-lookup"><span data-stu-id="37ca4-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="37ca4-129">Looping continues while the condition remains `True`.</span><span class="sxs-lookup"><span data-stu-id="37ca4-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="37ca4-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span><span class="sxs-lookup"><span data-stu-id="37ca4-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="37ca4-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span><span class="sxs-lookup"><span data-stu-id="37ca4-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="37ca4-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="37ca4-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="37ca4-133">You can nest `While` loops by placing one loop within another.</span><span class="sxs-lookup"><span data-stu-id="37ca4-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="37ca4-134">You can also nest different kinds of control structures within one another.</span><span class="sxs-lookup"><span data-stu-id="37ca4-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="37ca4-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="37ca4-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="37ca4-136">Exit While</span><span class="sxs-lookup"><span data-stu-id="37ca4-136">Exit While</span></span>  
 <span data-ttu-id="37ca4-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span><span class="sxs-lookup"><span data-stu-id="37ca4-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="37ca4-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span><span class="sxs-lookup"><span data-stu-id="37ca4-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="37ca4-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span><span class="sxs-lookup"><span data-stu-id="37ca4-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="37ca4-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span><span class="sxs-lookup"><span data-stu-id="37ca4-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="37ca4-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span><span class="sxs-lookup"><span data-stu-id="37ca4-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="37ca4-142">You can then use `Exit While` to escape the loop.</span><span class="sxs-lookup"><span data-stu-id="37ca4-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="37ca4-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span><span class="sxs-lookup"><span data-stu-id="37ca4-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="37ca4-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span><span class="sxs-lookup"><span data-stu-id="37ca4-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="37ca4-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span><span class="sxs-lookup"><span data-stu-id="37ca4-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="37ca4-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span><span class="sxs-lookup"><span data-stu-id="37ca4-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ca4-147">例</span><span class="sxs-lookup"><span data-stu-id="37ca4-147">Example</span></span>  
 <span data-ttu-id="37ca4-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span><span class="sxs-lookup"><span data-stu-id="37ca4-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="37ca4-149">例</span><span class="sxs-lookup"><span data-stu-id="37ca4-149">Example</span></span>  
 <span data-ttu-id="37ca4-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span><span class="sxs-lookup"><span data-stu-id="37ca4-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="37ca4-151">例</span><span class="sxs-lookup"><span data-stu-id="37ca4-151">Example</span></span>  
 <span data-ttu-id="37ca4-152">The following example reads all lines in a text file.</span><span class="sxs-lookup"><span data-stu-id="37ca4-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="37ca4-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span><span class="sxs-lookup"><span data-stu-id="37ca4-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="37ca4-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span><span class="sxs-lookup"><span data-stu-id="37ca4-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="37ca4-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="37ca4-155">See also</span></span>

- [<span data-ttu-id="37ca4-156">ループ構造</span><span class="sxs-lookup"><span data-stu-id="37ca4-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="37ca4-157">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="37ca4-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="37ca4-158">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="37ca4-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="37ca4-159">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="37ca4-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="37ca4-160">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="37ca4-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="37ca4-161">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="37ca4-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="37ca4-162">Continue ステートメント</span><span class="sxs-lookup"><span data-stu-id="37ca4-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
