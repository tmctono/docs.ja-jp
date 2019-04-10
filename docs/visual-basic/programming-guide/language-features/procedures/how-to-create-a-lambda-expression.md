---
title: '方法: ラムダ式 (Visual Basic) を作成します。'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344547"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="865b7-102">方法: ラムダ式 (Visual Basic) を作成します。</span><span class="sxs-lookup"><span data-stu-id="865b7-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="865b7-103">A*ラムダ式*は関数またはサブルーチンに名前がないです。</span><span class="sxs-lookup"><span data-stu-id="865b7-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="865b7-104">ラムダ式はデリゲート型が有効な場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="865b7-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="865b7-105">単一行のラムダ式の関数を作成するには</span><span class="sxs-lookup"><span data-stu-id="865b7-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="865b7-106">キーワードの入力の場合は、デリゲート型を使用できる場所、 `Function`、次の例。</span><span class="sxs-lookup"><span data-stu-id="865b7-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="865b7-107">かっこで囲んで直後後`Function`関数のパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="865b7-107">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="865b7-108">後の名前が指定されていないことに注意してください。`Function`します。</span><span class="sxs-lookup"><span data-stu-id="865b7-108">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. <span data-ttu-id="865b7-109">次のパラメーターのリストには、関数の本体として 1 つの式を入力します。</span><span class="sxs-lookup"><span data-stu-id="865b7-109">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="865b7-110">式が評価される値は、関数によって返される値です。</span><span class="sxs-lookup"><span data-stu-id="865b7-110">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="865b7-111">使用しない、`As`句を戻り値の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="865b7-111">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="865b7-112">ラムダ式は、整数の引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="865b7-112">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="865b7-113">また、同じ結果は、次の例で実施されます。</span><span class="sxs-lookup"><span data-stu-id="865b7-113">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="865b7-114">単一行のラムダ式のサブルーチンを作成するには</span><span class="sxs-lookup"><span data-stu-id="865b7-114">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="865b7-115">キーワードの入力の場合は、デリゲート型を使用できる場所、`Sub`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="865b7-115">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="865b7-116">かっこで囲んで直後後`Sub`サブルーチンのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="865b7-116">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="865b7-117">後の名前が指定されていないことに注意してください。`Sub`します。</span><span class="sxs-lookup"><span data-stu-id="865b7-117">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. <span data-ttu-id="865b7-118">次のパラメーターのリストには、サブルーチンの本文として 1 つのステートメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="865b7-118">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="865b7-119">ラムダ式は、文字列引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="865b7-119">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="865b7-120">複数行のラムダ式の関数を作成するには</span><span class="sxs-lookup"><span data-stu-id="865b7-120">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="865b7-121">キーワードの入力の場合は、デリゲート型を使用できる場所、`Function`次の例のようにします。</span><span class="sxs-lookup"><span data-stu-id="865b7-121">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="865b7-122">かっこで囲んで直後後`Function`関数のパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="865b7-122">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="865b7-123">後の名前が指定されていないことに注意してください。`Function`します。</span><span class="sxs-lookup"><span data-stu-id="865b7-123">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. <span data-ttu-id="865b7-124">ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="865b7-124">Press ENTER.</span></span> <span data-ttu-id="865b7-125">`End Function`ステートメントが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="865b7-125">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="865b7-126">関数の本体には、式を作成し、値を返すには、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="865b7-126">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="865b7-127">使用しない、`As`句を戻り値の型を指定します。</span><span class="sxs-lookup"><span data-stu-id="865b7-127">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="865b7-128">ラムダ式は、整数の引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="865b7-128">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="865b7-129">複数行のラムダ式のサブルーチンを作成するには</span><span class="sxs-lookup"><span data-stu-id="865b7-129">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="865b7-130">キーワードの入力の場合は、デリゲート型を使用できる場所、`Sub`次の例のように。</span><span class="sxs-lookup"><span data-stu-id="865b7-130">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="865b7-131">かっこで囲んで直後後`Sub`サブルーチンのパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="865b7-131">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="865b7-132">後の名前が指定されていないことに注意してください。`Sub`します。</span><span class="sxs-lookup"><span data-stu-id="865b7-132">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. <span data-ttu-id="865b7-133">ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="865b7-133">Press ENTER.</span></span> <span data-ttu-id="865b7-134">`End Sub`ステートメントが自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="865b7-134">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="865b7-135">関数の本体には、次のサブルーチンが呼び出されたときに実行するコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="865b7-135">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="865b7-136">ラムダ式は、文字列引数を渡すことによって呼び出します。</span><span class="sxs-lookup"><span data-stu-id="865b7-136">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="865b7-137">例</span><span class="sxs-lookup"><span data-stu-id="865b7-137">Example</span></span>  
 <span data-ttu-id="865b7-138">型を持つパラメーターの引数として渡すことができる関数を定義するラムダ式の一般的な用途は、`Delegate`します。</span><span class="sxs-lookup"><span data-stu-id="865b7-138">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="865b7-139">次の例では、<xref:System.Diagnostics.Process.GetProcesses%2A>メソッドは、ローカル コンピューターで実行されているプロセスの配列を返します。</span><span class="sxs-lookup"><span data-stu-id="865b7-139">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="865b7-140"><xref:System.Linq.Enumerable.Where%2A>からメソッド、<xref:System.Linq.Enumerable>クラスが必要です、`Boolean`デリゲートの引数として。</span><span class="sxs-lookup"><span data-stu-id="865b7-140">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="865b7-141">ラムダ式の例では、目的のために使用されます。</span><span class="sxs-lookup"><span data-stu-id="865b7-141">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="865b7-142">返します`True`プロセスごとに 1 つのスレッドし、でそれらが選択されて`filteredList`します。</span><span class="sxs-lookup"><span data-stu-id="865b7-142">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="865b7-143">前の例は次のコードで記述されている[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]構文。</span><span class="sxs-lookup"><span data-stu-id="865b7-143">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="865b7-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="865b7-144">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="865b7-145">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="865b7-145">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="865b7-146">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="865b7-146">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="865b7-147">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="865b7-147">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="865b7-148">デリゲート</span><span class="sxs-lookup"><span data-stu-id="865b7-148">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="865b7-149">方法: Visual Basic での別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="865b7-149">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="865b7-150">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="865b7-150">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="865b7-151">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="865b7-151">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
