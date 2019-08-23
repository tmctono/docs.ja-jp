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
ms.openlocfilehash: 9a9aed51f6d7bf3233e6e89116b8209b22f3d15d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912419"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="9f94b-102">For...Next ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f94b-102">For...Next Statement (Visual Basic)</span></span>
<span data-ttu-id="9f94b-103">ステートメントのグループを指定された回数だけ繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-103">Repeats a group of statements a specified number of times.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f94b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9f94b-104">Syntax</span></span>  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## <a name="parts"></a><span data-ttu-id="9f94b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9f94b-105">Parts</span></span>  
  
|<span data-ttu-id="9f94b-106">パーツ</span><span class="sxs-lookup"><span data-stu-id="9f94b-106">Part</span></span>|<span data-ttu-id="9f94b-107">説明</span><span class="sxs-lookup"><span data-stu-id="9f94b-107">Description</span></span>|  
|----------|-----------------|  
|`counter`|<span data-ttu-id="9f94b-108">ステートメントでは`For`必須です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-108">Required in the `For` statement.</span></span> <span data-ttu-id="9f94b-109">数値変数。</span><span class="sxs-lookup"><span data-stu-id="9f94b-109">Numeric variable.</span></span> <span data-ttu-id="9f94b-110">ループのコントロール変数。</span><span class="sxs-lookup"><span data-stu-id="9f94b-110">The control variable for the loop.</span></span> <span data-ttu-id="9f94b-111">詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`datatype`|<span data-ttu-id="9f94b-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-112">Optional.</span></span> <span data-ttu-id="9f94b-113">の`counter`データ型。</span><span class="sxs-lookup"><span data-stu-id="9f94b-113">Data type of `counter`.</span></span> <span data-ttu-id="9f94b-114">詳細については、このトピックで後述する「 [Counter 引数](#BKMK_Counter)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|  
|`start`|<span data-ttu-id="9f94b-115">必須。</span><span class="sxs-lookup"><span data-stu-id="9f94b-115">Required.</span></span> <span data-ttu-id="9f94b-116">数値式。</span><span class="sxs-lookup"><span data-stu-id="9f94b-116">Numeric expression.</span></span> <span data-ttu-id="9f94b-117">`counter` の初期値になります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-117">The initial value of `counter`.</span></span>|  
|`end`|<span data-ttu-id="9f94b-118">必須。</span><span class="sxs-lookup"><span data-stu-id="9f94b-118">Required.</span></span> <span data-ttu-id="9f94b-119">数値式。</span><span class="sxs-lookup"><span data-stu-id="9f94b-119">Numeric expression.</span></span> <span data-ttu-id="9f94b-120">の最終的な`counter`値。</span><span class="sxs-lookup"><span data-stu-id="9f94b-120">The final value of `counter`.</span></span>|  
|`step`|<span data-ttu-id="9f94b-121">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-121">Optional.</span></span> <span data-ttu-id="9f94b-122">数値式。</span><span class="sxs-lookup"><span data-stu-id="9f94b-122">Numeric expression.</span></span> <span data-ttu-id="9f94b-123">がループを通じ`counter`て毎回インクリメントされる量。</span><span class="sxs-lookup"><span data-stu-id="9f94b-123">The amount by which `counter` is incremented each time through the loop.</span></span>|  
|`statements`|<span data-ttu-id="9f94b-124">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-124">Optional.</span></span> <span data-ttu-id="9f94b-125">指定した回数だけ`For`実行`Next`される、との間の1つ以上のステートメント。</span><span class="sxs-lookup"><span data-stu-id="9f94b-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|  
|`Continue For`|<span data-ttu-id="9f94b-126">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-126">Optional.</span></span> <span data-ttu-id="9f94b-127">次のループの反復処理に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-127">Transfers control to the next loop iteration.</span></span>|  
|`Exit For`|<span data-ttu-id="9f94b-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-128">Optional.</span></span> <span data-ttu-id="9f94b-129">制御を`For`ループの外に転送します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-129">Transfers control out of the `For` loop.</span></span>|  
|`Next`|<span data-ttu-id="9f94b-130">必須。</span><span class="sxs-lookup"><span data-stu-id="9f94b-130">Required.</span></span> <span data-ttu-id="9f94b-131">`For`ループの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-131">Terminates the definition of the `For` loop.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="9f94b-132">このステートメントでは、キーワードを使用して、カウンターの範囲を指定します。`To`</span><span class="sxs-lookup"><span data-stu-id="9f94b-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="9f94b-133">このキーワードは、 [Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)と配列宣言。</span><span class="sxs-lookup"><span data-stu-id="9f94b-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="9f94b-134">配列の宣言の詳細については、「 [Dim ステートメント](../../../visual-basic/language-reference/statements/dim-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="simple-examples"></a><span data-ttu-id="9f94b-135">簡単な例</span><span class="sxs-lookup"><span data-stu-id="9f94b-135">Simple Examples</span></span>  
 <span data-ttu-id="9f94b-136">使用`For`している...`Next`一連のステートメントを設定された回数繰り返し実行する場合は、構造体。</span><span class="sxs-lookup"><span data-stu-id="9f94b-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>  
  
 <span data-ttu-id="9f94b-137">次の例では、 `index`変数は値1で始まり、ループの繰り返しごとにインクリメントされます。これは、の`index`値が5に達した後に終了します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 <span data-ttu-id="9f94b-138">次の例では、 `number`変数は2から開始され、ループの反復ごとに0.25 によって減少し、の`number`値が0になると終了します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="9f94b-139">`Step` の`-.25`引数は、ループの各反復処理で値を0.25 ずつ減らします。</span><span class="sxs-lookup"><span data-stu-id="9f94b-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  <span data-ttu-id="9f94b-140">[While...End While ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)または[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)は、ループ内でステートメントを実行する回数が事前にわからない場合にうまく機能します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="9f94b-141">ただし、特定回数だけループを実行する場合は`For`.`Next`ループの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="9f94b-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="9f94b-142">ループを最初に入力するときに、イテレーションの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-142">You determine the number of iterations when you first enter the loop.</span></span>  
  
