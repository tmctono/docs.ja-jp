---
title: コンピュテーション式
description: 制御フローの構造とバインディングを使用してF#シーケンス処理および結合できる、で計算を記述するための便利な構文を作成する方法について説明します。
ms.date: 03/15/2019
ms.openlocfilehash: ea560bb6eec82672544c7c442b671b63e405474c
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799049"
---
# <a name="computation-expressions"></a><span data-ttu-id="4bdc6-103">コンピュテーション式</span><span class="sxs-lookup"><span data-stu-id="4bdc6-103">Computation Expressions</span></span>

<span data-ttu-id="4bdc6-104">のF#コンピュテーション式は、制御フローの構造とバインディングを使用して、シーケンス処理および結合できる計算を作成するための便利な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="4bdc6-105">計算式の種類によっては、monads、モノ id、monads トランスフォーマー、およびアプリケーションを表現する方法と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="4bdc6-106">ただし、Haskell*のような*他の言語とは異なり、それらは1つの抽象化に関連付けられておらず、マクロやその他の形式のメタプログラミングに依存せず、便利で状況依存の構文を実現できません。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="4bdc6-107">概要</span><span class="sxs-lookup"><span data-stu-id="4bdc6-107">Overview</span></span>

<span data-ttu-id="4bdc6-108">計算には多くの形式が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-108">Computations can take many forms.</span></span> <span data-ttu-id="4bdc6-109">最も一般的な計算形式は、簡単に理解して変更できるシングルスレッド実行です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="4bdc6-110">ただし、すべての形式の計算は、シングルスレッド実行と単純なものではありません。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="4bdc6-111">次に、それらの例の一部を示します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-111">Some examples include:</span></span>

- <span data-ttu-id="4bdc6-112">非決定的な計算</span><span class="sxs-lookup"><span data-stu-id="4bdc6-112">Non-deterministic computations</span></span>
- <span data-ttu-id="4bdc6-113">非同期計算</span><span class="sxs-lookup"><span data-stu-id="4bdc6-113">Asynchronous computations</span></span>
- <span data-ttu-id="4bdc6-114">Effectful の計算</span><span class="sxs-lookup"><span data-stu-id="4bdc6-114">Effectful computations</span></span>
- <span data-ttu-id="4bdc6-115">注釈の計算</span><span class="sxs-lookup"><span data-stu-id="4bdc6-115">Generative computations</span></span>

<span data-ttu-id="4bdc6-116">一般に、アプリケーションの特定の部分で実行する必要がある*状況依存*の計算があります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="4bdc6-117">コンテキストに依存するコードを記述することは困難な場合があります。これは、特定のコンテキストの外では、抽象化を行わずに "リーク" の計算を簡単に行うことができるためです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="4bdc6-118">多くの場合、これらの抽象化は自分で記述することF#が困難です。そのため、**コンピュテーション式**と呼ばれる汎用的な方法があります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="4bdc6-119">コンピュテーション式は、文脈に依存した計算をエンコードするための統一された構文と抽象化モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="4bdc6-120">すべての計算式は、*ビルダー*型によってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="4bdc6-121">ビルダーの型は、コンピュテーション式で使用できる操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="4bdc6-122">「[コンピュテーション式の新しい型の作成](computation-expressions.md#creating-a-new-type-of-computation-expression)」を参照してください。これは、カスタム計算式の作成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="4bdc6-123">構文の概要</span><span class="sxs-lookup"><span data-stu-id="4bdc6-123">Syntax overview</span></span>

