---
title: 非同期プログラミング
description: F# では、コア機能プログラミングの概念から派生した言語レベルのプログラミング モデルに基づいて、非同期のクリーン サポートを提供する方法について説明します。
ms.date: 12/17/2018
ms.openlocfilehash: 0a7d400c9778e30d6b25798239f12b7b2b0e3d82
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021522"
---
# <a name="async-programming-in-f"></a><span data-ttu-id="f3009-103">F の非同期プログラミング\#</span><span class="sxs-lookup"><span data-stu-id="f3009-103">Async programming in F\#</span></span>

<span data-ttu-id="f3009-104">非同期プログラミングは、さまざまな理由で最新のアプリケーションに不可欠なメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="f3009-104">Asynchronous programming is a mechanism that is essential to modern applications for diverse reasons.</span></span> <span data-ttu-id="f3009-105">ほとんどの開発者が遭遇する主な使用例は次の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="f3009-105">There are two primary use cases that most developers will encounter:</span></span>

- <span data-ttu-id="f3009-106">大量の同時着信要求に対応できるサーバー・プロセスを提示し、要求処理がそのプロセスの外部のシステムまたはサービスからの入力を待機する間、占有されるシステム・リソースを最小化する。</span><span class="sxs-lookup"><span data-stu-id="f3009-106">Presenting a server process that can service a significant number of concurrent incoming requests, while minimizing the system resources occupied while request processing awaits inputs from systems or services external to that process</span></span>
- <span data-ttu-id="f3009-107">バックグラウンド作業を同時に進行しながら、応答性の高い UI またはメイン スレッドを維持する</span><span class="sxs-lookup"><span data-stu-id="f3009-107">Maintaining a responsive UI or main thread while concurrently progressing background work</span></span>

<span data-ttu-id="f3009-108">バックグラウンドでの作業には複数のスレッドの使用が伴うことがよくありますが、非同期とマルチスレッドの概念を別々に考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f3009-108">Although background work often does involve the utilization of multiple threads, it's important to consider the concepts of asynchrony and multi-threading separately.</span></span> <span data-ttu-id="f3009-109">実際、それらは別々の懸念事項であり、一方は他方を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-109">In fact, they are separate concerns, and one does not imply the other.</span></span> <span data-ttu-id="f3009-110">この記事では、個別の概念について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="f3009-110">This article describes the separate concepts in more detail.</span></span>

## <a name="asynchrony-defined"></a><span data-ttu-id="f3009-111">非同期定義</span><span class="sxs-lookup"><span data-stu-id="f3009-111">Asynchrony defined</span></span>

<span data-ttu-id="f3009-112">非同期が複数のスレッドの使用率とは無関係であるという前の点は、もう少し説明する価値があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-112">The previous point - that asynchrony is independent of the utilization of multiple threads - is worth explaining a bit further.</span></span> <span data-ttu-id="f3009-113">関連する場合もありますが、互いに厳密に独立している 3 つの概念があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-113">There are three concepts that are sometimes related, but strictly independent of one another:</span></span>

- <span data-ttu-id="f3009-114">同時実行;複数の計算が重複する期間で実行される場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-114">Concurrency; when multiple computations execute in overlapping time periods.</span></span>
- <span data-ttu-id="f3009-115">並列処理;複数の計算または単一の計算の複数の部分がまったく同時に実行される場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-115">Parallelism; when multiple computations or several parts of a single computation run at exactly the same time.</span></span>
- <span data-ttu-id="f3009-116">非同期;1 つ以上の計算がメインプログラムフローとは別に実行できる場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-116">Asynchrony; when one or more computations can execute separately from the main program flow.</span></span>

<span data-ttu-id="f3009-117">3つとも直交概念ですが、特に一緒に使用する場合は簡単に収縮できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-117">All three are orthogonal concepts, but can be easily conflated, especially when they are used together.</span></span> <span data-ttu-id="f3009-118">たとえば、複数の非同期計算を並列に実行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-118">For example, you may need to execute multiple asynchronous computations in parallel.</span></span> <span data-ttu-id="f3009-119">この関係は、並列性や非同期が互いを暗示することを意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-119">This relationship does not mean that parallelism or asynchrony imply one another.</span></span>

<span data-ttu-id="f3009-120">"非同期" という語の語源を考えると、次の 2 つの部分が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3009-120">If you consider the etymology of the word "asynchronous", there are two pieces involved:</span></span>

- <span data-ttu-id="f3009-121">"a"、つまり"not"。</span><span class="sxs-lookup"><span data-stu-id="f3009-121">"a", meaning "not".</span></span>
- <span data-ttu-id="f3009-122">「同期」、つまり「同時に」を意味します。</span><span class="sxs-lookup"><span data-stu-id="f3009-122">"synchronous", meaning "at the same time".</span></span>

<span data-ttu-id="f3009-123">これら 2 つの用語を組み合わせると、「非同期」とは「同時に」という意味ではないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="f3009-123">When you put these two terms together, you'll see that "asynchronous" means "not at the same time".</span></span> <span data-ttu-id="f3009-124">これで完了です。</span><span class="sxs-lookup"><span data-stu-id="f3009-124">That's it!</span></span> <span data-ttu-id="f3009-125">この定義には、同時実行または並列処理の意味はありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-125">There is no implication of concurrency or parallelism in this definition.</span></span> <span data-ttu-id="f3009-126">これは実際にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="f3009-126">This is also true in practice.</span></span>

