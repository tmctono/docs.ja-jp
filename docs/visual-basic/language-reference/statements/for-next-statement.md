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
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404642"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="dd691-102">For...Next ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd691-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="dd691-103">ステートメントのグループを指定した回数だけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dd691-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="dd691-104">構文</span><span class="sxs-lookup"><span data-stu-id="dd691-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="dd691-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="dd691-105">Parts</span></span>

|<span data-ttu-id="dd691-106">パーツ</span><span class="sxs-lookup"><span data-stu-id="dd691-106">Part</span></span>|<span data-ttu-id="dd691-107">説明</span><span class="sxs-lookup"><span data-stu-id="dd691-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="dd691-108">`For` ステートメントには必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="dd691-108">Required in the `For` statement.</span></span> <span data-ttu-id="dd691-109">数値変数。</span><span class="sxs-lookup"><span data-stu-id="dd691-109">Numeric variable.</span></span> <span data-ttu-id="dd691-110">ループの制御変数。</span><span class="sxs-lookup"><span data-stu-id="dd691-110">The control variable for the loop.</span></span> <span data-ttu-id="dd691-111">詳細については、このトピックで後述する「[Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="dd691-112">任意。</span><span class="sxs-lookup"><span data-stu-id="dd691-112">Optional.</span></span> <span data-ttu-id="dd691-113">`counter` のデータ型。</span><span class="sxs-lookup"><span data-stu-id="dd691-113">Data type of `counter`.</span></span> <span data-ttu-id="dd691-114">詳細については、このトピックで後述する「[Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="dd691-115">必須です。</span><span class="sxs-lookup"><span data-stu-id="dd691-115">Required.</span></span> <span data-ttu-id="dd691-116">数値式。</span><span class="sxs-lookup"><span data-stu-id="dd691-116">Numeric expression.</span></span> <span data-ttu-id="dd691-117">`counter` の初期値になります。</span><span class="sxs-lookup"><span data-stu-id="dd691-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="dd691-118">必須です。</span><span class="sxs-lookup"><span data-stu-id="dd691-118">Required.</span></span> <span data-ttu-id="dd691-119">数値式。</span><span class="sxs-lookup"><span data-stu-id="dd691-119">Numeric expression.</span></span> <span data-ttu-id="dd691-120">`counter` の最終値。</span><span class="sxs-lookup"><span data-stu-id="dd691-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="dd691-121">任意。</span><span class="sxs-lookup"><span data-stu-id="dd691-121">Optional.</span></span> <span data-ttu-id="dd691-122">数値式。</span><span class="sxs-lookup"><span data-stu-id="dd691-122">Numeric expression.</span></span> <span data-ttu-id="dd691-123">ループを通るたびに `counter` が増分される量。</span><span class="sxs-lookup"><span data-stu-id="dd691-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="dd691-124">任意。</span><span class="sxs-lookup"><span data-stu-id="dd691-124">Optional.</span></span> <span data-ttu-id="dd691-125">指定した回数だけ実行される、`For` と `Next` の間の 1 つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="dd691-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="dd691-126">任意。</span><span class="sxs-lookup"><span data-stu-id="dd691-126">Optional.</span></span> <span data-ttu-id="dd691-127">ループの次の反復に制御を移します。</span><span class="sxs-lookup"><span data-stu-id="dd691-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="dd691-128">任意。</span><span class="sxs-lookup"><span data-stu-id="dd691-128">Optional.</span></span> <span data-ttu-id="dd691-129">`For` ループから制御を移します。</span><span class="sxs-lookup"><span data-stu-id="dd691-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="dd691-130">必須です。</span><span class="sxs-lookup"><span data-stu-id="dd691-130">Required.</span></span> <span data-ttu-id="dd691-131">`For` ループの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="dd691-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="dd691-132">このステートメントで `To` キーワードを使用して、カウンターの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd691-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="dd691-133">また、このキーワードは、[Select...Case ステートメント](select-case-statement.md)と配列宣言でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd691-133">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="dd691-134">配列宣言の詳細については、「[Dim ステートメント](dim-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-134">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="dd691-135">簡単な例</span><span class="sxs-lookup"><span data-stu-id="dd691-135">Simple Examples</span></span>