<span data-ttu-id="4bdc6-124">すべての計算式の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="4bdc6-125">ここで `builder-expr` はコンピュテーション式を定義するビルダー型の名前、`cexper` はコンピュテーション式の式の本体です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="4bdc6-126">たとえば、`async` コンピュテーション式のコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="4bdc6-127">前の例で示したように、コンピュテーション式内で使用できる特殊な追加の構文があります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="4bdc6-128">コンピュテーション式では、次の式の形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="4bdc6-129">これらのキーワードおよびその他の標準F#のキーワードは、バッキングビルダーの型で定義されている場合にのみ、コンピュテーション式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="4bdc6-130">唯一の例外は `match!`です。これは、`let!` を使用するための構文砂糖であり、その後に結果のパターンマッチが続きます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="4bdc6-131">ビルダーの型は、コンピュテーション式のフラグメントの結合方法を制御する特殊なメソッドを定義するオブジェクトです。つまり、そのメソッドは、コンピュテーション式の動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="4bdc6-132">ビルダークラスを記述するもう1つの方法は、ループやバインドなど、さまざまF#な構造の操作をカスタマイズできるということです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="4bdc6-133">`let!` キーワードは、別のコンピュテーション式への呼び出しの結果を名前にバインドします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="4bdc6-134">`let`でコンピュテーション式への呼び出しをバインドすると、コンピュテーション式の結果は得られません。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="4bdc6-135">代わりに、そのコンピュテーション式に対して、*実現*されていない呼び出しの値をバインドします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="4bdc6-136">`let!` を使用して、結果にバインドします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="4bdc6-137">`let!` は、ビルダー型の `Bind(x, f)` メンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="4bdc6-138">`do!` キーワードは、`unit`に似た型 (ビルダーの `Zero` メンバーによって定義) を返すコンピュテーション式を呼び出すためのものです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="4bdc6-139">[非同期ワークフロー](asynchronous-workflows.md)の場合、この型は `Async<unit>`です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="4bdc6-140">その他の計算式では、型が `CExpType<unit>`される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="4bdc6-141">`do!` は、`f` が `unit`を生成するビルダー型の `Bind(x, f)` メンバーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="4bdc6-142">`yield` キーワードは、<xref:System.Collections.Generic.IEnumerable%601>として使用できるように、コンピュテーション式から値を返すためのものです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="4bdc6-143">[ C#で yield キーワード](../../csharp/language-reference/keywords/yield.md)を使用する場合と同様に、コンピュテーション式の各要素は反復処理されるときに返されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="4bdc6-144">`yield` は、ビルダー型の `Yield(x)` メンバーによって定義されます。 `x` は、返される項目です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="4bdc6-145">`yield!` キーワードは、コンピュテーション式から値のコレクションをフラット化するためのものです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="4bdc6-146">評価された場合、`yield!` によって呼び出されるコンピュテーション式の項目は1つずつ返され、結果がフラット化されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="4bdc6-147">`yield!` は、ビルダー型の `YieldFrom(x)` メンバーによって定義されます。 `x` は値のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="4bdc6-148">`return` キーワードは、コンピュテーション式に対応する型の値をラップします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="4bdc6-149">`yield`を使用した計算式とは別に、計算式を "完了" するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="4bdc6-150">`return` は、ビルダーの型の `Return(x)` メンバーによって定義されます。 `x` は、ラップする項目です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="4bdc6-151">`return!` キーワードは、コンピュテーション式の値を認識し、その結果をコンピュテーション式に対応する型にラップします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="4bdc6-152">`return!` は、ビルダーの型の `ReturnFrom(x)` メンバーによって定義されます。 `x` は別のコンピュテーション式です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="4bdc6-153">F# 4.5 以降では、`match!`キーワードを使用して、その結果に対して別のコンピュテーション式とパターン一致の呼び出しをインライン化できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="4bdc6-154">`match!`でコンピュテーション式を呼び出すと、`let!`のような呼び出しの結果が認識されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="4bdc6-155">これは、通常、結果が[省略可能](options.md)であるコンピュテーション式を呼び出すときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="4bdc6-156">組み込みのコンピュテーション式</span><span class="sxs-lookup"><span data-stu-id="4bdc6-156">Built-in computation expressions</span></span>

