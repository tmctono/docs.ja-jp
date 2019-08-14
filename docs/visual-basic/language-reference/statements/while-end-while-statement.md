---
title: While...End While ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934226"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="1fcb4-102">While...End While ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fcb4-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="1fcb4-103">指定された条件が真`True`である間、一連のステートメントを繰り返し実行します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcb4-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fcb4-104">Syntax</span></span>  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="1fcb4-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="1fcb4-105">Parts</span></span>  
  
|<span data-ttu-id="1fcb4-106">用語</span><span class="sxs-lookup"><span data-stu-id="1fcb4-106">Term</span></span>|<span data-ttu-id="1fcb4-107">定義</span><span class="sxs-lookup"><span data-stu-id="1fcb4-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="1fcb4-108">必須。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-108">Required.</span></span> <span data-ttu-id="1fcb4-109">`Boolean` 式。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-109">`Boolean` expression.</span></span> <span data-ttu-id="1fcb4-110">場合`condition`は`Nothing`、Visual Basic として扱います`False`します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="1fcb4-111">任意。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-111">Optional.</span></span> <span data-ttu-id="1fcb4-112">1 つまたは複数のステートメントの次`While`、毎回を実行する`condition`は`True`します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="1fcb4-113">任意。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-113">Optional.</span></span> <span data-ttu-id="1fcb4-114">次のイテレーションに制御を転送、`While`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="1fcb4-115">任意。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-115">Optional.</span></span> <span data-ttu-id="1fcb4-116">うちに制御を転送、`While`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="1fcb4-117">必須。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-117">Required.</span></span> <span data-ttu-id="1fcb4-118">`While` ブロックの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fcb4-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="1fcb4-119">Remarks</span></span>  
 <span data-ttu-id="1fcb4-120">使用して、`While...End While`条件が残っている限りを一連の回数、不特定数のステートメントを繰り返し表示するときに`True`します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="1fcb4-121">お勧めのその条件をテストするか、結果の判定をより柔軟にテストする場合、[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span> <span data-ttu-id="1fcb4-122">設定された数の時間、ステートメントを繰り返し表示する場合、[For...Next ステートメント](../../../visual-basic/language-reference/statements/for-next-statement.md)は、通常のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-122">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1fcb4-123">`While`でキーワードを使用しても、[Do...Loop ステートメント](../../../visual-basic/language-reference/statements/do-loop-statement.md)、 [Skip While 句](../../../visual-basic/language-reference/queries/skip-while-clause.md)と[Take While 句](../../../visual-basic/language-reference/queries/take-while-clause.md)します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-123">The `While` keyword is also used in the [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md), the [Skip While Clause](../../../visual-basic/language-reference/queries/skip-while-clause.md) and the [Take While Clause](../../../visual-basic/language-reference/queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="1fcb4-124">場合`condition`は`True`、すべての`statements`まで実行、`End While`ステートメントが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="1fcb4-125">制御を返します、`While`ステートメント、および`condition`が再度チェックします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="1fcb4-126">場合`condition`が`True`プロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="1fcb4-127">`False`、コントロールに続くステートメントに渡す、`End While`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="1fcb4-128">`While`ステートメントは常に、ループを開始する前に、条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="1fcb4-129">条件がループが継続`True`します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="1fcb4-130">場合`condition`は`False`一度も実行されない、ループを最初に入力するとします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="1fcb4-131">`condition`が 2 つの値の比較からの結果に評価される任意の式は、通常、[Boolean データ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)値 (`True`または`False`)。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="1fcb4-132">この式は、数値型に変換されているなどの別のデータ型の値を含めることができます`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="1fcb4-133">入れ子にすることができます`While`内に別の 1 つのループを配置することでループします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="1fcb4-134">さまざまな種類の制御構造を入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="1fcb4-135">詳細については、次を参照してください。[制御構造の入れ子になった](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-135">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="1fcb4-136">Exit While</span><span class="sxs-lookup"><span data-stu-id="1fcb4-136">Exit While</span></span>  
 <span data-ttu-id="1fcb4-137">[Exit While](../../../visual-basic/language-reference/statements/exit-statement.md)ステートメントが終了する別の方法を提供する`While`ループします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-137">The [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="1fcb4-138">`Exit While` すぐに続くステートメントに制御を転送、`End While`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="1fcb4-139">通常使用する`Exit While`いくつかの条件が評価された後 (たとえば、`If...Then...Else`構造)。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="1fcb4-140">不要なまたは不可能なエラー値や終了要求など、反復処理を続行する条件を検出した場合、ループを終了する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="1fcb4-141">使用することができます`Exit While`の考えられる原因の条件をテストするとき、*無限ループ*、これは、非常に大規模または無限も可能回数だけ実行できるループします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="1fcb4-142">使用することができますし、`Exit While`ループを抜けます。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="1fcb4-143">任意の数を配置する`Exit While`でステートメントを任意の場所、`While`ループします。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="1fcb4-144">使用すると内で入れ子になった`While`ループ、`Exit While`上位レベルの入れ子にして、最も内側のループからコントロールを転送します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="1fcb4-145">`Continue While`ステートメントはすぐに、ループの次のイテレーションに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="1fcb4-146">詳細については、次を参照してください。 [Continue ステートメント](../../../visual-basic/language-reference/statements/continue-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-146">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fcb4-147">例</span><span class="sxs-lookup"><span data-stu-id="1fcb4-147">Example</span></span>  
 <span data-ttu-id="1fcb4-148">次の例では、ループ内のステートメントの続行までを実行する、`index`変数が 10 より大きい。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="1fcb4-149">例</span><span class="sxs-lookup"><span data-stu-id="1fcb4-149">Example</span></span>  
 <span data-ttu-id="1fcb4-150">次の例では、使用、`Continue While`と`Exit While`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="1fcb4-151">例</span><span class="sxs-lookup"><span data-stu-id="1fcb4-151">Example</span></span>  
 <span data-ttu-id="1fcb4-152">次の例では、テキスト ファイルのすべての行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="1fcb4-153"><xref:System.IO.File.OpenText%2A>メソッドは、ファイルを開くし、取得、<xref:System.IO.StreamReader>文字を読み取る。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="1fcb4-154">`While`条件、<xref:System.IO.StreamReader.Peek%2A>のメソッド、`StreamReader`ファイルに追加の文字が含まれているかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1fcb4-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="1fcb4-155">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fcb4-155">See also</span></span>

- [<span data-ttu-id="1fcb4-156">ループ構造</span><span class="sxs-lookup"><span data-stu-id="1fcb4-156">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="1fcb4-157">Do...Loop ステートメント</span><span class="sxs-lookup"><span data-stu-id="1fcb4-157">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="1fcb4-158">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="1fcb4-158">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="1fcb4-159">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="1fcb4-159">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="1fcb4-160">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="1fcb4-160">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="1fcb4-161">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="1fcb4-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="1fcb4-162">Continue ステートメント</span><span class="sxs-lookup"><span data-stu-id="1fcb4-162">Continue Statement</span></span>](../../../visual-basic/language-reference/statements/continue-statement.md)