## <a name="nesting-loops"></a><span data-ttu-id="9f94b-143">ループの入れ子</span><span class="sxs-lookup"><span data-stu-id="9f94b-143">Nesting Loops</span></span>  
 <span data-ttu-id="9f94b-144">ループを入れ子`For`にするには、ループを別のループ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="9f94b-145">入れ子になっ`For`たの例を次に示します。`Next`異なるステップ値を持つ構造体。</span><span class="sxs-lookup"><span data-stu-id="9f94b-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="9f94b-146">外側のループは、ループの反復ごとに文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="9f94b-147">内側のループは、ループの反復ごとにループカウンター変数をデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="9f94b-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 <span data-ttu-id="9f94b-148">ループを入れ子にする場合、各ループは`counter`一意の変数を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>  
  
 <span data-ttu-id="9f94b-149">また、さまざまな種類のコントロール構造を入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="9f94b-150">詳細については、「[入れ子になったコントロール構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-for-and-continue-for"></a><span data-ttu-id="9f94b-151">Exit For と Continue For</span><span class="sxs-lookup"><span data-stu-id="9f94b-151">Exit For and Continue For</span></span>  
 <span data-ttu-id="9f94b-152">ステートメント`Exit For`は、 `For`すぐに...`Next`</span><span class="sxs-lookup"><span data-stu-id="9f94b-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="9f94b-153">ループし、 `Next`ステートメントの後のステートメントに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>  
  
 <span data-ttu-id="9f94b-154">ステートメント`Continue For`は、ループの次の反復処理に制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="9f94b-155">詳細については、「 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
 <span data-ttu-id="9f94b-156">次の例は、ステートメント`Continue For`と`Exit For`ステートメントの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f94b-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 <span data-ttu-id="9f94b-157">には、 `For`任意の数`Exit For`のステートメントを含めることができます...`Next`</span><span class="sxs-lookup"><span data-stu-id="9f94b-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="9f94b-158">ループ.</span><span class="sxs-lookup"><span data-stu-id="9f94b-158">loop.</span></span> <span data-ttu-id="9f94b-159">入れ子になっ`For`た... 内で使用された場合`Next`</span><span class="sxs-lookup"><span data-stu-id="9f94b-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="9f94b-160">ループし`Exit For` 、最も内側のループを終了して、次の上位レベルの入れ子に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="9f94b-161">`Exit For` は何らかの条件 (たとえば、 `If`...`Then`...`Else`構造) を評価した後によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="9f94b-162">次の条件の場合、`Exit For`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-162">You might want to use `Exit For` for the following conditions:</span></span>  
  
- <span data-ttu-id="9f94b-163">反復処理を続行することは不要または不可能です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="9f94b-164">この条件は、エラー値または終了要求によって作成できます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-164">An erroneous value or a termination request might create this condition.</span></span>  
  
- <span data-ttu-id="9f94b-165">`Try`...`Catch`...`Finally`ステートメントは例外をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="9f94b-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="9f94b-166">`Finally`ブロックの最後に`Exit For`を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-166">You might use `Exit For` at the end of the `Finally` block.</span></span>  
  
- <span data-ttu-id="9f94b-167">無限ループがあります。これは、大規模または無限の回数実行されるループです。</span><span class="sxs-lookup"><span data-stu-id="9f94b-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="9f94b-168">このような条件を検出した場合は`Exit For`を使用してループをエスケープすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="9f94b-169">詳細については、[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="9f94b-170">技術的な実装</span><span class="sxs-lookup"><span data-stu-id="9f94b-170">Technical Implementation</span></span>  
 <span data-ttu-id="9f94b-171">`For`When...ループが開始され、 `end`Visual Basic が`step`、、およびを評価`start`します。 `Next`</span><span class="sxs-lookup"><span data-stu-id="9f94b-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="9f94b-172">Visual Basic は、現時点ではこれらの値のみを`start`評価`counter`し、にを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="9f94b-173">ステートメントブロックが実行される前に`counter` 、 `end`Visual Basic はと比較されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="9f94b-174">が`counter`既に`end`値より大きい (またはが負`step`の場合は小さい) `For`場合、 `Next`ループは終了し、ステートメントの後のステートメントに制御が移ります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="9f94b-175">それ以外の場合は、ステートメントブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-175">Otherwise, the statement block runs.</span></span>  
  
 <span data-ttu-id="9f94b-176">Visual Basic が`Next`ステートメントを検出するたびに、 `counter` `For`に`step`よってインクリメントされ、ステートメントに戻ります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="9f94b-177">ここでも`counter`と`end`を比較し、その結果に応じてブロックを実行するか、ループを終了します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="9f94b-178">このプロセスは、 `counter`が`end`成功する`Exit For`か、ステートメントが検出されるまで続行されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>  
  
 <span data-ttu-id="9f94b-179">が渡さ`counter` `end`れるまで、ループは停止しません。</span><span class="sxs-lookup"><span data-stu-id="9f94b-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="9f94b-180">が`counter` に`end`等しい場合、ループは続行されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="9f94b-181">`step`が正で、 `end`  <=  `counter` が負`counter`である場合に、ブロックを実行するかどうかを決定する比較。  >=  `end` `step`</span><span class="sxs-lookup"><span data-stu-id="9f94b-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>  
  
 <span data-ttu-id="9f94b-182">ループ内での`counter`値を変更すると、コードの読み取りやデバッグが困難になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="9f94b-183">、 `start` `step` 、またはの値を変更しても、ループが最初に入力されたときに決定された反復値には影響しません。 `end`</span><span class="sxs-lookup"><span data-stu-id="9f94b-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>  
  
 <span data-ttu-id="9f94b-184">ループを入れ子にした場合、内部レベルの`Next` `Next`ステートメントの前に外側の入れ子レベルのステートメントが検出されると、コンパイラはエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="9f94b-185">ただし、コンパイラは、すべて`counter` `Next`のステートメントでを指定した場合にのみ、この重複エラーを検出できます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>  
  
### <a name="step-argument"></a><span data-ttu-id="9f94b-186">ステップ引数</span><span class="sxs-lookup"><span data-stu-id="9f94b-186">Step Argument</span></span>  
 <span data-ttu-id="9f94b-187">の値に`step`は、正または負のどちらかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="9f94b-188">このパラメーターは、次の表に従ってループ処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-188">This parameter determines loop processing according to the following table:</span></span>  
  
|<span data-ttu-id="9f94b-189">**ステップ値**</span><span class="sxs-lookup"><span data-stu-id="9f94b-189">**Step value**</span></span>|<span data-ttu-id="9f94b-190">**ループが実行される場合**</span><span class="sxs-lookup"><span data-stu-id="9f94b-190">**Loop executes if**</span></span>|  
|--------------------|--------------------------|  
|<span data-ttu-id="9f94b-191">正または0</span><span class="sxs-lookup"><span data-stu-id="9f94b-191">Positive or zero</span></span>|`counter` <= `end`|  
|<span data-ttu-id="9f94b-192">負</span><span class="sxs-lookup"><span data-stu-id="9f94b-192">Negative</span></span>|`counter` >= `end`|  
  
 <span data-ttu-id="9f94b-193">の`step`既定値は1です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-193">The default value of `step` is 1.</span></span>  
  
### <a name="BKMK_Counter"></a><span data-ttu-id="9f94b-194">Counter 引数</span><span class="sxs-lookup"><span data-stu-id="9f94b-194">Counter Argument</span></span>  
 <span data-ttu-id="9f94b-195">次の表は、 `counter`がループ全体`For…Next`を対象とする新しいローカル変数を定義するかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f94b-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="9f94b-196">この決定は`counter` 、が`datatype`存在し、が既に定義されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>  
  
|<span data-ttu-id="9f94b-197">存在`datatype`していますか?</span><span class="sxs-lookup"><span data-stu-id="9f94b-197">Is `datatype` present?</span></span>|<span data-ttu-id="9f94b-198">は`counter`既に定義されていますか?</span><span class="sxs-lookup"><span data-stu-id="9f94b-198">Is `counter` already defined?</span></span>|<span data-ttu-id="9f94b-199">Result (に`counter`よって、ループ全体`For...Next`を対象とする新しいローカル変数が定義されているかどうか)</span><span class="sxs-lookup"><span data-stu-id="9f94b-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="9f94b-200">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f94b-200">No</span></span>|<span data-ttu-id="9f94b-201">[はい]</span><span class="sxs-lookup"><span data-stu-id="9f94b-201">Yes</span></span>|<span data-ttu-id="9f94b-202">いいえ。は既に定義されています。 `counter`</span><span class="sxs-lookup"><span data-stu-id="9f94b-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="9f94b-203">のスコープがプロシージャ`counter`に対してローカルでない場合は、コンパイル時の警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|  
|<span data-ttu-id="9f94b-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f94b-204">No</span></span>|<span data-ttu-id="9f94b-205">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f94b-205">No</span></span>|<span data-ttu-id="9f94b-206">はい。</span><span class="sxs-lookup"><span data-stu-id="9f94b-206">Yes.</span></span> <span data-ttu-id="9f94b-207">データ型は`start`、 `end`、、および`step`の各式から推論されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="9f94b-208">型の推定の詳細については、「[オプション推論ステートメント](../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型の推論](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f94b-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|  
|<span data-ttu-id="9f94b-209">[はい]</span><span class="sxs-lookup"><span data-stu-id="9f94b-209">Yes</span></span>|<span data-ttu-id="9f94b-210">[はい]</span><span class="sxs-lookup"><span data-stu-id="9f94b-210">Yes</span></span>|<span data-ttu-id="9f94b-211">はい。ただし、既存`counter`の変数がプロシージャの外部で定義されている場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="9f94b-212">この変数は個別に保持されます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-212">That variable remains separate.</span></span> <span data-ttu-id="9f94b-213">既存`counter`の変数のスコープがプロシージャに対してローカルである場合は、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="9f94b-214">[はい]</span><span class="sxs-lookup"><span data-stu-id="9f94b-214">Yes</span></span>|<span data-ttu-id="9f94b-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="9f94b-215">No</span></span>|<span data-ttu-id="9f94b-216">はい。</span><span class="sxs-lookup"><span data-stu-id="9f94b-216">Yes.</span></span>|  
  
 <span data-ttu-id="9f94b-217">の`counter`データ型によって、反復処理の種類が決まります。次のいずれかの型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>  
  
- <span data-ttu-id="9f94b-218">`Byte` `SByte` `UShort` `Short` 、、`Double`、、、、、、、、または。 `UInteger` `Integer` `ULong` `Long` `Decimal` `Single`</span><span class="sxs-lookup"><span data-stu-id="9f94b-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>  
  
- <span data-ttu-id="9f94b-219">[Enum ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言する列挙体。</span><span class="sxs-lookup"><span data-stu-id="9f94b-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
- <span data-ttu-id="9f94b-220">`Object`。</span><span class="sxs-lookup"><span data-stu-id="9f94b-220">An `Object`.</span></span>  
  
- <span data-ttu-id="9f94b-221">次の`T`演算子`B`を持つ型。は、 `Boolean`式で使用できる型です。</span><span class="sxs-lookup"><span data-stu-id="9f94b-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 <span data-ttu-id="9f94b-222">`counter` 必要`Next`に応じて、ステートメントで変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f94b-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="9f94b-223">この構文を使用すると、特に入れ子になっ`For`たループがある場合に、プログラムの読みやすさが向上します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="9f94b-224">対応`For`するステートメントに表示される変数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>  
  
 <span data-ttu-id="9f94b-225">、 `start` 、`end`および`counter`の各式は、の型に拡大変換される任意のデータ型に評価されます。 `step`</span><span class="sxs-lookup"><span data-stu-id="9f94b-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="9f94b-226">`counter`にユーザー定義型を使用する場合は、、 `end`、または`step`の`start`型`CType`をの`counter`型に変換するために、変換演算子を定義することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f94b-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f94b-227">例</span><span class="sxs-lookup"><span data-stu-id="9f94b-227">Example</span></span>  
 <span data-ttu-id="9f94b-228">次の例では、ジェネリックリストからすべての要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="9f94b-229">この例では、[For Each...Next ステートメント](../../../visual-basic/language-reference/statements/for-each-next-statement.md)の代わりに、降順に反復処理する`For`...`Next`ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="9f94b-230">例では、`removeAt`メソッドで削除された要素の後にある要素のインデックス値がより小さくなるため、この手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a><span data-ttu-id="9f94b-231">例</span><span class="sxs-lookup"><span data-stu-id="9f94b-231">Example</span></span>  
 <span data-ttu-id="9f94b-232">次の例では、列挙[ステートメント](../../../visual-basic/language-reference/statements/enum-statement.md)を使用して宣言された列挙型を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="9f94b-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a><span data-ttu-id="9f94b-233">例</span><span class="sxs-lookup"><span data-stu-id="9f94b-233">Example</span></span>  
 <span data-ttu-id="9f94b-234">次の例では、ステートメントの`+`パラメーターは`>=`、、 `-`、、および`<=`の各演算子に対して演算子のオーバーロードを持つクラスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="9f94b-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="9f94b-235">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f94b-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="9f94b-236">ループ構造</span><span class="sxs-lookup"><span data-stu-id="9f94b-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="9f94b-237">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f94b-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="9f94b-238">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f94b-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="9f94b-239">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="9f94b-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="9f94b-240">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="9f94b-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="9f94b-241">コレクション</span><span class="sxs-lookup"><span data-stu-id="9f94b-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
