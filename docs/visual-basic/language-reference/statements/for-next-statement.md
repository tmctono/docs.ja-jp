---
title: For...Next ステートメント (Visual Basic)
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
ms.openlocfilehash: a60293fc837b6d12810a211892c391f24a46d4e6
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582957"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="cac97-102">For...Next ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cac97-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="cac97-103">ステートメントのグループを指定された回数だけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cac97-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="cac97-104">構文</span><span class="sxs-lookup"><span data-stu-id="cac97-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="cac97-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="cac97-105">Parts</span></span>

|<span data-ttu-id="cac97-106">パーツ</span><span class="sxs-lookup"><span data-stu-id="cac97-106">Part</span></span>|<span data-ttu-id="cac97-107">説明</span><span class="sxs-lookup"><span data-stu-id="cac97-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="cac97-108">@No__t_0 ステートメントで必要です。</span><span class="sxs-lookup"><span data-stu-id="cac97-108">Required in the `For` statement.</span></span> <span data-ttu-id="cac97-109">数値変数。</span><span class="sxs-lookup"><span data-stu-id="cac97-109">Numeric variable.</span></span> <span data-ttu-id="cac97-110">ループのコントロール変数。</span><span class="sxs-lookup"><span data-stu-id="cac97-110">The control variable for the loop.</span></span> <span data-ttu-id="cac97-111">詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac97-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="cac97-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cac97-112">Optional.</span></span> <span data-ttu-id="cac97-113">@No__t_0 のデータ型。</span><span class="sxs-lookup"><span data-stu-id="cac97-113">Data type of `counter`.</span></span> <span data-ttu-id="cac97-114">詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac97-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="cac97-115">必須です。</span><span class="sxs-lookup"><span data-stu-id="cac97-115">Required.</span></span> <span data-ttu-id="cac97-116">数値式。</span><span class="sxs-lookup"><span data-stu-id="cac97-116">Numeric expression.</span></span> <span data-ttu-id="cac97-117">`counter` の初期値になります。</span><span class="sxs-lookup"><span data-stu-id="cac97-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="cac97-118">必須です。</span><span class="sxs-lookup"><span data-stu-id="cac97-118">Required.</span></span> <span data-ttu-id="cac97-119">数値式。</span><span class="sxs-lookup"><span data-stu-id="cac97-119">Numeric expression.</span></span> <span data-ttu-id="cac97-120">@No__t_0 の最終的な値。</span><span class="sxs-lookup"><span data-stu-id="cac97-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="cac97-121">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cac97-121">Optional.</span></span> <span data-ttu-id="cac97-122">数値式。</span><span class="sxs-lookup"><span data-stu-id="cac97-122">Numeric expression.</span></span> <span data-ttu-id="cac97-123">ループを通じて毎回 `counter` をインクリメントする量。</span><span class="sxs-lookup"><span data-stu-id="cac97-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="cac97-124">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cac97-124">Optional.</span></span> <span data-ttu-id="cac97-125">指定した回数だけ実行される、`For` と `Next` 間の1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="cac97-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="cac97-126">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cac97-126">Optional.</span></span> <span data-ttu-id="cac97-127">次のループの反復処理に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="cac97-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="cac97-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="cac97-128">Optional.</span></span> <span data-ttu-id="cac97-129">@No__t_0 ループから制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="cac97-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="cac97-130">必須です。</span><span class="sxs-lookup"><span data-stu-id="cac97-130">Required.</span></span> <span data-ttu-id="cac97-131">@No__t_0 ループの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="cac97-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="cac97-132">このステートメントで `To` キーワードを使用して、カウンターの範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="cac97-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="cac97-133">このキーワードは、 [Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)と配列宣言。</span><span class="sxs-lookup"><span data-stu-id="cac97-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="cac97-134">配列の宣言の詳細については、「 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac97-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="cac97-135">簡単な例</span><span class="sxs-lookup"><span data-stu-id="cac97-135">Simple Examples</span></span>

