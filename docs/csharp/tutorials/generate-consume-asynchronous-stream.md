---
title: 非同期ストリームの生成と使用
description: この高度なチュートリアルでは、非同期ストリームの生成と使用により、非同期で生成できるデータ シーケンスをより自然な方法で操作するシナリオを示します。
ms.date: 02/10/2019
ms.custom: mvc
ms.openlocfilehash: 04c4fe1c7e33138273c5b49c6985efc60767a724
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216554"
---
# <a name="tutorial-generate-and-consume-async-streams-using-c-80-and-net-core-30"></a><span data-ttu-id="e6663-103">チュートリアル: C#8.0 および .NET Core 3.0 を使用して非同期ストリームを生成および使用する</span><span class="sxs-lookup"><span data-stu-id="e6663-103">Tutorial: Generate and consume async streams using C# 8.0 and .NET Core 3.0</span></span>

<span data-ttu-id="e6663-104">C#8.0 では、データ ストリーム内の要素を非同期で取得または生成できる場合にデータのストリーミング ソースをモデル化する**非同期ストリーム**が導入されています。</span><span class="sxs-lookup"><span data-stu-id="e6663-104">C# 8.0 introduces **async streams**, which model a streaming source of data when the elements in the data stream may be retrieved or generated asynchronously.</span></span> <span data-ttu-id="e6663-105">非同期ストリームは、.NET Standard 2.1 で導入され、.NET Core 3.0 で実装された新しいインターフェイスに依存して、非同期ストリーミング データ ソース用の自然なプログラミング モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="e6663-105">Async streams rely on new interfaces introduced in .NET Standard 2.1 and implemented in .NET Core 3.0 to provide a natural programming model for asynchronous streaming data sources.</span></span>

<span data-ttu-id="e6663-106">このチュートリアルでは、次の作業を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e6663-106">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="e6663-107">データ要素のシーケンスを非同期で生成するデータ ソースを作成します。</span><span class="sxs-lookup"><span data-stu-id="e6663-107">Create a data source that generates a sequence of data elements asynchronously.</span></span>
> - <span data-ttu-id="e6663-108">そのデータ ソースを非同期で使用します。</span><span class="sxs-lookup"><span data-stu-id="e6663-108">Consume that data source asynchronously.</span></span>
> - <span data-ttu-id="e6663-109">新しいインターフェイスとデータ ソースが以前の同期データ シーケンスより優先される場合を認識します。</span><span class="sxs-lookup"><span data-stu-id="e6663-109">Recognize when the new interface and data source are preferred to earlier synchronous data sequences.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6663-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e6663-110">Prerequisites</span></span>

<span data-ttu-id="e6663-111">お使いのコンピューターを、.NET Core が実行されるように設定する必要があります。C# 8.0 コンパイラも実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="e6663-111">You’ll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="e6663-112">C# 8 コンパイラは [Visual Studio 2019 バージョン 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) または [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) 以降で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-112">The C# 8 compiler is available starting with [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="e6663-113">[GitHub アクセス トークン](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token)を作成して、GitHub GraphQL エンドポイントにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6663-113">You'll need to create a [GitHub access token](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/#creating-a-token) so that you can access the GitHub GraphQL endpoint.</span></span> <span data-ttu-id="e6663-114">GitHub アクセス トークンに対して次のアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6663-114">Select the following permissions for your GitHub Access Token:</span></span>

- <span data-ttu-id="e6663-115">repo:status</span><span class="sxs-lookup"><span data-stu-id="e6663-115">repo:status</span></span>
- <span data-ttu-id="e6663-116">public_repo</span><span class="sxs-lookup"><span data-stu-id="e6663-116">public_repo</span></span>

<span data-ttu-id="e6663-117">アクセス トークンを安全な場所に保存して、GitHub API エンドポイントへのアクセス権を得るために使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e6663-117">Save the access token in a safe place so you can use it to gain access to the GitHub API endpoint.</span></span>

> [!WARNING]
> <span data-ttu-id="e6663-118">自分の個人用アクセス トークンをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="e6663-118">Keep your personal access token secure.</span></span> <span data-ttu-id="e6663-119">個人用アクセス トークンを使用するソフトウェアでは、ユーザーのアクセス権を使用して GitHub API 呼び出しが行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e6663-119">Any software with your personal access token could make GitHub API calls using your access rights.</span></span>

<span data-ttu-id="e6663-120">このチュートリアルでは、.NET と、C# と Visual Studio または .NET Core CLI のいずれかに精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e6663-120">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="run-the-starter-application"></a><span data-ttu-id="e6663-121">初期アプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="e6663-121">Run the starter application</span></span>

