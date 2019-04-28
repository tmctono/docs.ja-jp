---
title: コンピュテーション式
description: 計算を作成するための便利な構文を作成する方法についてF#、制御できることがシーケンス処理されたと結合を使用してフローの作成とバインドします。
ms.date: 03/15/2019
ms.openlocfilehash: 3c2abb5c6204309fc8d5215a53ce8af46c01d218
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766065"
---
# <a name="computation-expressions"></a><span data-ttu-id="e5b62-103">コンピュテーション式</span><span class="sxs-lookup"><span data-stu-id="e5b62-103">Computation Expressions</span></span>

<span data-ttu-id="e5b62-104">コンピュテーション式でF#シーケンス処理できるし、制御フローの作成とバインドを使用して結合する計算を作成するための便利な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="e5b62-105">コンピュテーション式の種類、に応じてには、モナド、monoids、monad トランスフォーマー、および適用したファンクターを表現する手段として、考えるができます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="e5b62-106">その他の言語とは異なり、(など*do 表記*Haskell で)、単一の抽象化に関連付けられていない、マクロやその他の形式に依存しないメタプログラミングを便利で状況依存の構文を実現します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="e5b62-107">概要</span><span class="sxs-lookup"><span data-stu-id="e5b62-107">Overview</span></span>

<span data-ttu-id="e5b62-108">計算には、多くの形式を取ります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-108">Computations can take many forms.</span></span> <span data-ttu-id="e5b62-109">計算の最も一般的な形式は、シングル スレッド実行は簡単に理解して変更できます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="e5b62-110">ただし、すべての形態の計算はシングル スレッド実行するように単純です。</span><span class="sxs-lookup"><span data-stu-id="e5b62-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="e5b62-111">次に、それらの例の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-111">Some examples include:</span></span>

* <span data-ttu-id="e5b62-112">非決定論的な計算</span><span class="sxs-lookup"><span data-stu-id="e5b62-112">Non-deterministic computations</span></span>
* <span data-ttu-id="e5b62-113">非同期計算</span><span class="sxs-lookup"><span data-stu-id="e5b62-113">Asynchronous computations</span></span>
* <span data-ttu-id="e5b62-114">Effectful 計算</span><span class="sxs-lookup"><span data-stu-id="e5b62-114">Effectful computations</span></span>
* <span data-ttu-id="e5b62-115">当初の計算</span><span class="sxs-lookup"><span data-stu-id="e5b62-115">Generative computations</span></span>

<span data-ttu-id="e5b62-116">一般的には、ある*状況に応じた*計算アプリケーションの特定の部分で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="e5b62-117">状況依存のコードの記述はそうことを防止するための抽象化せず、特定のコンテキストの外部で「リーク」計算を簡単に難しいことができます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="e5b62-118">これらの抽象化は、自分が F# には、実行する一般的な方法と呼ばれるものを記述する多くの場合、時間がかかります**コンピュテーション式**します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="e5b62-119">コンピュテーション式では、状況依存の計算をエンコードするための統一された構文と抽象化モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="e5b62-120">すべての計算式を支え、*ビルダー*型。</span><span class="sxs-lookup"><span data-stu-id="e5b62-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="e5b62-121">ビルダーの型は、そのコンピュテーション式で利用可能な操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="e5b62-122">参照してください[コンピュテーション式の新しい型を作成する](computation-expressions.md#creating-a-new-type-of-computation-expression)、カスタム計算式を作成する方法します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="e5b62-123">構文の概要</span><span class="sxs-lookup"><span data-stu-id="e5b62-123">Syntax overview</span></span>

