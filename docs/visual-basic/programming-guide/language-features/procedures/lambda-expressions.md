---
title: ラムダ式
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249670"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="54ee0-102">ラムダ式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54ee0-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="54ee0-103">"*ラムダ式*" は、デリゲートが有効な場所であればどこでも使用できる、名前のない関数またはサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="54ee0-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="54ee0-104">ラムダ式は関数またはサブルーチンにすることができ、単一行または複数行にすることができます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="54ee0-105">値を現在のスコープからラムダ式に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="54ee0-106">`RemoveHandler` ステートメントは例外です。</span><span class="sxs-lookup"><span data-stu-id="54ee0-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="54ee0-107">`RemoveHandler` のデリゲート パラメーターにラムダ式を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="54ee0-108">標準の関数またはサブルーチンを作成する場合と同様に、`Function` または `Sub` キーワードを使用してラムダ式を作成します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="54ee0-109">ただし、ラムダ式はステートメントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="54ee0-110">次の例は、引数をインクリメントして値を返すラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="54ee0-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="54ee0-111">この例は、関数の単一行および複数行のラムダ式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="54ee0-112">次の例は、コンソールに値を書き込むラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="54ee0-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="54ee0-113">この例は、サブルーチンの単一行および複数行のラムダ式の構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="54ee0-114">上記の例では、ラムダ式が変数名に割り当てられていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54ee0-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="54ee0-115">変数を参照するときは常にラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="54ee0-116">次の例に示すように、ラムダ式の宣言と呼び出しを同時に行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="54ee0-117">ラムダ式は関数呼び出しの値として返すことも (このトピックで後述する「[コンテキスト](#context)」の例を参照)、次の例に示すように、デリゲート型を受け取るパラメーターに引数として渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="54ee0-118">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="54ee0-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="54ee0-119">ラムダ式の構文は、標準の関数またはサブルーチンの構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="54ee0-120">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="54ee0-120">The differences are as follows:</span></span>

- <span data-ttu-id="54ee0-121">ラムダ式には名前はありません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="54ee0-122">ラムダ式には、`Overloads` や `Overrides` などの修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="54ee0-123">単一行のラムダ関数では、`As` 句を戻り値の型を指定しません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="54ee0-124">代わりに、ラムダ式の本体が評価される値から型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="54ee0-125">たとえば、ラムダ式の本体が `cust.City = "London"` の場合、戻り値の型は `Boolean` になります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="54ee0-126">複数行のラムダ関数では、`As` 句を使用して戻り値の型を指定することも、戻り値の型が推論されるように `As` 句を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="54ee0-127">複数行のラムダ関数で `As` 句を省略すると、戻り値の型として、複数行のラムダ関数のすべての `Return` ステートメントから最も優先度の高い型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="54ee0-128">"*最も優先度の高い型*" は、他のすべての型から拡大変換できる一意の型です。</span><span class="sxs-lookup"><span data-stu-id="54ee0-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="54ee0-129">この一意の型を特定できない場合、最も優先度の高い型は、配列内の他のすべての型から縮小変換できる一意の型になります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="54ee0-130">これらの一意の型をどちらも特定できない場合は、 `Object`が最も優先度の高い型になります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="54ee0-131">この場合、`Option Strict` が `On` に設定されていると、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="54ee0-132">たとえば、`Return` ステートメントに指定された式に、`Integer`、`Long`、`Double` の各型の値が含まれている場合、結果の配列は `Double` 型になります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="54ee0-133">`Integer` と `Long` はどちらも `Double` に拡大変換され、`Double` のみになります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="54ee0-134">そのため、 `Double` が最も優先度の高い型になります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="54ee0-135">詳細については、「 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54ee0-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="54ee0-136">単一行の関数の本体は、ステートメントではなく、値を返す式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="54ee0-137">単一行の関数の `Return` ステートメントはありません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="54ee0-138">単一行の関数によって返される値は、関数の本体に含まれる式の値です。</span><span class="sxs-lookup"><span data-stu-id="54ee0-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="54ee0-139">単一行のサブルーチンの本体は、単一行のステートメントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="54ee0-140">単一行の関数とサブルーチンには、`End Function` または `End Sub` ステートメントは含まれません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="54ee0-141">`As` キーワードを使用して、ラムダ式のパラメーターのデータ型を指定できます。また、パラメーターのデータ型を推論することもできます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="54ee0-142">すべてのパラメーターにデータ型が指定されているか、すべて推論される必要があります。</span><span class="sxs-lookup"><span data-stu-id="54ee0-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="54ee0-143">`Optional` および `Paramarray` パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="54ee0-144">ジェネリック パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="54ee0-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="54ee0-145">非同期ラムダ</span><span class="sxs-lookup"><span data-stu-id="54ee0-145">Async Lambdas</span></span>