<span data-ttu-id="cac97-136">@No__t_0 を使用しています...一連のステートメントを設定された回数繰り返し実行する場合は `Next` 構造体。</span><span class="sxs-lookup"><span data-stu-id="cac97-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="cac97-137">次の例では、`index` 変数は値1で始まり、ループの反復ごとにインクリメントされ、`index` の値が5に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="cac97-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="cac97-138">次の例では、`number` 変数は2から始まり、ループの反復ごとに0.25 によって減少し、`number` の値が0に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="cac97-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="cac97-139">@No__t_1 の `Step` 引数は、ループの各反復処理で値を0.25 ずつ減らします。</span><span class="sxs-lookup"><span data-stu-id="cac97-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="cac97-140">しばらくお待ちください... [End While ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)または[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)は、ループ内でステートメントを実行する回数が事前にわからない場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="cac97-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="cac97-141">ただし、ループを特定の回数繰り返し実行することが予想される場合は、`For`...`Next` ループの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="cac97-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="cac97-142">ループに最初に入るときのイテレーションの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="cac97-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="cac97-143">ループの入れ子</span><span class="sxs-lookup"><span data-stu-id="cac97-143">Nesting Loops</span></span>

<span data-ttu-id="cac97-144">ループを入れ子にするには、別のループ内にループを挿入し `For` ます。</span><span class="sxs-lookup"><span data-stu-id="cac97-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="cac97-145">入れ子になった `For` の例を次に示します。異なるステップ値を持つ構造体を `Next` します。</span><span class="sxs-lookup"><span data-stu-id="cac97-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="cac97-146">外側のループは、ループの反復ごとに文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="cac97-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="cac97-147">内側のループは、ループの反復ごとにループカウンター変数をデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="cac97-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="cac97-148">ループを入れ子にする場合、各ループには一意の `counter` 変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="cac97-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="cac97-149">また、さまざまな種類のコントロール構造を入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cac97-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="cac97-150">詳細については、[入れ子になった制御構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac97-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="cac97-151">を終了し、を続行します。</span><span class="sxs-lookup"><span data-stu-id="cac97-151">Exit For and Continue For</span></span>

<span data-ttu-id="cac97-152">@No__t_0 ステートメントは、すぐに `For`... `Next` を終了します。</span><span class="sxs-lookup"><span data-stu-id="cac97-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="cac97-153">ループし、`Next` ステートメントの後のステートメントに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="cac97-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="cac97-154">@No__t_0 ステートメントは、ループの次の反復処理に制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="cac97-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="cac97-155">詳細については、「 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac97-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>

