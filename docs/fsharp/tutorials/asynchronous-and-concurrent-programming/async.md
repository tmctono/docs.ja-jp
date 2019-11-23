---
title: での非同期プログラミングF#
description: がコアF#関数型プログラミングの概念から派生した言語レベルのプログラミングモデルに基づいて、非同期性のクリーンなサポートを提供する方法について説明します。
ms.date: 12/17/2018
ms.openlocfilehash: 1ede4a5c1e26df271ac94f9b2c216ac84fb38f59
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395790"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="54062-103">F\# での非同期プログラミング</span><span class="sxs-lookup"><span data-stu-id="54062-103">Async programming in F\#</span></span>

<span data-ttu-id="54062-104">非同期プログラミングは、さまざまな理由で、最新のアプリケーションに不可欠なメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="54062-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="54062-105">ほとんどの開発者が直面する主なユースケースには、次の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="54062-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="54062-106">多数の同時受信要求を処理できるサーバープロセスを提供する一方で、要求の処理中に使用されるシステムリソースを最小限に抑えながら、そのプロセスの外部のシステムまたはサービスからの入力を待機する</span><span class="sxs-lookup"><span data-stu-id="54062-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="54062-107">バックグラウンド作業の同時進行中に応答性の高い UI またはメインスレッドを維持する</span><span class="sxs-lookup"><span data-stu-id="54062-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="54062-108">多くの場合、バックグラウンド作業には複数のスレッドの使用が含まれますが、非同期性とマルチスレッドの概念を個別に考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="54062-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="54062-109">実際、別々の検討事項であり、互いに他者を意味する訳ではありません。</span><span class="sxs-lookup"><span data-stu-id="54062-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="54062-110">この記事では、これについてさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="54062-110">What follows in this article will describe this in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="54062-111">非同期性の定義</span><span class="sxs-lookup"><span data-stu-id="54062-111">Asynchrony defined</span></span>

<span data-ttu-id="54062-112">非同期性はマルチスレッドの利用と独立である、という点に関してもう少し説明しておいた方が良いでしょう。</span><span class="sxs-lookup"><span data-stu-id="54062-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="54062-113">関連することがある 3 つの概念がありますが、これらは厳密には独立した概念です。</span><span class="sxs-lookup"><span data-stu-id="54062-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="54062-114">並行処理: 複数の計算がオーバーラップする時間帯に実行される場合</span><span class="sxs-lookup"><span data-stu-id="54062-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="54062-115">並列処理: 複数の計算または 1 つの計算の複数の部分が厳密に同じ時間に実行される場合</span><span class="sxs-lookup"><span data-stu-id="54062-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="54062-116">非同期処理: メインのプログラムとは別に、1 つ以上の計算が実行される場合</span><span class="sxs-lookup"><span data-stu-id="54062-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="54062-117">これら 3 つは直交概念ですが、一緒に用いてしまうと混同する場合があります。</span><span class="sxs-lookup"><span data-stu-id="54062-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="54062-118">たとえば、複数の非同期計算を並行して実行することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54062-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="54062-119">これは、並列処理または非同期処理が互いを意味するという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="54062-119">This does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="54062-120">"非同期" という語の語源を考慮すると、次の2つの部分が関係します。</span><span class="sxs-lookup"><span data-stu-id="54062-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="54062-121">「ない」を意味する"a"</span><span class="sxs-lookup"><span data-stu-id="54062-121">"a", meaning "not".</span></span>
- <span data-ttu-id="54062-122">「同時に」を意味する"synchronous"</span><span class="sxs-lookup"><span data-stu-id="54062-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="54062-123">これらの2つの用語をまとめると、"非同期" とは "同時に実行しない" ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="54062-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="54062-124">以上で終わりです。</span><span class="sxs-lookup"><span data-stu-id="54062-124">That's it!</span></span> <span data-ttu-id="54062-125">この定義には、並行処理も並列処理もありません。</span><span class="sxs-lookup"><span data-stu-id="54062-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="54062-126">このことは実際にも当てはまるのです。</span><span class="sxs-lookup"><span data-stu-id="54062-126">This is also true in practice.</span></span>

