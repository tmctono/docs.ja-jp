---
title: '方法: ラムダ式 (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344547"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="4e0e9-102">方法: ラムダ式 (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="4e0e9-103">A*ラムダ式*は関数またはサブルーチンに名前がないです。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="4e0e9-104">ラムダ式はデリゲート型が有効な場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="4e0e9-105">単一行のラムダ式の関数を作成するには</span><span class="sxs-lookup"><span data-stu-id="4e0e9-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="4e0e9-106">キーワードの入力の場合は、デリゲート型を使用できる場所、 `Function`、次の例。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="4e0e9-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="4e0e9-108">かっこで囲んで直後後`Function`関数のパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="4e0e9-109">後の名前が指定されていないことに注意してください。`Function`します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="4e0e9-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="4e0e9-111">次のパラメーターのリストには、関数の本体として 1 つの式を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="4e0e9-112">式が評価される値は、関数によって返される値です。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="4e0e9-113">使用しない、`As`句を戻り値の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="4e0e9-114">ラムダ式は、整数の引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="4e0e9-115">また、同じ結果は、次の例で実施されます。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="4e0e9-116">単一行のラムダ式のサブルーチンを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e0e9-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="4e0e9-117">キーワードの入力の場合は、デリゲート型を使用できる場所、`Sub`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="4e0e9-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="4e0e9-119">かっこで囲んで直後後`Sub`サブルーチンのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="4e0e9-120">後の名前が指定されていないことに注意してください。`Sub`します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="4e0e9-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="4e0e9-122">次のパラメーターのリストには、サブルーチンの本文として 1 つのステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="4e0e9-123">ラムダ式は、文字列引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="4e0e9-124">複数行のラムダ式の関数を作成するには</span><span class="sxs-lookup"><span data-stu-id="4e0e9-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="4e0e9-125">キーワードの入力の場合は、デリゲート型を使用できる場所、`Function`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="4e0e9-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="4e0e9-127">かっこで囲んで直後後`Function`関数のパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="4e0e9-128">後の名前が指定されていないことに注意してください。`Function`します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="4e0e9-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="4e0e9-130">ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-130">Press ENTER.</span></span> <span data-ttu-id="4e0e9-131">`End Function`ステートメントが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="4e0e9-132">関数の本体には、式を作成し、値を返すには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="4e0e9-133">使用しない、`As`句を戻り値の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="4e0e9-134">ラムダ式は、整数の引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="4e0e9-135">複数行のラムダ式のサブルーチンを作成するには</span><span class="sxs-lookup"><span data-stu-id="4e0e9-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="4e0e9-136">キーワードの入力の場合は、デリゲート型を使用できる場所、`Sub`次の例のように。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="4e0e9-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="4e0e9-138">かっこで囲んで直後後`Sub`サブルーチンのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="4e0e9-139">後の名前が指定されていないことに注意してください。`Sub`します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="4e0e9-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="4e0e9-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="4e0e9-141">ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-141">Press ENTER.</span></span> <span data-ttu-id="4e0e9-142">`End Sub`ステートメントが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="4e0e9-143">関数の本体には、次のサブルーチンが呼び出されたときに実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="4e0e9-144">ラムダ式は、文字列引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="4e0e9-145">例</span><span class="sxs-lookup"><span data-stu-id="4e0e9-145">Example</span></span>  
 <span data-ttu-id="4e0e9-146">型を持つパラメーターの引数として渡すことができる関数を定義するラムダ式の一般的な用途は、`Delegate`します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="4e0e9-147">次の例では、<xref:System.Diagnostics.Process.GetProcesses%2A>メソッドは、ローカル コンピューターで実行されているプロセスの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="4e0e9-148"><xref:System.Linq.Enumerable.Where%2A>からメソッド、<xref:System.Linq.Enumerable>クラスが必要です、`Boolean`デリゲートの引数として。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="4e0e9-149">ラムダ式の例では、目的のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="4e0e9-150">返します`True`プロセスごとに 1 つのスレッドし、でそれらが選択されて`filteredList`します。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="4e0e9-151">前の例は次のコードで記述されている[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]構文。</span><span class="sxs-lookup"><span data-stu-id="4e0e9-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="4e0e9-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e0e9-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="4e0e9-153">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="4e0e9-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="4e0e9-154">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e0e9-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="4e0e9-155">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e0e9-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4e0e9-156">デリゲート</span><span class="sxs-lookup"><span data-stu-id="4e0e9-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="4e0e9-157">方法: Visual Basic での別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="4e0e9-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="4e0e9-158">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="4e0e9-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="4e0e9-159">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="4e0e9-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
