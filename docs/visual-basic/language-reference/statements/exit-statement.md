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
ms.openlocfilehash: 9c25653809c51662ea5b606ab97be6a9b50d5986
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71956942"
---
# <a name="exit-statement-visual-basic"></a><span data-ttu-id="e13fa-102">Exit ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e13fa-102">Exit Statement (Visual Basic)</span></span>

<span data-ttu-id="e13fa-103">プロシージャまたはブロックを終了し、プロシージャ呼び出しまたはブロック定義に続くステートメントに制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-103">Exits a procedure or block and transfers control immediately to the statement following the procedure call or the block definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="e13fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="e13fa-104">Syntax</span></span>

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a><span data-ttu-id="e13fa-105">ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-105">Statements</span></span>

 `Exit Do`  
 <span data-ttu-id="e13fa-106">が表示されている `Do` ループを直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-106">Immediately exits the `Do` loop in which it appears.</span></span> <span data-ttu-id="e13fa-107">実行は、`Loop` ステートメントに続くステートメントを使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-107">Execution continues with the statement following the `Loop` statement.</span></span> <span data-ttu-id="e13fa-108">`Exit Do` は、`Do` ループ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-108">`Exit Do` can be used only inside a `Do` loop.</span></span> <span data-ttu-id="e13fa-109">入れ子になった `Do` ループ内で使用すると、`Exit Do` 最も内側のループを終了し、次に高い入れ子レベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-109">When used within nested `Do` loops, `Exit Do` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit For`  
 <span data-ttu-id="e13fa-110">が表示されている `For` ループを直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-110">Immediately exits the `For` loop in which it appears.</span></span> <span data-ttu-id="e13fa-111">実行は、`Next` ステートメントに続くステートメントを使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-111">Execution continues with the statement following the `Next` statement.</span></span> <span data-ttu-id="e13fa-112">`Exit For` は、`For`...`Next` または `For Each`...`Next` ループ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-112">`Exit For` can be used only inside a `For`...`Next` or `For Each`...`Next` loop.</span></span> <span data-ttu-id="e13fa-113">入れ子になった `For` ループ内で使用すると、`Exit For` 最も内側のループを終了し、次に高い入れ子レベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-113">When used within nested `For` loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

 `Exit Function`  
 <span data-ttu-id="e13fa-114">が表示されている `Function` プロシージャをすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-114">Immediately exits the `Function` procedure in which it appears.</span></span> <span data-ttu-id="e13fa-115">実行は、`Function` プロシージャを呼び出したステートメントの後に続くステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-115">Execution continues with the statement following the statement that called the `Function` procedure.</span></span> <span data-ttu-id="e13fa-116">`Exit Function` は、`Function` プロシージャ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-116">`Exit Function` can be used only inside a `Function` procedure.</span></span>

 <span data-ttu-id="e13fa-117">戻り値を指定するには、`Exit Function` ステートメントの前にある行の関数名に値を代入します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-117">To specify a return value, you can assign the value to the function name on a line before the `Exit Function` statement.</span></span> <span data-ttu-id="e13fa-118">戻り値を割り当てて、1つのステートメントで関数を終了するには、代わりに[Return ステートメント](return-statement.md)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-118">To assign the return value and exit the function in one statement, you can instead use the [Return Statement](return-statement.md).</span></span>

 `Exit Property`  
 <span data-ttu-id="e13fa-119">が表示されている `Property` プロシージャをすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-119">Immediately exits the `Property` procedure in which it appears.</span></span> <span data-ttu-id="e13fa-120">実行は、`Property` プロシージャを呼び出したステートメント、つまり、プロパティの値を要求または設定するステートメントによって続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-120">Execution continues with the statement that called the `Property` procedure, that is, with the statement requesting or setting the property's value.</span></span> <span data-ttu-id="e13fa-121">`Exit Property` は、プロパティの `Get` または `Set` プロシージャ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-121">`Exit Property` can be used only inside a property's `Get` or `Set` procedure.</span></span>

 <span data-ttu-id="e13fa-122">`Get` プロシージャで戻り値を指定するには、`Exit Property` ステートメントの前にある行の関数名に値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-122">To specify a return value in a `Get` procedure, you can assign the value to the function name on a line before the `Exit Property` statement.</span></span> <span data-ttu-id="e13fa-123">1つのステートメントで戻り値を割り当てて `Get` プロシージャを終了するには、代わりに `Return` ステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-123">To assign the return value and exit the `Get` procedure in one statement, you can instead use the `Return` statement.</span></span>

 <span data-ttu-id="e13fa-124">`Set` のプロシージャでは、`Exit Property` ステートメントは `Return` ステートメントと同じです。</span><span class="sxs-lookup"><span data-stu-id="e13fa-124">In a `Set` procedure, the `Exit Property` statement is equivalent to the `Return` statement.</span></span>

 `Exit Select`  
 <span data-ttu-id="e13fa-125">が表示されている `Select Case` ブロックを直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-125">Immediately exits the `Select Case` block in which it appears.</span></span> <span data-ttu-id="e13fa-126">実行は、`End Select` ステートメントに続くステートメントを使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-126">Execution continues with the statement following the `End Select` statement.</span></span> <span data-ttu-id="e13fa-127">`Exit Select` は、`Select Case` ステートメント内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-127">`Exit Select` can be used only inside a `Select Case` statement.</span></span>

 `Exit Sub`  
 <span data-ttu-id="e13fa-128">が表示されている `Sub` プロシージャをすぐに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-128">Immediately exits the `Sub` procedure in which it appears.</span></span> <span data-ttu-id="e13fa-129">実行は、`Sub` プロシージャを呼び出したステートメントの後に続くステートメントから続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-129">Execution continues with the statement following the statement that called the `Sub` procedure.</span></span> <span data-ttu-id="e13fa-130">`Exit Sub` は、`Sub` プロシージャ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-130">`Exit Sub` can be used only inside a `Sub` procedure.</span></span>

 <span data-ttu-id="e13fa-131">`Sub` のプロシージャでは、`Exit Sub` ステートメントは `Return` ステートメントと同じです。</span><span class="sxs-lookup"><span data-stu-id="e13fa-131">In a `Sub` procedure, the `Exit Sub` statement is equivalent to the `Return` statement.</span></span>

 `Exit Try`  
 <span data-ttu-id="e13fa-132">が表示されている `Try` または `Catch` ブロックを直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-132">Immediately exits the `Try` or `Catch` block in which it appears.</span></span> <span data-ttu-id="e13fa-133">実行は、存在する場合は `Finally` ブロックで続行されます。それ以外の場合は `End Try` ステートメントの後のステートメントで続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-133">Execution continues with the `Finally` block if there is one, or with the statement following the `End Try` statement otherwise.</span></span> <span data-ttu-id="e13fa-134">`Exit Try` は、`Finally` ブロック内ではなく、`Try` または `Catch` ブロック内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-134">`Exit Try` can be used only inside a `Try` or `Catch` block, and not inside a `Finally` block.</span></span>

 `Exit While`  
 <span data-ttu-id="e13fa-135">が表示されている `While` ループを直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-135">Immediately exits the `While` loop in which it appears.</span></span> <span data-ttu-id="e13fa-136">実行は、`End While` ステートメントに続くステートメントを使用して続行されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-136">Execution continues with the statement following the `End While` statement.</span></span> <span data-ttu-id="e13fa-137">`Exit While` は、`While` ループ内でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-137">`Exit While` can be used only inside a `While` loop.</span></span> <span data-ttu-id="e13fa-138">入れ子になった `While` ループ内で使用される場合、`Exit While` は `Exit While` が発生するループの上に入れ子になった1つのレベルであるループに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-138">When used within nested `While` loops, `Exit While` transfers control to the loop that is one nested level above the loop where `Exit While` occurs.</span></span>

## <a name="remarks"></a><span data-ttu-id="e13fa-139">コメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-139">Remarks</span></span>

<span data-ttu-id="e13fa-140">`Exit` ステートメントを `End` ステートメントと混同しないでください。</span><span class="sxs-lookup"><span data-stu-id="e13fa-140">Do not confuse `Exit` statements with `End` statements.</span></span> <span data-ttu-id="e13fa-141">`Exit` では、ステートメントの末尾が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="e13fa-141">`Exit` does not define the end of a statement.</span></span>

## <a name="example"></a><span data-ttu-id="e13fa-142">例</span><span class="sxs-lookup"><span data-stu-id="e13fa-142">Example</span></span>

<span data-ttu-id="e13fa-143">次の例では、`index` 変数が100より大きい場合、ループ条件によってループが停止します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-143">In the following example, the loop condition stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="e13fa-144">ただし、ループ内の `If` ステートメントでは、インデックス変数が10より大きい場合、`Exit Do` ステートメントによってループが停止されます。</span><span class="sxs-lookup"><span data-stu-id="e13fa-144">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a><span data-ttu-id="e13fa-145">例</span><span class="sxs-lookup"><span data-stu-id="e13fa-145">Example</span></span>

<span data-ttu-id="e13fa-146">次の例では、関数名 `myFunction`に戻り値を代入し、`Exit Function` を使用して関数からを返します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-146">The following example assigns the return value to the function name `myFunction`, and then uses `Exit Function` to return from the function:</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a><span data-ttu-id="e13fa-147">例</span><span class="sxs-lookup"><span data-stu-id="e13fa-147">Example</span></span>

<span data-ttu-id="e13fa-148">次の例では、 [Return ステートメント](return-statement.md)を使用して戻り値を割り当て、関数を終了します。</span><span class="sxs-lookup"><span data-stu-id="e13fa-148">The following example uses the [Return Statement](return-statement.md) to assign the return value and exit the function:</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a><span data-ttu-id="e13fa-149">参照</span><span class="sxs-lookup"><span data-stu-id="e13fa-149">See also</span></span>

- [<span data-ttu-id="e13fa-150">Continue ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-150">Continue Statement</span></span>](continue-statement.md)
- [<span data-ttu-id="e13fa-151">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-151">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="e13fa-152">End ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-152">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="e13fa-153">For Each...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-153">For Each...Next Statement</span></span>](for-each-next-statement.md)
- [<span data-ttu-id="e13fa-154">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-154">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="e13fa-155">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-155">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="e13fa-156">Return ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-156">Return Statement</span></span>](return-statement.md)
- [<span data-ttu-id="e13fa-157">Stop ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-157">Stop Statement</span></span>](stop-statement.md)
- [<span data-ttu-id="e13fa-158">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-158">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="e13fa-159">Try...Catch...Finally ステートメント</span><span class="sxs-lookup"><span data-stu-id="e13fa-159">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