<span data-ttu-id="f3009-127">実際には、F# の非同期計算は、メイン プログラム フローとは独立して実行するようにスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="f3009-127">In practical terms, asynchronous computations in F# are scheduled to execute independently of the main program flow.</span></span> <span data-ttu-id="f3009-128">この独立した実行は、同時実行や並列処理を意味するわけではなく、計算が常にバックグラウンドで行われるという意味でもありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-128">This independent execution doesn't imply concurrency or parallelism, nor does it imply that a computation always happens in the background.</span></span> <span data-ttu-id="f3009-129">実際、非同期計算は、計算の性質や計算が実行される環境に応じて、同期的に実行されることさえあります。</span><span class="sxs-lookup"><span data-stu-id="f3009-129">In fact, asynchronous computations can even execute synchronously, depending on the nature of the computation and the environment the computation is executing in.</span></span>

<span data-ttu-id="f3009-130">主な取り上げは、非同期計算はメインプログラムフローから独立していることです。</span><span class="sxs-lookup"><span data-stu-id="f3009-130">The main takeaway you should have is that asynchronous computations are independent of the main program flow.</span></span> <span data-ttu-id="f3009-131">非同期計算の実行時期や方法に関する保証はほとんどありませんが、それらを調整してスケジュールする方法がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f3009-131">Although there are few guarantees about when or how an asynchronous computation executes, there are some approaches to orchestrating and scheduling them.</span></span> <span data-ttu-id="f3009-132">この記事の残りの部分では、F# 非同期の主要な概念と、F# に組み込まれている型、関数、および式の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3009-132">The rest of this article explores core concepts for F# asynchrony and how to use the types, functions, and expressions built into F#.</span></span>

## <a name="core-concepts"></a><span data-ttu-id="f3009-133">主要な概念</span><span class="sxs-lookup"><span data-stu-id="f3009-133">Core concepts</span></span>

<span data-ttu-id="f3009-134">F# では、非同期プログラミングは、次の 3 つの主要な概念を中心にしています。</span><span class="sxs-lookup"><span data-stu-id="f3009-134">In F#, asynchronous programming is centered around three core concepts:</span></span>

- <span data-ttu-id="f3009-135">構成`Async<'T>`可能な非同期計算を表す型。</span><span class="sxs-lookup"><span data-stu-id="f3009-135">The `Async<'T>` type, which represents a composable asynchronous computation.</span></span>
- <span data-ttu-id="f3009-136">非同期`Async`処理のスケジュール設定、非同期計算の作成、非同期結果の変換を行うモジュール関数。</span><span class="sxs-lookup"><span data-stu-id="f3009-136">The `Async` module functions, which let you schedule asynchronous work, compose asynchronous computations, and transform asynchronous results.</span></span>
- <span data-ttu-id="f3009-137">`async { }`[計算式](../../language-reference/computation-expressions.md)は、非同期計算を構築および制御するための便利な構文を提供します。</span><span class="sxs-lookup"><span data-stu-id="f3009-137">The `async { }` [computation expression](../../language-reference/computation-expressions.md), which provides a convenient syntax for building and controlling asynchronous computations.</span></span>

<span data-ttu-id="f3009-138">次の例では、これら 3 つの概念を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-138">You can see these three concepts in the following example:</span></span>

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

<span data-ttu-id="f3009-139">この例では、`printTotalFileBytes`関数の型`string -> Async<unit>`は です。</span><span class="sxs-lookup"><span data-stu-id="f3009-139">In the example, the `printTotalFileBytes` function is of type `string -> Async<unit>`.</span></span> <span data-ttu-id="f3009-140">関数を呼び出しても、実際には非同期計算は実行されません。</span><span class="sxs-lookup"><span data-stu-id="f3009-140">Calling the function does not actually execute the asynchronous computation.</span></span> <span data-ttu-id="f3009-141">代わりに、非同期的`Async<unit>`に実行する作業の*仕様*として機能する を返します。</span><span class="sxs-lookup"><span data-stu-id="f3009-141">Instead, it returns an `Async<unit>` that acts as a *specification* of the work that is to execute asynchronously.</span></span> <span data-ttu-id="f3009-142">この関数`Async.AwaitTask`は、その本文を呼び出し、<xref:System.IO.File.ReadAllBytesAsync%2A>結果を適切な型に変換します。</span><span class="sxs-lookup"><span data-stu-id="f3009-142">It calls `Async.AwaitTask` in its body, which converts the result of <xref:System.IO.File.ReadAllBytesAsync%2A> to an appropriate type.</span></span>

<span data-ttu-id="f3009-143">もう 1 つの重要な`Async.RunSynchronously`行は、 への呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="f3009-143">Another important line is the call to `Async.RunSynchronously`.</span></span> <span data-ttu-id="f3009-144">これは、F# 非同期計算を実際に実行する場合に呼び出す必要がある Async モジュールの開始関数の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="f3009-144">This is one of the Async module starting functions that you'll need to call if you want to actually execute an F# asynchronous computation.</span></span>

<span data-ttu-id="f3009-145">これは、C# /Visual Basic のプログラミングスタイルと`async`の基本的な違いです。</span><span class="sxs-lookup"><span data-stu-id="f3009-145">This is a fundamental difference with the C#/Visual Basic style of `async` programming.</span></span> <span data-ttu-id="f3009-146">F# では、非同期計算は**Cold タスク**と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="f3009-146">In F#, asynchronous computations can be thought of as **Cold tasks**.</span></span> <span data-ttu-id="f3009-147">実際に実行するには、明示的に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-147">They must be explicitly started to actually execute.</span></span> <span data-ttu-id="f3009-148">C# や Visual Basic よりも簡単に非同期作業を組み合わせたり、シーケンス処理したりできるため、この方法には利点があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-148">This has some advantages, as it allows you to combine and sequence asynchronous work much more easily than in C# or Visual Basic.</span></span>

## <a name="combine-asynchronous-computations"></a><span data-ttu-id="f3009-149">非同期計算を組み合わせる</span><span class="sxs-lookup"><span data-stu-id="f3009-149">Combine asynchronous computations</span></span>

