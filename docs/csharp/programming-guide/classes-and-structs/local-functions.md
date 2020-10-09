---
title: ローカル関数 - C# プログラミング ガイド
description: C# のローカル関数は、別のメンバーの入れ子になっているプライベート メソッドであり、その親メンバーから呼び出すことができます。
ms.date: 10/02/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: a91995757048c8c54253d7f4b923d5194f69bc7b
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654921"
---
# <a name="local-functions-c-programming-guide"></a><span data-ttu-id="e5191-103">ローカル関数 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="e5191-103">Local functions (C# Programming Guide)</span></span>

<span data-ttu-id="e5191-104">C# 7.0 以降、C# では*ローカル関数*がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e5191-104">Starting with C# 7.0, C# supports *local functions*.</span></span> <span data-ttu-id="e5191-105">ローカル関数は、別のメンバーの入れ子になっているタイプのプライベート メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e5191-105">Local functions are private methods of a type that are nested in another member.</span></span> <span data-ttu-id="e5191-106">親メンバーからのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-106">They can only be called from their containing member.</span></span> <span data-ttu-id="e5191-107">ローカル関数は次の要素で宣言し、呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-107">Local functions can be declared in and called from:</span></span>

- <span data-ttu-id="e5191-108">メソッド (特に反復子メソッドと非同期メソッド)</span><span class="sxs-lookup"><span data-stu-id="e5191-108">Methods, especially iterator methods and async methods</span></span>
- <span data-ttu-id="e5191-109">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="e5191-109">Constructors</span></span>
- <span data-ttu-id="e5191-110">プロパティ アクセサー</span><span class="sxs-lookup"><span data-stu-id="e5191-110">Property accessors</span></span>
- <span data-ttu-id="e5191-111">イベント アクセサー</span><span class="sxs-lookup"><span data-stu-id="e5191-111">Event accessors</span></span>
- <span data-ttu-id="e5191-112">匿名メソッド</span><span class="sxs-lookup"><span data-stu-id="e5191-112">Anonymous methods</span></span>
- <span data-ttu-id="e5191-113">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="e5191-113">Lambda expressions</span></span>
- <span data-ttu-id="e5191-114">ファイナライザー</span><span class="sxs-lookup"><span data-stu-id="e5191-114">Finalizers</span></span>
- <span data-ttu-id="e5191-115">その他のローカル関数</span><span class="sxs-lookup"><span data-stu-id="e5191-115">Other local functions</span></span>

<span data-ttu-id="e5191-116">ただし、ローカル関数は、式形式のメンバーの内部では宣言できません。</span><span class="sxs-lookup"><span data-stu-id="e5191-116">However, local functions can't be declared inside an expression-bodied member.</span></span>