<span data-ttu-id="e5b62-124">すべての計算式では、次の形式があります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="e5b62-125">場所`builder-expr`そのコンピュテーション式を定義するビルダー型の名前を指定および`cexper`コンピュテーション式の式の本文です。</span><span class="sxs-lookup"><span data-stu-id="e5b62-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="e5b62-126">たとえば、`async`式のコードを計算できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="e5b62-127">その他の特別な構文、コンピュテーション式内で使用可能な前の例で示すように。</span><span class="sxs-lookup"><span data-stu-id="e5b62-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="e5b62-128">次の式のフォームがコンピュテーション式と考えられます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="e5b62-129">これらのキーワードおよびその他の標準の F# キーワードの各はバッキング ビルダー型で定義されている場合のみコンピュテーション式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="e5b62-130">唯一の例外は`match!`、糖衣構文の使用は`let!`結果で、パターン一致の後にします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="e5b62-131">ビルダーの型はコンピュテーション式のフラグメントを結合する方法を制御する特殊なメソッドを定義するオブジェクトです。つまり、そのメソッドは、コンピュテーション式の動作方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="e5b62-132">ビルダー クラスを記述する別の方法は、多く F# の構成要素、ループやバインドなどの操作をカスタマイズできるには。</span><span class="sxs-lookup"><span data-stu-id="e5b62-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="e5b62-133">`let!`キーワード名に別のコンピュテーション式の呼び出しの結果をバインドします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="e5b62-134">コンピュテーション式での呼び出しをバインドするかどうかは`let`コンピュテーション式の結果は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e5b62-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="e5b62-135">代わりにバインドしてからの値、*実現されていない*そのコンピュテーション式を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="e5b62-136">使用`let!`結果にバインドします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="e5b62-137">`let!` `Bind(x, f)`ビルダー型のメンバー。</span><span class="sxs-lookup"><span data-stu-id="e5b62-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="e5b62-138">`do!`キーワードはコンピュテーション式の呼び出しを返します、 `unit`-などの型 (によって定義された、`Zero`ビルダーでのメンバー)。</span><span class="sxs-lookup"><span data-stu-id="e5b62-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="e5b62-139">[非同期ワークフロー](asynchronous-workflows.md)、この型は`Async<unit>`します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="e5b62-140">その他のコンピュテーション式の型がある可能性があります`CExpType<unit>`します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="e5b62-141">`do!` によって定義されます、`Bind(x, f)`ビルダーの型のメンバー、`f`生成、`unit`します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="e5b62-142">`yield`として利用できるように、コンピュテーション式から値を返すためのキーワードは、 <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="e5b62-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="e5b62-143">同様、 [yield キーワード (C#)](../../csharp/language-reference/keywords/yield.md)、それが反復処理にそのコンピュテーション式内の各要素が返されます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="e5b62-144">`yield` によって定義されます、`Yield(x)`ビルダーの型のメンバー、`x`はバックアップを生成する項目です。</span><span class="sxs-lookup"><span data-stu-id="e5b62-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="e5b62-145">`yield!`キーワードがコンピュテーション式から値のコレクションをフラット化するためには。</span><span class="sxs-lookup"><span data-stu-id="e5b62-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="e5b62-146">そのコンピュテーション式と呼ばれる評価されると、`yield!`がその項目になり、戻る 1 つずつ、結果をフラット化します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="e5b62-147">`yield!` によって定義されます、`YieldFrom(x)`ビルダーの型のメンバー、`x`値のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e5b62-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="e5b62-148">`return`キーワード コンピュテーション式に対応する型の値をラップします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="e5b62-149">使用して計算式とは別に`yield`コンピュテーション式を「完了」に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="e5b62-150">`return` によって定義されます、`Return(x)`ビルダーの型のメンバー、`x`をラップする項目。</span><span class="sxs-lookup"><span data-stu-id="e5b62-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="e5b62-151">`return!`キーワード コンピュテーション式の値を認識およびコンピュテーション式に対応する型でその結果をラップします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="e5b62-152">`return!` によって定義されます、`ReturnFrom(x)`ビルダーの型のメンバー、`x`別の計算式です。</span><span class="sxs-lookup"><span data-stu-id="e5b62-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="e5b62-153">以降でF#、4.5、`match!`キーワードを使用するインラインを別の計算式とパターン一致の結果への呼び出し。</span><span class="sxs-lookup"><span data-stu-id="e5b62-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="e5b62-154">計算式を呼び出すときに`match!`のような呼び出しの結果を実現は`let!`します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="e5b62-155">これは、多くの場合、使用結果がコンピュテーション式を呼び出すときに、[省略可能な](options.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="e5b62-156">組み込みのコンピュテーション式</span><span class="sxs-lookup"><span data-stu-id="e5b62-156">Built-in computation expressions</span></span>