<span data-ttu-id="54062-127">実際には、のF#非同期計算は、メインプログラムフローとは別に実行するようにスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="54062-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="54062-128">これは、同時実行または並列処理を意味しません。また、計算が常にバックグラウンドで発生することも意味しません。</span><span class="sxs-lookup"><span data-stu-id="54062-128">This doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="54062-129">実際、非同期計算は、計算の性質と計算が実行されている環境に応じて、同期的に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="54062-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="54062-130">重要なことは、非同期計算はメインプログラムフローから独立していることです。</span><span class="sxs-lookup"><span data-stu-id="54062-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="54062-131">非同期計算がいつまたはどのように実行されるかに関する保証はほとんどありませんが、それらを調整しスケジューリングするためのアプローチがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="54062-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="54062-132">この記事の残りの部分では、 F# の非同期処理に関する主要な概念と、F# に組み込まれている型、関数、および式の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="54062-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="54062-133">主要な概念</span><span class="sxs-lookup"><span data-stu-id="54062-133">Core concepts</span></span>

<span data-ttu-id="54062-134">F# では、非同期プログラミングは次の 3 つの主要な概念を中心にしています。</span><span class="sxs-lookup"><span data-stu-id="54062-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="54062-135">`Async<'T>` 型。これは、コンポーザブルな非同期計算を表します。</span><span class="sxs-lookup"><span data-stu-id="54062-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="54062-136">`Async` モジュール関数を使用すると、非同期処理のスケジュール、非同期計算の作成、および非同期結果の変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="54062-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="54062-137">`async { }`[コンピュテーション式](../../language-reference/computation-expressions.md)。非同期計算を構築および制御するための便利な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="54062-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="54062-138">これら 3 つの概念を、次の例で確認できます。</span><span class="sxs-lookup"><span data-stu-id="54062-138">You can see these three concepts in the following example:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    printTotalFileBytes "path-to-file.txt"
    |> Async.RunSynchronously

    Console.Read() |> ignore
    0
```

<span data-ttu-id="54062-139">この例では、`printTotalFileBytes` 関数は `string -> Async<unit>`型です。</span><span class="sxs-lookup"><span data-stu-id="54062-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="54062-140">関数を呼び出すと、実際には非同期計算が実行されません。</span><span class="sxs-lookup"><span data-stu-id="54062-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="54062-141">代わりに、非同期的に実行する作業の \* 仕様として機能する `Async<unit>` が返されます。</span><span class="sxs-lookup"><span data-stu-id="54062-141">Instead, it returns an `Async<unit>` that acts as a \*specification- of the work that is to execute asynchronously.</span></span> <span data-ttu-id="54062-142">このメソッドは、本文で `Async.AwaitTask` を呼び出します。これにより、<xref:System.IO.File.WriteAllBytesAsync%2A> の結果が呼び出されたときに適切な型に変換されます。</span><span class="sxs-lookup"><span data-stu-id="54062-142">It will call `Async.AwaitTask` in its body, which will convert the result of <xref:System.IO.File.WriteAllBytesAsync%2A> to an appropriate type when it is called.</span></span>

<span data-ttu-id="54062-143">もう 1 つの重要な行は `Async.RunSynchronously` の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="54062-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="54062-144">これは、 F# の非同期計算を実際に実行する際に呼び出す必要のある Async モジュールの開始関数の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="54062-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="54062-145">これはC#/VB スタイルの `async` プログラミングとの根本的に異なる点です。</span><span class="sxs-lookup"><span data-stu-id="54062-145">This is a fundamental difference with the C#/VB style of `async` programming.</span></span> <span data-ttu-id="54062-146">F#では、非同期計算は**コールド(冷たい)タスク**として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="54062-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="54062-147">これらを実際に実行するには、明示的に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54062-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="54062-148">これには、C#/VBよりもはるかに簡単に非同期作業を組み合わせることができるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="54062-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C#/VB.</span></span>

## <a name="combining-asynchronous-computations"></a><span data-ttu-id="54062-149">非同期計算の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="54062-149">Combining asynchronous computations</span></span>

<span data-ttu-id="54062-150">次に、上記の例をもとに計算処理を組み合わせる例を示します。</span><span class="sxs-lookup"><span data-stu-id="54062-150">Here is an example that builds upon the previous one by combining computations:</span></span>

```fsharp
open System
open System.IO