<span data-ttu-id="f3009-150">次に、計算を組み合わせて前の例に基づいて作成する例を示します。</span><span class="sxs-lookup"><span data-stu-id="f3009-150">Here is an example that builds upon the previous one by combining computations:</span></span>

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

<span data-ttu-id="f3009-151">ご覧のとおり、この`main`関数にはさらに多くの呼び出しが行われます。</span><span class="sxs-lookup"><span data-stu-id="f3009-151">As you can see, the `main` function has quite a few more calls made.</span></span> <span data-ttu-id="f3009-152">概念的には、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="f3009-152">Conceptually, it does the following:</span></span>

1. <span data-ttu-id="f3009-153">コマンド ライン引数を を`Async<unit>`使用して`Array.map`計算に変換します。</span><span class="sxs-lookup"><span data-stu-id="f3009-153">Transform the command-line arguments into `Async<unit>` computations with `Array.map`.</span></span>
2. <span data-ttu-id="f3009-154">実行時`Async<'T[]>`に計算を並列に`printTotalFileBytes`実行する を作成します。</span><span class="sxs-lookup"><span data-stu-id="f3009-154">Create an `Async<'T[]>` that schedules and runs the `printTotalFileBytes` computations in parallel when it runs.</span></span>
3. <span data-ttu-id="f3009-155">並列計算`Async<unit>`を実行し、その結果を無視する を作成します。</span><span class="sxs-lookup"><span data-stu-id="f3009-155">Create an `Async<unit>` that will run the parallel computation and ignore its result.</span></span>
4. <span data-ttu-id="f3009-156">最後の計算を明示的に実行`Async.RunSynchronously`し、最後の計算を完了するまでブロックします。</span><span class="sxs-lookup"><span data-stu-id="f3009-156">Explicitly run the last computation with `Async.RunSynchronously` and block until it completes.</span></span>

<span data-ttu-id="f3009-157">このプログラムを実行すると`printTotalFileBytes`、コマンド ライン引数ごとに並列実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-157">When this program runs, `printTotalFileBytes` runs in parallel for each command-line argument.</span></span> <span data-ttu-id="f3009-158">非同期計算はプログラム フローとは独立して実行されるため、情報を出力して実行を終了する順序はありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-158">Because asynchronous computations execute independently of program flow, there is no order in which they print their information and finish executing.</span></span> <span data-ttu-id="f3009-159">計算は並列にスケジュールされますが、実行順序は保証されません。</span><span class="sxs-lookup"><span data-stu-id="f3009-159">The computations will be scheduled in parallel, but their order of execution is not guaranteed.</span></span>

## <a name="sequence-asynchronous-computations"></a><span data-ttu-id="f3009-160">シーケンス非同期計算</span><span class="sxs-lookup"><span data-stu-id="f3009-160">Sequence asynchronous computations</span></span>

<span data-ttu-id="f3009-161">既`Async<'T>`に実行されているタスクではなく、作業の仕様であるため、複雑な変換を簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-161">Because `Async<'T>` is a specification of work rather than an already-running task, you can perform more intricate transformations easily.</span></span> <span data-ttu-id="f3009-162">次に、非同期計算のセットをシーケンスして、次の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3009-162">Here is an example that sequences a set of Async computations so they execute one after another.</span></span>

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
    |> Async.Ignore
    |> Async.RunSynchronously
    |> ignore
```

<span data-ttu-id="f3009-163">これは、並列`printTotalFileBytes`にスケジュールするのではなく、要素`argv`の順序で実行するようにスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="f3009-163">This will schedule `printTotalFileBytes` to execute in the order of the elements of `argv` rather than scheduling them in parallel.</span></span> <span data-ttu-id="f3009-164">次の項目は、最後の計算の実行が終了するまでスケジュールされないため、実行に重複がないように計算が順番に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-164">Because the next item will not be scheduled until after the last computation has finished executing, the computations are sequenced such that there is no overlap in their execution.</span></span>

## <a name="important-async-module-functions"></a><span data-ttu-id="f3009-165">重要な非同期モジュール関数</span><span class="sxs-lookup"><span data-stu-id="f3009-165">Important Async module functions</span></span>

<span data-ttu-id="f3009-166">F# で非同期コードを記述する場合、通常は計算のスケジューリングを処理するフレームワークと対話します。</span><span class="sxs-lookup"><span data-stu-id="f3009-166">When you write async code in F#, you'll usually interact with a framework that handles scheduling of computations for you.</span></span> <span data-ttu-id="f3009-167">ただし、必ずしもそうであるとは限らないので、非同期作業をスケジュールするさまざまな開始関数を学習することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3009-167">However, this is not always the case, so it is good to learn the various starting functions to schedule asynchronous work.</span></span>

<span data-ttu-id="f3009-168">F# 非同期計算は、既に実行されている作業の表現ではなく、作業の_仕様_であるため、開始関数を使用して明示的に開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-168">Because F# asynchronous computations are a _specification_ of work rather than a representation of work that is already executing, they must be explicitly started with a starting function.</span></span> <span data-ttu-id="f3009-169">さまざまなコンテキストで役立つ非同期[開始関数](https://msdn.microsoft.com/library/ee370232.aspx)が多数あります。</span><span class="sxs-lookup"><span data-stu-id="f3009-169">There are many [Async starting functions](https://msdn.microsoft.com/library/ee370232.aspx) that are helpful in different contexts.</span></span> <span data-ttu-id="f3009-170">次のセクションでは、一般的な開始関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="f3009-170">The following section describes some of the more common starting functions.</span></span>

### <a name="asyncstartchild"></a><span data-ttu-id="f3009-171">非同期.スタートチャイルド</span><span class="sxs-lookup"><span data-stu-id="f3009-171">Async.StartChild</span></span>

<span data-ttu-id="f3009-172">非同期計算内で子の計算を開始します。</span><span class="sxs-lookup"><span data-stu-id="f3009-172">Starts a child computation within an asynchronous computation.</span></span> <span data-ttu-id="f3009-173">これにより、複数の非同期計算を同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-173">This allows multiple asynchronous computations to be executed concurrently.</span></span> <span data-ttu-id="f3009-174">子計算は、親の計算とキャンセル トークンを共有します。</span><span class="sxs-lookup"><span data-stu-id="f3009-174">The child computation shares a cancellation token with the parent computation.</span></span> <span data-ttu-id="f3009-175">親の計算がキャンセルされた場合、子計算も取り消されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-175">If the parent computation is canceled, the child computation is also canceled.</span></span>

<span data-ttu-id="f3009-176">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-176">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int -> Async<Async<'T>>
```

