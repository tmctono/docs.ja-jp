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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249670"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="4482d-102">ラムダ式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4482d-102">Lambda Expressions (Visual Basic)</span></span>

<span data-ttu-id="4482d-103">*ラムダ式*は、デリゲートが有効な場所であれば、名前のない関数またはサブルーチンです。</span><span class="sxs-lookup"><span data-stu-id="4482d-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="4482d-104">ラムダ式は、関数またはサブルーチンで、単一行または複数行の場合があります。</span><span class="sxs-lookup"><span data-stu-id="4482d-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="4482d-105">現在のスコープからラムダ式に値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4482d-105">You can pass values from the current scope to a lambda expression.</span></span>

> [!NOTE]
> <span data-ttu-id="4482d-106">この`RemoveHandler`ステートメントは例外です。</span><span class="sxs-lookup"><span data-stu-id="4482d-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="4482d-107">のデリゲート パラメーターにラムダ式を 渡すことはできません`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="4482d-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>

<span data-ttu-id="4482d-108">ラムダ式は、標準の`Function`関数`Sub`またはサブルーチンを作成するのと同じように、 or キーワードを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="4482d-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="4482d-109">ただし、ラムダ式はステートメントに含まれます。</span><span class="sxs-lookup"><span data-stu-id="4482d-109">However, lambda expressions are included in a statement.</span></span>

<span data-ttu-id="4482d-110">次の例は、引数をインクリメントして値を返すラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="4482d-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="4482d-111">この例では、関数の単一行と複数行のラムダ式の構文の両方を示します。</span><span class="sxs-lookup"><span data-stu-id="4482d-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

<span data-ttu-id="4482d-112">次の例は、コンソールに値を書き込むラムダ式です。</span><span class="sxs-lookup"><span data-stu-id="4482d-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="4482d-113">この例では、サブルーチンの単一行と複数行のラムダ式の構文の両方を示しています。</span><span class="sxs-lookup"><span data-stu-id="4482d-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

<span data-ttu-id="4482d-114">前の例では、ラムダ式が変数名に割り当てられていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4482d-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="4482d-115">変数を参照するたびに、ラムダ式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4482d-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="4482d-116">次の例に示すように、ラムダ式を同時に宣言して呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4482d-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