let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Parallel
    |> Async.Ignore
    |> Async.RunSynchronously

    0
```

<span data-ttu-id="54062-151">ご覧のように、`main` 関数には、さらに多くの呼び出しが行われています。</span><span class="sxs-lookup"><span data-stu-id="54062-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="54062-152">概念的には、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="54062-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="54062-153">コマンドライン引数を、`Async<unit>` を指定して `Array.map` の計算に変換します。</span><span class="sxs-lookup"><span data-stu-id="54062-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="54062-154">実行時に並列で `Async<'T[]>` の計算をスケジュールして実行する `printTotalFileBytes` を作成します。</span><span class="sxs-lookup"><span data-stu-id="54062-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="54062-155">`Async<unit>` を生成しますが、これは並列計算を実行してその結果を無視します。</span><span class="sxs-lookup"><span data-stu-id="54062-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="54062-156">`Async.RunSynchronously` で最後の計算を明示的に実行し、完了するまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="54062-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it is completes.</span></span>

<span data-ttu-id="54062-157">このプログラムを実行すると、コマンドライン引数ごとに `printTotalFileBytes` が並列実行されます。</span><span class="sxs-lookup"><span data-stu-id="54062-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="54062-158">非同期計算はプログラムフローとは無関係に実行されるため、それぞれ情報を出力して終了する順序は決まりません。</span><span class="sxs-lookup"><span data-stu-id="54062-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="54062-159">計算処理は並列にスケジューリングされますが、その実行順序は保証されません。</span><span class="sxs-lookup"><span data-stu-id="54062-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequencing-asynchronous-computations"></a><span data-ttu-id="54062-160">非同期計算の順序処理</span><span class="sxs-lookup"><span data-stu-id="54062-160">Sequencing asynchronous computations</span></span>

<span data-ttu-id="54062-161">`Async<'T>` は既に実行されているタスクではなく作業の仕様であるため、より複雑な変換を簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="54062-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="54062-162">非同期計算のセットをシーケンス処理して、1つずつ実行する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="54062-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