<span data-ttu-id="e5b62-157">F#コア ライブラリが 3 つの組み込みのコンピュテーション式を定義します。[シーケンス式](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、および[クエリ式](query-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="e5b62-158">コンピュテーション式の新しい型を作成します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="e5b62-159">ビルダー クラスを作成し、クラスの特定の特殊なメソッドを定義することは、独自のコンピュテーション式の特性を定義できます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="e5b62-160">必要に応じて、ビルダー クラスは、次の表に記載されている、メソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="e5b62-161">次の表では、ワークフロー ビルダー クラスで使用できるメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="e5b62-162">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="e5b62-162">**Method**</span></span>|<span data-ttu-id="e5b62-163">**通常のシグネチャ**</span><span class="sxs-lookup"><span data-stu-id="e5b62-163">**Typical signature(s)**</span></span>|<span data-ttu-id="e5b62-164">**説明**</span><span class="sxs-lookup"><span data-stu-id="e5b62-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="e5b62-165">に対して呼び出されて`let!`と`do!`コンピュテーション式で。</span><span class="sxs-lookup"><span data-stu-id="e5b62-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="e5b62-166">コンピュテーション式として関数をラップします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="e5b62-167">に対して呼び出されて`return`コンピュテーション式で。</span><span class="sxs-lookup"><span data-stu-id="e5b62-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="e5b62-168">に対して呼び出されて`return!`コンピュテーション式で。</span><span class="sxs-lookup"><span data-stu-id="e5b62-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="e5b62-169">`M<'T> -> M<'T>` または</span><span class="sxs-lookup"><span data-stu-id="e5b62-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="e5b62-170">コンピュテーション式を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="e5b62-171">`M<'T> * M<'T> -> M<'T>` または</span><span class="sxs-lookup"><span data-stu-id="e5b62-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="e5b62-172">コンピュテーション式でシーケンス処理と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="e5b62-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` または</span><span class="sxs-lookup"><span data-stu-id="e5b62-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="e5b62-174">に対して呼び出されて`for...do`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="e5b62-175">に対して呼び出されて`try...finally`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="e5b62-176">に対して呼び出されて`try...with`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="e5b62-177">に対して呼び出されて`use`コンピュテーション式でバインドします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="e5b62-178">に対して呼び出されて`while...do`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="e5b62-179">に対して呼び出されて`yield`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="e5b62-180">に対して呼び出されて`yield!`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="e5b62-181">空のという`else`の分岐`if...then`コンピュテーション式内の式。</span><span class="sxs-lookup"><span data-stu-id="e5b62-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="e5b62-182">コンピュテーション式に渡されることを示します、`Run`引用符としてメンバー。</span><span class="sxs-lookup"><span data-stu-id="e5b62-182">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="e5b62-183">見積に計算のすべてのインスタンスを変換します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-183">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="e5b62-184">ビルダー クラスのメソッドの多くを使用し、返す、`M<'T>`コンス トラクターは、たとえば、結合している計算の種類の特性を設定するとは別に定義されている型は通常、`Async<'T>`ための非同期ワークフローと`Seq<'T>`ワークフローのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="e5b62-184">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="e5b62-185">これらのメソッドのシグネチャは、1 つの構築から返されるワークフロー オブジェクトは、次に渡すことができるようにそれらを結合し、相互に入れ子に有効にします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-185">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="e5b62-186">計算式を解析するとき、コンパイラは、上記の表に、メソッドとそのコンピュテーション式のコードを使用して、一連の入れ子になった関数呼び出しに式を変換します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-186">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="e5b62-187">入れ子になった式は、次の形式では。</span><span class="sxs-lookup"><span data-stu-id="e5b62-187">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="e5b62-188">上記のコードへの呼び出しで`Run`と`Delay`計算式ビルダー クラスで定義されていない場合は省略します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-188">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="e5b62-189">としてここで示される、計算式の本体`{| cexpr |}`は、次の表で説明されている翻訳によってビルダー クラスのメソッドに関連する呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-189">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="e5b62-190">コンピュテーション式`{| cexpr |}`に従ってこれらの変換を再帰的に定義されているは、 `expr` F# の式と`cexpr`計算式です。</span><span class="sxs-lookup"><span data-stu-id="e5b62-190">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="e5b62-191">正規表現</span><span class="sxs-lookup"><span data-stu-id="e5b62-191">Expression</span></span>|<span data-ttu-id="e5b62-192">変換</span><span class="sxs-lookup"><span data-stu-id="e5b62-192">Translation</span></span>|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr, builder.Delay({&#124;cexpr &#124;}))</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|