<span data-ttu-id="f3009-177">使う状況:</span><span class="sxs-lookup"><span data-stu-id="f3009-177">When to use:</span></span>

- <span data-ttu-id="f3009-178">複数の非同期計算を同時に実行する場合は、同時に 1 つずつ実行するのではなく、並列にスケジュールを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-178">When you want to execute multiple asynchronous computations concurrently rather than one at a time, but not have them scheduled in parallel.</span></span>
- <span data-ttu-id="f3009-179">子計算の有効期間を親計算の有効期間に結び付ける場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-179">When you wish to tie the lifetime of a child computation to that of a parent computation.</span></span>

<span data-ttu-id="f3009-180">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-180">What to watch out for:</span></span>

- <span data-ttu-id="f3009-181">複数の計算を並列`Async.StartChild`に実行する場合と同じではありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-181">Starting multiple computations with `Async.StartChild` isn't the same as scheduling them in parallel.</span></span> <span data-ttu-id="f3009-182">計算を並列にスケジュールする場合は、 を`Async.Parallel`使用します。</span><span class="sxs-lookup"><span data-stu-id="f3009-182">If you wish to schedule computations in parallel, use `Async.Parallel`.</span></span>
- <span data-ttu-id="f3009-183">親計算をキャンセルすると、開始したすべての子計算のキャンセルがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="f3009-183">Canceling a parent computation will trigger cancellation of all child computations it started.</span></span>

### <a name="asyncstartimmediate"></a><span data-ttu-id="f3009-184">非同期.スタートイミディエイト</span><span class="sxs-lookup"><span data-stu-id="f3009-184">Async.StartImmediate</span></span>

<span data-ttu-id="f3009-185">非同期計算を実行し、現在のオペレーティング システムのスレッドですぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="f3009-185">Runs an asynchronous computation, starting immediately on the current operating system thread.</span></span> <span data-ttu-id="f3009-186">これは、計算中に呼び出し元のスレッドで何かを更新する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f3009-186">This is helpful if you need to update something on the calling thread during the computation.</span></span> <span data-ttu-id="f3009-187">たとえば、非同期計算で UI を更新する必要がある場合 (進行状況バーの更新など`Async.StartImmediate`)、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-187">For example, if an asynchronous computation must update a UI (such as updating a progress bar), then `Async.StartImmediate` should be used.</span></span>

<span data-ttu-id="f3009-188">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-188">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="f3009-189">使う状況:</span><span class="sxs-lookup"><span data-stu-id="f3009-189">When to use:</span></span>

- <span data-ttu-id="f3009-190">非同期計算の途中で呼び出し元スレッドで何かを更新する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-190">When you need to update something on the calling thread in the middle of an asynchronous computation.</span></span>

<span data-ttu-id="f3009-191">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-191">What to watch out for:</span></span>

- <span data-ttu-id="f3009-192">非同期計算のコードは、スケジュールされたスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-192">Code in the asynchronous computation will run on whatever thread one happens to be scheduled on.</span></span> <span data-ttu-id="f3009-193">これは、UI スレッドなど、何らかの形でスレッドが機密性の高い場合に問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-193">This can be problematic if that thread is in some way sensitive, such as a UI thread.</span></span> <span data-ttu-id="f3009-194">このような場合、`Async.StartImmediate`使用することは不適切である可能性が高い。</span><span class="sxs-lookup"><span data-stu-id="f3009-194">In such cases, `Async.StartImmediate` is likely inappropriate to use.</span></span>

### <a name="asyncstartastask"></a><span data-ttu-id="f3009-195">非同期.スタートタスタスク</span><span class="sxs-lookup"><span data-stu-id="f3009-195">Async.StartAsTask</span></span>

<span data-ttu-id="f3009-196">スレッド プールで計算を実行します。</span><span class="sxs-lookup"><span data-stu-id="f3009-196">Executes a computation in the thread pool.</span></span> <span data-ttu-id="f3009-197">計算<xref:System.Threading.Tasks.Task%601>が終了すると(結果が生成されるか、例外をスローするか、またはキャンセルされるか)、対応する状態で完了するを返します。</span><span class="sxs-lookup"><span data-stu-id="f3009-197">Returns a <xref:System.Threading.Tasks.Task%601> that will be completed on the corresponding state once the computation terminates (produces the result, throws exception, or gets canceled).</span></span> <span data-ttu-id="f3009-198">キャンセル トークンが指定されていない場合は、既定のキャンセル トークンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-198">If no cancellation token is provided, then the default cancellation token is used.</span></span>

<span data-ttu-id="f3009-199">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-199">Signature:</span></span>

```fsharp
computation: Async<'T> * taskCreationOptions: ?TaskCreationOptions * cancellationToken: ?CancellationToken -> Task<'T>
```

