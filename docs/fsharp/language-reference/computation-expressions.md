---
title: コンピュテーション式
description: 制御フローの構成体とバインディングを使用してシーケンス処理および結合できる、F# で計算を記述するための便利な構文を作成する方法について説明します。
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401083"
---
# <a name="computation-expressions"></a><span data-ttu-id="54db7-103">コンピュテーション式</span><span class="sxs-lookup"><span data-stu-id="54db7-103">Computation Expressions</span></span>

<span data-ttu-id="54db7-104">F# の計算式は、制御フローの構成体とバインディングを使用してシーケンス処理および結合できる計算を記述するための便利な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="54db7-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="54db7-105">計算式の種類に応じて、モナド、モノイド、モナド変圧器、および適用的なファンクタを表現する方法として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="54db7-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="54db7-106">しかし、他の言語 (Haskell の*記述*など) とは異なり、それらは単一の抽象化に結び付けられておらず、便利で状況に応じて構文を実行するためにマクロやその他の形のメタプログラミングに依存しません。</span><span class="sxs-lookup"><span data-stu-id="54db7-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="54db7-107">概要</span><span class="sxs-lookup"><span data-stu-id="54db7-107">Overview</span></span>

<span data-ttu-id="54db7-108">計算には多くの形式があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-108">Computations can take many forms.</span></span> <span data-ttu-id="54db7-109">最も一般的な計算形式はシングルスレッド実行であり、これは理解しやすく、変更が容易です。</span><span class="sxs-lookup"><span data-stu-id="54db7-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="54db7-110">ただし、すべての形式の計算がシングルスレッド実行ほど簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="54db7-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="54db7-111">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="54db7-111">Some examples include:</span></span>

- <span data-ttu-id="54db7-112">非決定論的計算</span><span class="sxs-lookup"><span data-stu-id="54db7-112">Non-deterministic computations</span></span>
- <span data-ttu-id="54db7-113">非同期計算</span><span class="sxs-lookup"><span data-stu-id="54db7-113">Asynchronous computations</span></span>
- <span data-ttu-id="54db7-114">効果のある計算</span><span class="sxs-lookup"><span data-stu-id="54db7-114">Effectful computations</span></span>
- <span data-ttu-id="54db7-115">生成計算</span><span class="sxs-lookup"><span data-stu-id="54db7-115">Generative computations</span></span>

<span data-ttu-id="54db7-116">より一般的には、*アプリケーションの特定の*部分で実行する必要がある状況依存の計算があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="54db7-117">コンテキスト依存型コードの記述は、抽象化せずに特定のコンテキストの外部で計算を「リーク」し、そうすることを防ぐために簡単に行われるため、困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="54db7-118">これらの抽象化は、多くの場合、自分で記述するのが難しいので、F# には **、いわゆる計算式**を行うための一般的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="54db7-119">計算式は、コンテキスト依存計算をエンコードするための統一された構文と抽象化モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="54db7-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="54db7-120">すべての計算式は *、ビルダー*型によって裏付けられます。</span><span class="sxs-lookup"><span data-stu-id="54db7-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="54db7-121">ビルダーの型は、計算式で使用できる操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="54db7-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="54db7-122">カスタム[計算式の作成方法を示す「新しいタイプの計算式](computation-expressions.md#creating-a-new-type-of-computation-expression)の作成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54db7-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="54db7-123">構文の概要</span><span class="sxs-lookup"><span data-stu-id="54db7-123">Syntax overview</span></span>