```fsharp
let printTotalFileBytes path =
    async {
        let! bytes = File.ReadAllBytesAsync(path) |> Async.AwaitTask
        let fileName = Path.GetFileName(path)
        printfn "File %s has %d bytes" fileName bytes.Length
    }

[<EntryPoint>]
let main argv =
    argv
    |> Array.map printTotalFileBytes
    |> Async.Sequential
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="54062-163">これにより、`printTotalFileBytes` を並行してスケジュールするのではなく、`argv` の要素の順序で実行するようにスケジュールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="54062-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="54062-164">次の項目は、最後の計算の実行が完了するまではスケジュールされないため、実行中に重複が発生しないように計算がシーケンス処理されます。</span><span class="sxs-lookup"><span data-stu-id="54062-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="54062-165">重要な Async モジュール関数</span><span class="sxs-lookup"><span data-stu-id="54062-165">Important Async module functions</span></span>

<span data-ttu-id="54062-166">非同期コードF#を記述する場合は、通常、計算のスケジューリングを処理するフレームワークと対話します。</span><span class="sxs-lookup"><span data-stu-id="54062-166">When you write async code in F# you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="54062-167">ただし、これは常にであるとは限りません。そのため、非同期処理をスケジュールするためのさまざまな開始関数について学習することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="54062-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="54062-168">F# の非同期計算は、既に実行されている作業を表すのではなく、作業の_仕様_を表しているので、開始関数を使用して明示的に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54062-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="54062-169">さまざまなコンテキストで役に立つ[Async開始関数](https://msdn.microsoft.com/library/ee370232.aspx) が多数あります。</span><span class="sxs-lookup"><span data-stu-id="54062-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="54062-170">次のセクションでは、より一般的な開始関数のいくつかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="54062-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="54062-171">Async.StartChild</span><span class="sxs-lookup"><span data-stu-id="54062-171">Async.StartChild</span></span>

<span data-ttu-id="54062-172">非同期計算内で子計算を開始します。</span><span class="sxs-lookup"><span data-stu-id="54062-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="54062-173">これを用いることで、複数の非同期計算を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="54062-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="54062-174">子の計算では、キャンセルトークンを親計算と共有しています。</span><span class="sxs-lookup"><span data-stu-id="54062-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="54062-175">親の計算が取り消された場合は、子の計算も取り消されます。</span><span class="sxs-lookup"><span data-stu-id="54062-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="54062-176">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-176">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="54062-177">使用すべき状況:</span><span class="sxs-lookup"><span data-stu-id="54062-177">When to use:</span></span>

- <span data-ttu-id="54062-178">一度に 1 つずつではなく、複数の非同期計算を同時に実行するが、並列でスケジューリングされない場合。</span><span class="sxs-lookup"><span data-stu-id="54062-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="54062-179">子計算の有効期間を親計算の有効期間に関連付ける場合。</span><span class="sxs-lookup"><span data-stu-id="54062-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="54062-180">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-180">What to watch out for:</span></span>

- <span data-ttu-id="54062-181">`Async.StartChild` を使用した複数の計算の開始は、並列でのスケジュール設定と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="54062-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="54062-182">計算を並列でスケジュールする場合は、`Async.Parallel`を使用します。</span><span class="sxs-lookup"><span data-stu-id="54062-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="54062-183">親計算を取り消すと、開始したすべての子計算の取り消しをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="54062-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="54062-184">Async.StartImmediate</span><span class="sxs-lookup"><span data-stu-id="54062-184">Async.StartImmediate</span></span>

<span data-ttu-id="54062-185">非同期計算を実行し、現在のオペレーティング システムのスレッドですぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="54062-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="54062-186">これは、計算中に呼び出し元のスレッドで何かを更新する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="54062-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="54062-187">たとえば、非同期計算で UI を更新する必要がある場合 (進行状況バーを更新する場合など) は、`Async.StartImmediate` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="54062-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="54062-188">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-188">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="54062-189">使用すべき状況:</span><span class="sxs-lookup"><span data-stu-id="54062-189">When to use:</span></span>

- <span data-ttu-id="54062-190">非同期計算の途中で、呼び出し元のスレッドで何かを更新する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="54062-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="54062-191">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-191">What to watch out for:</span></span>

- <span data-ttu-id="54062-192">非同期計算のコードは、スケジュールされている任意のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="54062-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="54062-193">これは、そのスレッドが UI スレッドなど、何らかの方法で重要な場合に問題になることがあります。</span><span class="sxs-lookup"><span data-stu-id="54062-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="54062-194">このような場合、`Async.StartImmediate` の使用は不適切である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54062-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="54062-195">Async.StartAsTask</span><span class="sxs-lookup"><span data-stu-id="54062-195">Async.StartAsTask</span></span>

<span data-ttu-id="54062-196">スレッド プールで計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="54062-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="54062-197">計算が終了した後、対応する状態で完了する <xref:System.Threading.Tasks.Task%601> を返します (結果を生成するか、例外をスローするか、または取り消されます)。</span><span class="sxs-lookup"><span data-stu-id="54062-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="54062-198">キャンセルトークンが指定されていない場合は、既定のキャンセルトークンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="54062-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="54062-199">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-199">Signature:</span></span>

```fsharp
computation: Async<'T> - taskCreationOptions: ?TaskCreationOptions - cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="54062-200">使用すべき状況:</span><span class="sxs-lookup"><span data-stu-id="54062-200">When to use:</span></span>