<span data-ttu-id="f3009-200">使う状況:</span><span class="sxs-lookup"><span data-stu-id="f3009-200">When to use:</span></span>

- <span data-ttu-id="f3009-201">非同期計算の結果を表すことを期待する .NET <xref:System.Threading.Tasks.Task%601> API を呼び出す必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-201">When you need to call into a .NET API that expects a <xref:System.Threading.Tasks.Task%601> to represent the result of an asynchronous computation.</span></span>

<span data-ttu-id="f3009-202">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-202">What to watch out for:</span></span>

- <span data-ttu-id="f3009-203">この呼び出しは`Task`追加のオブジェクトを割り当て、頻繁に使用する場合はオーバーヘッドを増加させます。</span><span class="sxs-lookup"><span data-stu-id="f3009-203">This call will allocate an additional `Task` object, which can increase overhead if it is used often.</span></span>

### <a name="asyncparallel"></a><span data-ttu-id="f3009-204">非同期.パラレル</span><span class="sxs-lookup"><span data-stu-id="f3009-204">Async.Parallel</span></span>

<span data-ttu-id="f3009-205">並列実行される非同期計算のシーケンスをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="f3009-205">Schedules a sequence of asynchronous computations to be executed in parallel.</span></span> <span data-ttu-id="f3009-206">並列処理の度合いは、`maxDegreesOfParallelism`パラメーターを指定することによって、必要に応じて調整/調整できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-206">The degree of parallelism can be optionally tuned/throttled by specifying the `maxDegreesOfParallelism` parameter.</span></span>

<span data-ttu-id="f3009-207">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-207">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> * ?maxDegreesOfParallelism: int -> Async<'T[]>
```

<span data-ttu-id="f3009-208">使用するタイミング:</span><span class="sxs-lookup"><span data-stu-id="f3009-208">When to use it:</span></span>

- <span data-ttu-id="f3009-209">一連の計算を同時に実行する必要があり、その実行順序に依存しない場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-209">If you need to run a set of computations at the same time and have no reliance on their order of execution.</span></span>
- <span data-ttu-id="f3009-210">並列にスケジュールされた計算の結果が完了するまで必要ない場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-210">If you don't require results from computations scheduled in parallel until they have all completed.</span></span>

<span data-ttu-id="f3009-211">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-211">What to watch out for:</span></span>

- <span data-ttu-id="f3009-212">すべての計算が完了した後にのみ、結果の値の配列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f3009-212">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="f3009-213">計算は、スケジュールが設定されるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-213">Computations will be run whenever they end up getting scheduled.</span></span> <span data-ttu-id="f3009-214">この動作は、実行順序に依存できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f3009-214">This behavior means you cannot rely on their order of their execution.</span></span>

### <a name="asyncsequential"></a><span data-ttu-id="f3009-215">非同期.シーケンシャル</span><span class="sxs-lookup"><span data-stu-id="f3009-215">Async.Sequential</span></span>

<span data-ttu-id="f3009-216">渡された順序で実行される非同期計算のシーケンスをスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="f3009-216">Schedules a sequence of asynchronous computations to be executed in the order that they are passed.</span></span> <span data-ttu-id="f3009-217">最初の計算が実行され、次に次の計算が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-217">The first computation will be executed, then the next, and so on.</span></span> <span data-ttu-id="f3009-218">並列計算は実行されません。</span><span class="sxs-lookup"><span data-stu-id="f3009-218">No computations will be executed in parallel.</span></span>

<span data-ttu-id="f3009-219">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-219">Signature:</span></span>

```fsharp
computations: seq<Async<'T>> -> Async<'T[]>
```

<span data-ttu-id="f3009-220">使用するタイミング:</span><span class="sxs-lookup"><span data-stu-id="f3009-220">When to use it:</span></span>

- <span data-ttu-id="f3009-221">複数の計算を順番に実行する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-221">If you need to execute multiple computations in order.</span></span>

<span data-ttu-id="f3009-222">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-222">What to watch out for:</span></span>

- <span data-ttu-id="f3009-223">すべての計算が完了した後にのみ、結果の値の配列にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f3009-223">You can only access the resulting array of values once all computations have finished.</span></span>
- <span data-ttu-id="f3009-224">計算はこの関数に渡された順序で実行されるため、結果が返されるまでの時間が増える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-224">Computations will be run in the order that they are passed to this function, which can mean that more time will elapse before the results are returned.</span></span>

### <a name="asyncawaittask"></a><span data-ttu-id="f3009-225">非同期.Awaitタスク</span><span class="sxs-lookup"><span data-stu-id="f3009-225">Async.AwaitTask</span></span>

<span data-ttu-id="f3009-226">指定<xref:System.Threading.Tasks.Task%601>された計算が完了するのを待ち、結果を`Async<'T>`</span><span class="sxs-lookup"><span data-stu-id="f3009-226">Returns an asynchronous computation that waits for the given <xref:System.Threading.Tasks.Task%601> to complete and returns its result as an `Async<'T>`</span></span>

<span data-ttu-id="f3009-227">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-227">Signature:</span></span>

```fsharp
task: Task<'T> -> Async<'T>
```

<span data-ttu-id="f3009-228">使う状況:</span><span class="sxs-lookup"><span data-stu-id="f3009-228">When to use:</span></span>

- <span data-ttu-id="f3009-229">F# の非同期計算内でを<xref:System.Threading.Tasks.Task%601>返す .NET API を使用している場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-229">When you are consuming a .NET API that returns a <xref:System.Threading.Tasks.Task%601> within an F# asynchronous computation.</span></span>

<span data-ttu-id="f3009-230">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-230">What to watch out for:</span></span>

- <span data-ttu-id="f3009-231">例外はタスク並列ライブラリ<xref:System.AggregateException>の規則に従ってラップされ、この動作は、F# 非同期が一般的に例外を表面化する方法とは異なります。</span><span class="sxs-lookup"><span data-stu-id="f3009-231">Exceptions are wrapped in <xref:System.AggregateException> following the convention of the Task Parallel Library, and this behavior is different from how F# async generally surfaces exceptions.</span></span>

### <a name="asynccatch"></a><span data-ttu-id="f3009-232">非同期キャッチ</span><span class="sxs-lookup"><span data-stu-id="f3009-232">Async.Catch</span></span>

<span data-ttu-id="f3009-233">指定`Async<'T>`された を実行する非同期計算を作成します`Async<Choice<'T, exn>>`。</span><span class="sxs-lookup"><span data-stu-id="f3009-233">Creates an asynchronous computation that executes a given `Async<'T>`, returning an `Async<Choice<'T, exn>>`.</span></span> <span data-ttu-id="f3009-234">指定`Async<'T>`された値が正常に完了すると、結果`Choice1Of2`の値を a が返されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-234">If the given `Async<'T>` completes successfully, then a `Choice1Of2` is returned with the resultant value.</span></span> <span data-ttu-id="f3009-235">例外が完了する前にスローされた場合、a`Choice2of2`が返され、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="f3009-235">If an exception is thrown before it completes, then a `Choice2of2` is returned with the raised exception.</span></span> <span data-ttu-id="f3009-236">それ自体が多くの計算で構成されている非同期計算で使用され、それらの計算の 1 つが例外をスローする場合、包含計算は完全に停止されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-236">If it is used on an asynchronous computation that is itself composed of many computations, and one of those computations throws an exception, the encompassing computation will be stopped entirely.</span></span>

<span data-ttu-id="f3009-237">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-237">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<Choice<'T, exn>>
```