<span data-ttu-id="54db7-124">すべての計算式の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="54db7-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="54db7-125">ここで`builder-expr`、計算式を定義するビルダー型の名前であり`cexper`、計算式の式本体です。</span><span class="sxs-lookup"><span data-stu-id="54db7-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="54db7-126">たとえば、`async`計算式コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="54db7-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="54db7-127">前の例に示すように、計算式内で使用できる特別な追加構文があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="54db7-128">計算式では、次の式フォームが可能です。</span><span class="sxs-lookup"><span data-stu-id="54db7-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="54db7-129">これらのキーワード、およびその他の標準 F# キーワードは、バッキング ビルダーの型で定義されている場合にのみ、計算式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="54db7-130">唯一の例外は、`match!`それ自体が結果にパターンマッチ`let!`を続けて使用するための構文砂糖です。</span><span class="sxs-lookup"><span data-stu-id="54db7-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="54db7-131">ビルダー型は、計算式のフラグメントを結合する方法を制御する特別なメソッドを定義するオブジェクトです。つまり、そのメソッドは、計算式の動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="54db7-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="54db7-132">ビルダー クラスを記述するもう 1 つの方法は、ループやバインドなど、多くの F# 構造体の操作をカスタマイズできるということです。</span><span class="sxs-lookup"><span data-stu-id="54db7-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="54db7-133">キーワード`let!`は、別の計算式の呼び出しの結果を名前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="54db7-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="54db7-134">を使用`let`して計算式に呼び出しをバインドすると、計算式の結果は得られない。</span><span class="sxs-lookup"><span data-stu-id="54db7-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="54db7-135">代わりに、*未実現*呼び出しの値をその計算式にバインドします。</span><span class="sxs-lookup"><span data-stu-id="54db7-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="54db7-136">結果`let!`にバインドするために使用します。</span><span class="sxs-lookup"><span data-stu-id="54db7-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="54db7-137">`let!`は、ビルダー型`Bind(x, f)`のメンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="54db7-138">キーワード`do!`は、-like 型 (ビルダーの`unit`メンバーによって定義される) を`Zero`返す計算式を呼び出す場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="54db7-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="54db7-139">[非同期ワークフロー](asynchronous-workflows.md)の場合、このタイプは`Async<unit>`です。</span><span class="sxs-lookup"><span data-stu-id="54db7-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="54db7-140">その他の計算式の場合、型は`CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="54db7-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="54db7-141">`do!`は、ビルダー型`Bind(x, f)`のメンバーによって定義されます。 `f` `unit`</span><span class="sxs-lookup"><span data-stu-id="54db7-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="54db7-142">キーワード`yield`は、計算式から値を返し、それをとして使用するためのキーワードです<xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="54db7-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="54db7-143">ほとんどの場合、呼び出し元によって省略できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="54db7-144">省略`yield`する最も一般的な方法は`->`、演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="54db7-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="54db7-145">多くの異なる値を生成する可能性があるより複雑な式、およびおそらく条件付きで、キーワードを省略するだけで、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="54db7-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