<span data-ttu-id="e6663-122">このチュートリアルで使用される初期アプリケーションのコードは、[csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) フォルダー内の [dotnet/samples](https://github.com/dotnet/samples) リポジトリから取得できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-122">You can get the code for the starter application used in this tutorial from our [dotnet/samples](https://github.com/dotnet/samples) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/start) folder.</span></span>

<span data-ttu-id="e6663-123">初期アプリケーションは、[GitHub GraphQL](https://developer.github.com/v4/) インターフェイスを使用して、[dotnet/docs](https://github.com/dotnet/docs) リポジトリに書き込まれた最近の問題を取得するコンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="e6663-123">The starter application is a console application that uses the [GitHub GraphQL](https://developer.github.com/v4/) interface to retrieve recent issues written in the [dotnet/docs](https://github.com/dotnet/docs) repository.</span></span> <span data-ttu-id="e6663-124">まず、初期アプリの `Main` メソッドについて次のコードを参照します。</span><span class="sxs-lookup"><span data-stu-id="e6663-124">Start by looking at the following code for the starter app `Main` method:</span></span>

[!code-csharp[StarterAppMain](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#StarterAppMain)]

<span data-ttu-id="e6663-125">`GitHubKey` 環境変数を自分の個人用アクセス トークンに設定するか、`GenEnvVariable` への呼び出しの最後の引数を自分の個人用アクセス トークンで置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="e6663-125">You can either set a `GitHubKey` environment variable to your personal access token, or you can replace the last argument in the call to `GenEnvVariable` with your personal access token.</span></span> <span data-ttu-id="e6663-126">ソースを他のユーザーと共同で保存したり、共有ソース リポジトリに入れたりする場合は、ソース コードにアクセス コードを入れないでください。</span><span class="sxs-lookup"><span data-stu-id="e6663-126">Don't put your access code in source code if you'll be saving the source with others, or putting it in a shared source repository.</span></span>

<span data-ttu-id="e6663-127">GitHub クライアントの作成後に、`Main` 内のコードによって進行状況レポート オブジェクトとキャンセル トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-127">After creating the GitHub client, the code in `Main` creates a progress reporting object and a cancellation token.</span></span> <span data-ttu-id="e6663-128">これらのオブジェクトが作成されると、`Main` によって `runPagedQueryAsync` が呼び出されて、作成された直近 250 件の問題が取得されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-128">Once those objects are created, `Main` calls `runPagedQueryAsync` to retrieve the most recent 250 created issues.</span></span> <span data-ttu-id="e6663-129">そのタスクが完了すると、結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-129">After that task has finished, the results are displayed.</span></span>

<span data-ttu-id="e6663-130">初期アプリケーションを実行するときに、このアプリケーションの実行方法についていくつかの重要な観察を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e6663-130">When you run the starter application, you can make some important observations about how this application runs.</span></span>  <span data-ttu-id="e6663-131">GitHub から返される各ページについてレポートされる進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6663-131">You'll see progress reported for each page returned from GitHub.</span></span> <span data-ttu-id="e6663-132">問題の新しい各ページが GitHub から返される前に、注目すべき一時停止を観察できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-132">You can observe a noticeable pause before GitHub returns each new page of issues.</span></span> <span data-ttu-id="e6663-133">最後に、問題は GitHub から 10 ページすべてが取得された後にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-133">Finally, the issues are displayed only after all 10 pages have been retrieved from GitHub.</span></span>

## <a name="examine-the-implementation"></a><span data-ttu-id="e6663-134">実装を調べる</span><span class="sxs-lookup"><span data-stu-id="e6663-134">Examine the implementation</span></span>

<span data-ttu-id="e6663-135">実装では、前のセクションで説明した動作を観察した理由が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="e6663-135">The implementation reveals why you observed the behavior discussed in the previous section.</span></span> <span data-ttu-id="e6663-136">`runPagedQueryAsync` のコードを調べます:</span><span class="sxs-lookup"><span data-stu-id="e6663-136">Examine the code for `runPagedQueryAsync`:</span></span>

[!code-csharp[RunPagedQueryStarter](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#RunPagedQuery)]

<span data-ttu-id="e6663-137">上記のコードのページング アルゴリズムと非同期構造体に注目してみましょう。</span><span class="sxs-lookup"><span data-stu-id="e6663-137">Let's concentrate on the paging algorithm and async structure of the preceding code.</span></span> <span data-ttu-id="e6663-138">(GitHub GraphQL API について詳しくは、[GitHub GraphQL のドキュメント](https://developer.github.com/v4/guides/)をご覧ください。)`runPagedQueryAsync` メソッドでは、問題が新しい順に列挙されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-138">(You can consult the [GitHub GraphQL documentation](https://developer.github.com/v4/guides/) for details on the GitHub GraphQL API.) The `runPagedQueryAsync` method enumerates the issues from most recent to oldest.</span></span> <span data-ttu-id="e6663-139">1 ページあたり 25 件の問題を要求し、応答の `pageInfo` 構造体を調べて前のページに進みます。</span><span class="sxs-lookup"><span data-stu-id="e6663-139">It requests 25 issues per page and examines the `pageInfo` structure of the response to continue with the previous page.</span></span> <span data-ttu-id="e6663-140">次の GraphQL の標準的なページングでは、複数ページの応答がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6663-140">That follows GraphQL's standard paging support for multi-page responses.</span></span> <span data-ttu-id="e6663-141">応答には、前のページを要求するために使用される `hasPreviousPages` 値と `startCursor` 値を含む `pageInfo` オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e6663-141">The response includes a `pageInfo` object that includes a `hasPreviousPages` value and a `startCursor` value used to request the previous page.</span></span> <span data-ttu-id="e6663-142">問題は `nodes` 配列内にあります。</span><span class="sxs-lookup"><span data-stu-id="e6663-142">The issues are in the `nodes` array.</span></span> <span data-ttu-id="e6663-143">`runPagedQueryAsync` メソッドでは、すべてのページからのすべての結果を格納する配列にこれらのノードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-143">The `runPagedQueryAsync` method appends these nodes to an array that contains all the results from all pages.</span></span>

<span data-ttu-id="e6663-144">結果のページを取得し、復元した後、`runPagedQueryAsync` によって進行状況がレポートされ、キャンセルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="e6663-144">After retrieving and restoring a page of results, `runPagedQueryAsync` reports progress and checks for cancellation.</span></span> <span data-ttu-id="e6663-145">キャンセルが要求されている場合は、`runPagedQueryAsync` によって <xref:System.OperationCanceledException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e6663-145">If cancellation has been requested, `runPagedQueryAsync` throws an <xref:System.OperationCanceledException>.</span></span>

<span data-ttu-id="e6663-146">このコードには、改善できる要素がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e6663-146">There are several elements in this code that can be improved.</span></span> <span data-ttu-id="e6663-147">最も重要なものとして、`runPagedQueryAsync` では返されるすべての問題に記憶域を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6663-147">Most importantly, `runPagedQueryAsync` must allocate storage for all the issues returned.</span></span> <span data-ttu-id="e6663-148">未解決の問題をすべて取得するには、取得したすべての問題を格納するためにはるかに多くのメモリが必要になるので、このサンプルは 250 件の問題で停止します。</span><span class="sxs-lookup"><span data-stu-id="e6663-148">This sample stops at 250 issues because retrieving all open issues would require much more memory to store all the retrieved issues.</span></span> <span data-ttu-id="e6663-149">また、進行状況のサポートとキャンセルのサポートのプロトコルにより、アルゴリズムを初めて読んだ時点で理解することが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="e6663-149">In addition, the protocols for supporting progress and supporting cancellation make the algorithm harder to understand on its first reading.</span></span> <span data-ttu-id="e6663-150">進行状況クラスを検索して、進行状況がレポートされている場所を見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6663-150">You must look for the progress class to find where progress is reported.</span></span> <span data-ttu-id="e6663-151"><xref:System.Threading.CancellationTokenSource> とそれに関連付けられた <xref:System.Threading.CancellationToken> を通じた通信をトレースして、キャンセルが要求されている場所と、付与されている場所を理解する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="e6663-151">You also have to trace the communications through the <xref:System.Threading.CancellationTokenSource> and its associated <xref:System.Threading.CancellationToken> to understand where cancellation is requested and where it's granted.</span></span>

## <a name="async-streams-provide-a-better-way"></a><span data-ttu-id="e6663-152">非同期ストリームではより優れた方法が提供される</span><span class="sxs-lookup"><span data-stu-id="e6663-152">Async streams provide a better way</span></span>

<span data-ttu-id="e6663-153">非同期ストリームおよび関連付けられている言語サポートは、これらすべての問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="e6663-153">Async streams and the associated language support address all those concerns.</span></span> <span data-ttu-id="e6663-154">シーケンスを生成するコードでは、`yield return` を使用して、`async` 修飾子で宣言されたメソッド内で要素を返せるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e6663-154">The code that generates the sequence can now use `yield return` to return elements in a method that was declared with the `async` modifier.</span></span> <span data-ttu-id="e6663-155">`foreach` ループを使用してシーケンスを使用する場合と同様に、`await foreach` ループを使用して非同期ストリームを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e6663-155">You can consume an async stream using an `await foreach` loop just as you consume any sequence using a `foreach` loop.</span></span>

<span data-ttu-id="e6663-156">これらの新しい言語機能は、.NET Standard 2.1 に追加され、.NET Core 3.0 で実装された 3 つの新しいインターフェイスに依存します。</span><span class="sxs-lookup"><span data-stu-id="e6663-156">These new language features depend on three new interfaces added to .NET Standard 2.1 and implemented in .NET Core 3.0:</span></span>

```csharp
namespace System.Collections.Generic
{
    public interface IAsyncEnumerable<out T>
    {
        IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default);
    }

    public interface IAsyncEnumerator<out T> : IAsyncDisposable
    {
        T Current { get; }

        ValueTask<bool> MoveNextAsync();
    }
}

namespace System
{
    public interface IAsyncDisposable
    {
        ValueTask DisposeAsync();
    }
}
```

<span data-ttu-id="e6663-157">この 3 つのインターフェイスは、ほとんどの C# 開発者にとって見慣れたものです。</span><span class="sxs-lookup"><span data-stu-id="e6663-157">These three interfaces should be familiar to most C# developers.</span></span> <span data-ttu-id="e6663-158">これらは、同期版と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="e6663-158">They behave in a manner similar to their synchronous counterparts:</span></span>

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.IEnumerator%601?displayProperty=nameWithType>
- <xref:System.IDisposable?displayProperty=nameWithType>

<span data-ttu-id="e6663-159">見慣れない可能性のある 1 つの型は <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType> です。</span><span class="sxs-lookup"><span data-stu-id="e6663-159">One type that may be unfamiliar is <xref:System.Threading.Tasks.ValueTask?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e6663-160">`ValueTask` 構造体では、<xref:System.Threading.Tasks.Task?displayProperty=nameWithType> クラスと同様の API が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-160">The `ValueTask` struct provides a similar API to the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="e6663-161">パフォーマンス上の理由から、これらのインターフェイスでは `ValueTask` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-161">`ValueTask` is used in these interfaces for performance reasons.</span></span>

## <a name="convert-to-async-streams"></a><span data-ttu-id="e6663-162">非同期ストリームに変換する</span><span class="sxs-lookup"><span data-stu-id="e6663-162">Convert to async streams</span></span>

<span data-ttu-id="e6663-163">次に、`runPagedQueryAsync` メソッドを変換して非同期ストリームを生成します。</span><span class="sxs-lookup"><span data-stu-id="e6663-163">Next, convert the `runPagedQueryAsync` method to generate an async stream.</span></span> <span data-ttu-id="e6663-164">まず、`IAsyncEnumerable<JToken>` を返すように `runPagedQueryAsync` のシグネチャを変更し、次のコードに示すように、パラメーター リストからキャンセル トークンと進行状況オブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="e6663-164">First, change the signature of `runPagedQueryAsync` to return an `IAsyncEnumerable<JToken>`, and remove the cancellation token and progress objects from the parameter list as shown in the following code:</span></span>

[!code-csharp[FinishedSignature](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#UpdateSignature)]

<span data-ttu-id="e6663-165">次のコードに示すように、初期コードではページが取得されると各ページが処理されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-165">The starter code processes each page as the page is retrieved, as shown in the following code:</span></span>

[!code-csharp[StarterPaging](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#ProcessPage)]

<span data-ttu-id="e6663-166">この 3 行を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e6663-166">Replace those three lines with the following code:</span></span>

[!code-csharp[FinishedPaging](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#YieldReturnPage)]

<span data-ttu-id="e6663-167">このメソッドの前の方にある `finalResults` の宣言と、変更したループに続く `return` ステートメントを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e6663-167">You can also remove the declaration of `finalResults` earlier in this method and the `return` statement that follows the loop you modified.</span></span>

<span data-ttu-id="e6663-168">非同期ストリームを生成するための変更が完了しました。</span><span class="sxs-lookup"><span data-stu-id="e6663-168">You've finished the changes to generate an async stream.</span></span> <span data-ttu-id="e6663-169">完成したメソッドは、次のコードのようになります。</span><span class="sxs-lookup"><span data-stu-id="e6663-169">The finished method should resemble the code below:</span></span>

[!code-csharp[FinishedGenerate](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#GenerateAsyncStream)]

<span data-ttu-id="e6663-170">次に、コレクションを使用するコードを変更して、非同期ストリームを使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="e6663-170">Next, you change the code that consumes the collection to consume the async stream.</span></span> <span data-ttu-id="e6663-171">`Main` 内で、問題のコレクションを処理する次のコードを探します。</span><span class="sxs-lookup"><span data-stu-id="e6663-171">Find the following code in `Main` that processes the collection of issues:</span></span>

[!code-csharp[EnumerateOldStyle](~/samples/csharp/tutorials/AsyncStreams/start/IssuePRreport/IssuePRreport/Program.cs#EnumerateOldStyle)]

<span data-ttu-id="e6663-172">このコードを次の `await foreach` ループに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e6663-172">Replace that code with the following `await foreach` loop:</span></span>

[!code-csharp[FinishedEnumerateAsyncStream](~/samples/csharp/tutorials/AsyncStreams/finished/IssuePRreport/IssuePRreport/Program.cs#EnumerateAsyncStream)]

<span data-ttu-id="e6663-173">完了したチュートリアルのコードは、[csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) フォルダー内の [dotnet/samples](https://github.com/dotnet/samples) リポジトリから取得できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-173">You can get the code for the finished tutorial from the [dotnet/samples](https://github.com/dotnet/samples) repository in the [csharp/tutorials/AsyncStreams](https://github.com/dotnet/samples/tree/master/csharp/tutorials/AsyncStreams/finished) folder.</span></span>

## <a name="run-the-finished-application"></a><span data-ttu-id="e6663-174">完成したアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="e6663-174">Run the finished application</span></span>

<span data-ttu-id="e6663-175">アプリケーションをもう一度実行します。</span><span class="sxs-lookup"><span data-stu-id="e6663-175">Run the application again.</span></span> <span data-ttu-id="e6663-176">その動作を初期アプリケーションの動作と比較します。</span><span class="sxs-lookup"><span data-stu-id="e6663-176">Contrast its behavior with the behavior of the starter application.</span></span> <span data-ttu-id="e6663-177">結果の最初のページは、使用可能になるとすぐに列挙されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-177">The first page of results is enumerated as soon as it's available.</span></span> <span data-ttu-id="e6663-178">新しい各ページが要求され、取得されるときに観測可能な一時停止があり、次のページの結果がすぐに列挙されます。</span><span class="sxs-lookup"><span data-stu-id="e6663-178">There's an observable pause as each new page is requested and retrieved, then the next page's results are quickly enumerated.</span></span> <span data-ttu-id="e6663-179">`try` / `catch` ブロックではキャンセルを処理する必要はありません。呼び出し元がコレクションの列挙を停止できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-179">The `try` / `catch` block isn't needed to handle cancellation: the caller can stop enumerating the collection.</span></span> <span data-ttu-id="e6663-180">各ページがダウンロードされるときに非同期ストリームによって結果が生成されるので、進行状況が明確にレポートされます。</span><span class="sxs-lookup"><span data-stu-id="e6663-180">Progress is clearly reported because the async stream generates results as each page is downloaded.</span></span>

<span data-ttu-id="e6663-181">コードを調べることで、メモリの改善を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-181">You can see improvements in memory use by examining the code.</span></span> <span data-ttu-id="e6663-182">すべての結果が列挙される前にそれらを格納するコレクションを割り当てる必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="e6663-182">You no longer need to allocate a collection to store all the results before they're enumerated.</span></span> <span data-ttu-id="e6663-183">呼び出し元では、結果を使用する方法、および記憶域のコレクションが必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-183">The caller can determine how to consume the results and if a storage collection is needed.</span></span>

<span data-ttu-id="e6663-184">初期アプリケーションと完成したアプリケーションの両方を実行し、実装間の違いを自分で確認できます。</span><span class="sxs-lookup"><span data-stu-id="e6663-184">Run both the starter and finished applications and you can observe the differences between the implementations for yourself.</span></span> <span data-ttu-id="e6663-185">完了後に、このチュートリアルの開始時に作成した GitHub アクセス トークンを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e6663-185">You can delete the GitHub access token you created when you started this tutorial after you've finished.</span></span> <span data-ttu-id="e6663-186">攻撃者は、そのトークンへのアクセス権を獲得すると、ユーザーの資格情報を使用して GitHub API にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e6663-186">If an attacker gained access to that token, they could access GitHub APIs using your credentials.</span></span>
