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
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="5d7fa-102">While...End While ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d7fa-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="5d7fa-103">指定された条件が `True`場合に限り、一連のステートメントを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d7fa-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d7fa-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="5d7fa-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5d7fa-105">Parts</span></span>  
  
|<span data-ttu-id="5d7fa-106">用語</span><span class="sxs-lookup"><span data-stu-id="5d7fa-106">Term</span></span>|<span data-ttu-id="5d7fa-107">Definition</span><span class="sxs-lookup"><span data-stu-id="5d7fa-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="5d7fa-108">必須。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-108">Required.</span></span> <span data-ttu-id="5d7fa-109">`Boolean` 式です。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-109">`Boolean` expression.</span></span> <span data-ttu-id="5d7fa-110">`condition` が `Nothing`場合、Visual Basic はそれを `False`として扱います。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="5d7fa-111">省略可。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-111">Optional.</span></span> <span data-ttu-id="5d7fa-112">`While`の後に1つ以上のステートメントがあり、`condition` が `True`たびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="5d7fa-113">省略可。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-113">Optional.</span></span> <span data-ttu-id="5d7fa-114">`While` ブロックの次の反復処理に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="5d7fa-115">省略可。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-115">Optional.</span></span> <span data-ttu-id="5d7fa-116">`While` ブロックの外に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="5d7fa-117">必須。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-117">Required.</span></span> <span data-ttu-id="5d7fa-118">`While` ブロックの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d7fa-119">コメント</span><span class="sxs-lookup"><span data-stu-id="5d7fa-119">Remarks</span></span>  
 <span data-ttu-id="5d7fa-120">条件が `True` のままである限り、一連のステートメントを無期限に繰り返す場合は、`While...End While` 構造体を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="5d7fa-121">条件またはテスト対象の結果をテストする場所を柔軟に指定できるようにするには、[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)を選択します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="5d7fa-122">ステートメントを設定された回数繰り返し実行する場合、通常は[For...Next ステートメント](../../../visual-basic/language-reference/statements/for-next-statement.md)がより適しています。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d7fa-123">`While` キーワードは、 [Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)、 [Skip while 句](../../../visual-basic/language-reference/queries/skip-while-clause.md)、 [Take while 句](../../../visual-basic/language-reference/queries/take-while-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="5d7fa-124">`condition` が `True`場合、`End While` ステートメントが検出されるまで、すべての `statements` が実行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="5d7fa-125">制御が `While` ステートメントに戻り、`condition` が再度オンになります。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="5d7fa-126">`condition` がまだ `True`場合は、プロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="5d7fa-127">`False`の場合、制御は、`End While` ステートメントの後のステートメントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="5d7fa-128">`While` ステートメントは、ループを開始する前に常に条件をチェックします。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="5d7fa-129">ループは、条件が `True`のまま続行されます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="5d7fa-130">最初にループを入力したときに `condition` が `False` 場合は、一度も実行されません。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="5d7fa-131">通常、`condition` は2つの値を比較した結果になりますが、[Boolean データ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md) の値 (`True` または `False`) に評価される任意の式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="5d7fa-132">この式には、`Boolean`に変換された別のデータ型 (数値型など) の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="5d7fa-133">ループを `While` 入れ子にするには、別のループ内に1つのループを配置します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="5d7fa-134">また、さまざまな種類の制御構造を相互に入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="5d7fa-135">詳細については、「[入れ子になったコントロール構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="5d7fa-136">Exit While</span><span class="sxs-lookup"><span data-stu-id="5d7fa-136">Exit While</span></span>  
 <span data-ttu-id="5d7fa-137">[Exit While](../../../visual-basic/language-reference/statements/exit-statement.md)ステートメントを使用すると、`While` ループを終了する別の方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="5d7fa-138">`Exit While` は、`End While` ステートメントの後にあるステートメントに制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="5d7fa-139">通常は、何らかの条件が評価された後 (たとえば、`If...Then...Else` 構造) に `Exit While` を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="5d7fa-140">誤った値や終了要求など、反復処理を続行することが不要または不可能な条件を検出した場合は、ループを終了することができます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="5d7fa-141">*無限ループ*の原因となる可能性のある条件をテストするときに、`Exit While` を使用できます。これは、非常に大きいまたは無限の回数実行されるループです。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="5d7fa-142">その後、`Exit While` を使用してループをエスケープできます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="5d7fa-143">`While` ループ内の任意の場所に、任意の数の `Exit While` ステートメントを配置できます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="5d7fa-144">入れ子になった `While` ループ内で使用された場合、`Exit While` は最も内側のループから次の上位レベルの入れ子に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="5d7fa-145">`Continue While` ステートメントは、ループの次の反復処理に制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="5d7fa-146">詳細については、「 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d7fa-147">例</span><span class="sxs-lookup"><span data-stu-id="5d7fa-147">Example</span></span>  
 <span data-ttu-id="5d7fa-148">次の例では、ループ内のステートメントは、`index` 変数が10を超えるまで実行を続けます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="5d7fa-149">例</span><span class="sxs-lookup"><span data-stu-id="5d7fa-149">Example</span></span>  
 <span data-ttu-id="5d7fa-150">次の例は、`Continue While` と `Exit While` ステートメントの使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="5d7fa-151">例</span><span class="sxs-lookup"><span data-stu-id="5d7fa-151">Example</span></span>  
 <span data-ttu-id="5d7fa-152">次の例では、テキストファイル内のすべての行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="5d7fa-153"><xref:System.IO.File.OpenText%2A> メソッドは、ファイルを開き、文字を読み取る <xref:System.IO.StreamReader> を返します。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="5d7fa-154">`While` 条件では、`StreamReader` の <xref:System.IO.StreamReader.Peek%2A> メソッドによって、ファイルに追加の文字が含まれているかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="5d7fa-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="5d7fa-155">参照</span><span class="sxs-lookup"><span data-stu-id="5d7fa-155">See also</span></span>

- [<span data-ttu-id="5d7fa-156">ループ構造</span><span class="sxs-lookup"><span data-stu-id="5d7fa-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="5d7fa-157">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="5d7fa-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="5d7fa-158">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="5d7fa-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="5d7fa-159">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="5d7fa-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="5d7fa-160">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="5d7fa-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="5d7fa-161">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="5d7fa-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="5d7fa-162">Continue ステートメント</span><span class="sxs-lookup"><span data-stu-id="5d7fa-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