<span data-ttu-id="4bdc6-157">コアF#ライブラリでは、[シーケンス式](sequences.md)、[非同期ワークフロー](asynchronous-workflows.md)、[クエリ式](query-expressions.md)という3つの組み込みのコンピュテーション式が定義されています。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="4bdc6-158">新しい種類のコンピュテーション式の作成</span><span class="sxs-lookup"><span data-stu-id="4bdc6-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="4bdc6-159">ビルダークラスを作成し、クラスに特定の特別なメソッドを定義することで、独自のコンピュテーション式の特性を定義できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="4bdc6-160">ビルダークラスでは、次の表に示すように、必要に応じてメソッドを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="4bdc6-161">次の表では、ワークフロービルダークラスで使用できるメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="4bdc6-162">**メソッド**</span><span class="sxs-lookup"><span data-stu-id="4bdc6-162">**Method**</span></span>|<span data-ttu-id="4bdc6-163">**一般的な署名**</span><span class="sxs-lookup"><span data-stu-id="4bdc6-163">**Typical signature(s)**</span></span>|<span data-ttu-id="4bdc6-164">**説明**</span><span class="sxs-lookup"><span data-stu-id="4bdc6-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="4bdc6-165">コンピュテーション式で `let!` および `do!` に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="4bdc6-166">計算式を関数としてラップします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="4bdc6-167">コンピュテーション式の `return` に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="4bdc6-168">コンピュテーション式の `return!` に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="4bdc6-169">`M<'T> -> M<'T>` または</span><span class="sxs-lookup"><span data-stu-id="4bdc6-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="4bdc6-170">コンピュテーション式を実行します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="4bdc6-171">`M<'T> * M<'T> -> M<'T>` または</span><span class="sxs-lookup"><span data-stu-id="4bdc6-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="4bdc6-172">コンピュテーション式でシーケンス処理を行うために呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="4bdc6-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` または</span><span class="sxs-lookup"><span data-stu-id="4bdc6-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="4bdc6-174">コンピュテーション式の `for...do` 式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="4bdc6-175">コンピュテーション式の `try...finally` 式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="4bdc6-176">コンピュテーション式の `try...with` 式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="4bdc6-177">コンピュテーション式の `use` バインドに対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="4bdc6-178">コンピュテーション式の `while...do` 式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="4bdc6-179">コンピュテーション式の `yield` 式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="4bdc6-180">コンピュテーション式の `yield!` 式に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="4bdc6-181">コンピュテーション式の `if...then` 式の空の `else` 分岐に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="4bdc6-182">コンピュテーション式が `Run` メンバーに引用符として渡されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-182">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="4bdc6-183">計算のすべてのインスタンスを引用符に変換します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-183">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="4bdc6-184">ビルダークラスのメソッドの多くは、`M<'T>` コンストラクトを使用して返します。通常、これは、結合する計算の種類を特徴とする個別に定義された型です。たとえば、非同期ワークフローの場合は `Async<'T>`、シーケンスの場合は `Seq<'T>` です。コンフィギュレーション.</span><span class="sxs-lookup"><span data-stu-id="4bdc6-184">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="4bdc6-185">これらのメソッドのシグネチャを使用すると、1つのコンストラクトから返されるワークフローオブジェクトを次の構造体に渡すことができるように、それらを組み合わせて入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-185">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="4bdc6-186">コンパイラは、コンピュテーション式を解析するときに、前の表のメソッドとコンピュテーション式のコードを使用して、一連の入れ子になった関数呼び出しに式を変換します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-186">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="4bdc6-187">入れ子になった式の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-187">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="4bdc6-188">上記のコードでは、コンピュテーション式ビルダークラスで定義されていない場合、`Run` と `Delay` への呼び出しは省略されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-188">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="4bdc6-189">ここでは `{| cexpr |}`として示されているコンピュテーション式の本体は、次の表に示す翻訳によって、ビルダークラスのメソッドを含む呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-189">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="4bdc6-190">コンピュテーション式 `{| cexpr |}` は、これらの変換に従って、`expr` がF#式で、`cexpr`がコンピュテーション式である場合に、再帰的に定義されます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-190">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="4bdc6-191">正規表現</span><span class="sxs-lookup"><span data-stu-id="4bdc6-191">Expression</span></span>|<span data-ttu-id="4bdc6-192">変換</span><span class="sxs-lookup"><span data-stu-id="4bdc6-192">Translation</span></span>|
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
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else binder.Zero()</code>|
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