<span data-ttu-id="f3009-238">使う状況:</span><span class="sxs-lookup"><span data-stu-id="f3009-238">When to use:</span></span>

- <span data-ttu-id="f3009-239">例外で失敗する可能性がある非同期作業を実行していて、呼び出し元でその例外を処理する場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-239">When you are performing asynchronous work that may fail with an exception and you want to handle that exception in the caller.</span></span>

<span data-ttu-id="f3009-240">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-240">What to watch out for:</span></span>

- <span data-ttu-id="f3009-241">結合された非同期計算または順序付き非同期計算を使用する場合、包含計算は、その「内部」計算の 1 つが例外をスローした場合に完全に停止します。</span><span class="sxs-lookup"><span data-stu-id="f3009-241">When using combined or sequenced asynchronous computations, the encompassing computation will fully stop if one of its "internal" computations throws an exception.</span></span>

### <a name="asyncignore"></a><span data-ttu-id="f3009-242">非同期.無視</span><span class="sxs-lookup"><span data-stu-id="f3009-242">Async.Ignore</span></span>

<span data-ttu-id="f3009-243">指定された計算を実行し、その結果を無視する非同期計算を作成します。</span><span class="sxs-lookup"><span data-stu-id="f3009-243">Creates an asynchronous computation that runs the given computation and ignores its result.</span></span>

<span data-ttu-id="f3009-244">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-244">Signature:</span></span>

```fsharp
computation: Async<'T> -> Async<unit>
```

<span data-ttu-id="f3009-245">使う状況:</span><span class="sxs-lookup"><span data-stu-id="f3009-245">When to use:</span></span>

- <span data-ttu-id="f3009-246">非同期計算の結果が不要な場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-246">When you have an asynchronous computation whose result is not needed.</span></span> <span data-ttu-id="f3009-247">これは、非同期ではないコードの`ignore`コードに似ています。</span><span class="sxs-lookup"><span data-stu-id="f3009-247">This is analogous to the `ignore` code for non-asynchronous code.</span></span>

<span data-ttu-id="f3009-248">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-248">What to watch out for:</span></span>

- <span data-ttu-id="f3009-249">を使用`Async.Ignore`する必要がある場合`Async.Start`や、 を必要とする別の`Async<unit>`関数を使用する必要がある場合は、結果を破棄しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-249">If you must use `Async.Ignore` because you wish to use `Async.Start` or another function that requires `Async<unit>`, consider if discarding the result is okay.</span></span> <span data-ttu-id="f3009-250">型シグネチャに適合するだけの結果を破棄しないようにします。</span><span class="sxs-lookup"><span data-stu-id="f3009-250">Avoid discarding results just to fit a type signature.</span></span>

### <a name="asyncrunsynchronously"></a><span data-ttu-id="f3009-251">同期.実行同期的に</span><span class="sxs-lookup"><span data-stu-id="f3009-251">Async.RunSynchronously</span></span>

<span data-ttu-id="f3009-252">非同期計算を実行し、呼び出し元のスレッドで結果を待機します。</span><span class="sxs-lookup"><span data-stu-id="f3009-252">Runs an asynchronous computation and awaits its result on the calling thread.</span></span> <span data-ttu-id="f3009-253">この呼び出しはブロックしています。</span><span class="sxs-lookup"><span data-stu-id="f3009-253">This call is blocking.</span></span>

<span data-ttu-id="f3009-254">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-254">Signature:</span></span>

```fsharp
computation: Async<'T> * timeout: ?int * cancellationToken: ?CancellationToken -> 'T
```

<span data-ttu-id="f3009-255">使用するタイミング:</span><span class="sxs-lookup"><span data-stu-id="f3009-255">When to use it:</span></span>

