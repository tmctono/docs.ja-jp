---
title: '方法: ラムダ式を作成する'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: cc2de38f7375848d104edff6f419656d9caa9cb2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071925"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="8ba3e-102">方法: ラムダ式を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ba3e-102">How to: Create a Lambda Expression (Visual Basic)</span></span>

<span data-ttu-id="8ba3e-103">"*ラムダ式*" は、名前のない関数またはサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="8ba3e-104">ラムダ式は、デリゲート型が有効であれば使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="8ba3e-105">単一行のラムダ式関数を作成するには</span><span class="sxs-lookup"><span data-stu-id="8ba3e-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="8ba3e-106">デリゲート型を使用できる場合、次の例に示すように、キーワード `Function` を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="8ba3e-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="8ba3e-108">`Function` の直後のかっこ内に、関数のパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="8ba3e-109">`Function` の後に名前を指定しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="8ba3e-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="8ba3e-111">パラメーター リストの後に、関数の本体として単一の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="8ba3e-112">式が評価される値は、関数によって返される値です。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="8ba3e-113">`As` 句を使用して戻り値の型は指定しません。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="8ba3e-114">整数引数を渡してラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="8ba3e-115">代わりに、次の例でも同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="8ba3e-116">単一行のラムダ式サブルーチンを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ba3e-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="8ba3e-117">デリゲート型を使用できる場合、次の例に示すように、キーワード `Sub` を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="8ba3e-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="8ba3e-119">`Sub` の直後のかっこ内に、サブルーチンのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="8ba3e-120">`Sub` の後に名前を指定しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="8ba3e-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="8ba3e-122">パラメーター リストの後に、サブルーチンの本体として単一のステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="8ba3e-123">文字列引数を渡してラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="8ba3e-124">複数行のラムダ式関数を作成するには</span><span class="sxs-lookup"><span data-stu-id="8ba3e-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="8ba3e-125">デリゲート型を使用できる場合、次の例に示すように、キーワード `Function` を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="8ba3e-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="8ba3e-127">`Function` の直後のかっこ内に、関数のパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="8ba3e-128">`Function` の後に名前を指定しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="8ba3e-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="8ba3e-130">ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-130">Press ENTER.</span></span> <span data-ttu-id="8ba3e-131">`End Function` ステートメントが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="8ba3e-132">関数の本体内に、次のコードを追加して式を作成し、値を返します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="8ba3e-133">`As` 句を使用して戻り値の型は指定しません。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="8ba3e-134">整数引数を渡してラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="8ba3e-135">複数行のラムダ式サブルーチンを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ba3e-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="8ba3e-136">デリゲート型を使用できる場合、次の例に示すように、キーワード `Sub` を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="8ba3e-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="8ba3e-138">`Sub` の直後のかっこ内に、サブルーチンのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="8ba3e-139">`Sub` の後に名前を指定しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="8ba3e-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="8ba3e-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="8ba3e-141">ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-141">Press ENTER.</span></span> <span data-ttu-id="8ba3e-142">`End Sub` ステートメントが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="8ba3e-143">関数の本体内に、サブルーチンが呼び出されたときに実行する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="8ba3e-144">文字列引数を渡してラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="8ba3e-145">例</span><span class="sxs-lookup"><span data-stu-id="8ba3e-145">Example</span></span>  

 <span data-ttu-id="8ba3e-146">ラムダ式の一般的な用途は、型が `Delegate` のパラメーターの引数として渡すことができる関数を定義することです。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="8ba3e-147">次の例では、<xref:System.Diagnostics.Process.GetProcesses%2A> メソッドはローカルコンピューターで実行されているプロセスの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="8ba3e-148"><xref:System.Linq.Enumerable> クラスの <xref:System.Linq.Enumerable.Where%2A> メソッドには、引数として `Boolean` デリゲートが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="8ba3e-149">この例のラムダ式は、そのために使用されています。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="8ba3e-150">スレッドが 1 つしかないプロセスごとに `True` が返されます。それらは `filteredList` で選択されています。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="8ba3e-151">前の例は、統合言語クエリ (LINQ) 構文で記述された次のコードに相当します。</span><span class="sxs-lookup"><span data-stu-id="8ba3e-151">The previous example is equivalent to the following code, which is written in Language-Integrated Query (LINQ) syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="8ba3e-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ba3e-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="8ba3e-153">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="8ba3e-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="8ba3e-154">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="8ba3e-154">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="8ba3e-155">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="8ba3e-155">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="8ba3e-156">デリゲート</span><span class="sxs-lookup"><span data-stu-id="8ba3e-156">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="8ba3e-157">方法: Visual Basic でプロシージャを別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="8ba3e-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="8ba3e-158">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="8ba3e-158">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="8ba3e-159">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="8ba3e-159">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
