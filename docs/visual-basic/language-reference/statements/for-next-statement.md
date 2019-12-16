---
title: For...Next ステートメント
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 3cae44abb8e790542f11e6c5a5f1e317675ff988
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351182"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="b336c-102">For...Next ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b336c-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="b336c-103">ステートメントのグループを指定された回数だけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="b336c-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="b336c-104">構文</span><span class="sxs-lookup"><span data-stu-id="b336c-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="b336c-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="b336c-105">Parts</span></span>

|<span data-ttu-id="b336c-106">要素</span><span class="sxs-lookup"><span data-stu-id="b336c-106">Part</span></span>|<span data-ttu-id="b336c-107">説明</span><span class="sxs-lookup"><span data-stu-id="b336c-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="b336c-108">`For` ステートメントで必要です。</span><span class="sxs-lookup"><span data-stu-id="b336c-108">Required in the `For` statement.</span></span> <span data-ttu-id="b336c-109">数値変数。</span><span class="sxs-lookup"><span data-stu-id="b336c-109">Numeric variable.</span></span> <span data-ttu-id="b336c-110">ループのコントロール変数。</span><span class="sxs-lookup"><span data-stu-id="b336c-110">The control variable for the loop.</span></span> <span data-ttu-id="b336c-111">詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b336c-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="b336c-112">省略可。</span><span class="sxs-lookup"><span data-stu-id="b336c-112">Optional.</span></span> <span data-ttu-id="b336c-113">`counter`のデータ型。</span><span class="sxs-lookup"><span data-stu-id="b336c-113">Data type of `counter`.</span></span> <span data-ttu-id="b336c-114">詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b336c-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="b336c-115">必須。</span><span class="sxs-lookup"><span data-stu-id="b336c-115">Required.</span></span> <span data-ttu-id="b336c-116">数値式。</span><span class="sxs-lookup"><span data-stu-id="b336c-116">Numeric expression.</span></span> <span data-ttu-id="b336c-117">`counter` の初期値になります。</span><span class="sxs-lookup"><span data-stu-id="b336c-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="b336c-118">必須。</span><span class="sxs-lookup"><span data-stu-id="b336c-118">Required.</span></span> <span data-ttu-id="b336c-119">数値式。</span><span class="sxs-lookup"><span data-stu-id="b336c-119">Numeric expression.</span></span> <span data-ttu-id="b336c-120">`counter`の最終的な値。</span><span class="sxs-lookup"><span data-stu-id="b336c-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="b336c-121">省略可。</span><span class="sxs-lookup"><span data-stu-id="b336c-121">Optional.</span></span> <span data-ttu-id="b336c-122">数値式。</span><span class="sxs-lookup"><span data-stu-id="b336c-122">Numeric expression.</span></span> <span data-ttu-id="b336c-123">ループを通じて毎回 `counter` をインクリメントする量。</span><span class="sxs-lookup"><span data-stu-id="b336c-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="b336c-124">省略可。</span><span class="sxs-lookup"><span data-stu-id="b336c-124">Optional.</span></span> <span data-ttu-id="b336c-125">指定した回数だけ実行される、`For` と `Next` 間の1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="b336c-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="b336c-126">省略可。</span><span class="sxs-lookup"><span data-stu-id="b336c-126">Optional.</span></span> <span data-ttu-id="b336c-127">次のループの反復処理に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="b336c-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="b336c-128">省略可。</span><span class="sxs-lookup"><span data-stu-id="b336c-128">Optional.</span></span> <span data-ttu-id="b336c-129">`For` ループから制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="b336c-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="b336c-130">必須。</span><span class="sxs-lookup"><span data-stu-id="b336c-130">Required.</span></span> <span data-ttu-id="b336c-131">`For` ループの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="b336c-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="b336c-132">このステートメントで `To` キーワードを使用して、カウンターの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="b336c-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="b336c-133">このキーワードは、 [Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)と配列宣言。</span><span class="sxs-lookup"><span data-stu-id="b336c-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="b336c-134">配列の宣言の詳細については、「[Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b336c-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="b336c-135">簡単な例</span><span class="sxs-lookup"><span data-stu-id="b336c-135">Simple Examples</span></span>

<span data-ttu-id="b336c-136">一連のステートメントを設定した回数だけ繰り返す場合は、`For`...`Next` 構造体を使用します。</span><span class="sxs-lookup"><span data-stu-id="b336c-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="b336c-137">次の例では、`index` 変数は値1で始まり、ループの反復ごとにインクリメントされ、`index` の値が5に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="b336c-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="b336c-138">次の例では、`number` 変数は2から始まり、ループの反復ごとに0.25 によって減少し、`number` の値が0に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="b336c-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="b336c-139">`-.25` の `Step` 引数は、ループの各反復処理で値を0.25 ずつ減らします。</span><span class="sxs-lookup"><span data-stu-id="b336c-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="b336c-140">しばらくお待ちください... [End While ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)または[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)は、ループ内でステートメントを実行する回数が事前にわからない場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="b336c-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="b336c-141">ただし、ループを特定の回数だけ実行する場合は、`For`...`Next` ループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b336c-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="b336c-142">ループを最初に入力するときに、イテレーションの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="b336c-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="b336c-143">ループの入れ子</span><span class="sxs-lookup"><span data-stu-id="b336c-143">Nesting Loops</span></span>

<span data-ttu-id="b336c-144">ループを入れ子にするには、別のループ内にループを挿入し `For` ます。</span><span class="sxs-lookup"><span data-stu-id="b336c-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="b336c-145">次の例は、異なるステップ値を持つ入れ子になった `For`...`Next` 構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="b336c-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="b336c-146">外側のループは、ループの反復ごとに文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="b336c-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="b336c-147">内側のループは、ループの反復ごとにループカウンター変数をデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="b336c-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="b336c-148">ループを入れ子にする場合、各ループには一意の `counter` 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="b336c-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="b336c-149">さまざまな種類の制御構造を入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b336c-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="b336c-150">詳細については、「[入れ子になったコントロール構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b336c-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="b336c-151">Exit For と Continue For</span><span class="sxs-lookup"><span data-stu-id="b336c-151">Exit For and Continue For</span></span>

<span data-ttu-id="b336c-152">`Exit For` ステートメントは、すぐに `For`...`Next` を終了します。</span><span class="sxs-lookup"><span data-stu-id="b336c-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="b336c-153">ループし、`Next` ステートメントの後のステートメントに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="b336c-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="b336c-154">`Continue For` ステートメントは、ループの次の反復処理に制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="b336c-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="b336c-155">詳細については、「 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b336c-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>

<span data-ttu-id="b336c-156">次の例は、`Continue For` と `Exit For` ステートメントの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b336c-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="b336c-157">`For`には、任意の数の `Exit For` ステートメントを含めることができ`Next`</span><span class="sxs-lookup"><span data-stu-id="b336c-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="b336c-158">loop。</span><span class="sxs-lookup"><span data-stu-id="b336c-158">loop.</span></span> <span data-ttu-id="b336c-159">入れ子になった `For`...`Next` 内で使用する場合</span><span class="sxs-lookup"><span data-stu-id="b336c-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="b336c-160">ループ、`Exit For` 最も内側のループを終了し、次に高い入れ子レベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="b336c-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="b336c-161">`Exit For` は、何らかの条件 (たとえば、`If`...`Then`...`Else` 構造) を評価した後によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="b336c-162">次の条件に `Exit For` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b336c-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="b336c-163">反復処理を続行することは不要または不可能です。</span><span class="sxs-lookup"><span data-stu-id="b336c-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="b336c-164">この条件は、エラー値または終了要求によって作成できます。</span><span class="sxs-lookup"><span data-stu-id="b336c-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="b336c-165">`Try`...`Catch`...`Finally` ステートメントが例外をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="b336c-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="b336c-166">`Finally` ブロックの末尾に `Exit For` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b336c-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="b336c-167">無限ループがあります。これは、大規模または無限の回数実行されるループです。</span><span class="sxs-lookup"><span data-stu-id="b336c-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="b336c-168">このような条件を検出した場合は、`Exit For` を使用してループをエスケープできます。</span><span class="sxs-lookup"><span data-stu-id="b336c-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="b336c-169">詳細については、「 [Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b336c-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="b336c-170">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="b336c-170">Technical Implementation</span></span>

<span data-ttu-id="b336c-171">`For`...`Next` ループが開始されると、Visual Basic は `start`、`end`、および `step`を評価します。</span><span class="sxs-lookup"><span data-stu-id="b336c-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="b336c-172">Visual Basic は、現時点ではこれらの値のみを評価し、`start` を `counter`に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b336c-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="b336c-173">ステートメントブロックが実行される前に、Visual Basic は `counter` と `end`を比較します。</span><span class="sxs-lookup"><span data-stu-id="b336c-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="b336c-174">`counter` が `end` の値よりも大きい場合 (または `step` が負の場合) は、`For` ループが終了し、制御が `Next` ステートメントの後のステートメントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="b336c-175">それ以外の場合は、ステートメントブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="b336c-176">Visual Basic が `Next` ステートメントを検出するたびに、`step` によって `counter` がインクリメントされ、`For` ステートメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="b336c-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="b336c-177">ここでも、`counter` を `end`と比較し、その結果に応じてブロックを実行するか、ループを終了します。</span><span class="sxs-lookup"><span data-stu-id="b336c-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="b336c-178">このプロセスは `counter` が `end` になるか、`Exit For` ステートメントが検出されるまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="b336c-179">`counter` が `end`になるまで、ループは停止しません。</span><span class="sxs-lookup"><span data-stu-id="b336c-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="b336c-180">`counter` が `end`に等しい場合、ループは続行されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="b336c-181">ブロックを実行するかどうかを決定する比較は、`step` が正の場合は `end`  <= `counter`、`counter`が負の場合は  >= `end` `step` になります。</span><span class="sxs-lookup"><span data-stu-id="b336c-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="b336c-182">ループ内で `counter` の値を変更すると、コードの読み取りやデバッグが困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b336c-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="b336c-183">`start`、`end`、または `step` の値を変更しても、ループが最初に入力されたときに決定された反復値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="b336c-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="b336c-184">ループを入れ子にした場合、内部レベルの `Next` ステートメントの前に外側の入れ子レベルの `Next` ステートメントが検出されると、コンパイラはエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="b336c-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="b336c-185">ただし、コンパイラは、すべての `Next` ステートメントで `counter` を指定した場合にのみ、この重複エラーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="b336c-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="b336c-186">ステップ引数</span><span class="sxs-lookup"><span data-stu-id="b336c-186">Step Argument</span></span>

<span data-ttu-id="b336c-187">`step` の値には、正または負のどちらかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b336c-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="b336c-188">このパラメーターは、次の表に従ってループ処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="b336c-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="b336c-189">**ステップ値**</span><span class="sxs-lookup"><span data-stu-id="b336c-189">**Step value**</span></span>|<span data-ttu-id="b336c-190">**ループが実行される場合**</span><span class="sxs-lookup"><span data-stu-id="b336c-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="b336c-191">正または0</span><span class="sxs-lookup"><span data-stu-id="b336c-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="b336c-192">不適切</span><span class="sxs-lookup"><span data-stu-id="b336c-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="b336c-193">`step` の既定値は1です。</span><span class="sxs-lookup"><span data-stu-id="b336c-193">The default value of `step` is 1.</span></span>

### <a name="BKMK_Counter"></a><span data-ttu-id="b336c-194">Counter 引数</span><span class="sxs-lookup"><span data-stu-id="b336c-194">Counter Argument</span></span>

<span data-ttu-id="b336c-195">次の表は、`counter` が `For…Next` ループ全体を対象とする新しいローカル変数を定義するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="b336c-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="b336c-196">この決定は `datatype` が存在するかどうか、`counter` が既に定義されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b336c-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="b336c-197">`datatype` 存在しますか?</span><span class="sxs-lookup"><span data-stu-id="b336c-197">Is `datatype` present?</span></span>|<span data-ttu-id="b336c-198">`counter` 既に定義されていますか?</span><span class="sxs-lookup"><span data-stu-id="b336c-198">Is `counter` already defined?</span></span>|<span data-ttu-id="b336c-199">結果 (`counter` で、`For...Next` ループ全体にスコープが設定された新しいローカル変数が定義されているかどうか)</span><span class="sxs-lookup"><span data-stu-id="b336c-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="b336c-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="b336c-200">No</span></span>|<span data-ttu-id="b336c-201">はい</span><span class="sxs-lookup"><span data-stu-id="b336c-201">Yes</span></span>|<span data-ttu-id="b336c-202">いいえ。 `counter` は既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="b336c-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="b336c-203">`counter` のスコープがプロシージャに対してローカルでない場合は、コンパイル時の警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="b336c-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="b336c-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="b336c-204">No</span></span>|<span data-ttu-id="b336c-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="b336c-205">No</span></span>|<span data-ttu-id="b336c-206">はい。</span><span class="sxs-lookup"><span data-stu-id="b336c-206">Yes.</span></span> <span data-ttu-id="b336c-207">データ型は、`start`、`end`、および `step` 式から推論されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="b336c-208">型の推定の詳細については、「[オプション推論ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型の推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b336c-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="b336c-209">はい</span><span class="sxs-lookup"><span data-stu-id="b336c-209">Yes</span></span>|<span data-ttu-id="b336c-210">はい</span><span class="sxs-lookup"><span data-stu-id="b336c-210">Yes</span></span>|<span data-ttu-id="b336c-211">はい。ただし、既存の `counter` 変数がプロシージャの外部で定義されている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="b336c-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="b336c-212">この変数は個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-212">That variable remains separate.</span></span> <span data-ttu-id="b336c-213">既存の `counter` 変数のスコープがプロシージャに対してローカルである場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b336c-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="b336c-214">はい</span><span class="sxs-lookup"><span data-stu-id="b336c-214">Yes</span></span>|<span data-ttu-id="b336c-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="b336c-215">No</span></span>|<span data-ttu-id="b336c-216">はい。</span><span class="sxs-lookup"><span data-stu-id="b336c-216">Yes.</span></span>|

<span data-ttu-id="b336c-217">`counter` のデータ型によって、イテレーションの種類が決定されます。この型は、次のいずれかの型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b336c-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="b336c-218">`Byte`、`SByte`、`UShort`、`Short`、`UInteger`、`Integer`、`ULong`、`Long`、`Decimal`、`Single`、`Double`。</span><span class="sxs-lookup"><span data-stu-id="b336c-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="b336c-219">[Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言する列挙体。</span><span class="sxs-lookup"><span data-stu-id="b336c-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

- <span data-ttu-id="b336c-220">`Object`。</span><span class="sxs-lookup"><span data-stu-id="b336c-220">An `Object`.</span></span>

- <span data-ttu-id="b336c-221">次の演算子を持つ `T` 型。 `B` は `Boolean` 式で使用できる型です。</span><span class="sxs-lookup"><span data-stu-id="b336c-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="b336c-222">必要に応じて、`Next` ステートメントで `counter` 変数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b336c-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="b336c-223">この構文を使用すると、特に `For` ループが入れ子になっている場合に、プログラムの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="b336c-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="b336c-224">対応する `For` ステートメントに表示される変数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b336c-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="b336c-225">`start`、`end`、および `step` 式は、`counter`の型に拡大変換される任意のデータ型に評価されます。</span><span class="sxs-lookup"><span data-stu-id="b336c-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="b336c-226">`counter`にユーザー定義型を使用する場合は、`start`、`end`、または `step` の型を `counter`の型に変換するために、`CType` 変換演算子を定義することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b336c-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="b336c-227">例</span><span class="sxs-lookup"><span data-stu-id="b336c-227">Example</span></span>

<span data-ttu-id="b336c-228">次の例では、ジェネリックリストからすべての要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="b336c-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="b336c-229">[For Each...次のステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)の例では、降順に反復処理する `For`...`Next` ステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="b336c-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="b336c-230">この例では、`removeAt` メソッドによって、削除された要素の後にある要素のインデックス値が小さくなるため、この手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="b336c-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="b336c-231">例</span><span class="sxs-lookup"><span data-stu-id="b336c-231">Example</span></span>

<span data-ttu-id="b336c-232">次の例では、[Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言された列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="b336c-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="b336c-233">例</span><span class="sxs-lookup"><span data-stu-id="b336c-233">Example</span></span>

<span data-ttu-id="b336c-234">次の例では、ステートメントのパラメーターは、`+`、`-`、`>=`、および `<=` の各演算子に対して演算子のオーバーロードを持つクラスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="b336c-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="b336c-235">参照</span><span class="sxs-lookup"><span data-stu-id="b336c-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="b336c-236">ループ構造</span><span class="sxs-lookup"><span data-stu-id="b336c-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="b336c-237">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="b336c-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="b336c-238">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="b336c-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="b336c-239">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="b336c-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="b336c-240">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="b336c-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="b336c-241">コレクション</span><span class="sxs-lookup"><span data-stu-id="b336c-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