- <span data-ttu-id="f3009-256">必要な場合は、アプリケーション内で 1 回だけ使用します 。</span><span class="sxs-lookup"><span data-stu-id="f3009-256">If you need it, use it only once in an application - at the entry point for an executable.</span></span>
- <span data-ttu-id="f3009-257">パフォーマンスを気にしないで、他の一連の非同期操作を一度に実行する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="f3009-257">When you don't care about performance and want to execute a set of other asynchronous operations at once.</span></span>

<span data-ttu-id="f3009-258">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-258">What to watch out for:</span></span>

- <span data-ttu-id="f3009-259">呼`Async.RunSynchronously`び出しは、実行が完了するまで呼び出しスレッドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="f3009-259">Calling `Async.RunSynchronously` blocks the calling thread until the execution completes.</span></span>

### <a name="asyncstart"></a><span data-ttu-id="f3009-260">非同期.開始</span><span class="sxs-lookup"><span data-stu-id="f3009-260">Async.Start</span></span>

<span data-ttu-id="f3009-261">を返`unit`すスレッド プールで非同期計算を開始します。</span><span class="sxs-lookup"><span data-stu-id="f3009-261">Starts an asynchronous computation in the thread pool that returns `unit`.</span></span> <span data-ttu-id="f3009-262">結果を待ちません。</span><span class="sxs-lookup"><span data-stu-id="f3009-262">Doesn't wait for its result.</span></span> <span data-ttu-id="f3009-263">で`Async.Start`開始された入れ子になった計算は、それを呼び出した親の計算とは無関係に開始されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-263">Nested computations started with `Async.Start` are started independently of the parent computation that called them.</span></span> <span data-ttu-id="f3009-264">その有効期間は、親の計算に関連付けられてはいません。</span><span class="sxs-lookup"><span data-stu-id="f3009-264">Their lifetime is not tied to any parent computation.</span></span> <span data-ttu-id="f3009-265">親の計算がキャンセルされた場合、子の計算は取り消されません。</span><span class="sxs-lookup"><span data-stu-id="f3009-265">If the parent computation is canceled, no child computations are canceled.</span></span>

<span data-ttu-id="f3009-266">署名:</span><span class="sxs-lookup"><span data-stu-id="f3009-266">Signature:</span></span>

```fsharp
computation: Async<unit> * cancellationToken: ?CancellationToken -> unit
```

<span data-ttu-id="f3009-267">次の場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="f3009-267">Use only when:</span></span>

- <span data-ttu-id="f3009-268">非同期計算では、結果が得られないか、処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="f3009-268">You have an asynchronous computation that doesn't yield a result and/or require processing of one.</span></span>
- <span data-ttu-id="f3009-269">非同期計算がいつ完了したのか知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-269">You don't need to know when an asynchronous computation completes.</span></span>
- <span data-ttu-id="f3009-270">非同期計算が実行されるスレッドは気にしません。</span><span class="sxs-lookup"><span data-stu-id="f3009-270">You don't care which thread an asynchronous computation runs on.</span></span>
- <span data-ttu-id="f3009-271">タスクの結果として生じる例外を認識したり報告したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-271">You don't have any need to be aware of or report exceptions resulting from the task.</span></span>

<span data-ttu-id="f3009-272">注意すべきこと:</span><span class="sxs-lookup"><span data-stu-id="f3009-272">What to watch out for:</span></span>

- <span data-ttu-id="f3009-273">で開始された計算によって発生した例外`Async.Start`は、呼び出し元に伝達されません。</span><span class="sxs-lookup"><span data-stu-id="f3009-273">Exceptions raised by computations started with `Async.Start` aren't propagated to the caller.</span></span> <span data-ttu-id="f3009-274">呼び出し履歴は完全に巻き戻されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-274">The call stack will be completely unwound.</span></span>
- <span data-ttu-id="f3009-275">呼び出し`printfn``Async.Start`など、すべての作業は、プログラムの実行のメイン スレッドで発生する影響を発生しません。</span><span class="sxs-lookup"><span data-stu-id="f3009-275">Any work (such as calling `printfn`) started with `Async.Start` won't cause the effect to happen on the main thread of a program's execution.</span></span>

## <a name="interoperate-with-net"></a><span data-ttu-id="f3009-276">NET との相互運用</span><span class="sxs-lookup"><span data-stu-id="f3009-276">Interoperate with .NET</span></span>

<span data-ttu-id="f3009-277">[非同期/await](../../../standard/async.md)スタイルの非同期プログラミングを使用する .NET ライブラリまたは C# コードベースを使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-277">You may be working with a .NET library or C# codebase that uses [async/await](../../../standard/async.md)-style asynchronous programming.</span></span> <span data-ttu-id="f3009-278">C# と大部分の .NET ライブラリでは<xref:System.Threading.Tasks.Task%601>、<xref:System.Threading.Tasks.Task>と の型を使用するのではなく`Async<'T>`、コアの抽象化として使用するため、非同期処理にはこれら 2 つのアプローチの境界を越える必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-278">Because C# and the majority of .NET libraries use the <xref:System.Threading.Tasks.Task%601> and <xref:System.Threading.Tasks.Task> types as their core abstractions rather than `Async<'T>`, you must cross a boundary between these two approaches to asynchrony.</span></span>

### <a name="how-to-work-with-net-async-and-taskt"></a><span data-ttu-id="f3009-279">NET 非同期と .NET の使用方法`Task<T>`</span><span class="sxs-lookup"><span data-stu-id="f3009-279">How to work with .NET async and `Task<T>`</span></span>

<span data-ttu-id="f3009-280">NET 非同期ライブラリとコードベースを使用<xref:System.Threading.Tasks.Task%601>する (つまり、戻り値を持つ非同期計算) は簡単で、F# でサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f3009-280">Working with .NET async libraries and codebases that use <xref:System.Threading.Tasks.Task%601> (that is, async computations that have return values) is straightforward and has built-in support with F#.</span></span>

