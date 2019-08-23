---
title: Do...Loop ステートメント (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 75a2129a9f332024831d97021e381f1b3d4fa048
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942994"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="7b8c1-102">Do...Loop ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b8c1-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="7b8c1-103">`Boolean`条件がで`True` ある`True`か、条件がになるまで、ステートメントのブロックを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8c1-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b8c1-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="7b8c1-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="7b8c1-105">Parts</span></span>  
  
|<span data-ttu-id="7b8c1-106">用語</span><span class="sxs-lookup"><span data-stu-id="7b8c1-106">Term</span></span>|<span data-ttu-id="7b8c1-107">定義</span><span class="sxs-lookup"><span data-stu-id="7b8c1-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="7b8c1-108">必須。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-108">Required.</span></span> <span data-ttu-id="7b8c1-109">`Do`ループの定義を開始します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="7b8c1-110">`Until` を使用しない場合に、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-110">Required unless `Until` is used.</span></span> <span data-ttu-id="7b8c1-111">がに`condition` `False`なるまでループを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="7b8c1-112">`While` を使用しない場合に、必ず指定します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-112">Required unless `While` is used.</span></span> <span data-ttu-id="7b8c1-113">がに`condition` `True`なるまでループを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="7b8c1-114">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-114">Optional.</span></span> <span data-ttu-id="7b8c1-115">`Boolean`条件.</span><span class="sxs-lookup"><span data-stu-id="7b8c1-115">`Boolean` expression.</span></span> <span data-ttu-id="7b8c1-116">`False`が`condition` の場合、VisualBasicはとし`Nothing`て扱います。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="7b8c1-117">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-117">Optional.</span></span> <span data-ttu-id="7b8c1-118">または`condition`の間に繰り返される1つ以上のステートメントが`True`です。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="7b8c1-119">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-119">Optional.</span></span> <span data-ttu-id="7b8c1-120">`Do`ループの次の反復処理に制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="7b8c1-121">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-121">Optional.</span></span> <span data-ttu-id="7b8c1-122">制御を`Do`ループの外に転送します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="7b8c1-123">必須。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-123">Required.</span></span> <span data-ttu-id="7b8c1-124">`Do`ループの定義を終了します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b8c1-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="7b8c1-125">Remarks</span></span>  
 <span data-ttu-id="7b8c1-126">条件が`Do...Loop`満たされるまで、一連のステートメントを不特定の回数繰り返し繰り返す場合は、構造体を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="7b8c1-127">設定された数の時間、ステートメントを繰り返し表示する場合、[For...Next ステートメント](../../../visual-basic/language-reference/statements/for-next-statement.md)は、通常のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="7b8c1-128">または`While` `Until`のいずれかを使用`condition`して、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="7b8c1-129">ループの開始`condition`時または終了時に1回だけテストできます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="7b8c1-130">ループの開始`condition`時 ( `Do`ステートメント内) にテストした場合、ループは一度も実行されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="7b8c1-131">ループの最後 ( `Loop`ステートメント内) でテストした場合、ループは常に少なくとも1回は実行されます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="7b8c1-132">通常、この条件は2つの値の比較によって得られますが、[ブールデータ型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)の値 (`True`また`False`は) に評価される任意の式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="7b8c1-133">これには、に`Boolean`変換された他のデータ型 (数値型など) の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="7b8c1-134">ループを入れ子`Do`にするには、ループを別のループ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="7b8c1-135">また、さまざまな種類の制御構造を相互に入れ子にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="7b8c1-136">詳細については、「[入れ子になったコントロール構造](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b8c1-137">`Do...Loop`構造体によって、より高い柔軟性が得られます。 [End while ステートメント](../../../visual-basic/language-reference/statements/while-end-while-statement.md)を使用すると、ループが停止`condition` `True`したとき、または最初`True`に発生したときに、ループを終了するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="7b8c1-138">また、ループの開始時`condition`または終了時にテストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="7b8c1-139">終了</span><span class="sxs-lookup"><span data-stu-id="7b8c1-139">Exit Do</span></span>  
 <span data-ttu-id="7b8c1-140">[Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md)ステートメントは、を終了する別の`Do…Loop`方法を提供できます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="7b8c1-141">`Exit Do``Loop`ステートメントの後にあるステートメントに制御を直ちに転送します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="7b8c1-142">`Exit Do`は、 `If...Then...Else`構造体などの条件を評価した後に頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="7b8c1-143">誤った値や終了要求など、反復処理を続行することが不要または不可能な条件を検出した場合は、ループを終了することができます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="7b8c1-144">の1つ`Exit Do`の用途は、*無限ループ*の原因となる可能性のある条件をテストすることです。これは、大規模または無限の回数実行されるループです。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="7b8c1-145">を使用`Exit Do`すると、ループをエスケープできます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="7b8c1-146">内の任意の場所に`Exit Do`任意の数のステートメントを含めることができます。`Do…Loop`</span><span class="sxs-lookup"><span data-stu-id="7b8c1-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="7b8c1-147">入れ子になっ`Do`たループ内`Exit Do`で使用すると、最も内側のループから、入れ子の次の上位レベルに制御を転送します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b8c1-148">例</span><span class="sxs-lookup"><span data-stu-id="7b8c1-148">Example</span></span>  
 <span data-ttu-id="7b8c1-149">次の例では、 `index`変数が10を超えるまで、ループ内のステートメントが実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="7b8c1-150">`Until`句はループの最後にあります。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="7b8c1-151">例</span><span class="sxs-lookup"><span data-stu-id="7b8c1-151">Example</span></span>  
 <span data-ttu-id="7b8c1-152">次の例では`While` 、 `Until`句ではなく句を`condition`使用して、末尾ではなくループの開始時にテストします。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="7b8c1-153">例</span><span class="sxs-lookup"><span data-stu-id="7b8c1-153">Example</span></span>  
 <span data-ttu-id="7b8c1-154">次の例では`condition` 、 `index`変数が100より大きい場合、はループを停止します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="7b8c1-155">ただし、ループ内の`Exit Do` ステートメントを指定すると、インデックス変数が10を超える場合、ステートメントによってループが停止します。`If`</span><span class="sxs-lookup"><span data-stu-id="7b8c1-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="7b8c1-156">例</span><span class="sxs-lookup"><span data-stu-id="7b8c1-156">Example</span></span>  
 <span data-ttu-id="7b8c1-157">次の例では、テキストファイル内のすべての行を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="7b8c1-158">メソッド<xref:System.IO.File.OpenText%2A>は、ファイルを開き、文字<xref:System.IO.StreamReader>を読み取るを返します。</span><span class="sxs-lookup"><span data-stu-id="7b8c1-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="7b8c1-159">条件では、 `StreamReader`のメソッドによって、追加の文字があるかどうかが判断されます。<xref:System.IO.StreamReader.Peek%2A> `Do...Loop`</span><span class="sxs-lookup"><span data-stu-id="7b8c1-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="7b8c1-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b8c1-160">See also</span></span>

- [<span data-ttu-id="7b8c1-161">ループ構造</span><span class="sxs-lookup"><span data-stu-id="7b8c1-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="7b8c1-162">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b8c1-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="7b8c1-163">Boolean データ型</span><span class="sxs-lookup"><span data-stu-id="7b8c1-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="7b8c1-164">入れ子になった制御構造</span><span class="sxs-lookup"><span data-stu-id="7b8c1-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="7b8c1-165">Exit ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b8c1-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="7b8c1-166">While...End While ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b8c1-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