- <span data-ttu-id="54062-201">非同期計算の結果を表すために <xref:System.Threading.Tasks.Task%601> を想定している .NET API を呼び出す必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="54062-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="54062-202">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-202">What to watch out for:</span></span>

- <span data-ttu-id="54062-203">この呼び出しでは、追加の `Task` オブジェクトを割り当てます。よってこれを頻繁に使用される場合にオーバーヘッドが増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="54062-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="54062-204">Async.Parallel</span><span class="sxs-lookup"><span data-stu-id="54062-204">Async.Parallel</span></span>

<span data-ttu-id="54062-205">並列で実行される一連の非同期計算をスケジューリングします。</span><span class="sxs-lookup"><span data-stu-id="54062-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="54062-206">`maxDegreesOfParallelism` パラメーターを指定することによって、必要に応じて並列処理の次数をチューニング/調整できます。</span><span class="sxs-lookup"><span data-stu-id="54062-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="54062-207">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> - ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="54062-208">使用するタイミング:</span><span class="sxs-lookup"><span data-stu-id="54062-208">When to use it:</span></span>

- <span data-ttu-id="54062-209">一連の計算を同時に実行する必要があるが、実行の順序に依存しない場合。</span><span class="sxs-lookup"><span data-stu-id="54062-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="54062-210">すべてが完了するまで並列でスケジューリングされた計算結果を必要としない場合。</span><span class="sxs-lookup"><span data-stu-id="54062-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="54062-211">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-211">What to watch out for:</span></span>

- <span data-ttu-id="54062-212">すべての計算が完了するまで、結果として得られる値の配列にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="54062-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="54062-213">計算は実行されますが、スケジュールが設定されます。</span><span class="sxs-lookup"><span data-stu-id="54062-213">Computations will be run however they end up getting scheduled.</span></span> <span data-ttu-id="54062-214">つまり、実行の順序に依存することはできません。</span><span class="sxs-lookup"><span data-stu-id="54062-214">This means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="54062-215">Async.Sequential</span><span class="sxs-lookup"><span data-stu-id="54062-215">Async.Sequential</span></span>

<span data-ttu-id="54062-216">一連の非同期計算を渡された順序で実行されるようにスケジューリングします。</span><span class="sxs-lookup"><span data-stu-id="54062-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="54062-217">最初の計算を実行し、その後、その次という具合です。</span><span class="sxs-lookup"><span data-stu-id="54062-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="54062-218">計算は並列実行されません。</span><span class="sxs-lookup"><span data-stu-id="54062-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="54062-219">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="54062-220">使用するタイミング:</span><span class="sxs-lookup"><span data-stu-id="54062-220">When to use it:</span></span>

- <span data-ttu-id="54062-221">複数の計算を順番に実行する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="54062-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="54062-222">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-222">What to watch out for:</span></span>

- <span data-ttu-id="54062-223">すべての計算が完了するまで、結果として得られる値の配列にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="54062-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="54062-224">計算は、この関数に渡される順序で実行されます。そのため、結果が返されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="54062-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="54062-225">Async.AwaitTask</span><span class="sxs-lookup"><span data-stu-id="54062-225">Async.AwaitTask</span></span>

<span data-ttu-id="54062-226">指定された <xref:System.Threading.Tasks.Task%601> が完了するまで待機し、その結果を `Async<'T>` として返すような非同期計算を返します。</span><span class="sxs-lookup"><span data-stu-id="54062-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="54062-227">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-227">Signature:</span></span>