<span data-ttu-id="f3009-281">この関数を`Async.AwaitTask`使用して、.NET 非同期計算を待機できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-281">You can use the `Async.AwaitTask` function to await a .NET asynchronous computation:</span></span>

```fsharp
let getValueFromLibrary param =
    async {
        let! value = DotNetLibrary.GetValueAsync param |> Async.AwaitTask
        return value
    }
```

<span data-ttu-id="f3009-282">この関数を`Async.StartAsTask`使用して、非同期計算を .NET 呼び出し元に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f3009-282">You can use the `Async.StartAsTask` function to pass an asynchronous computation to a .NET caller:</span></span>

```fsharp
let computationForCaller param =
    async {
        let! result = getAsyncResult param
        return result
    } |> Async.StartAsTask
```

### <a name="how-to-work-with-net-async-and-task"></a><span data-ttu-id="f3009-283">NET 非同期と .NET の使用方法`Task`</span><span class="sxs-lookup"><span data-stu-id="f3009-283">How to work with .NET async and `Task`</span></span>

<span data-ttu-id="f3009-284">を使用<xref:System.Threading.Tasks.Task>する API (つまり、値を返さない .NET 非同期計算) を使用するには、 を`Async<'T>`に変換する関数を追加する必要がある場合<xref:System.Threading.Tasks.Task>があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-284">To work with APIs that use <xref:System.Threading.Tasks.Task> (that is, .NET async computations that do not return a value), you may need to add an additional function that will convert an `Async<'T>` to a <xref:System.Threading.Tasks.Task>:</span></span>

```fsharp
module Async =
    // Async<unit> -> Task
    let startTaskFromAsyncUnit (comp: Async<unit>) =
        Async.StartAsTask comp :> Task
```

<span data-ttu-id="f3009-285">as 入力を`Async.AwaitTask`受け入れる<xref:System.Threading.Tasks.Task>ものが既にあります。</span><span class="sxs-lookup"><span data-stu-id="f3009-285">There is already an `Async.AwaitTask` that accepts a <xref:System.Threading.Tasks.Task> as input.</span></span> <span data-ttu-id="f3009-286">これと以前に定義`startTaskFromAsyncUnit`した関数を使用すると、F#<xref:System.Threading.Tasks.Task>非同期計算から型を開始し、待機できます。</span><span class="sxs-lookup"><span data-stu-id="f3009-286">With this and the previously defined `startTaskFromAsyncUnit` function, you can start and await <xref:System.Threading.Tasks.Task> types from an F# async computation.</span></span>

## <a name="relationship-to-multi-threading"></a><span data-ttu-id="f3009-287">マルチスレッドとの関係</span><span class="sxs-lookup"><span data-stu-id="f3009-287">Relationship to multi-threading</span></span>

<span data-ttu-id="f3009-288">この記事ではスレッド処理について説明していますが、注意が必要な 2 つの点があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-288">Although threading is mentioned throughout this article, there are two important things to remember:</span></span>

1. <span data-ttu-id="f3009-289">現在のスレッドで明示的に開始しない限り、非同期計算とスレッドの間には関係性がありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-289">There is no affinity between an asynchronous computation and a thread, unless explicitly started on the current thread.</span></span>
1. <span data-ttu-id="f3009-290">F# の非同期プログラミングは、マルチスレッドの抽象化ではありません。</span><span class="sxs-lookup"><span data-stu-id="f3009-290">Asynchronous programming in F# is not an abstraction for multi-threading.</span></span>

<span data-ttu-id="f3009-291">たとえば、計算は、実際には、作業の性質に応じて、その呼び出し元のスレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f3009-291">For example, a computation may actually run on its caller's thread, depending on the nature of the work.</span></span> <span data-ttu-id="f3009-292">計算は、スレッド間で「ジャンプ」し、スレッドを少しの時間借りて、"待機中" の期間 (ネットワーク呼び出しが転送中の場合など) の間に有益な作業を行う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3009-292">A computation could also "jump" between threads, borrowing them for a small amount of time to do useful work in between periods of "waiting" (such as when a network call is in transit).</span></span>

<span data-ttu-id="f3009-293">F# には、現在のスレッドで非同期計算を開始する機能がいくつか用意されていますが (明示的に現在のスレッドでは使用できません)、非同期は通常、特定のスレッド化戦略に関連付けらされていません。</span><span class="sxs-lookup"><span data-stu-id="f3009-293">Although F# provides some abilities to start an asynchronous computation on the current thread (or explicitly not on the current thread), asynchrony generally is not associated with a particular threading strategy.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3009-294">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3009-294">See also</span></span>

- [<span data-ttu-id="f3009-295">F# 非同期プログラミング モデル</span><span class="sxs-lookup"><span data-stu-id="f3009-295">The F# Asynchronous Programming Model</span></span>](https://www.microsoft.com/research/publication/the-f-asynchronous-programming-model)
- [<span data-ttu-id="f3009-296">Jet.com の F# 非同期ガイド</span><span class="sxs-lookup"><span data-stu-id="f3009-296">Jet.com's F# Async Guide</span></span>](https://medium.com/jettech/f-async-guide-eb3c8a2d180a)
- [<span data-ttu-id="f3009-297">F# の楽しさと利益の非同期プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f3009-297">F# for fun and profit's Asynchronous Programming guide</span></span>](https://fsharpforfunandprofit.com/posts/concurrency-async-and-parallel/)
- [<span data-ttu-id="f3009-298">C# と F# の非同期: C の非同期の問題#</span><span class="sxs-lookup"><span data-stu-id="f3009-298">Async in C# and F#: Asynchronous gotchas in C#</span></span>](http://tomasp.net/blog/csharp-async-gotchas.aspx/)