<span data-ttu-id="e5b62-193">前の表に`other-expr`それ以外の場合、表に一覧表示されない式について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-193">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="e5b62-194">ビルダー クラスは、すべてのメソッドを実装し、前の表に、翻訳のすべてをサポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e5b62-194">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="e5b62-195">実装されていないこれらのコンストラクトでは、その型のコンピュテーション式で使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5b62-195">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="e5b62-196">例では、サポートしない場合、 `use` 、コンピュテーション式、キーワードの定義を省略できます`Use`ビルダー クラスにします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-196">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="e5b62-197">次のコード例では、一連のことができる手順を一度に 1 つのステップを評価すると、計算をカプセル化する計算式を示します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-197">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="e5b62-198">A 判別共用体型、 `OkOrException`、これまでに評価された式のエラー状態をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e5b62-198">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="e5b62-199">このコードは、ビルダー メソッドのいくつかの定型実装など、コンピュテーション式で使用できるいくつかの一般的なパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="e5b62-199">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="e5b62-200">コンピュテーション式には、式から返される、基になる型があります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-200">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="e5b62-201">計算の結果または遅延の計算を実行できる、基になる型を表すことがあります。 または何らかの種類のコレクションを反復処理する方法を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-201">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="e5b62-202">前の例では、基になる型が**最終的に**します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-202">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="e5b62-203">シーケンス式では、基になる型は<xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-203">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e5b62-204">クエリ式では、基になる型は<xref:System.Linq.IQueryable?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-204">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e5b62-205">非同期ワークフローでは、基になる型は[ `Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-205">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="e5b62-206">`Async`オブジェクトは、結果を計算するために実行する作業を表します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-206">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="e5b62-207">たとえば、呼び出す[ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)計算を実行し、結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-207">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="e5b62-208">カスタム操作</span><span class="sxs-lookup"><span data-stu-id="e5b62-208">Custom Operations</span></span>

<span data-ttu-id="e5b62-209">コンピュテーション式のカスタム処理を定義し、オペレーターはコンピュテーション式でカスタム操作を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-209">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="e5b62-210">たとえば、クエリ式でクエリ演算子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-210">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="e5b62-211">カスタム操作を定義するときに、Yield を定義する必要がありますとコンピュテーション式内のメソッド。</span><span class="sxs-lookup"><span data-stu-id="e5b62-211">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="e5b62-212">カスタム操作を定義するには、そのコンピュテーション式のビルダー クラスに配置し、適用、 [ `CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-212">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="e5b62-213">この属性は、カスタム操作で使用する名前を引数として文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-213">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="e5b62-214">この名前は、そのコンピュテーション式の中かっこの開始時のスコープに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-214">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="e5b62-215">そのため、このブロックでカスタム操作と同じ名前を指定する識別子を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="e5b62-215">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="e5b62-216">たとえばなどの識別子の使用を避ける`all`または`last`クエリ式で。</span><span class="sxs-lookup"><span data-stu-id="e5b62-216">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="e5b62-217">新しいカスタム操作で既存のビルダーを拡張します。</span><span class="sxs-lookup"><span data-stu-id="e5b62-217">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="e5b62-218">ビルダー クラスは、既にある場合は、このビルダー クラスの外部からのカスタム操作が拡張できます。</span><span class="sxs-lookup"><span data-stu-id="e5b62-218">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="e5b62-219">拡張機能は、モジュール内で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5b62-219">Extensions must be declared in modules.</span></span> <span data-ttu-id="e5b62-220">名前空間には、同じファイルで、型が定義されている同じ名前空間宣言のグループを除く拡張メンバーを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e5b62-220">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="e5b62-221">次の例は、既存の拡張機能`Microsoft.FSharp.Linq.QueryBuilder`クラス。</span><span class="sxs-lookup"><span data-stu-id="e5b62-221">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="e5b62-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5b62-222">See also</span></span>

- [<span data-ttu-id="e5b62-223">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="e5b62-223">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e5b62-224">非同期ワークフロー</span><span class="sxs-lookup"><span data-stu-id="e5b62-224">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="e5b62-225">シーケンス</span><span class="sxs-lookup"><span data-stu-id="e5b62-225">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="e5b62-226">クエリ式</span><span class="sxs-lookup"><span data-stu-id="e5b62-226">Query Expressions</span></span>](query-expressions.md)