```fsharp
task: Task<'T>  -> Async<'T>
```

<span data-ttu-id="54062-228">使用すべき状況:</span><span class="sxs-lookup"><span data-stu-id="54062-228">When to use:</span></span>

- <span data-ttu-id="54062-229">F#の非同期計算内で <xref:System.Threading.Tasks.Task%601> を返す .NET API を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="54062-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="54062-230">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-230">What to watch out for:</span></span>

- <span data-ttu-id="54062-231">例外は、タスク並列ライブラリ(Task Parallel Library)の規則に従って <xref:System.AggregateException> でラップされます。これは、 F#の非同期における例外の処理方法と異なります。</span><span class="sxs-lookup"><span data-stu-id="54062-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="54062-232">Async.Catch</span><span class="sxs-lookup"><span data-stu-id="54062-232">Async.Catch</span></span>

<span data-ttu-id="54062-233">指定された `Async<'T>`を実行し、`Async<Choice<'T, exn>>`を返す非同期計算を作成します。</span><span class="sxs-lookup"><span data-stu-id="54062-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="54062-234">指定された `Async<'T>` が正常に完了した場合、結果の値と共に `Choice1Of2` が返されます。</span><span class="sxs-lookup"><span data-stu-id="54062-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="54062-235">完了前に例外がスローされた場合は、発生した例外と共に `Choice2of2` が返されます。</span><span class="sxs-lookup"><span data-stu-id="54062-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="54062-236">多くの計算で構成され、その計算の1つが例外をスローする非同期計算で使用される場合、外側の計算は完全に停止されます。</span><span class="sxs-lookup"><span data-stu-id="54062-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="54062-237">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="54062-238">使用すべき状況:</span><span class="sxs-lookup"><span data-stu-id="54062-238">When to use:</span></span>

- <span data-ttu-id="54062-239">例外によって失敗する可能性があり、呼び出し元でその例外を処理する必要がある非同期処理を実行する場合。</span><span class="sxs-lookup"><span data-stu-id="54062-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="54062-240">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-240">What to watch out for:</span></span>

- <span data-ttu-id="54062-241">結合またはシーケンスされた非同期計算を使用する場合、その "内部" 計算の1つが例外をスローすると、外側の計算が完全に停止します。</span><span class="sxs-lookup"><span data-stu-id="54062-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="54062-242">Async.Ignore</span><span class="sxs-lookup"><span data-stu-id="54062-242">Async.Ignore</span></span>

<span data-ttu-id="54062-243">指定された計算を実行し、その結果を無視する非同期計算を作成します。</span><span class="sxs-lookup"><span data-stu-id="54062-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="54062-244">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="54062-245">使用すべき状況:</span><span class="sxs-lookup"><span data-stu-id="54062-245">When to use:</span></span>

- <span data-ttu-id="54062-246">結果が不要な非同期計算がある場合。</span><span class="sxs-lookup"><span data-stu-id="54062-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="54062-247">これは、非非同期コードの `ignore` コードに似ています。</span><span class="sxs-lookup"><span data-stu-id="54062-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="54062-248">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-248">What to watch out for:</span></span>

- <span data-ttu-id="54062-249">`Async.Start` または `Async<unit>`を必要とする別の関数を使用するためにこれを使用する必要がある場合は、結果を破棄することができるかどうかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="54062-249">If you must use this because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay to do.</span></span> <span data-ttu-id="54062-250">型シグネチャに一致するように結果を破棄することは、通常はできません。</span><span class="sxs-lookup"><span data-stu-id="54062-250">Discarding results just to fit a type signature should not generally be done.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="54062-251">Async.RunSynchronously</span><span class="sxs-lookup"><span data-stu-id="54062-251">Async.RunSynchronously</span></span>

<span data-ttu-id="54062-252">非同期計算を実行し、呼び出し元のスレッドでその結果を待機します。</span><span class="sxs-lookup"><span data-stu-id="54062-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="54062-253">これはブロッキングする呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="54062-253">This call is blocking.</span></span>

