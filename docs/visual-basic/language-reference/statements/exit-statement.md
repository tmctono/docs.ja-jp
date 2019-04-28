---
title: Exit ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638117"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="39c62-102">Exit ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39c62-102">Exit Statement (Visual Basic)</span></span>
<span data-ttu-id="39c62-103">プロシージャまたはブロックを終了し、プロシージャの呼び出しまたはブロックの定義を次のステートメントに直ちに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="39c62-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c62-104">構文</span><span class="sxs-lookup"><span data-stu-id="39c62-104">Syntax</span></span>  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a><span data-ttu-id="39c62-105">ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-105">Statements</span></span>  
 `Exit Do`  
 <span data-ttu-id="39c62-106">すぐに終了させる、`Do`ループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="39c62-107">ステートメントに次の実行が続行されます、`Loop`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="39c62-108">`Exit Do` 内部でのみ使用できます、`Do`ループします。</span><span class="sxs-lookup"><span data-stu-id="39c62-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="39c62-109">使用すると内で入れ子になった`Do`ループ、`Exit Do`最も内側のループを終了し、入れ子の上位のレベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="39c62-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit For`  
 <span data-ttu-id="39c62-110">すぐに終了させる、`For`ループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="39c62-111">ステートメントに次の実行が続行されます、`Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="39c62-112">`Exit For` 内部でのみ使用できます、 `For`.`Next`または`For Each`.`Next`ループします。</span><span class="sxs-lookup"><span data-stu-id="39c62-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="39c62-113">使用すると内で入れ子になった`For`ループ、`Exit For`最も内側のループを終了し、入れ子の上位のレベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="39c62-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 `Exit Function`  
 <span data-ttu-id="39c62-114">すぐに終了させる、`Function`プロシージャが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="39c62-115">呼び出したステートメントの次のステートメントと実行が継続、`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="39c62-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="39c62-116">`Exit Function` 内部でのみ使用できます、`Function`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="39c62-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>  
  
 <span data-ttu-id="39c62-117">戻り値を指定するには前に、の行に関数名に値を割り当てることができます、`Exit Function`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="39c62-118">戻り値を代入を 1 つのステートメント内の関数の終了は、代わりに使える、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="39c62-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 `Exit Property`  
 <span data-ttu-id="39c62-119">すぐに終了させる、`Property`プロシージャが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="39c62-120">呼び出したステートメントと実行が継続、`Property`手順、つまり、要求またはプロパティの値を設定するステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="39c62-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="39c62-121">`Exit Property` プロパティの内部でのみ使用できます`Get`または`Set`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="39c62-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>  
  
 <span data-ttu-id="39c62-122">戻り値を指定する、`Get`プロシージャでは前に、の行に関数名に値を割り当てることができます、`Exit Property`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="39c62-123">戻り値と終了を割り当てる、 `Get` 1 つのステートメントでプロシージャを使用する、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>  
  
 <span data-ttu-id="39c62-124">`Set`プロシージャ、`Exit Property`ステートメントは、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Select`  
 <span data-ttu-id="39c62-125">すぐに終了させる、`Select Case`ブロックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="39c62-126">ステートメントに次の実行が続行されます、`End Select`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="39c62-127">`Exit Select` 内部でのみ使用できます、`Select Case`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>  
  
 `Exit Sub`  
 <span data-ttu-id="39c62-128">すぐに終了させる、`Sub`プロシージャが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="39c62-129">呼び出したステートメントの次のステートメントと実行が継続、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="39c62-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="39c62-130">`Exit Sub` 内部でのみ使用できます、`Sub`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="39c62-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>  
  
 <span data-ttu-id="39c62-131">`Sub`プロシージャ、`Exit Sub`ステートメントは、`Return`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>  
  
 `Exit Try`  
 <span data-ttu-id="39c62-132">すぐに終了させる、`Try`または`Catch`ブロックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="39c62-133">実行が継続、 `Finally` 、1 つである場合、またはステートメントに次のブロック、`End Try`ステートメントがそれ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="39c62-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="39c62-134">`Exit Try` 内部でのみ使用できます、`Try`または`Catch`ブロック内部に存在しないと、`Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="39c62-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>  
  
 `Exit While`  
 <span data-ttu-id="39c62-135">すぐに終了させる、`While`ループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c62-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="39c62-136">ステートメントに次の実行が続行されます、`End While`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="39c62-137">`Exit While` 内部でのみ使用できます、`While`ループします。</span><span class="sxs-lookup"><span data-stu-id="39c62-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="39c62-138">使用すると内で入れ子になった`While`ループ、`Exit While`ループの 1 つの入れ子になったレベルは、ループに制御を転送、`Exit While`に発生します。</span><span class="sxs-lookup"><span data-stu-id="39c62-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39c62-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="39c62-139">Remarks</span></span>  
 <span data-ttu-id="39c62-140">混同しないでください`Exit`ステートメントと`End`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="39c62-141">`Exit` ステートメントの末尾を一切定義しません。</span><span class="sxs-lookup"><span data-stu-id="39c62-141">`Exit` does not define the end of a statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c62-142">例</span><span class="sxs-lookup"><span data-stu-id="39c62-142">Example</span></span>  
 <span data-ttu-id="39c62-143">次の例では、ループの条件がループを終了時に、`index`変数が 100 より大きい。</span><span class="sxs-lookup"><span data-stu-id="39c62-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="39c62-144">`If`ループでは、ステートメントがただし、により、`Exit Do`インデックス変数が 10 より大きい場合は、ループを停止するステートメント。</span><span class="sxs-lookup"><span data-stu-id="39c62-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="39c62-145">例</span><span class="sxs-lookup"><span data-stu-id="39c62-145">Example</span></span>  
 <span data-ttu-id="39c62-146">次の例では、関数名に、戻り値を割り当てて`myFunction`、しを使用して`Exit Function`関数から返される。</span><span class="sxs-lookup"><span data-stu-id="39c62-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="39c62-147">例</span><span class="sxs-lookup"><span data-stu-id="39c62-147">Example</span></span>  
 <span data-ttu-id="39c62-148">次の例では、 [Return ステートメント](../../../visual-basic/language-reference/statements/return-statement.md)戻り値を代入し、関数を終了します。</span><span class="sxs-lookup"><span data-stu-id="39c62-148">The following example uses the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) to assign the return value and exit the function.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="39c62-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="39c62-149">See also</span></span>

- [<span data-ttu-id="39c62-150">Continue ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-150">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
- [<span data-ttu-id="39c62-151">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-151">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="39c62-152">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-152">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="39c62-153">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-153">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="39c62-154">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-154">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="39c62-155">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-155">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="39c62-156">Return ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-156">Return Statement</span></span>](../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="39c62-157">Stop ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-157">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="39c62-158">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-158">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="39c62-159">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="39c62-159">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