<span data-ttu-id="dd691-136">一連のステートメントを設定した回数だけ繰り返す場合は、`For`...`Next` 構造を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd691-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="dd691-137">次の例では、`index` 変数は値 1 で始まり、ループの反復ごとに増分され、`index` の値が 5 に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="dd691-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="dd691-138">次の例では、`number` 変数は 2 から始まり、ループの反復ごとに 0.25 減り、`number` の値が 0 に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="dd691-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="dd691-139">`-.25` の `Step` 引数は、ループの反復ごとに値を 0.25 ずつ減らします。</span><span class="sxs-lookup"><span data-stu-id="dd691-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="dd691-140">[While...End While ステートメント](while-end-while-statement.md)または [Do...Loop ステートメント](do-loop-statement.md)は、ループ内でステートメントを実行する回数が事前にわからない場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="dd691-140">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="dd691-141">ただし、ループを特定の回数だけ実行する場合は、`For`...`Next` ループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dd691-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="dd691-142">ループに最初に入るときの反復の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="dd691-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="dd691-143">ループを入れ子にする</span><span class="sxs-lookup"><span data-stu-id="dd691-143">Nesting Loops</span></span>

<span data-ttu-id="dd691-144">`For` ループを入れ子にするには、別のループ内にループを配置します。</span><span class="sxs-lookup"><span data-stu-id="dd691-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="dd691-145">次の例は、異なるステップ値を持つ入れ子になった `For`...`Next` 構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="dd691-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="dd691-146">外側のループは、ループの反復ごとに文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="dd691-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="dd691-147">内側のループは、ループの反復ごとにループ カウンター変数の値を減らします。</span><span class="sxs-lookup"><span data-stu-id="dd691-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="dd691-148">ループを入れ子にする場合、各ループには一意の `counter` 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd691-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="dd691-149">また、さまざまな種類の制御構造を相互に入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="dd691-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="dd691-150">詳細については、「[入れ子になった制御構造](../../programming-guide/language-features/control-flow/nested-control-structures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-150">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="dd691-151">Exit For と Continue For</span><span class="sxs-lookup"><span data-stu-id="dd691-151">Exit For and Continue For</span></span>