<span data-ttu-id="54062-254">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-254">Signature:</span></span>

```fsharp
computation: Async<'T> - timeout: ?int - cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="54062-255">使用するタイミング:</span><span class="sxs-lookup"><span data-stu-id="54062-255">When to use it:</span></span>

- <span data-ttu-id="54062-256">必要な場合、実行可能ファイルのエントリポイントでアプリケーション内で 1 回だけ使用します。</span><span class="sxs-lookup"><span data-stu-id="54062-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="54062-257">パフォーマンスを気にせずに、他の一連の非同期操作を一度に実行する場合。</span><span class="sxs-lookup"><span data-stu-id="54062-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="54062-258">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-258">What to watch out for:</span></span>

- <span data-ttu-id="54062-259">`Async.RunSynchronously` を呼び出すと、実行が完了するまで呼び出し元のスレッドがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="54062-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="54062-260">Async.Start</span><span class="sxs-lookup"><span data-stu-id="54062-260">Async.Start</span></span>

<span data-ttu-id="54062-261">`unit`を返すスレッドプール内の非同期計算を開始します。</span><span class="sxs-lookup"><span data-stu-id="54062-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="54062-262">は結果を待機しません。</span><span class="sxs-lookup"><span data-stu-id="54062-262">Doesn't wait for its result.</span></span> <span data-ttu-id="54062-263">`Async.Start` で開始された入れ子になった計算は、それを呼び出した親計算とは無関係に完全に開始されます。</span><span class="sxs-lookup"><span data-stu-id="54062-263">Nested computations started with `Async.Start` are started completely independently of the parent computation that called them.</span></span> <span data-ttu-id="54062-264">有効期間は、どの親計算にも関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="54062-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="54062-265">親計算が取り消された場合、子計算は取り消されません。</span><span class="sxs-lookup"><span data-stu-id="54062-265">If the parent computation is canceled, no child computations are cancelled.</span></span>

<span data-ttu-id="54062-266">型シグニチャ:</span><span class="sxs-lookup"><span data-stu-id="54062-266">Signature:</span></span>

```fsharp
computation: Async<unit> - cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="54062-267">次の場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="54062-267">Use only when:</span></span>

- <span data-ttu-id="54062-268">非同期計算による結果が得られない、かつ/またはその結果を処理する必要がない。</span><span class="sxs-lookup"><span data-stu-id="54062-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="54062-269">非同期計算がいつ完了するかを知る必要がない。</span><span class="sxs-lookup"><span data-stu-id="54062-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="54062-270">非同期計算が実行されるスレッドを認識する必要がない。</span><span class="sxs-lookup"><span data-stu-id="54062-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="54062-271">タスクの結果として発生した例外を認識したり、報告したりする必要がない。</span><span class="sxs-lookup"><span data-stu-id="54062-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="54062-272">注意事項:</span><span class="sxs-lookup"><span data-stu-id="54062-272">What to watch out for:</span></span>

- <span data-ttu-id="54062-273">`Async.Start` で開始された計算によって発生した例外は、呼び出し元に反映されません。</span><span class="sxs-lookup"><span data-stu-id="54062-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="54062-274">呼び出し履歴は完全にアンワインドされます。</span><span class="sxs-lookup"><span data-stu-id="54062-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="54062-275">`printfn` で開始された effectful 作業 (`Async.Start` の呼び出しなど) では、プログラムの実行のメインスレッドで効果が発生しません。</span><span class="sxs-lookup"><span data-stu-id="54062-275">Any effectful work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperating-with-net"></a><span data-ttu-id="54062-276">.NET との相互運用</span><span class="sxs-lookup"><span data-stu-id="54062-276">Interoperating with .NET</span></span>

