---
title: ラムダ式 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: c43739e098a91d54d300fa7074d1563da179c0e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665794"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="5e403-102">ラムダ式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e403-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="5e403-103">A*ラムダ式*は関数またはサブルーチン デリゲートは、有効な場所で使用できる名前のないです。</span><span class="sxs-lookup"><span data-stu-id="5e403-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="5e403-104">ラムダ式は関数またはサブルーチンを指定でき、単一行または複数行を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5e403-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="5e403-105">ラムダ式に現在のスコープから値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5e403-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e403-106">`RemoveHandler`ステートメントは例外です。</span><span class="sxs-lookup"><span data-stu-id="5e403-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="5e403-107">デリゲート パラメーターのラムダ式を渡すことはできません`RemoveHandler`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="5e403-108">使用してラムダ式を作成する、`Function`または`Sub`キーワード、標準の関数またはサブルーチンを作成すると同じようにします。</span><span class="sxs-lookup"><span data-stu-id="5e403-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="5e403-109">ただし、ステートメントでは、ラムダ式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e403-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="5e403-110">次の例は、ラムダ式を引数をインクリメントし、値を返します。</span><span class="sxs-lookup"><span data-stu-id="5e403-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="5e403-111">この例では、単一行および複数行のラムダ式の両方の構文、関数を示します。</span><span class="sxs-lookup"><span data-stu-id="5e403-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 <span data-ttu-id="5e403-112">次の例では、値をコンソールに出力するラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="5e403-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="5e403-113">この例では、サブルーチンの両方の単一行および複数行のラムダ式構文を示します。</span><span class="sxs-lookup"><span data-stu-id="5e403-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 <span data-ttu-id="5e403-114">前の例では、変数名にラムダ式が割り当てられてに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5e403-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="5e403-115">変数を参照するには、ラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5e403-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="5e403-116">宣言し、同時に、ラムダ式を呼び出す次の例に示すようにできます。</span><span class="sxs-lookup"><span data-stu-id="5e403-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 <span data-ttu-id="5e403-117">ラムダ式は関数呼び出しの結果値として返されることができます (例では、のように、[コンテキスト](#context)このトピックで後述する「)、またはパラメーターに渡される引数として、デリゲート型を受け取る次に示すように例です。</span><span class="sxs-lookup"><span data-stu-id="5e403-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="5e403-118">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="5e403-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="5e403-119">標準の関数またはサブルーチンのラムダ式の構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="5e403-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="5e403-120">相違点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e403-120">The differences are as follows:</span></span>  
  
- <span data-ttu-id="5e403-121">ラムダ式の名前ではありません。</span><span class="sxs-lookup"><span data-stu-id="5e403-121">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="5e403-122">ラムダ式などで、修飾子を含めることはできません`Overloads`または`Overrides`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="5e403-123">単一行のラムダ関数は使用しないでください、`As`戻り値の型を指定する句。</span><span class="sxs-lookup"><span data-stu-id="5e403-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="5e403-124">代わりに、型は、ラムダ式の本体に評価される値から推論されます。</span><span class="sxs-lookup"><span data-stu-id="5e403-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="5e403-125">たとえば、ラムダ式の本体が`cust.City = "London"`、戻り値の型は`Boolean`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="5e403-126">複数行ラムダの関数にするかを指定できます戻り値の型を使用して、`As`句、または省略、`As`句戻り値の型を推論できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5e403-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="5e403-127">ときに、`As`複数行ラムダ関数の句を省略すると、すべての主要な型と戻り値の型が推論されます、`Return`複数行ラムダの関数内のステートメント。</span><span class="sxs-lookup"><span data-stu-id="5e403-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="5e403-128">*優先型*は一意の型に拡大変換できるその他のすべての種類です。</span><span class="sxs-lookup"><span data-stu-id="5e403-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="5e403-129">この一意の型を決定できない場合に絞り込むことが、配列内の他のすべての型を一意の型は、主要な型。</span><span class="sxs-lookup"><span data-stu-id="5e403-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="5e403-130">これらの一意の型をどちらも特定できない場合は、 `Object`が最も優先度の高い型になります。</span><span class="sxs-lookup"><span data-stu-id="5e403-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="5e403-131">この場合は場合、`Option Strict`に設定されている`On`、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5e403-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="5e403-132">式が指定された場合など、`Return`ステートメントは、型の値を含めることが`Integer`、 `Long`、および`Double`、結果の配列の型は`Double`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="5e403-133">両方`Integer`と`Long`に拡大変換`Double`とのみ`Double`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="5e403-134">そのため、 `Double` が最も優先度の高い型になります。</span><span class="sxs-lookup"><span data-stu-id="5e403-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="5e403-135">詳細については、「 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e403-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
- <span data-ttu-id="5e403-136">単一行の関数の本体は、ステートメントではなく、値を返す式を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e403-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="5e403-137">ない`Return`関数の単一行ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5e403-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="5e403-138">単一行の関数によって返される値は、関数の本体での式の値です。</span><span class="sxs-lookup"><span data-stu-id="5e403-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
- <span data-ttu-id="5e403-139">単一行のサブルーチンの本文は、単一行ステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e403-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
- <span data-ttu-id="5e403-140">単一行の関数とサブルーチンは含まれません、`End Function`または`End Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="5e403-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="5e403-141">使用して、ラムダ式のパラメーターのデータ型を指定することができます、`As`キーワード、またはパラメーターのデータ型を推論することができます。</span><span class="sxs-lookup"><span data-stu-id="5e403-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="5e403-142">すべてのパラメーターまたはすべてのデータ型を推論する必要があります指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e403-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="5e403-143">`Optional` `Paramarray`パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5e403-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
- <span data-ttu-id="5e403-144">ジェネリック パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="5e403-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="5e403-145">非同期ラムダ</span><span class="sxs-lookup"><span data-stu-id="5e403-145">Async Lambdas</span></span>  
 <span data-ttu-id="5e403-146">使用して非同期処理を組み込んだするラムダ式およびステートメントを簡単に作成することができます、 [Async](../../../../visual-basic/language-reference/modifiers/async.md)と[Await 演算子](../../../../visual-basic/language-reference/operators/await-operator.md)キーワード。</span><span class="sxs-lookup"><span data-stu-id="5e403-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="5e403-147">たとえば、次に示す Windows フォーム例には、非同期メソッド `ExampleMethodAsync`を呼び出して待機するイベント ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e403-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="5e403-148">非同期のラムダを使用して、同じイベント ハンドラーを追加することができます、 [AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e403-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="5e403-149">次の例に示すように、このハンドラーを追加するには、ラムダ パラメーター リストの前に `Async` 修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e403-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="5e403-150">作成して、非同期メソッドを使用する方法の詳細については、次を参照してください。 [Async および Await を使用した非同期プログラミング](../../../../visual-basic/programming-guide/concepts/async/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e403-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="context"></a> <span data-ttu-id="5e403-151">コンテキスト</span><span class="sxs-lookup"><span data-stu-id="5e403-151">Context</span></span>  
 <span data-ttu-id="5e403-152">ラムダ式が定義されている外側のスコープとコンテキストを共有します。</span><span class="sxs-lookup"><span data-stu-id="5e403-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="5e403-153">コンテナーのスコープで記述された任意のコードと同じアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="5e403-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="5e403-154">これにより、メンバー変数、関数とサブへのアクセスが含まれます。 `Me`、コンテナーのスコープ内のローカル変数やパラメーター。</span><span class="sxs-lookup"><span data-stu-id="5e403-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="5e403-155">ローカル変数とスコープのパラメーターへのアクセスは、そのスコープの有効期間を超えて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="5e403-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="5e403-156">ラムダ式を参照するデリゲートがガベージ コレクションを使用できない場合に限り、元の環境変数へのアクセスは保持されます。</span><span class="sxs-lookup"><span data-stu-id="5e403-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="5e403-157">次の例で変数`target`のローカル`makeTheGame`をメソッド、ラムダ式`playTheGame`が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5e403-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="5e403-158">返されたラムダ式が割り当てられているので注意`takeAGuess`で`Main`、ローカル変数へのアクセスにまだ`target`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 <span data-ttu-id="5e403-159">次の例では、さまざまな入れ子になったラムダ式のアクセス権を示します。</span><span class="sxs-lookup"><span data-stu-id="5e403-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="5e403-160">返されたラムダ式が実行されると`Main`として`aDel`、これらの要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5e403-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
- <span data-ttu-id="5e403-161">定義されているクラスのフィールド: `aField`</span><span class="sxs-lookup"><span data-stu-id="5e403-161">A field of the class in which it is defined: `aField`</span></span>  
  
- <span data-ttu-id="5e403-162">定義されているクラスのプロパティ: `aProp`</span><span class="sxs-lookup"><span data-stu-id="5e403-162">A property of the class in which it is defined: `aProp`</span></span>  
  
- <span data-ttu-id="5e403-163">メソッドのパラメーター `functionWithNestedLambda`、それが定義されています。 `level1`</span><span class="sxs-lookup"><span data-stu-id="5e403-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
- <span data-ttu-id="5e403-164">ローカル変数`functionWithNestedLambda`: `localVar`</span><span class="sxs-lookup"><span data-stu-id="5e403-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
- <span data-ttu-id="5e403-165">入れ子になったラムダ式のパラメーター: `level2`</span><span class="sxs-lookup"><span data-stu-id="5e403-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="5e403-166">デリゲート型に変換します。</span><span class="sxs-lookup"><span data-stu-id="5e403-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="5e403-167">ラムダ式は、互換性のあるデリゲート型に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="5e403-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="5e403-168">互換性のための一般的な要件については、次を参照してください。[厳密でないデリゲート変換](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e403-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="5e403-169">たとえば、次のコード例に暗黙的に変換されるラムダ式を示しています。`Func(Of Integer, Boolean)`またはデリゲートのシグネチャが一致します。</span><span class="sxs-lookup"><span data-stu-id="5e403-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 <span data-ttu-id="5e403-170">次のコード例に暗黙的に変換されるラムダ式を示しています。`Sub(Of Double, String, Double)`またはデリゲートのシグネチャが一致します。</span><span class="sxs-lookup"><span data-stu-id="5e403-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 <span data-ttu-id="5e403-171">ラムダ式をデリゲートに割り当てるまたはプロシージャに引数として渡したりするときに、パラメーター名を指定は、データ型、型がデリゲートから取得されるを省略できます。</span><span class="sxs-lookup"><span data-stu-id="5e403-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5e403-172">使用例</span><span class="sxs-lookup"><span data-stu-id="5e403-172">Examples</span></span>  
  
- <span data-ttu-id="5e403-173">次の例を返すラムダ式を定義する`True`null 許容型の引数に値が割り当てられる場合と`False`場合、その値は`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="5e403-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
- <span data-ttu-id="5e403-174">次の例では、配列内の最後の要素のインデックスを返すラムダ式を定義します。</span><span class="sxs-lookup"><span data-stu-id="5e403-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5e403-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e403-175">See also</span></span>

- [<span data-ttu-id="5e403-176">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="5e403-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5e403-177">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="5e403-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="5e403-178">デリゲート</span><span class="sxs-lookup"><span data-stu-id="5e403-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="5e403-179">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="5e403-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="5e403-180">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="5e403-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="5e403-181">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="5e403-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="5e403-182">方法: Visual Basic での別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="5e403-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="5e403-183">方法: ラムダ式を作成します。</span><span class="sxs-lookup"><span data-stu-id="5e403-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="5e403-184">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="5e403-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