<span data-ttu-id="dd691-152">`Exit For` ステートメントは、`For`...`Next`</span><span class="sxs-lookup"><span data-stu-id="dd691-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="dd691-153">ループを終了し、`Next` ステートメントの次のステートメントに制御を移します。</span><span class="sxs-lookup"><span data-stu-id="dd691-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="dd691-154">`Continue For` ステートメントは、ループの次の反復に直ちに制御を移します。</span><span class="sxs-lookup"><span data-stu-id="dd691-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="dd691-155">詳細については、「[Continue ステートメント](continue-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-155">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="dd691-156">次の例では、`Continue For` および `Exit For` ステートメントの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dd691-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="dd691-157">`For`...`Next` ループには、任意の数の `Exit For` ステートメントを</span><span class="sxs-lookup"><span data-stu-id="dd691-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="dd691-158">含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dd691-158">loop.</span></span> <span data-ttu-id="dd691-159">入れ子になった `For`...`Next` ループ内で使用すると、</span><span class="sxs-lookup"><span data-stu-id="dd691-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="dd691-160">`Exit For` は、最も内側のループを終了し、次に高いレベルの入れ子に制御を移します。</span><span class="sxs-lookup"><span data-stu-id="dd691-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="dd691-161">`Exit For` は、何らかの条件 (たとえば、`If`...`Then`...`Else` 構造など) を評価した後によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="dd691-162">`Exit For` は次の条件で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd691-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="dd691-163">反復処理の続行が不要または不可能である。</span><span class="sxs-lookup"><span data-stu-id="dd691-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="dd691-164">この条件は、正しくない値または終了要求によって生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd691-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="dd691-165">`Try`...`Catch`...`Finally` ステートメントが例外をキャッチする。</span><span class="sxs-lookup"><span data-stu-id="dd691-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="dd691-166">`Exit For` ブロックの末尾で `Finally` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd691-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="dd691-167">無限ループがある。無限ループは、膨大な回数または無限に実行されるループです。</span><span class="sxs-lookup"><span data-stu-id="dd691-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="dd691-168">このような条件を検出した場合は、`Exit For` を使用してループをエスケープできます。</span><span class="sxs-lookup"><span data-stu-id="dd691-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="dd691-169">詳細については、「[Do...Loop ステートメント](do-loop-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-169">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="dd691-170">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="dd691-170">Technical Implementation</span></span>

<span data-ttu-id="dd691-171">`For`...`Next` ループが開始されると、Visual Basic は `start`、`end`、および `step` を評価します。</span><span class="sxs-lookup"><span data-stu-id="dd691-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="dd691-172">Visual Basic は、現時点ではこれらの値のみを評価してから、`start` を `counter` に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dd691-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="dd691-173">ステートメント ブロックが実行される前に、Visual Basic は `counter` と `end` を比較します。</span><span class="sxs-lookup"><span data-stu-id="dd691-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="dd691-174">`counter` が既に `end` の値よりも大きい場合 (または `step` が負の場合)、`For` ループは終了し、制御は `Next` ステートメントの次のステートメントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="dd691-175">それ以外の場合は、ステートメント ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="dd691-176">Visual Basic は、`Next` ステートメントを検出するたびに `counter` を `step` ずつ増分し、`For` ステートメントに返します。</span><span class="sxs-lookup"><span data-stu-id="dd691-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="dd691-177">もう一度 `counter` と `end` を比較し、その結果に応じて、もう一度ブロックを実行するかループを終了します。</span><span class="sxs-lookup"><span data-stu-id="dd691-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="dd691-178">このプロセスは、`counter` が `end` を渡すか、`Exit For` ステートメントが検出されるまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="dd691-179">`counter` が `end` を渡すまで、ループは停止しません。</span><span class="sxs-lookup"><span data-stu-id="dd691-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="dd691-180">`counter` が `end` に等しい場合、ループは続行されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="dd691-181">ブロックを実行するかどうかを決定する比較は、`step` が正の場合は `counter` <= `end`、`counter` が負の場合は  >= `end``step` です。</span><span class="sxs-lookup"><span data-stu-id="dd691-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="dd691-182">ループ内にあるときに `counter` の値を変更すると、コードの読み取りやデバッグが困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="dd691-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="dd691-183">`start`、`end`、または `step` の値を変更しても、ループが最初に入力されたときに決定された反復値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="dd691-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="dd691-184">ループを入れ子にした場合、内側のレベルの `Next` ステートメントの前に外側の入れ子レベルの `Next` ステートメントが検出されると、コンパイラはエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="dd691-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="dd691-185">ただし、コンパイラは、すべての `Next` ステートメントで `counter` を指定した場合にのみ、この重複エラーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="dd691-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="dd691-186">Step 引数</span><span class="sxs-lookup"><span data-stu-id="dd691-186">Step Argument</span></span>

<span data-ttu-id="dd691-187">`step` の値には、正または負のどちらかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dd691-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="dd691-188">このパラメーターは、次の表に従ってループ処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="dd691-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="dd691-189">**ステップ値**</span><span class="sxs-lookup"><span data-stu-id="dd691-189">**Step value**</span></span>|<span data-ttu-id="dd691-190">**ループが実行される場合**</span><span class="sxs-lookup"><span data-stu-id="dd691-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="dd691-191">正または 0</span><span class="sxs-lookup"><span data-stu-id="dd691-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="dd691-192">負</span><span class="sxs-lookup"><span data-stu-id="dd691-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="dd691-193">`step` の既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="dd691-193">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a> <span data-ttu-id="dd691-194">Counter 引数</span><span class="sxs-lookup"><span data-stu-id="dd691-194">Counter Argument</span></span>

<span data-ttu-id="dd691-195">次の表は、`counter` が `For…Next` ループ全体に範囲が設定されている新しいローカル変数を定義するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd691-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="dd691-196">この決定は、`datatype` が存在するかどうかと、`counter` が既に定義されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="dd691-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="dd691-197">`datatype` が存在する</span><span class="sxs-lookup"><span data-stu-id="dd691-197">Is `datatype` present?</span></span>|<span data-ttu-id="dd691-198">`counter` が既に定義されている</span><span class="sxs-lookup"><span data-stu-id="dd691-198">Is `counter` already defined?</span></span>|<span data-ttu-id="dd691-199">結果 (`counter` が `For...Next` ループ全体にスコープ設定されている新しいローカル変数を定義するかどうか)</span><span class="sxs-lookup"><span data-stu-id="dd691-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="dd691-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="dd691-200">No</span></span>|<span data-ttu-id="dd691-201">はい</span><span class="sxs-lookup"><span data-stu-id="dd691-201">Yes</span></span>|<span data-ttu-id="dd691-202">いいえ。`counter` が既に定義されているため。</span><span class="sxs-lookup"><span data-stu-id="dd691-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="dd691-203">`counter` のスコープがプロシージャに対してローカルでない場合は、コンパイル時の警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="dd691-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="dd691-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="dd691-204">No</span></span>|<span data-ttu-id="dd691-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="dd691-205">No</span></span>|<span data-ttu-id="dd691-206">はい。</span><span class="sxs-lookup"><span data-stu-id="dd691-206">Yes.</span></span> <span data-ttu-id="dd691-207">データ型は、`start`、`end`、および `step` 式から推論されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="dd691-208">型の推定については、「[Option Infer ステートメント](option-infer-statement.md)」と「[ローカル型の推論](../../programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd691-208">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="dd691-209">はい</span><span class="sxs-lookup"><span data-stu-id="dd691-209">Yes</span></span>|<span data-ttu-id="dd691-210">はい</span><span class="sxs-lookup"><span data-stu-id="dd691-210">Yes</span></span>|<span data-ttu-id="dd691-211">はい。ただし、既存の `counter` 変数がプロシージャの外側で定義されている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="dd691-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="dd691-212">この変数は個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="dd691-212">That variable remains separate.</span></span> <span data-ttu-id="dd691-213">既存の `counter` 変数のスコープがプロシージャに対してローカルである場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dd691-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="dd691-214">はい</span><span class="sxs-lookup"><span data-stu-id="dd691-214">Yes</span></span>|<span data-ttu-id="dd691-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="dd691-215">No</span></span>|<span data-ttu-id="dd691-216">はい。</span><span class="sxs-lookup"><span data-stu-id="dd691-216">Yes.</span></span>|

<span data-ttu-id="dd691-217">`counter` のデータ型によって、反復の種類が決定されます。これは、次のいずれかの型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd691-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="dd691-218">`Byte`、`SByte`、`UShort`、`Short`、`UInteger`、`Integer`、`ULong`、`Long`、`Decimal`、`Single`、または `Double`。</span><span class="sxs-lookup"><span data-stu-id="dd691-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="dd691-219">[Enum ステートメント](enum-statement.md)を使用して宣言する列挙型。</span><span class="sxs-lookup"><span data-stu-id="dd691-219">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="dd691-220">`Object`。</span><span class="sxs-lookup"><span data-stu-id="dd691-220">An `Object`.</span></span>

- <span data-ttu-id="dd691-221">次の演算子を持つ型 `T`。ここで、`B` は `Boolean` 式で使用できる型です。</span><span class="sxs-lookup"><span data-stu-id="dd691-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="dd691-222">必要であれば、`Next` ステートメントに `counter` 変数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd691-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="dd691-223">この構文を使用すると、特に `For` ループを入れ子にした場合に、プログラムの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="dd691-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="dd691-224">対応する `For` ステートメントに存在する変数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd691-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="dd691-225">`start`、`end`、および `step` 式は、型 `counter` に拡大変換される任意のデータ型に評価できます。</span><span class="sxs-lookup"><span data-stu-id="dd691-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="dd691-226">`counter` にユーザー定義型を使用する場合は、型 `start`、`end`、または `step` を型 `counter` に変換するために `CType` 変換演算子を定義することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd691-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="dd691-227">例</span><span class="sxs-lookup"><span data-stu-id="dd691-227">Example</span></span>

<span data-ttu-id="dd691-228">次の例では、ジェネリック リストからすべての要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="dd691-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="dd691-229">[For Each...Next ステートメント](for-each-next-statement.md)の代わりに、この例では、降順で反復する `For`...`Next` ステートメントを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd691-229">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="dd691-230">`removeAt` メソッドを実行すると、削除された要素の後にある各要素のインデックス値が小さくなるため、この例ではこの手法を使用しています。</span><span class="sxs-lookup"><span data-stu-id="dd691-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="dd691-231">例</span><span class="sxs-lookup"><span data-stu-id="dd691-231">Example</span></span>

<span data-ttu-id="dd691-232">次の例では、[Enum ステートメント](enum-statement.md)を使用して宣言された列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="dd691-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="dd691-233">例</span><span class="sxs-lookup"><span data-stu-id="dd691-233">Example</span></span>

<span data-ttu-id="dd691-234">次の例では、ステートメントのパラメーターは、`+`、`-`、`>=`、および `<=` の各演算子に対して演算子のオーバーロードがあるクラスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dd691-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="dd691-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd691-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="dd691-236">ループ構造</span><span class="sxs-lookup"><span data-stu-id="dd691-236">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="dd691-237">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="dd691-237">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="dd691-238">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="dd691-238">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="dd691-239">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="dd691-239">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="dd691-240">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="dd691-240">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="dd691-241">コレクション</span><span class="sxs-lookup"><span data-stu-id="dd691-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