<span data-ttu-id="4482d-117">ラムダ式は、関数呼び出しの値として返されるか (このトピックの後の[「Context」](#context)セクションの例で示されているように)、デリゲート型を受け取るパラメーターに引数として渡されます。</span><span class="sxs-lookup"><span data-stu-id="4482d-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a><span data-ttu-id="4482d-118">ラムダ式の構文</span><span class="sxs-lookup"><span data-stu-id="4482d-118">Lambda Expression Syntax</span></span>

<span data-ttu-id="4482d-119">ラムダ式の構文は、標準関数またはサブルーチンの構文に似ています。</span><span class="sxs-lookup"><span data-stu-id="4482d-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="4482d-120">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4482d-120">The differences are as follows:</span></span>

- <span data-ttu-id="4482d-121">ラムダ式に名前がありません。</span><span class="sxs-lookup"><span data-stu-id="4482d-121">A lambda expression does not have a name.</span></span>

- <span data-ttu-id="4482d-122">ラムダ式には、 や`Overloads``Overrides`などの修飾子を指定できません。</span><span class="sxs-lookup"><span data-stu-id="4482d-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>

- <span data-ttu-id="4482d-123">単一行のラムダ関数では、`As`戻り値の型を指定する句は使用しません。</span><span class="sxs-lookup"><span data-stu-id="4482d-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="4482d-124">その代わりに、ラムダ式の本体が評価する値から型が推論されます。</span><span class="sxs-lookup"><span data-stu-id="4482d-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="4482d-125">たとえば、ラムダ式の本体が の場合`cust.City = "London"`、その戻り値`Boolean`の型は です。</span><span class="sxs-lookup"><span data-stu-id="4482d-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>

- <span data-ttu-id="4482d-126">複数行のラムダ関数では、句を使用して戻り値の型`As`を指定するか、または`As`戻り値の型が推論されるように句を省略できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="4482d-127">複数行`As`のラムダ関数に対して句を省略すると、戻り値の型は、複数行のラムダ関数のすべての`Return`ステートメントから主要な型であると推論されます。</span><span class="sxs-lookup"><span data-stu-id="4482d-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="4482d-128">*ドミナント型*は、他のすべての型が拡大できる一意の型です。</span><span class="sxs-lookup"><span data-stu-id="4482d-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="4482d-129">この一意の型を決定できない場合、主要な型は、配列内の他のすべての型が絞り込むことができる一意の型になります。</span><span class="sxs-lookup"><span data-stu-id="4482d-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="4482d-130">これらの一意の型をどちらも特定できない場合は、 `Object`が最も優先度の高い型になります。</span><span class="sxs-lookup"><span data-stu-id="4482d-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="4482d-131">この場合、に設定`Option Strict``On`されている場合は、コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4482d-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>

     <span data-ttu-id="4482d-132">たとえば、ステートメントに指定された`Return`式に 、 `Integer` `Long`、 、および`Double`の値が含まれている場合、結果`Double`の配列は型 です。</span><span class="sxs-lookup"><span data-stu-id="4482d-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="4482d-133">両方`Integer`に`Long`広く`Double`、そして`Double`唯一.</span><span class="sxs-lookup"><span data-stu-id="4482d-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="4482d-134">そのため、 `Double` が最も優先度の高い型になります。</span><span class="sxs-lookup"><span data-stu-id="4482d-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="4482d-135">詳細については、「 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4482d-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

- <span data-ttu-id="4482d-136">単一行関数の本体は、ステートメントではなく値を返す式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4482d-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="4482d-137">単一行`Return`関数のステートメントはありません。</span><span class="sxs-lookup"><span data-stu-id="4482d-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="4482d-138">単一行関数によって返される値は、関数本体の式の値です。</span><span class="sxs-lookup"><span data-stu-id="4482d-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>

- <span data-ttu-id="4482d-139">単一行のサブルーチンの本体は、単一行のステートメントでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="4482d-139">The body of a single-line subroutine must be single-line statement.</span></span>

- <span data-ttu-id="4482d-140">単一行の関数およびサブルーチンには、 または`End Function``End Sub`ステートメントは含まれません。</span><span class="sxs-lookup"><span data-stu-id="4482d-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>

- <span data-ttu-id="4482d-141">`As`ラムダ式パラメーターのデータ型は、キーワードを使用して指定するか、パラメーターのデータ型を推論できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="4482d-142">すべてのパラメーターにデータ型を指定するか、またはすべて推論する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4482d-142">Either all parameters must have specified data types or all must be inferred.</span></span>

- <span data-ttu-id="4482d-143">`Optional`および`Paramarray`パラメーターは許可されません。</span><span class="sxs-lookup"><span data-stu-id="4482d-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>

- <span data-ttu-id="4482d-144">ジェネリック パラメーターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4482d-144">Generic parameters are not permitted.</span></span>

## <a name="async-lambdas"></a><span data-ttu-id="4482d-145">非同期ラムダ</span><span class="sxs-lookup"><span data-stu-id="4482d-145">Async Lambdas</span></span>

<span data-ttu-id="4482d-146">[非同期](../../../../visual-basic/language-reference/modifiers/async.md)演算子キーワードと[Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md)キーワードを使用すると、非同期処理を組み込んだラムダ式とステートメントを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="4482d-147">たとえば、次に示す Windows フォーム例には、非同期メソッド `ExampleMethodAsync`を呼び出して待機するイベント ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4482d-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="4482d-148">[AddHandler ステートメント](../../../../visual-basic/language-reference/statements/addhandler-statement.md)で非同期ラムダを使用して、同じイベント ハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="4482d-149">次の例に示すように、このハンドラーを追加するには、ラムダ パラメーター リストの前に `Async` 修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="4482d-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>

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

<span data-ttu-id="4482d-150">非同期メソッドの作成方法と使用方法の詳細については、「[非同期と Await を使用した非同期プログラミング](../../../../visual-basic/programming-guide/concepts/async/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4482d-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

## <a name="context"></a><span data-ttu-id="4482d-151">Context</span><span class="sxs-lookup"><span data-stu-id="4482d-151">Context</span></span>

<span data-ttu-id="4482d-152">ラムダ式は、そのコンテキストを定義されているスコープと共有します。</span><span class="sxs-lookup"><span data-stu-id="4482d-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="4482d-153">このオブジェクトには、包含スコープで記述されたコードと同じアクセス権があります。</span><span class="sxs-lookup"><span data-stu-id="4482d-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="4482d-154">これには、メンバー変数、関数とサブ、および`Me`パラメーター、および、そのスコープ内のローカル変数へのアクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4482d-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>

<span data-ttu-id="4482d-155">格納スコープ内のローカル変数およびパラメーターへのアクセスは、そのスコープの有効期間を超えて拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="4482d-156">ラムダ式を参照するデリゲートがガベージ コレクションで使用できない限り、元の環境の変数へのアクセスは保持されます。</span><span class="sxs-lookup"><span data-stu-id="4482d-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="4482d-157">次の例では、ラム`target`ダ式`playTheGame`が`makeTheGame`定義されているメソッドに対して変数がローカルになります。</span><span class="sxs-lookup"><span data-stu-id="4482d-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="4482d-158">返されたラムダ式は、`takeAGuess`に`Main`割り当てられ、依然としてローカル変数`target`にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4482d-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

<span data-ttu-id="4482d-159">入れ子になったラムダ式のアクセス権の範囲を示す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4482d-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="4482d-160">返されたラムダ式が`Main``aDel`から実行されると、 は、次の要素にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4482d-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>

- <span data-ttu-id="4482d-161">定義されているクラスのフィールド。`aField`</span><span class="sxs-lookup"><span data-stu-id="4482d-161">A field of the class in which it is defined: `aField`</span></span>

- <span data-ttu-id="4482d-162">定義されているクラスのプロパティ。`aProp`</span><span class="sxs-lookup"><span data-stu-id="4482d-162">A property of the class in which it is defined: `aProp`</span></span>

- <span data-ttu-id="4482d-163">定義されているメソッド`functionWithNestedLambda`のパラメータ:`level1`</span><span class="sxs-lookup"><span data-stu-id="4482d-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>

- <span data-ttu-id="4482d-164">のローカル変数`functionWithNestedLambda`。`localVar`</span><span class="sxs-lookup"><span data-stu-id="4482d-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>

- <span data-ttu-id="4482d-165">入れ子になっているラムダ式のパラメータ。`level2`</span><span class="sxs-lookup"><span data-stu-id="4482d-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="4482d-166">デリゲート型への変換</span><span class="sxs-lookup"><span data-stu-id="4482d-166">Converting to a Delegate Type</span></span>

<span data-ttu-id="4482d-167">ラムダ式は、互換性のあるデリゲート型に暗黙的に変換できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="4482d-168">互換性の一般的な要件については、「[デリゲート変換の緩和](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4482d-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="4482d-169">たとえば、次のコード例は、暗黙的にデリゲートシグネチャに`Func(Of Integer, Boolean)`変換するラムダ式または一致するデリゲート シグネチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="4482d-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

<span data-ttu-id="4482d-170">次のコード例は、暗黙的に変換するラムダ式`Sub(Of Double, String, Double)`、または一致するデリゲート シグネチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="4482d-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

<span data-ttu-id="4482d-171">ラムダ式をデリゲートに割り当てたり、プロシージャに引数として渡したりするときには、パラメーター名を指定できますが、そのデータ型を省略して、デリゲートから型を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4482d-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>

## <a name="examples"></a><span data-ttu-id="4482d-172">例</span><span class="sxs-lookup"><span data-stu-id="4482d-172">Examples</span></span>

- <span data-ttu-id="4482d-173">次の例では、null 許容値`True`型引数に値が割り当てられている場合、およびその`False`値が の場合`Nothing`に返すラムダ式を定義します。</span><span class="sxs-lookup"><span data-stu-id="4482d-173">The following example defines a lambda expression that returns `True` if the nullable value type argument has an assigned value, and `False` if its value is `Nothing`.</span></span>

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- <span data-ttu-id="4482d-174">次の例では、配列の最後の要素のインデックスを返すラムダ式を定義します。</span><span class="sxs-lookup"><span data-stu-id="4482d-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="4482d-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="4482d-175">See also</span></span>

- [<span data-ttu-id="4482d-176">プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4482d-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4482d-177">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="4482d-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4482d-178">デリゲート</span><span class="sxs-lookup"><span data-stu-id="4482d-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="4482d-179">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="4482d-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="4482d-180">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="4482d-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4482d-181">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="4482d-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="4482d-182">方法 : Visual Basic でプロシージャを別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="4482d-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="4482d-183">方法: ラムダ式を作成する</span><span class="sxs-lookup"><span data-stu-id="4482d-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="4482d-184">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="4482d-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