<span data-ttu-id="54db7-146">[C#](../../csharp/language-reference/keywords/yield.md)の yield キーワードと同様に、計算式の各要素は、反復処理のたびに返されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="54db7-147">`yield`は、ビルダー型`Yield(x)``x`のメンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="54db7-148">キーワード`yield!`は、計算式から値のコレクションをフラット化するためのものです。</span><span class="sxs-lookup"><span data-stu-id="54db7-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

<span data-ttu-id="54db7-149">評価されると、 によって`yield!`呼び出される計算式の項目が 1 つずつ戻され、結果が平坦化されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="54db7-150">`yield!`は、値の`YieldFrom(x)`コレクション`x`であるビルダー型のメンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="54db7-151">と`yield`は`yield!`異なり、 明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="54db7-152">その動作は、計算式では暗黙的ではありません。</span><span class="sxs-lookup"><span data-stu-id="54db7-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="54db7-153">この`return`キーワードは、計算式に対応する型の値をラップします。</span><span class="sxs-lookup"><span data-stu-id="54db7-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="54db7-154">を使用する`yield`計算式以外に、計算式を「完了」するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="54db7-155">`return`は、`x`ビルダー型`Return(x)`のメンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="54db7-156">キーワード`return!`は、計算式の値を認識し、その結果、計算式に対応する型をラップします。</span><span class="sxs-lookup"><span data-stu-id="54db7-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="54db7-157">`return!`は、別の`ReturnFrom(x)`計算式である`x`ビルダー型のメンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="54db7-158">この`match!`キーワードを使用すると、別の計算式とパターン一致の呼び出しをインライン化できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="54db7-159">で`match!`計算式を呼び出すと、呼び出しの結果が`let!`.</span><span class="sxs-lookup"><span data-stu-id="54db7-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="54db7-160">これは、結果がオプションである計算式を呼び出すときによく使用[されます](options.md)。</span><span class="sxs-lookup"><span data-stu-id="54db7-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="54db7-161">組み込みの計算式</span><span class="sxs-lookup"><span data-stu-id="54db7-161">Built-in computation expressions</span></span>

<span data-ttu-id="54db7-162">F# コア ライブラリは、[シーケンス式](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[クエリ式](query-expressions.md)という 3 つの組み込みの計算式を定義します。</span><span class="sxs-lookup"><span data-stu-id="54db7-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="54db7-163">新しい型の計算式の作成</span><span class="sxs-lookup"><span data-stu-id="54db7-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="54db7-164">独自の計算式の特性を定義するには、ビルダー クラスを作成し、クラスに特定の特殊なメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="54db7-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="54db7-165">ビルダー クラスは、次の表に示すようにメソッドをオプションで定義できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="54db7-166">次の表は、ワークフロー ビルダー クラスで使用できるメソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="54db7-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="54db7-167">**Method**</span><span class="sxs-lookup"><span data-stu-id="54db7-167">**Method**</span></span>|<span data-ttu-id="54db7-168">**一般的な署名**</span><span class="sxs-lookup"><span data-stu-id="54db7-168">**Typical signature(s)**</span></span>|<span data-ttu-id="54db7-169">**説明**</span><span class="sxs-lookup"><span data-stu-id="54db7-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="54db7-170">計算式`let!`で`do!`呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="54db7-171">計算式を関数としてラップします。</span><span class="sxs-lookup"><span data-stu-id="54db7-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="54db7-172">計算式`return`で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="54db7-173">計算式`return!`で呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="54db7-174">`M<'T> -> M<'T>` または</span><span class="sxs-lookup"><span data-stu-id="54db7-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="54db7-175">計算式を実行します。</span><span class="sxs-lookup"><span data-stu-id="54db7-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="54db7-176">`M<'T> * M<'T> -> M<'T>` または</span><span class="sxs-lookup"><span data-stu-id="54db7-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="54db7-177">計算式のシーケンス処理に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="54db7-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` または</span><span class="sxs-lookup"><span data-stu-id="54db7-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="54db7-179">計算式`for...do`の式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="54db7-180">計算式`try...finally`の式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="54db7-181">計算式`try...with`の式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="54db7-182">計算式`use`のバインディングに対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="54db7-183">計算式`while...do`の式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="54db7-184">計算式`yield`の式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="54db7-185">計算式`yield!`の式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="54db7-186">計算式の`else`式の`if...then`空の分岐に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="54db7-187">計算式が引用符としてメンバーに`Run`渡されることを示します。</span><span class="sxs-lookup"><span data-stu-id="54db7-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="54db7-188">これは、計算のすべてのインスタンスを引用に変換します。</span><span class="sxs-lookup"><span data-stu-id="54db7-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="54db7-189">ビルダー クラスのメソッドの多くは、コンストラクト`M<'T>`を使用して返します。 `Async<'T>` `Seq<'T>`</span><span class="sxs-lookup"><span data-stu-id="54db7-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="54db7-190">これらのメソッドのシグネチャを使用すると、それらを結合して入れ子にして、ある構成要素から返されるワークフロー オブジェクトを次の構成要素に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="54db7-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="54db7-191">コンパイラは、計算式を解析するときに、前の表のメソッドと計算式のコードを使用して、その式を一連の入れ子になった関数呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="54db7-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="54db7-192">ネストされた式は次の形式です。</span><span class="sxs-lookup"><span data-stu-id="54db7-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="54db7-193">上記のコードでは、計算式ビルダー `Run` `Delay`クラスで定義されていない場合は、呼び出しと省略されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="54db7-194">ここで示す`{| cexpr |}`計算式の本体は、次の表に示す変換によって、ビルダー クラスのメソッドを含む呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="54db7-195">計算式`{| cexpr |}`は、F# 式であり、`expr``cexpr`計算式であるこれらの変換に従って再帰的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="54db7-196">式</span><span class="sxs-lookup"><span data-stu-id="54db7-196">Expression</span></span>|<span data-ttu-id="54db7-197">翻訳</span><span class="sxs-lookup"><span data-stu-id="54db7-197">Translation</span></span>|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

<span data-ttu-id="54db7-198">前の表では、`other-expr`表にリストされていない式について説明します。</span><span class="sxs-lookup"><span data-stu-id="54db7-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="54db7-199">ビルダー クラスは、すべてのメソッドを実装する必要はありませんし、前の表に示されているすべての変換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="54db7-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="54db7-200">実装されていないコンストラクトは、その型の計算式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="54db7-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="54db7-201">たとえば、計算式で`use`キーワードをサポートしたくない場合は、ビルダークラス`Use`の定義を省略できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="54db7-202">次のコード例は、計算を一度に 1 ステップずつ評価できる一連のステップとしてカプセル化する計算式を示しています。</span><span class="sxs-lookup"><span data-stu-id="54db7-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="54db7-203">判別共用体型 は`OkOrException`、これまで評価された式のエラー状態をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="54db7-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="54db7-204">このコードは、いくつかのビルダー メソッドの定型的な実装など、計算式で使用できるいくつかの一般的なパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="54db7-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> func value
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res ->
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally
            (whileLoop
                (fun () -> ie.MoveNext())
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step
```

<span data-ttu-id="54db7-205">計算式には基になる型があり、式が返されます。</span><span class="sxs-lookup"><span data-stu-id="54db7-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="54db7-206">基になる型は、計算結果または実行できる遅延計算を表す場合もあれば、何らかの種類のコレクションを反復処理する方法を提供する場合があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="54db7-207">前の例では、基になる型は **"最終的" でした**。</span><span class="sxs-lookup"><span data-stu-id="54db7-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="54db7-208">シーケンス式の場合、基になる型は<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="54db7-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="54db7-209">クエリ式の場合、基になる型は<xref:System.Linq.IQueryable?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="54db7-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="54db7-210">非同期ワークフローの場合、基になる型は[`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)です。</span><span class="sxs-lookup"><span data-stu-id="54db7-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="54db7-211">オブジェクト`Async`は、結果を計算するために実行される作業を表します。</span><span class="sxs-lookup"><span data-stu-id="54db7-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="54db7-212">たとえば、計算を実行[`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)して結果を返す呼び出しを行うとします。</span><span class="sxs-lookup"><span data-stu-id="54db7-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="54db7-213">カスタム操作</span><span class="sxs-lookup"><span data-stu-id="54db7-213">Custom Operations</span></span>

<span data-ttu-id="54db7-214">計算式にカスタム演算を定義し、カスタム演算を計算式の演算子として使用できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="54db7-215">たとえば、クエリ式にクエリ演算子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="54db7-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="54db7-216">カスタム操作を定義する場合は、計算式で Yield メソッドと For メソッドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="54db7-217">カスタム操作を定義するには、計算式のビルダー クラスに配置し、 を適用します[`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)。</span><span class="sxs-lookup"><span data-stu-id="54db7-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="54db7-218">この属性は、引数として文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="54db7-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="54db7-219">この名前は、計算式の中かっこの先頭にスコープが付けられます。</span><span class="sxs-lookup"><span data-stu-id="54db7-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="54db7-220">したがって、このブロックでは、カスタム操作と同じ名前の識別子を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="54db7-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="54db7-221">たとえば、クエリ式などの識別子を`all``last`使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="54db7-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="54db7-222">新しいカスタム操作で既存のビルダーを拡張する</span><span class="sxs-lookup"><span data-stu-id="54db7-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="54db7-223">既にビルダー クラスがある場合は、そのカスタム操作をこのビルダー クラスの外部から拡張できます。</span><span class="sxs-lookup"><span data-stu-id="54db7-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="54db7-224">拡張機能はモジュールで宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54db7-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="54db7-225">名前空間には、同じファイルと、型が定義されている同じ名前空間宣言グループ内以外の拡張メンバーを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="54db7-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="54db7-226">既存の`Microsoft.FSharp.Linq.QueryBuilder`クラスの拡張を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="54db7-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="54db7-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="54db7-227">See also</span></span>

- [<span data-ttu-id="54db7-228">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="54db7-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="54db7-229">非同期ワークフロー</span><span class="sxs-lookup"><span data-stu-id="54db7-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="54db7-230">シーケンス</span><span class="sxs-lookup"><span data-stu-id="54db7-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="54db7-231">クエリ式</span><span class="sxs-lookup"><span data-stu-id="54db7-231">Query Expressions</span></span>](query-expressions.md)