<span data-ttu-id="54062-277">非同期[/await](../../../standard/async.md)スタイルの非同期プログラミングを使用C#する .net ライブラリまたはコードベースを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="54062-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="54062-278">ほとんどC#の .net ライブラリでは、`Async<'T>`ではなく、<xref:System.Threading.Tasks.Task%601> と <xref:System.Threading.Tasks.Task> の種類を中核となる抽象化として使用するため、これらの2つの方法の間には、非同期性にまたがる境界を越える必要があります。</span><span class="sxs-lookup"><span data-stu-id="54062-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="54062-279">.NET async と `Task<T>` を使用する方法-</span><span class="sxs-lookup"><span data-stu-id="54062-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="54062-280"><xref:System.Threading.Tasks.Task%601> (つまり、戻り値を持つ非同期計算) を使用する .NET 非同期ライブラリおよびコードベースを操作するのは簡単であり、F#には組み込みのサポート機能があります。</span><span class="sxs-lookup"><span data-stu-id="54062-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="54062-281">`Async.AwaitTask` 関数を使用すると、.NET の非同期計算を待機できます。</span><span class="sxs-lookup"><span data-stu-id="54062-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="54062-282">`Async.StartAsTask` 関数を使用して、非同期計算を .NET 呼び出し元に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="54062-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="54062-283">.NET async と `Task` を使用する方法-</span><span class="sxs-lookup"><span data-stu-id="54062-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="54062-284"><xref:System.Threading.Tasks.Task> (つまり、値を返さない .NET 非同期計算) を使用する Api を操作するには、`Async<'T>` を <xref:System.Threading.Tasks.Task> に変換する関数を追加することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="54062-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="54062-285">`Async.AwaitTask` を入力として受け取る <xref:System.Threading.Tasks.Task> が既に存在します。</span><span class="sxs-lookup"><span data-stu-id="54062-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="54062-286">これと以前に定義した `startTaskFromAsyncUnit` 関数を使用すると、 F#非同期計算から <xref:System.Threading.Tasks.Task> 型を開始および待機できます。</span><span class="sxs-lookup"><span data-stu-id="54062-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multithreading"></a><span data-ttu-id="54062-287">マルチスレッドとの関係</span><span class="sxs-lookup"><span data-stu-id="54062-287">Relationship to multithreading</span></span>

<span data-ttu-id="54062-288">この記事ではスレッド処理について説明していますが、次の2つの重要な点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="54062-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="54062-289">現在のスレッドで明示的に開始されている場合を除き、非同期計算とスレッド間の関係はありません。</span><span class="sxs-lookup"><span data-stu-id="54062-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="54062-290">F# での非同期プログラミングは、マルチスレッドを抽象的にしたものではありません。</span><span class="sxs-lookup"><span data-stu-id="54062-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="54062-291">たとえば、計算処理は作業の性質によっては実際には呼び出し元のスレッドで実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="54062-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="54062-292">また、計算処理がスレッド間を "ジャンプ" して、"待機中" の少しの時間 (ネットワーク呼び出しが転送中の場合など) の間に有用な作業を行うこともあります。</span><span class="sxs-lookup"><span data-stu-id="54062-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="54062-293">F# には現在のスレッド (または現在のスレッド以外) で 非同期計算を開始する機能を提供していますが、一般的には非同期処理は特定のスレッド処理方法に関連付けられません。</span><span class="sxs-lookup"><span data-stu-id="54062-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="54062-294">参照</span><span class="sxs-lookup"><span data-stu-id="54062-294">See also</span></span>

- [<span data-ttu-id="54062-295">F#非同期プログラミングモデル</span><span class="sxs-lookup"><span data-stu-id="54062-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="54062-296">Jet.com の F# 非同期ガイド</span><span class="sxs-lookup"><span data-stu-id="54062-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="54062-297">F# の楽しく得する非同期プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="54062-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="54062-298">C# と F# における非同期処理: C# の非同期処理の注意事項</span><span class="sxs-lookup"><span data-stu-id="54062-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