<span data-ttu-id="cac97-156">次の例は、`Continue For` と `Exit For` ステートメントの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cac97-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="cac97-157">@No__t_1 には、任意の数の `Exit For` ステートメントを含めることができ `Next`</span><span class="sxs-lookup"><span data-stu-id="cac97-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="cac97-158">ループ.</span><span class="sxs-lookup"><span data-stu-id="cac97-158">loop.</span></span> <span data-ttu-id="cac97-159">入れ子になった `For`... `Next` 内で使用する場合</span><span class="sxs-lookup"><span data-stu-id="cac97-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="cac97-160">ループ、`Exit For` 最も内側のループを終了し、次に高い入れ子レベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="cac97-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="cac97-161">`Exit For` は、何らかの条件 (たとえば、`If`... `Then`... `Else` 構造) を評価した後によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="cac97-162">次の条件に `Exit For` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cac97-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="cac97-163">反復処理を続行することは不要または不可能です。</span><span class="sxs-lookup"><span data-stu-id="cac97-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="cac97-164">この条件は、エラー値または終了要求によって作成できます。</span><span class="sxs-lookup"><span data-stu-id="cac97-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="cac97-165">@No__t_0...`Catch`...`Finally` ステートメントは例外をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="cac97-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="cac97-166">@No__t_1 ブロックの末尾に `Exit For` を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cac97-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="cac97-167">無限ループがあります。これは、大規模または無限の回数実行されるループです。</span><span class="sxs-lookup"><span data-stu-id="cac97-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="cac97-168">このような条件を検出した場合は、`Exit For` を使用してループをエスケープできます。</span><span class="sxs-lookup"><span data-stu-id="cac97-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="cac97-169">詳細については、「 [Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cac97-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="cac97-170">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="cac97-170">Technical Implementation</span></span>

<span data-ttu-id="cac97-171">@No__t_0 の場合`Next` ループが開始され、Visual Basic は `start`、`end`、および `step` を評価します。</span><span class="sxs-lookup"><span data-stu-id="cac97-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="cac97-172">Visual Basic は、現時点ではこれらの値のみを評価し、`start` を `counter` に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cac97-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="cac97-173">ステートメントブロックが実行される前に、Visual Basic は `counter` と `end` を比較します。</span><span class="sxs-lookup"><span data-stu-id="cac97-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="cac97-174">@No__t_0 が `end` の値よりも大きい場合 (または `step` が負の場合) は、`For` ループが終了し、制御が `Next` ステートメントの後のステートメントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="cac97-175">それ以外の場合は、ステートメントブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="cac97-176">Visual Basic が `Next` ステートメントを検出するたびに、`step` によって `counter` がインクリメントされ、`For` ステートメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="cac97-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="cac97-177">ここでも、`counter` を `end` と比較し、その結果に応じてブロックを実行するか、ループを終了します。</span><span class="sxs-lookup"><span data-stu-id="cac97-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="cac97-178">このプロセスは `counter` が `end` になるか、`Exit For` ステートメントが検出されるまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="cac97-179">@No__t_0 が `end` になるまで、ループは停止しません。</span><span class="sxs-lookup"><span data-stu-id="cac97-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="cac97-180">@No__t_0 が `end` に等しい場合、ループは続行されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="cac97-181">ブロックを実行するかどうかを決定する比較は、`step` が正の場合は `end`  <=  `counter`、`counter` が負の場合は  >=  `end` `step` になります。</span><span class="sxs-lookup"><span data-stu-id="cac97-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="cac97-182">ループ内で `counter` の値を変更すると、コードの読み取りやデバッグが困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="cac97-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="cac97-183">@No__t_0、`end`、または `step` の値を変更しても、ループが最初に入力されたときに決定された反復値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="cac97-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="cac97-184">ループを入れ子にした場合、内部レベルの `Next` ステートメントの前に外側の入れ子レベルの `Next` ステートメントが検出されると、コンパイラはエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="cac97-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="cac97-185">ただし、コンパイラは、すべての `Next` ステートメントで `counter` を指定した場合にのみ、この重複エラーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="cac97-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="cac97-186">ステップ引数</span><span class="sxs-lookup"><span data-stu-id="cac97-186">Step Argument</span></span>

<span data-ttu-id="cac97-187">@No__t_0 の値には、正または負のどちらかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cac97-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="cac97-188">このパラメーターは、次の表に従ってループ処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="cac97-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="cac97-189">**ステップ値**</span><span class="sxs-lookup"><span data-stu-id="cac97-189">**Step value**</span></span>|<span data-ttu-id="cac97-190">**ループが実行される場合**</span><span class="sxs-lookup"><span data-stu-id="cac97-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="cac97-191">正または0</span><span class="sxs-lookup"><span data-stu-id="cac97-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="cac97-192">負</span><span class="sxs-lookup"><span data-stu-id="cac97-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="cac97-193">@No__t_0 の既定値は1です。</span><span class="sxs-lookup"><span data-stu-id="cac97-193">The default value of `step` is 1.</span></span>

### <a name="BKMK_Counter"></a><span data-ttu-id="cac97-194">Counter 引数</span><span class="sxs-lookup"><span data-stu-id="cac97-194">Counter Argument</span></span>

<span data-ttu-id="cac97-195">次の表は、`counter` が `For…Next` ループ全体を対象とする新しいローカル変数を定義するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="cac97-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="cac97-196">この決定は `datatype` が存在するかどうか、`counter` が既に定義されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="cac97-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="cac97-197">@No__t_0 存在しますか?</span><span class="sxs-lookup"><span data-stu-id="cac97-197">Is `datatype` present?</span></span>|<span data-ttu-id="cac97-198">@No__t_0 既に定義されていますか?</span><span class="sxs-lookup"><span data-stu-id="cac97-198">Is `counter` already defined?</span></span>|<span data-ttu-id="cac97-199">結果 (`counter` で、`For...Next` ループ全体にスコープが設定された新しいローカル変数が定義されているかどうか)</span><span class="sxs-lookup"><span data-stu-id="cac97-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="cac97-200">Ｘ</span><span class="sxs-lookup"><span data-stu-id="cac97-200">No</span></span>|<span data-ttu-id="cac97-201">[はい]</span><span class="sxs-lookup"><span data-stu-id="cac97-201">Yes</span></span>|<span data-ttu-id="cac97-202">いいえ。 `counter` は既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="cac97-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="cac97-203">@No__t_0 のスコープがプロシージャに対してローカルでない場合は、コンパイル時の警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="cac97-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="cac97-204">Ｘ</span><span class="sxs-lookup"><span data-stu-id="cac97-204">No</span></span>|<span data-ttu-id="cac97-205">Ｘ</span><span class="sxs-lookup"><span data-stu-id="cac97-205">No</span></span>|<span data-ttu-id="cac97-206">はい。</span><span class="sxs-lookup"><span data-stu-id="cac97-206">Yes.</span></span> <span data-ttu-id="cac97-207">データ型は、`start`、`end`、および `step` 式から推論されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="cac97-208">型の推定の詳細については、「[オプション推論ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型の推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cac97-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="cac97-209">[はい]</span><span class="sxs-lookup"><span data-stu-id="cac97-209">Yes</span></span>|<span data-ttu-id="cac97-210">[はい]</span><span class="sxs-lookup"><span data-stu-id="cac97-210">Yes</span></span>|<span data-ttu-id="cac97-211">はい。ただし、既存の `counter` 変数がプロシージャの外部で定義されている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="cac97-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="cac97-212">この変数は個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-212">That variable remains separate.</span></span> <span data-ttu-id="cac97-213">既存の `counter` 変数のスコープがプロシージャに対してローカルである場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cac97-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="cac97-214">[はい]</span><span class="sxs-lookup"><span data-stu-id="cac97-214">Yes</span></span>|<span data-ttu-id="cac97-215">Ｘ</span><span class="sxs-lookup"><span data-stu-id="cac97-215">No</span></span>|<span data-ttu-id="cac97-216">はい。</span><span class="sxs-lookup"><span data-stu-id="cac97-216">Yes.</span></span>|

<span data-ttu-id="cac97-217">@No__t_0 のデータ型によって、イテレーションの種類が決定されます。この型は、次のいずれかの型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cac97-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="cac97-218">@No__t_0、`SByte`、`UShort`、`Short`、`UInteger`、`Integer`、`ULong`、`Long`、`Decimal`、`Single`、0。</span><span class="sxs-lookup"><span data-stu-id="cac97-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="cac97-219">[Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言する列挙体。</span><span class="sxs-lookup"><span data-stu-id="cac97-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

- <span data-ttu-id="cac97-220">`Object`。</span><span class="sxs-lookup"><span data-stu-id="cac97-220">An `Object`.</span></span>

- <span data-ttu-id="cac97-221">次の演算子を持つ `T` 型。 `B` は `Boolean` 式で使用できる型です。</span><span class="sxs-lookup"><span data-stu-id="cac97-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="cac97-222">必要に応じて、`Next` ステートメントで `counter` 変数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cac97-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="cac97-223">この構文を使用すると、特に `For` ループが入れ子になっている場合に、プログラムの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="cac97-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="cac97-224">対応する `For` ステートメントに表示される変数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cac97-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="cac97-225">@No__t_0、`end`、および `step` 式は、`counter` の型に拡大変換される任意のデータ型に評価されます。</span><span class="sxs-lookup"><span data-stu-id="cac97-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="cac97-226">@No__t_0 にユーザー定義型を使用する場合は、`start`、`end`、または `step` の型を `counter` の型に変換するために、`CType` 変換演算子を定義することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cac97-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="cac97-227">例</span><span class="sxs-lookup"><span data-stu-id="cac97-227">Example</span></span>

<span data-ttu-id="cac97-228">次の例では、ジェネリックリストからすべての要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="cac97-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="cac97-229">[For Each...次のステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)の例では、`For` を示しています...`Next` ステートメントを降順で反復処理します。</span><span class="sxs-lookup"><span data-stu-id="cac97-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="cac97-230">この例では、`removeAt` メソッドによって、削除された要素の後にある要素のインデックス値が小さくなるため、この手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cac97-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="cac97-231">例</span><span class="sxs-lookup"><span data-stu-id="cac97-231">Example</span></span>

<span data-ttu-id="cac97-232">次の例では、列挙[ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言された列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="cac97-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="cac97-233">例</span><span class="sxs-lookup"><span data-stu-id="cac97-233">Example</span></span>

<span data-ttu-id="cac97-234">次の例では、ステートメントのパラメーターは、`+`、`-`、`>=`、および `<=` の各演算子に対して演算子のオーバーロードを持つクラスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="cac97-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="cac97-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="cac97-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="cac97-236">ループ構造</span><span class="sxs-lookup"><span data-stu-id="cac97-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="cac97-237">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="cac97-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="cac97-238">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="cac97-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="cac97-239">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="cac97-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="cac97-240">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="cac97-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="cac97-241">コレクション</span><span class="sxs-lookup"><span data-stu-id="cac97-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