<span data-ttu-id="54ee0-146">[Async](../../../../visual-basic/language-reference/modifiers/async.md) キーワードと [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) キーワードを使用すると、非同期処理を組み込んだラムダ式およびステートメントを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="54ee0-147">たとえば、次に示す Windows フォーム例には、非同期メソッド `ExampleMethodAsync`を呼び出して待機するイベント ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="54ee0-148">[AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)で非同期ラムダを使用して、同じイベント ハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="54ee0-149">次の例に示すように、このハンドラーを追加するには、ラムダ パラメーター リストの前に `Async` 修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="54ee0-150">非同期メソッドの作成および使用方法の詳細については、「[Asynchronous programming with Async and Await (Async および Await を使用した非同期プログラミング)](../../../../visual-basic/programming-guide/concepts/async/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54ee0-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="54ee0-151">コンテキスト</span><span class="sxs-lookup"><span data-stu-id="54ee0-151">Context</span></span>

<span data-ttu-id="54ee0-152">ラムダ式は、その式が定義されているスコープとコンテキストを共有します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="54ee0-153">包含スコープで記述されたコードと同じアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="54ee0-154">これには、包含スコープ内のメンバー変数、関数とサブルーチン、`Me`、パラメーターとローカル変数へのアクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="54ee0-155">包含スコープ内のローカル変数とパラメーターへのアクセスは、そのスコープの有効期間を超えて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="54ee0-156">ラムダ式を参照するデリゲートがガベージ コレクションで使用できない間は、元の環境の変数へのアクセスが保持されます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="54ee0-157">次の例では、変数 `target` は、`makeTheGame` に対してローカルです。これは、ラムダ式 `playTheGame` が定義されているメソッドです。</span><span class="sxs-lookup"><span data-stu-id="54ee0-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="54ee0-158">`Main` で `takeAGuess` に割り当てられた、返されたラムダ式は、引き続きローカル変数 `target` にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="54ee0-159">次の例は、入れ子になったラムダ式の幅広いアクセス権を示しています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="54ee0-160">返されたラムダ式は、`Main` から `aDel` として実行されると、次の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="54ee0-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="54ee0-161">それが定義されているクラスのフィールド: `aField`</span><span class="sxs-lookup"><span data-stu-id="54ee0-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="54ee0-162">それが定義されているクラスのプロパティ: `aProp`</span><span class="sxs-lookup"><span data-stu-id="54ee0-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="54ee0-163">それが定義されている `functionWithNestedLambda` メソッドのパラメーター: `level1`</span><span class="sxs-lookup"><span data-stu-id="54ee0-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="54ee0-164">`functionWithNestedLambda` のローカル変数: `localVar`</span><span class="sxs-lookup"><span data-stu-id="54ee0-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="54ee0-165">それが入れ子になっているラムダ式のパラメーター: `level2`</span><span class="sxs-lookup"><span data-stu-id="54ee0-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="54ee0-166">デリゲート型への変換</span><span class="sxs-lookup"><span data-stu-id="54ee0-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="54ee0-167">ラムダ式は、互換性のあるデリゲート型に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="54ee0-168">互換性に関する一般的な要件については、「[厳密でないデリゲート変換](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="54ee0-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="54ee0-169">たとえば、次のコード例は、`Func(Of Integer, Boolean)` または一致するデリゲート シグネチャに暗黙的に変換するラムダ式を示しています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="54ee0-170">次のコード例は、`Sub(Of Double, String, Double)` または一致するデリゲート シグネチャに暗黙的に変換するラムダ式を示しています。</span><span class="sxs-lookup"><span data-stu-id="54ee0-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="54ee0-171">ラムダ式をデリゲートに割り当てるか、引数としてプロシージャに渡す場合、パラメーター名を指定できますが、データ型を省略することで、デリゲートから型を取得できます。</span><span class="sxs-lookup"><span data-stu-id="54ee0-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="54ee0-172">使用例</span><span class="sxs-lookup"><span data-stu-id="54ee0-172">Examples</span></span>

- <span data-ttu-id="54ee0-173">次の例では、null 許容値型引数に値が割り当てられている場合は `True` を返し、値が `Nothing` の場合は `False` を返すラムダ式を定義します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="54ee0-174">次の例では、配列の最後の要素のインデックスを返すラムダ式を定義します。</span><span class="sxs-lookup"><span data-stu-id="54ee0-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="54ee0-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="54ee0-175">See also</span></span>

- [<span data-ttu-id="54ee0-176">手順</span><span class="sxs-lookup"><span data-stu-id="54ee0-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="54ee0-177">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="54ee0-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="54ee0-178">デリゲート</span><span class="sxs-lookup"><span data-stu-id="54ee0-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="54ee0-179">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="54ee0-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="54ee0-180">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="54ee0-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="54ee0-181">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="54ee0-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="54ee0-182">方法: Visual Basic でプロシージャを別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="54ee0-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="54ee0-183">方法: ラムダ式を作成する</span><span class="sxs-lookup"><span data-stu-id="54ee0-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="54ee0-184">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="54ee0-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
