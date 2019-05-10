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
ms.openlocfilehash: 7f982c97bd76288ecd1a8d1f53fc2b25b0bb829e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623885"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="47d92-102">For...Next ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47d92-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="47d92-103">ステートメントのグループを指定した回数だけ繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="47d92-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d92-104">構文</span><span class="sxs-lookup"><span data-stu-id="47d92-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="47d92-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="47d92-105">Parts</span></span>  
  
|<span data-ttu-id="47d92-106">パーツ</span><span class="sxs-lookup"><span data-stu-id="47d92-106">Part</span></span>|<span data-ttu-id="47d92-107">説明</span><span class="sxs-lookup"><span data-stu-id="47d92-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="47d92-108">必要な`For`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-108">Required in the `For` statement.</span></span> <span data-ttu-id="47d92-109">数値型の変数。</span><span class="sxs-lookup"><span data-stu-id="47d92-109">Numeric variable.</span></span> <span data-ttu-id="47d92-110">ループ コントロール変数。</span><span class="sxs-lookup"><span data-stu-id="47d92-110">The control variable for the loop.</span></span> <span data-ttu-id="47d92-111">詳細については、次を参照してください。[カウンター引数](#BKMK_Counter)このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="47d92-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="47d92-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47d92-112">Optional.</span></span> <span data-ttu-id="47d92-113">データ型`counter`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-113">Data type of `counter`.</span></span> <span data-ttu-id="47d92-114">詳細については、次を参照してください。[カウンター引数](#BKMK_Counter)このトピックで後述します。</span><span class="sxs-lookup"><span data-stu-id="47d92-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="47d92-115">必須。</span><span class="sxs-lookup"><span data-stu-id="47d92-115">Required.</span></span> <span data-ttu-id="47d92-116">数値式。</span><span class="sxs-lookup"><span data-stu-id="47d92-116">Numeric expression.</span></span> <span data-ttu-id="47d92-117">`counter` の初期値になります。</span><span class="sxs-lookup"><span data-stu-id="47d92-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="47d92-118">必須。</span><span class="sxs-lookup"><span data-stu-id="47d92-118">Required.</span></span> <span data-ttu-id="47d92-119">数値式。</span><span class="sxs-lookup"><span data-stu-id="47d92-119">Numeric expression.</span></span> <span data-ttu-id="47d92-120">最終値`counter`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="47d92-121">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47d92-121">Optional.</span></span> <span data-ttu-id="47d92-122">数値式。</span><span class="sxs-lookup"><span data-stu-id="47d92-122">Numeric expression.</span></span> <span data-ttu-id="47d92-123">量`counter`ループのたびに増加します。</span><span class="sxs-lookup"><span data-stu-id="47d92-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="47d92-124">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47d92-124">Optional.</span></span> <span data-ttu-id="47d92-125">1 つまたは複数のステートメント間`For`と`Next`指定された回数を実行します。</span><span class="sxs-lookup"><span data-stu-id="47d92-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="47d92-126">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47d92-126">Optional.</span></span> <span data-ttu-id="47d92-127">次のループの反復処理の制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="47d92-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="47d92-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="47d92-128">Optional.</span></span> <span data-ttu-id="47d92-129">うちに制御を転送、`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="47d92-130">必須。</span><span class="sxs-lookup"><span data-stu-id="47d92-130">Required.</span></span> <span data-ttu-id="47d92-131">定義を終了、`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="47d92-132">`To`キーワードは、カウンターの範囲を指定するこのステートメントで使用されます。</span><span class="sxs-lookup"><span data-stu-id="47d92-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="47d92-133">このキーワードを使用することも、[を選択しています.Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)と配列の宣言。</span><span class="sxs-lookup"><span data-stu-id="47d92-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="47d92-134">配列の宣言に関する詳細については、次を参照してください。 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="47d92-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="47d92-135">簡単な例</span><span class="sxs-lookup"><span data-stu-id="47d92-135">Simple Examples</span></span>  
 <span data-ttu-id="47d92-136">使用する、 `For`.`Next`時間数の一連のステートメントを繰り返し表示するときに構造体します。</span><span class="sxs-lookup"><span data-stu-id="47d92-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="47d92-137">次の例では、`index`変数の値が 1 で開始し、終了の値の後に、ループの反復ごとにインクリメントされます`index`5 に到達します。</span><span class="sxs-lookup"><span data-stu-id="47d92-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 <span data-ttu-id="47d92-138">次の例では、`number`変数が 2 から開始し、終了の値の後に、ループの各反復処理で 0.25 を消費`number`が 0 になります。</span><span class="sxs-lookup"><span data-stu-id="47d92-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="47d92-139">`Step`の引数`-.25`ループの各反復処理で 0.25 で値を減らします。</span><span class="sxs-lookup"><span data-stu-id="47d92-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  <span data-ttu-id="47d92-140">A[中.While ステートメント終了](../../../visual-basic/language-reference/statements/while-end-while-statement.md)または[の操作を行います.Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)ときがわからない事前に、ループ内でステートメントを実行する回数をうまく機能します。</span><span class="sxs-lookup"><span data-stu-id="47d92-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="47d92-141">ただし、特定回数、ループを実行しようとする`For`.`Next`ループが適しています。</span><span class="sxs-lookup"><span data-stu-id="47d92-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="47d92-142">ループを最初に入力したときに、イテレーションの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="47d92-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="47d92-143">ループの入れ子</span><span class="sxs-lookup"><span data-stu-id="47d92-143">Nesting Loops</span></span>  
 <span data-ttu-id="47d92-144">入れ子にすることができます`For`内に別の 1 つのループを配置することでループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="47d92-145">次の例で入れ子になった`For`.`Next`異なるステップ値を持つ構造体。</span><span class="sxs-lookup"><span data-stu-id="47d92-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="47d92-146">外側のループは、ループのイテレーションごとに文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="47d92-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="47d92-147">内側のループのイテレーションごとのループ カウンター変数をデクリメントをループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 <span data-ttu-id="47d92-148">ループを入れ子にする場合は、各ループが一意必要があります`counter`変数。</span><span class="sxs-lookup"><span data-stu-id="47d92-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="47d92-149">内で他のさまざまな種類の制御構造を入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="47d92-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="47d92-150">詳細については、次を参照してください。[制御構造の入れ子になった](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)します。</span><span class="sxs-lookup"><span data-stu-id="47d92-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="47d92-151">終了しの続行</span><span class="sxs-lookup"><span data-stu-id="47d92-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="47d92-152">`Exit For`ステートメントがすぐに終了させる、 `For`.`Next`</span><span class="sxs-lookup"><span data-stu-id="47d92-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="47d92-153">これに続くステートメントにループと転送の制御、`Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="47d92-154">`Continue For`ステートメント コントロールに直ちに移します、ループの次の反復処理します。</span><span class="sxs-lookup"><span data-stu-id="47d92-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="47d92-155">詳細については、次を参照してください。 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="47d92-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="47d92-156">次の例では、使用、`Continue For`と`Exit For`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 <span data-ttu-id="47d92-157">任意の数を配置する`Exit For`内のステートメントを`For`.`Next`</span><span class="sxs-lookup"><span data-stu-id="47d92-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="47d92-158">ループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-158">loop.</span></span> <span data-ttu-id="47d92-159">使用すると内で入れ子になった`For`.`Next`</span><span class="sxs-lookup"><span data-stu-id="47d92-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="47d92-160">ループ、`Exit For`最も内側のループを終了し、入れ子の上位のレベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="47d92-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="47d92-161">`Exit For` いくつかの条件を評価した後は、よく使用 (たとえば、 `If`.`Then`...`Else`構造)。</span><span class="sxs-lookup"><span data-stu-id="47d92-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="47d92-162">使用する`Exit For`次の条件。</span><span class="sxs-lookup"><span data-stu-id="47d92-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
- <span data-ttu-id="47d92-163">反復処理を続けることは不要なか不可能です。</span><span class="sxs-lookup"><span data-stu-id="47d92-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="47d92-164">エラー値や終了要求は、この条件を作成可能性があります。</span><span class="sxs-lookup"><span data-stu-id="47d92-164">An erroneous value or a termination request might create this condition.</span></span>  
  
- <span data-ttu-id="47d92-165">A `Try`.`Catch`...`Finally`ステートメントが例外をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="47d92-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="47d92-166">使用する場合があります`Exit For`の最後に、`Finally`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="47d92-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
- <span data-ttu-id="47d92-167">何度も長時間または無限でも実行できるループ、無限ループがあります。</span><span class="sxs-lookup"><span data-stu-id="47d92-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="47d92-168">このような条件を検出した場合は使用できます`Exit For`ループを抜けます。</span><span class="sxs-lookup"><span data-stu-id="47d92-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="47d92-169">詳細については、次を参照してください[操作を行います...ステートメントをループ](../../../visual-basic/language-reference/statements/do-loop-statement.md)です。</span><span class="sxs-lookup"><span data-stu-id="47d92-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="47d92-170">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="47d92-170">Technical Implementation</span></span>  
 <span data-ttu-id="47d92-171">ときに、 `For`.`Next`ループの開始、Visual Basic の評価`start`、 `end`、および`step`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="47d92-172">Visual Basic では、この時間とし、割り当てにのみこれらの値を評価`start`に`counter`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="47d92-173">ステートメントの前にブロックが実行、Visual Basic の比較`counter`に`end`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="47d92-174">場合`counter`よりも大きいは既に、`end`値 (より小さい場合、または`step`が負の値)、`For`ループが終了と制御に続くステートメントに渡す、`Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="47d92-175">それ以外の場合、ステートメント ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="47d92-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="47d92-176">Visual Basic が発生するたびに、`Next`インクリメント ステートメントでは、`counter`によって`step`に戻って、`For`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="47d92-177">もう一度比較`counter`に`end`、もう一度、ブロックが実行か、その結果に応じて、ループが終了したとします。</span><span class="sxs-lookup"><span data-stu-id="47d92-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="47d92-178">までこのプロセスは継続`counter`渡します`end`または`Exit For`ステートメントが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="47d92-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="47d92-179">まで、ループが停止しない`counter`経過`end`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="47d92-180">場合`counter`と等しい`end`ループが続行されます。</span><span class="sxs-lookup"><span data-stu-id="47d92-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="47d92-181">ブロックを実行するかどうかを決定する比較では、 `counter`  <=  `end`場合`step`が正の値と`counter`  >=  `end`場合`step`が負の値。</span><span class="sxs-lookup"><span data-stu-id="47d92-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="47d92-182">値を変更する場合`counter`ループ内で、コードは読み取り、デバッグが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="47d92-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="47d92-183">値を変更する`start`、 `end`、または`step`ループが最初に入力すると判断した反復値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="47d92-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="47d92-184">ループを入れ子にする場合、コンパイラはエラーが発生したかどうか、`Next`する前に外側の入れ子レベルのステートメント、`Next`内部レベルのステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="47d92-185">ただし、コンパイラが検出できるこれを指定する場合にのみ、エラーを重複`counter`ですべて`Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="47d92-186">手順の引数</span><span class="sxs-lookup"><span data-stu-id="47d92-186">Step Argument</span></span>  
 <span data-ttu-id="47d92-187">値`step`正または負にすることができます。</span><span class="sxs-lookup"><span data-stu-id="47d92-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="47d92-188">このパラメーターは、次の表に従って、ループ処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="47d92-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="47d92-189">**ステップ値**</span><span class="sxs-lookup"><span data-stu-id="47d92-189">**Step value**</span></span>|<span data-ttu-id="47d92-190">**場合、ループが実行されます。**</span><span class="sxs-lookup"><span data-stu-id="47d92-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="47d92-191">正またはゼロ</span><span class="sxs-lookup"><span data-stu-id="47d92-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="47d92-192">負</span><span class="sxs-lookup"><span data-stu-id="47d92-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="47d92-193">既定値の`step`は 1 です。</span><span class="sxs-lookup"><span data-stu-id="47d92-193">The default value of `step` is 1.</span></span>  
  
### <a name="BKMK_Counter"></a> <span data-ttu-id="47d92-194">カウンターの引数</span><span class="sxs-lookup"><span data-stu-id="47d92-194">Counter Argument</span></span>  
 <span data-ttu-id="47d92-195">次の表に示すかどうか`counter`全体をスコープは、新しいローカル変数を定義します。`For…Next`ループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="47d92-196">この決定によって異なるかどうか`datatype`が存在するかどうかおよび`counter`は既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="47d92-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="47d92-197">`datatype`存在でしょうか。</span><span class="sxs-lookup"><span data-stu-id="47d92-197">Is `datatype` present?</span></span>|<span data-ttu-id="47d92-198">`counter`既に定義されていますか?</span><span class="sxs-lookup"><span data-stu-id="47d92-198">Is `counter` already defined?</span></span>|<span data-ttu-id="47d92-199">結果 (かどうか`counter`全体をスコープは、新しいローカル変数を定義します`For...Next`ループ)。</span><span class="sxs-lookup"><span data-stu-id="47d92-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="47d92-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="47d92-200">No</span></span>|<span data-ttu-id="47d92-201">[はい]</span><span class="sxs-lookup"><span data-stu-id="47d92-201">Yes</span></span>|<span data-ttu-id="47d92-202">いいえ、ため`counter`は既に定義されています。</span><span class="sxs-lookup"><span data-stu-id="47d92-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="47d92-203">場合のスコープ`counter`いない、プロシージャに対してローカルに、コンパイル時に警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="47d92-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="47d92-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="47d92-204">No</span></span>|<span data-ttu-id="47d92-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="47d92-205">No</span></span>|<span data-ttu-id="47d92-206">はい。</span><span class="sxs-lookup"><span data-stu-id="47d92-206">Yes.</span></span> <span data-ttu-id="47d92-207">データ型から推論されます、 `start`、 `end`、および`step`式。</span><span class="sxs-lookup"><span data-stu-id="47d92-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="47d92-208">型の推定については、次を参照してください。 [Option Infer ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="47d92-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="47d92-209">[はい]</span><span class="sxs-lookup"><span data-stu-id="47d92-209">Yes</span></span>|<span data-ttu-id="47d92-210">[はい]</span><span class="sxs-lookup"><span data-stu-id="47d92-210">Yes</span></span>|<span data-ttu-id="47d92-211">[はい] が場合にのみ、既存の`counter`プロシージャの外部変数が定義されています。</span><span class="sxs-lookup"><span data-stu-id="47d92-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="47d92-212">その変数は別に維持します。</span><span class="sxs-lookup"><span data-stu-id="47d92-212">That variable remains separate.</span></span> <span data-ttu-id="47d92-213">場合、既存のスコープ`counter`変数は、プロシージャに対してローカルに、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="47d92-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="47d92-214">[はい]</span><span class="sxs-lookup"><span data-stu-id="47d92-214">Yes</span></span>|<span data-ttu-id="47d92-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="47d92-215">No</span></span>|<span data-ttu-id="47d92-216">はい。</span><span class="sxs-lookup"><span data-stu-id="47d92-216">Yes.</span></span>|  
  
 <span data-ttu-id="47d92-217">データ型`counter`イテレーションでは、次の種類のいずれかを指定する必要がありますの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="47d92-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
- <span data-ttu-id="47d92-218">A `Byte`、 `SByte`、 `UShort`、 `Short`、 `UInteger`、 `Integer`、 `ULong`、 `Long`、 `Decimal`、 `Single`、または`Double`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
- <span data-ttu-id="47d92-219">列挙体を使用して宣言する、 [Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="47d92-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
- <span data-ttu-id="47d92-220">`Object`。</span><span class="sxs-lookup"><span data-stu-id="47d92-220">An `Object`.</span></span>  
  
- <span data-ttu-id="47d92-221">型`T`、次の演算子を持つ場所`B`型で使用できるは、`Boolean`式。</span><span class="sxs-lookup"><span data-stu-id="47d92-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="47d92-222">必要に応じて指定することができます、`counter`変数、`Next`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="47d92-223">入れ子にしていない場合は特に、この構文は、プログラムの読みやすさを向上`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="47d92-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="47d92-224">対応する表示される変数を指定する必要があります`For`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="47d92-225">`start`、 `end`、および`step`式が評価される任意のデータ型の型を拡張する`counter`します。</span><span class="sxs-lookup"><span data-stu-id="47d92-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="47d92-226">ユーザー定義型を使用する場合`counter`、定義する必要がありますが、`CType`変換演算子の型に変換する`start`、 `end`、または`step`の型に`counter`。</span><span class="sxs-lookup"><span data-stu-id="47d92-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d92-227">例</span><span class="sxs-lookup"><span data-stu-id="47d92-227">Example</span></span>  
 <span data-ttu-id="47d92-228">次の例では、ジェネリック リストからすべての要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="47d92-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="47d92-229">代わりに、[ごとにしています.次のステートメントの](../../../visual-basic/language-reference/statements/for-each-next-statement.md)、例を示します、 `For`.`Next`降順に反復処理するステートメント。</span><span class="sxs-lookup"><span data-stu-id="47d92-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="47d92-230">例では、ため、この手法を使用して、`removeAt`メソッドが低いインデックス値が削除された要素の後に要素をによりします。</span><span class="sxs-lookup"><span data-stu-id="47d92-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a><span data-ttu-id="47d92-231">例</span><span class="sxs-lookup"><span data-stu-id="47d92-231">Example</span></span>  
 <span data-ttu-id="47d92-232">次の例を使用して宣言されている列挙型を反復処理、 [Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="47d92-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a><span data-ttu-id="47d92-233">例</span><span class="sxs-lookup"><span data-stu-id="47d92-233">Example</span></span>  
 <span data-ttu-id="47d92-234">次の例では、ステートメントのパラメーターが演算子のオーバー ロードを持つクラスを使用して、 `+`、 `-`、 `>=`、および`<=`演算子。</span><span class="sxs-lookup"><span data-stu-id="47d92-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="47d92-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="47d92-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="47d92-236">ループ構造</span><span class="sxs-lookup"><span data-stu-id="47d92-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="47d92-237">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="47d92-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="47d92-238">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="47d92-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="47d92-239">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="47d92-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="47d92-240">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="47d92-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="47d92-241">コレクション</span><span class="sxs-lookup"><span data-stu-id="47d92-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