> [!NOTE]
> <span data-ttu-id="e5191-117">場合によっては、ラムダ式を使用して、ローカル関数でもサポートされている機能を実装できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-117">In some cases, you can use a lambda expression to implement functionality also supported by a local function.</span></span> <span data-ttu-id="e5191-118">比較については、「[ローカル関数とラムダ式の比較](#local-functions-vs-lambda-expressions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5191-118">For a comparison, see [Local functions vs. lambda expressions](#local-functions-vs-lambda-expressions).</span></span>

<span data-ttu-id="e5191-119">ローカル関数を使用すると、コードの意図が明確になります。</span><span class="sxs-lookup"><span data-stu-id="e5191-119">Local functions make the intent of your code clear.</span></span> <span data-ttu-id="e5191-120">コードを見た人は、メソッドが親メソッドによってのみ呼び出し可能であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e5191-120">Anyone reading your code can see that the method is not callable except by the containing method.</span></span> <span data-ttu-id="e5191-121">また、チーム プロジェクトの場合は、別の開発者がクラスや構造体の別の場所から誤ってメソッドを直接呼び出すことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="e5191-121">For team projects, they also make it impossible for another developer to mistakenly call the method directly from elsewhere in the class or struct.</span></span>

## <a name="local-function-syntax"></a><span data-ttu-id="e5191-122">ローカル関数の構文</span><span class="sxs-lookup"><span data-stu-id="e5191-122">Local function syntax</span></span>

<span data-ttu-id="e5191-123">ローカル関数は、親メンバーの内側に、入れ子になったメソッドとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-123">A local function is defined as a nested method inside a containing member.</span></span> <span data-ttu-id="e5191-124">その定義の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5191-124">Its definition has the following syntax:</span></span>

```csharp
<modifiers> <return-type> <method-name> <parameter-list>
```

<span data-ttu-id="e5191-125">ローカル関数と共に次の修飾子を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-125">You can use the following modifiers with a local function:</span></span>

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- <span data-ttu-id="e5191-126">[`static`](../../language-reference/keywords/static.md) (C# 8.0 以降)。</span><span class="sxs-lookup"><span data-stu-id="e5191-126">[`static`](../../language-reference/keywords/static.md) (in C# 8.0 and later).</span></span> <span data-ttu-id="e5191-127">静的なローカル関数では、ローカル変数やインスタンスの状態をキャプチャすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e5191-127">A static local function can't capture local variables or instance state.</span></span>
- <span data-ttu-id="e5191-128">[`extern`](../../language-reference/keywords/extern.md) (C# 9.0 以降)。</span><span class="sxs-lookup"><span data-stu-id="e5191-128">[`extern`](../../language-reference/keywords/extern.md) (in C# 9.0 and later).</span></span> <span data-ttu-id="e5191-129">外部ローカル関数は `static` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5191-129">An external local function must be `static`.</span></span>

<span data-ttu-id="e5191-130">メソッドのパラメーターを含め、親メンバー内で定義されているすべてのローカル変数は、非静的ローカル関数からアクセス可能です。</span><span class="sxs-lookup"><span data-stu-id="e5191-130">All local variables that are defined in the containing member, including its method parameters, are accessible in a non-static local function.</span></span>

<span data-ttu-id="e5191-131">メソッド定義とは異なり、ローカル関数の定義にメンバー アクセス修飾子を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e5191-131">Unlike a method definition, a local function definition cannot include the member access modifier.</span></span> <span data-ttu-id="e5191-132">すべてのローカル関数はプライベートであるため、`private` キーワードなどのアクセス修飾子が含まれていると、コンパイラ エラー CS0106 "修飾子 'private' がこの項目に対して有効ではありません" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-132">Because all local functions are private, including an access modifier, such as the `private` keyword, generates compiler error CS0106, "The modifier 'private' is not valid for this item."</span></span>

<span data-ttu-id="e5191-133">さらに、ローカル関数またはローカル関数のパラメーターと型パラメーターには属性を適用できません。</span><span class="sxs-lookup"><span data-stu-id="e5191-133">In addition, attributes can't be applied to the local function or to its parameters and type parameters.</span></span>

<span data-ttu-id="e5191-134">次の例は、`GetText` というメソッドに対してプライベートな `AppendPathSeparator` というローカル関数を定義しています。</span><span class="sxs-lookup"><span data-stu-id="e5191-134">The following example defines a local function named `AppendPathSeparator` that is private to a method named `GetText`:</span></span>

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a><span data-ttu-id="e5191-135">ローカル関数と例外</span><span class="sxs-lookup"><span data-stu-id="e5191-135">Local functions and exceptions</span></span>

<span data-ttu-id="e5191-136">ローカル関数の便利な機能の 1 つは、例外を直ちに検出できることです。</span><span class="sxs-lookup"><span data-stu-id="e5191-136">One of the useful features of local functions is that they can allow exceptions to surface immediately.</span></span> <span data-ttu-id="e5191-137">メソッド反復子の場合、例外は返されたシーケンスを列挙する時点でしか検出されず、反復子を取得した時点では検出されません。</span><span class="sxs-lookup"><span data-stu-id="e5191-137">For method iterators, exceptions are surfaced only when the returned sequence is enumerated, and not when the iterator is retrieved.</span></span> <span data-ttu-id="e5191-138">非同期メソッドの場合、非同期メソッドでスローされた例外は、タスクの戻りを待機中に検出されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-138">For async methods, any exceptions thrown in an async method are observed when the returned task is awaited.</span></span>

<span data-ttu-id="e5191-139">次の例は、指定した範囲にある奇数を列挙する `OddSequence` メソッドを定義しています。</span><span class="sxs-lookup"><span data-stu-id="e5191-139">The following example defines an `OddSequence` method that enumerates odd numbers between a specified range.</span></span> <span data-ttu-id="e5191-140">100 より大きい数値を `OddSequence` 列挙子メソッドに渡しているため、メソッドは <xref:System.ArgumentOutOfRangeException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="e5191-140">Because it passes a number greater than 100 to the `OddSequence` enumerator method, the method throws an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="e5191-141">この例の出力が示すように、例外は列挙子を取得したときではなく、数値を反復処理した時点でのみ検出されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-141">As the output from the example shows, the exception surfaces only when you iterate the numbers, and not when you retrieve the enumerator.</span></span>

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

<span data-ttu-id="e5191-142">これに対して、次の例に示すようにローカル関数から列挙子を返すことによって、列挙子を取得する前の検証を実行する時点で例外をスローできます。</span><span class="sxs-lookup"><span data-stu-id="e5191-142">Instead, you can throw an exception when performing validation and before retrieving the iterator by returning the iterator from a local function, as the following example shows.</span></span>

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

<span data-ttu-id="e5191-143">ローカル関数は、非同期操作の外部で例外を処理するために同様の方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-143">Local functions can be used in a similar way to handle exceptions outside of the asynchronous operation.</span></span> <span data-ttu-id="e5191-144">通常、非同期メソッドでスローされた例外では <xref:System.AggregateException> の内部例外を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5191-144">Ordinarily, exceptions thrown in async method require that you examine the inner exceptions of an <xref:System.AggregateException>.</span></span> <span data-ttu-id="e5191-145">ローカル関数を使用すると、コードを迅速に失敗させ (Fail Fast)、例外のスローと検出の両方を同時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-145">Local functions allow your code to fail fast and allow your exception to be both thrown and observed synchronously.</span></span>

<span data-ttu-id="e5191-146">次の例は、`GetMultipleAsync` という非同期メソッドを使用して、指定した秒数だけ一時停止した後、その秒数のランダムな倍数である値を返します。</span><span class="sxs-lookup"><span data-stu-id="e5191-146">The following example uses an asynchronous method named `GetMultipleAsync` to pause for a specified number of seconds and return a value that is a random multiple of that number of seconds.</span></span> <span data-ttu-id="e5191-147">遅延の最大値は 5 秒です。値が 5 より大きい場合は <xref:System.ArgumentOutOfRangeException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="e5191-147">The maximum delay is 5 seconds; an <xref:System.ArgumentOutOfRangeException> results if the value is greater than 5.</span></span> <span data-ttu-id="e5191-148">次の例に示すように、`GetMultipleAsync` メソッドに渡された値が 6 の場合にスローされる例外は、`GetMultipleAsync` メソッドの実行開始後、<xref:System.AggregateException> にラップされます。</span><span class="sxs-lookup"><span data-stu-id="e5191-148">As the following example shows, the exception that is thrown when a value of 6 is passed to the `GetMultipleAsync` method is wrapped in an <xref:System.AggregateException> after the `GetMultipleAsync` method begins execution.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

<span data-ttu-id="e5191-149">メソッド反復子と同様、非同期メソッドを呼び出す前に検証を実行するように、この例のコードをリファクターすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-149">As we did with the method iterator, we can refactor the code from this example to perform the validation before calling the asynchronous method.</span></span> <span data-ttu-id="e5191-150">次の例の出力に示されているように、<xref:System.ArgumentOutOfRangeException> は <xref:System.AggregateException> にラップされていません。</span><span class="sxs-lookup"><span data-stu-id="e5191-150">As the output from the following example shows, the <xref:System.ArgumentOutOfRangeException> is not wrapped in a <xref:System.AggregateException>.</span></span>

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="local-functions-vs-lambda-expressions"></a><span data-ttu-id="e5191-151">ローカル関数とラムダ式の比較</span><span class="sxs-lookup"><span data-stu-id="e5191-151">Local functions vs. lambda expressions</span></span>

<span data-ttu-id="e5191-152">一見したところ、ローカル関数と[ラムダ式](../../language-reference/operators/lambda-expressions.md)は、非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="e5191-152">At first glance, local functions and [lambda expressions](../../language-reference/operators/lambda-expressions.md) are very similar.</span></span> <span data-ttu-id="e5191-153">多くの場合、ラムダ式とローカル関数の使用のどちらを選択するかは、スタイルと個人的な好みの問題です。</span><span class="sxs-lookup"><span data-stu-id="e5191-153">In many cases, the choice between using lambda expressions and local functions is a matter of style and personal preference.</span></span> <span data-ttu-id="e5191-154">ただし、どちらか一方を使用できる場合、認識しておくべき実質的な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="e5191-154">However, there are real differences in where you can use one or the other that you should be aware of.</span></span>

<span data-ttu-id="e5191-155">階乗アルゴリズムのローカル関数とラムダ式の実装の違いについて見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="e5191-155">Let's examine the differences between the local function and lambda expression implementations of the factorial algorithm.</span></span> <span data-ttu-id="e5191-156">まずは、ローカル関数を使用するバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e5191-156">First the version using a local function:</span></span>

[!code-csharp[LocalFunctionFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

<span data-ttu-id="e5191-157">ラムダ式を使用するバージョンの実装と比較します。</span><span class="sxs-lookup"><span data-stu-id="e5191-157">Contrast that implementation with a version that uses lambda expressions:</span></span>

[!code-csharp[26_LambdaFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

<span data-ttu-id="e5191-158">ローカル関数には名前があります。</span><span class="sxs-lookup"><span data-stu-id="e5191-158">The local functions have names.</span></span> <span data-ttu-id="e5191-159">ラムダ式は匿名メソッドであり、`Func` または `Action` 型である変数に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e5191-159">The lambda expressions are anonymous methods that are assigned to variables that are `Func` or `Action` types.</span></span> <span data-ttu-id="e5191-160">ローカル関数を宣言する場合、引数の型と戻り値の型は関数宣言の一部となります。</span><span class="sxs-lookup"><span data-stu-id="e5191-160">When you declare a local function, the argument types and return type are part of the function declaration.</span></span> <span data-ttu-id="e5191-161">引数の型と戻り値の型は、ラムダ式の本体の一部ではなく、ラムダ式の変数型宣言の一部となります。</span><span class="sxs-lookup"><span data-stu-id="e5191-161">Instead of being part of the body of the lambda expression, the argument types and return type are part of the lambda expression's variable type declaration.</span></span> <span data-ttu-id="e5191-162">これら 2 つの違いにより、コードがわかりやすくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5191-162">Those two differences may result in clearer code.</span></span>

<span data-ttu-id="e5191-163">ローカル関数には、ラムダ式とは異なる確実な代入のルールがあります。</span><span class="sxs-lookup"><span data-stu-id="e5191-163">Local functions have different rules for definite assignment than lambda expressions.</span></span> <span data-ttu-id="e5191-164">ローカル関数宣言は、スコープ内にある任意のコードの場所から参照できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-164">A local function declaration can be referenced from any code location where it is in scope.</span></span> <span data-ttu-id="e5191-165">ラムダ式はデリゲート変数に割り当てないと、アクセスできません (ラムダ式を参照するデリゲートを通じて呼び出すこともできません)。</span><span class="sxs-lookup"><span data-stu-id="e5191-165">A lambda expression must be assigned to a delegate variable before it can be accessed (or called through the delegate referencing the lambda expression).</span></span> <span data-ttu-id="e5191-166">ラムダ式を使用したバージョンでは、ラムダ式 `nthFactorial` を定義する前に、宣言と初期化を行う必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5191-166">Notice that the version using the lambda expression must declare and initialize the lambda expression `nthFactorial` before defining it.</span></span> <span data-ttu-id="e5191-167">その手順を踏まないと、`nthFactorial` の割り当て前に参照することによるコンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e5191-167">Not doing so results in a compile time error for referencing `nthFactorial` before assigning it.</span></span> <span data-ttu-id="e5191-168">これらの違いは、再帰的なアルゴリズムの作成はローカル関数を使用する方が簡単であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e5191-168">These differences mean that recursive algorithms are easier to create using local functions.</span></span> <span data-ttu-id="e5191-169">自身を呼び出すローカル関数を宣言して定義することができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-169">You can declare and define a local function that calls itself.</span></span> <span data-ttu-id="e5191-170">ラムダ式は宣言して、既定値を割り当てないと、同じラムダ式を参照する本体に再割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="e5191-170">Lambda expressions must be declared, and assigned a default value before they can be re-assigned to a body that references the same lambda expression.</span></span>

<span data-ttu-id="e5191-171">確実な代入ルールは、ローカル関数またはラムダ式でキャプチャされる変数にも影響します。</span><span class="sxs-lookup"><span data-stu-id="e5191-171">Definite assignment rules also affect any variables that are captured by the local function or lambda expression.</span></span> <span data-ttu-id="e5191-172">ローカル関数とラムダ式の両方のルールでは、ローカル関数またはラムダ式がデリゲートに変換された時点で、キャプチャされた変数が確実に代入されることが要求されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-172">Both local functions and lambda expression rules demand that any captured variables are definitely assigned at the point when the local function or lambda expression is converted to a delegate.</span></span> <span data-ttu-id="e5191-173">違いは、ラムダ式が宣言時にデリゲートに変換されることです。</span><span class="sxs-lookup"><span data-stu-id="e5191-173">The difference is that lambda expressions are converted to delegates when they are declared.</span></span> <span data-ttu-id="e5191-174">ローカル関数は、デリゲートとして使用される場合にのみ、デリゲートに変換されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-174">Local functions are converted to delegates only when used as a delegate.</span></span> <span data-ttu-id="e5191-175">ローカル関数を宣言し、メソッドのように呼び出して参照のみを行う場合は、デリゲートに変換されません。</span><span class="sxs-lookup"><span data-stu-id="e5191-175">If you declare a local function and only reference it by calling it like a method, it will not be converted to a delegate.</span></span> <span data-ttu-id="e5191-176">このルールでは、外側のスコープ内の便利な場所でローカル関数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-176">That rule enables you to declare a local function at any convenient location in its enclosing scope.</span></span> <span data-ttu-id="e5191-177">親メソッドの末尾 (すべての return ステートメントの後) にローカル関数を宣言するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="e5191-177">It's common to declare local functions at the end of the parent method, after any return statements.</span></span>

<span data-ttu-id="e5191-178">3 つ目は、コンパイラは静的分析を実行できることです。これにより、ローカル関数で外側のスコープ内のキャプチャされた変数を確実に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e5191-178">Third, the compiler can perform static analysis that enables local functions to definitely assign captured variables in the enclosing scope.</span></span> <span data-ttu-id="e5191-179">次の例について考えます。</span><span class="sxs-lookup"><span data-stu-id="e5191-179">Consider this example:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="e5191-180">コンパイラは、呼び出し時に `LocalFunction` が `y` を確実に割り当てるかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-180">The compiler can determine that `LocalFunction` definitely assigns `y` when called.</span></span> <span data-ttu-id="e5191-181">`return` ステートメントの前に `LocalFunction` が呼び出されるため、`y` は `return` ステートメントで確実に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e5191-181">Because `LocalFunction` is called before the `return` statement, `y` is definitely assigned at the `return` statement.</span></span>

<span data-ttu-id="e5191-182">分析例を使用する分析では、4 つ目の違いを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-182">The analysis that enables the example analysis enables the fourth difference.</span></span> <span data-ttu-id="e5191-183">ローカル関数では、その使用に応じて、ラムダ式では常に必要なヒープの割り当てを回避できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-183">Depending on their use, local functions can avoid heap allocations that are always necessary for lambda expressions.</span></span> <span data-ttu-id="e5191-184">ローカル関数がデリゲートに変換されておらず、ローカル関数でキャプチャされたいずれの変数も、デリゲートに変換された他のラムダやローカル関数でキャプチャされていない場合、コンパイラはヒープの割り当てを回避できます。</span><span class="sxs-lookup"><span data-stu-id="e5191-184">If a local function is never converted to a delegate, and none of the variables captured by the local function is captured by other lambdas or local functions that are converted to delegates, the compiler can avoid heap allocations.</span></span>

<span data-ttu-id="e5191-185">次の非同期の例について考えます。</span><span class="sxs-lookup"><span data-stu-id="e5191-185">Consider this async example:</span></span>

[!code-csharp[TaskLambdaExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

<span data-ttu-id="e5191-186">このラムダ式のクロージャに含まれるのは、`address`、`index`、および `name` 変数です。</span><span class="sxs-lookup"><span data-stu-id="e5191-186">The closure for this lambda expression contains the `address`, `index` and `name` variables.</span></span> <span data-ttu-id="e5191-187">ローカル関数の場合、クロージャを実装するオブジェクトが `struct` になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5191-187">In the case of local functions, the object that implements the closure may be a `struct` type.</span></span> <span data-ttu-id="e5191-188">その構造体型はローカル関数に参照によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="e5191-188">That struct type would be passed by reference to the local function.</span></span> <span data-ttu-id="e5191-189">この実装の違いにより、割り当てが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="e5191-189">This difference in implementation would save on an allocation.</span></span>

<span data-ttu-id="e5191-190">ラムダ式に必要なインスタンス化では、余分なメモリの割り当てが必要となり、タイム クリティカルなコード パスに影響を与えるパフォーマンス因子となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e5191-190">The instantiation necessary for lambda expressions means extra memory allocations, which may be a performance factor in time-critical code paths.</span></span> <span data-ttu-id="e5191-191">ローカル関数では、このオーバーヘッドは発生しません。</span><span class="sxs-lookup"><span data-stu-id="e5191-191">Local functions do not incur this overhead.</span></span> <span data-ttu-id="e5191-192">上記の例では、ローカル関数のバージョンは、ラムダ式のバージョンよりも割り当てが 2 つ少なくなっています。</span><span class="sxs-lookup"><span data-stu-id="e5191-192">In the example above, the local functions version has 2 fewer allocations than the lambda expression version.</span></span>

> [!NOTE]
> <span data-ttu-id="e5191-193">このメソッドのローカル関数と同等のものも、同じクロージャのクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5191-193">The local function equivalent of this method also uses a class for the closure.</span></span> <span data-ttu-id="e5191-194">ローカル関数のクロージャが `class` として実装される場合でも、実装の詳細が `struct` である場合でも同様です。</span><span class="sxs-lookup"><span data-stu-id="e5191-194">Whether the closure for a local function is implemented as a `class` or a `struct` is an implementation detail.</span></span> <span data-ttu-id="e5191-195">ローカル関数は `struct` を使用する場合がありますが、ラムダは常に `class` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5191-195">A local function may use a `struct` whereas a lambda will always use a `class`.</span></span>

[!code-csharp[TaskLocalFunctionExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="e5191-196">この例では説明しませんが、最後の 1 つの利点は値のシーケンスを生成するために `yield return` 構文を使用して、ローカル関数を反復子として実装できることです。</span><span class="sxs-lookup"><span data-stu-id="e5191-196">One final advantage not demonstrated in this sample is that local functions can be implemented as iterators, using the `yield return` syntax to produce a sequence of values.</span></span> <span data-ttu-id="e5191-197">ラムダ式では `yield return` ステートメントは許可されません。</span><span class="sxs-lookup"><span data-stu-id="e5191-197">The `yield return` statement is not allowed in lambda expressions.</span></span>

<span data-ttu-id="e5191-198">ローカル関数はラムダ式より冗長に思えるかもしれませんが、実際にはさまざまな目的に役立ち、用途もさまざまです。</span><span class="sxs-lookup"><span data-stu-id="e5191-198">While local functions may seem redundant to lambda expressions, they actually serve different purposes and have different uses.</span></span> <span data-ttu-id="e5191-199">ローカル関数は、別のメソッドのコンテキストからのみ呼び出される関数を記述する場合に、より効率が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e5191-199">Local functions are more efficient for the case when you want to write a function that is called only from the context of another method.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5191-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5191-200">See also</span></span>

- [<span data-ttu-id="e5191-201">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5191-201">Methods</span></span>](methods.md)