<span data-ttu-id="4bdc6-193">前の表では、`other-expr` テーブルに記載されていない式について説明しています。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-193">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="4bdc6-194">ビルダークラスは、すべてのメソッドを実装する必要はなく、前の表に一覧表示されているすべての変換をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-194">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="4bdc6-195">実装されていない構造体は、その型のコンピュテーション式では使用できません。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-195">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="4bdc6-196">たとえば、コンピュテーション式で `use` キーワードをサポートしない場合は、ビルダークラスの `Use` の定義を省略できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-196">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="4bdc6-197">次のコード例は、一度に1ステップずつ評価できる一連のステップとして計算をカプセル化するコンピュテーション式を示しています。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-197">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="4bdc6-198">判別共用体型 `OkOrException`は、これまでに評価された式のエラー状態をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-198">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="4bdc6-199">このコードは、いくつかのビルダーメソッドの定型的な実装など、計算式で使用できる一般的なパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-199">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="4bdc6-200">コンピュテーション式には基になる型があり、この式はを返します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-200">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="4bdc6-201">基になる型は、計算された結果または実行可能な遅延計算を表すことができます。また、一部の型のコレクションを反復処理する方法を提供する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-201">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="4bdc6-202">前の例では、基になる型は**最終的**にでした。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-202">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="4bdc6-203">シーケンス式の場合、基になる型は <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-203">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4bdc6-204">クエリ式の場合、基になる型は <xref:System.Linq.IQueryable?displayProperty=nameWithType>です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-204">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4bdc6-205">非同期ワークフローの場合、基になる型は[`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-205">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="4bdc6-206">`Async` オブジェクトは、結果を計算するために実行する作業を表します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-206">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="4bdc6-207">たとえば、 [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b)を呼び出して計算を実行し、その結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-207">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="4bdc6-208">カスタム操作</span><span class="sxs-lookup"><span data-stu-id="4bdc6-208">Custom Operations</span></span>

<span data-ttu-id="4bdc6-209">コンピュテーション式でカスタム操作を定義し、コンピュテーション式で演算子としてカスタム操作を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-209">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="4bdc6-210">たとえば、クエリ式にクエリ演算子を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-210">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="4bdc6-211">カスタム操作を定義する場合は、コンピュテーション式の Yield メソッドと For メソッドを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-211">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="4bdc6-212">カスタム操作を定義するには、それをコンピュテーション式のビルダークラスに配置し、 [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)を適用します。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-212">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="4bdc6-213">この属性は、引数として文字列を受け取ります。これはカスタム操作で使用される名前です。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-213">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="4bdc6-214">この名前は、コンピュテーション式の左中かっこの先頭にあるスコープに含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-214">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="4bdc6-215">したがって、このブロック内のカスタム操作と同じ名前を持つ識別子は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-215">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="4bdc6-216">たとえば、クエリ式で `all` や `last` などの識別子を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-216">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="4bdc6-217">新しいカスタム操作を使用した既存のビルダーの拡張</span><span class="sxs-lookup"><span data-stu-id="4bdc6-217">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="4bdc6-218">既にビルダークラスがある場合は、そのカスタム操作をこのビルダークラスの外部から拡張できます。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-218">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="4bdc6-219">拡張機能はモジュール内で宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-219">Extensions must be declared in modules.</span></span> <span data-ttu-id="4bdc6-220">名前空間には、同じファイルと、型が定義されている同じ名前空間宣言グループ以外の拡張メンバーを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-220">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="4bdc6-221">次の例は、既存の `Microsoft.FSharp.Linq.QueryBuilder` クラスの拡張を示しています。</span><span class="sxs-lookup"><span data-stu-id="4bdc6-221">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="4bdc6-222">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bdc6-222">See also</span></span>

- [<span data-ttu-id="4bdc6-223">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="4bdc6-223">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4bdc6-224">非同期ワークフロー</span><span class="sxs-lookup"><span data-stu-id="4bdc6-224">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="4bdc6-225">シーケンス</span><span class="sxs-lookup"><span data-stu-id="4bdc6-225">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="4bdc6-226">クエリ式</span><span class="sxs-lookup"><span data-stu-id="4bdc6-226">Query Expressions</span></span>](query-expressions.md)
