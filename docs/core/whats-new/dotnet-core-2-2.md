---
title: .NET Core 2.2 の新機能
description: .NET Core 2.2 の新機能について。
dev_langs:
- csharp
- vb
ms.date: 12/04/2018
ms.openlocfilehash: e045c39240c99777d05ca86ee0a8cd1fa4309c4f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156583"
---
# <a name="whats-new-in-net-core-22"></a><span data-ttu-id="2ed88-103">.NET Core 2.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="2ed88-103">What's new in .NET Core 2.2</span></span>

<span data-ttu-id="2ed88-104">.NET Core 2.2 には、アプリケーションの配置、ランタイム サービスのイベント処理、Azure SQL データベースに対する認証、JIT コンパイラのパフォーマンス、`Main` メソッド実行前のコード インジェクションに関する機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2ed88-104">.NET Core 2.2 includes enhancements in application deployment, event handling for runtime services, authentication to Azure SQL databases, JIT compiler performance, and code injection prior to the execution of the `Main` method.</span></span>

## <a name="new-deployment-mode"></a><span data-ttu-id="2ed88-105">新しい配置モード</span><span class="sxs-lookup"><span data-stu-id="2ed88-105">New deployment mode</span></span>

<span data-ttu-id="2ed88-106">.NET Core 2.2 以降、[フレームワークに依存する実行可能ファイル](../deploying/index.md#publish-runtime-dependent)を配置できます。これは **.dll** ファイルではなく **.exe** ファイルとなります。</span><span class="sxs-lookup"><span data-stu-id="2ed88-106">Starting with .NET Core 2.2, you can deploy [framework-dependent executables](../deploying/index.md#publish-runtime-dependent), which are **.exe** files instead of **.dll** files.</span></span> <span data-ttu-id="2ed88-107">機能的にはフレームワーク依存の配置と似ていますが、フレームワークに依存する実行可能ファイル (FDE) は引き続き .NET Core のシステム全体の共有バージョンに依存して実行されます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-107">Functionally similar to framework-dependent deployments, framework-dependent executables (FDE) still rely on the presence of a shared system-wide version of .NET Core to run.</span></span> <span data-ttu-id="2ed88-108">アプリに含まれるものは、ご自身のコードとサードパーティの依存関係のみです。</span><span class="sxs-lookup"><span data-stu-id="2ed88-108">Your app contains only your code and any third-party dependencies.</span></span> <span data-ttu-id="2ed88-109">フレームワーク依存の配置とは異なり、FDE はプラットフォーム固有です。</span><span class="sxs-lookup"><span data-stu-id="2ed88-109">Unlike framework-dependent deployments, FDEs are platform-specific.</span></span>

<span data-ttu-id="2ed88-110">この新しい配置モードの際立った利点は、ライブラリの代わりに実行可能ファイルをビルドすることです。これは、最初に `dotnet` を呼び出すことなく、直接アプリを実行できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2ed88-110">This new deployment mode has the distinct advantage of building an executable instead of a library, which means you can run your app directly without invoking `dotnet` first.</span></span>

## <a name="core"></a><span data-ttu-id="2ed88-111">コア</span><span class="sxs-lookup"><span data-stu-id="2ed88-111">Core</span></span>

<span data-ttu-id="2ed88-112">**ランタイム サービスでのイベントの処理**</span><span class="sxs-lookup"><span data-stu-id="2ed88-112">**Handling events in runtime services**</span></span>

<span data-ttu-id="2ed88-113">GC、JIT、ThreadPool などのランタイム サービスがどのようにアプリケーションで使われているのか監視して、それがアプリケーションに与えている影響を把握したい場合がよくあります。</span><span class="sxs-lookup"><span data-stu-id="2ed88-113">You may often want to monitor your application's use of runtime services, such as the GC, JIT, and ThreadPool, to understand how they impact your application.</span></span><span data-ttu-id="2ed88-114"> Windows システムでは、これは通常、現在のプロセスの ETW イベントを監視することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-114"> On Windows systems, this is commonly done by monitoring the ETW events of the current process.</span></span><span data-ttu-id="2ed88-115"> これは引き続き正常に動作しますが、権限の低い環境内、または Linux や macOS 上で実行している場合は、常に ETW を使えるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="2ed88-115"> While this continues to work well, it's not always possible to use ETW if you're running in a low-privilege environment or on Linux or macOS.</span></span>

<span data-ttu-id="2ed88-116">.NET Core 2.2 以降では、<xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> クラスを使って CoreCLR イベントを使えるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2ed88-116">Starting with .NET Core 2.2, CoreCLR events can now be consumed using the <xref:System.Diagnostics.Tracing.EventListener?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="2ed88-117">これらのイベントでは、GC、JIT、ThreadPool、および相互運用などのランタイム サービスの動作が説明されます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-117">These events describe the behavior of such runtime services as GC, JIT, ThreadPool, and interop.</span></span> <span data-ttu-id="2ed88-118">これらは、CoreCLR ETW プロバイダーの一部として公開されるものと同じイベントです。</span><span class="sxs-lookup"><span data-stu-id="2ed88-118">These are the same events that are exposed as part of the CoreCLR ETW provider.</span></span><span data-ttu-id="2ed88-119">  このため、アプリケーションでは、これらのイベントを使うかトランスポート機構を使って、それらをテレメトリ集計サービスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-119">  This allows for applications to consume these events or use a transport mechanism to send them to a telemetry aggregation service.</span></span> <span data-ttu-id="2ed88-120">次のコード サンプルでイベントをサブスクライブする方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-120">You can see how to subscribe to events in the following code sample:</span></span>

```csharp
internal sealed class SimpleEventListener : EventListener
{
    // Called whenever an EventSource is created.
    protected override void OnEventSourceCreated(EventSource eventSource)
    {
        // Watch for the .NET runtime EventSource and enable all of its events.
        if (eventSource.Name.Equals("Microsoft-Windows-DotNETRuntime"))
        {
            EnableEvents(eventSource, EventLevel.Verbose, (EventKeywords)(-1));
        }
    }

    // Called whenever an event is written.
    protected override void OnEventWritten(EventWrittenEventArgs eventData)
    {
        // Write the contents of the event to the console.
        Console.WriteLine($"ThreadID = {eventData.OSThreadId} ID = {eventData.EventId} Name = {eventData.EventName}");
        for (int i = 0; i < eventData.Payload.Count; i++)
        {
            string payloadString = eventData.Payload[i]?.ToString() ?? string.Empty;
            Console.WriteLine($"\tName = \"{eventData.PayloadNames[i]}\" Value = \"{payloadString}\"");
        }
        Console.WriteLine("\n");
    }
}
```

<span data-ttu-id="2ed88-121">さらに、.NET Core 2.2 では次の 2 つのプロパティが <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> クラスに追加され、ETW イベントに関する追加情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-121">In addition, .NET Core 2.2 adds the following two properties to the <xref:System.Diagnostics.Tracing.EventWrittenEventArgs> class to provide additional information about ETW events:</span></span>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.OSThreadId?displayProperty=nameWithType>

- <xref:System.Diagnostics.Tracing.EventWrittenEventArgs.TimeStamp?displayProperty=nameWithType>

## <a name="data"></a><span data-ttu-id="2ed88-122">データ</span><span class="sxs-lookup"><span data-stu-id="2ed88-122">Data</span></span>

<span data-ttu-id="2ed88-123">**SqlConnection.AccessToken プロパティを使った Azure SQL データベースに対する AAD 認証**</span><span class="sxs-lookup"><span data-stu-id="2ed88-123">**AAD authentication to Azure SQL databases with the SqlConnection.AccessToken property**</span></span>

<span data-ttu-id="2ed88-124">.NET Core 2.2 以降では、Azure Active Directory によって発行されたアクセス トークンを、Azure SQL データベースへの認証に使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-124">Starting with .NET Core 2.2, an access token issued by Azure Active Directory can be used to authenticate to an Azure SQL database.</span></span> <span data-ttu-id="2ed88-125">アクセス トークンをサポートするために、<xref:System.Data.SqlClient.SqlConnection> クラスに <xref:System.Data.SqlClient.SqlConnection.AccessToken> プロパティが追加されています。</span><span class="sxs-lookup"><span data-stu-id="2ed88-125">To support access tokens, the <xref:System.Data.SqlClient.SqlConnection.AccessToken> property has been added to the <xref:System.Data.SqlClient.SqlConnection> class.</span></span> <span data-ttu-id="2ed88-126">AAD 認証を利用するには、バージョン 4.6 の System.Data.SqlClient NuGet パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2ed88-126">To take advantage of AAD authentication, download version 4.6 of the System.Data.SqlClient NuGet package.</span></span> <span data-ttu-id="2ed88-127">この機能を使うために、[`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet パッケージに含まれる [.NET 用 Active Directory 認証ライブラリ](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet)を使ってアクセス トークンの値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-127">In order to use the feature, you can obtain the access token value using the [Active Directory Authentication Library for .NET](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet) contained in the [`Microsoft.IdentityModel.Clients.ActiveDirectory`](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet package.</span></span>

## <a name="jit-compiler-improvements"></a><span data-ttu-id="2ed88-128">JIT コンパイラの機能強化</span><span class="sxs-lookup"><span data-stu-id="2ed88-128">JIT compiler improvements</span></span>

<span data-ttu-id="2ed88-129">**階層型コンパイルはオプトイン機能のまま**</span><span class="sxs-lookup"><span data-stu-id="2ed88-129">**Tiered compilation remains an opt-in feature**</span></span>

<span data-ttu-id="2ed88-130">.NET Core 2.1 では、JIT コンパイラに新しいコンパイラ テクノロジである "*階層型コンパイル*" がオプトイン機能として実装されました。</span><span class="sxs-lookup"><span data-stu-id="2ed88-130">In .NET Core 2.1, the JIT compiler implemented a new compiler technology, *tiered compilation*, as an opt-in feature.</span></span> <span data-ttu-id="2ed88-131">階層型コンパイルの目標はパフォーマンスの向上です。</span><span class="sxs-lookup"><span data-stu-id="2ed88-131">The goal of tiered compilation is improved performance.</span></span> <span data-ttu-id="2ed88-132">JIT コンパイラで実行される重要なタスクの 1 つはコード実行の最適化です。</span><span class="sxs-lookup"><span data-stu-id="2ed88-132">One of the important tasks performed by the JIT compiler is optimizing code execution.</span></span> <span data-ttu-id="2ed88-133">ただし、使用頻度の低いコード パスについては、最適化されていないコードの実行にランタイムが費やす時間よりも、コードの最適化にコンパイラが費やす時間の方が多くなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2ed88-133">For little-used code paths, however, the compiler may spend more time optimizing code than the runtime spends executing unoptimized code.</span></span> <span data-ttu-id="2ed88-134">階層型コンパイルによって JIT コンパイルに次の 2 つのステージが導入されます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-134">Tiered compilation introduces two stages in JIT compilation:</span></span>

- <span data-ttu-id="2ed88-135">**第 1 階層**: コードをできるだけ早く生成します。</span><span class="sxs-lookup"><span data-stu-id="2ed88-135">A **first tier**, which generates code as quickly as possible.</span></span>

- <span data-ttu-id="2ed88-136">**第 2 階層**: 頻繁に実行されるメソッドに対して、最適化されたコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="2ed88-136">A **second tier**, which generates optimized code for those methods that are executed frequently.</span></span> <span data-ttu-id="2ed88-137">コンパイルの第 2 階層は、パフォーマンスの向上と並行して実行されます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-137">The second tier of compilation is performed in parallel for enhanced performance.</span></span>

<span data-ttu-id="2ed88-138">階層型コンパイルによって得られるパフォーマンスの向上について詳しくは、「[Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/)」(.NET Core 2.2 Preview 2 の発表) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ed88-138">For information on the performance improvement that can result from tiered compilation, see [Announcing .NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span>

<span data-ttu-id="2ed88-139">.NET Core 2.2 Preview 2 では、階層型コンパイルが既定で有効になっていました。</span><span class="sxs-lookup"><span data-stu-id="2ed88-139">In .NET Core 2.2 Preview 2, tiered compilation was enabled by default.</span></span> <span data-ttu-id="2ed88-140">しかし、階層型コンパイルを既定で有効にする準備はまだ整っていないと判断されました。</span><span class="sxs-lookup"><span data-stu-id="2ed88-140">However, we've decided that we are still not ready to enable tiered compilation by default.</span></span> <span data-ttu-id="2ed88-141">このため .NET Core 2.2 では、階層型コンパイルはオプトイン機能のままとなります。</span><span class="sxs-lookup"><span data-stu-id="2ed88-141">So in .NET Core 2.2, tiered compilation continues to be an opt-in feature.</span></span> <span data-ttu-id="2ed88-142">階層型コンパイルに対するオプトインについて詳しくは、「[.NET Core 2.1 の新機能](dotnet-core-2-1.md)」の「[JIT コンパイラの機能強化](dotnet-core-2-1.md#jit-compiler-improvements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ed88-142">For information on opting in to tiered compilation, see [Jit compiler improvements](dotnet-core-2-1.md#jit-compiler-improvements) in [What's new in .NET Core 2.1](dotnet-core-2-1.md).</span></span>

## <a name="runtime"></a><span data-ttu-id="2ed88-143">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2ed88-143">Runtime</span></span>

<span data-ttu-id="2ed88-144">**Main メソッド実行前のコードの挿入**</span><span class="sxs-lookup"><span data-stu-id="2ed88-144">**Injecting code prior to executing the Main method**</span></span>

<span data-ttu-id="2ed88-145">.NET Core 2.2 以降では、スタートアップ フックを使って、アプリケーションの Main メソッドを実行する前にコードを挿入できます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-145">Starting with .NET Core 2.2, you can use a startup hook to inject code prior to running an application's Main method.</span></span> <span data-ttu-id="2ed88-146">スタートアップ フックを使うと、ホストはアプリケーションが配置された後に、再コンパイルしたりアプリケーションを変更したりすることなくその動作をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-146">Startup hooks make it possible for a host to customize the behavior of applications after they have been deployed without needing to recompile or change the application.</span></span>

<span data-ttu-id="2ed88-147">ホスティング プロバイダーは、 <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> 動作など、メイン エントリ ポイントの読み込み動作に影響を与える可能性がある設定を含む、カスタム構成とポリシーを定義することが想定されています。</span><span class="sxs-lookup"><span data-stu-id="2ed88-147">We expect hosting providers to define custom configuration and policy, including settings that potentially influence the load behavior of the main entry point, such as the <xref:System.Runtime.Loader.AssemblyLoadContext?displayProperty=nameWithType> behavior.</span></span> <span data-ttu-id="2ed88-148">フックは、トレースまたはテレメトリの挿入を設定するため、処理用のコールバックを設定するため、またはその他の環境依存の動作を定義するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2ed88-148">The hook can be used to set up tracing or telemetry injection, to set up callbacks for handling, or to define other environment-dependent behavior.</span></span> <span data-ttu-id="2ed88-149">フックはエントリ ポイントから独立しているため、ユーザー コードを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2ed88-149">The hook is separate from the entry point, so that user code doesn't need to be modified.</span></span>

<span data-ttu-id="2ed88-150">詳細については、「[Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md)」(スタートアップ フックのホスト) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2ed88-150">See [Host startup hook](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/host-startup-hook.md) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ed88-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="2ed88-151">See also</span></span>

- [<span data-ttu-id="2ed88-152">.NET Core の新機能</span><span class="sxs-lookup"><span data-stu-id="2ed88-152">What's new in .NET Core</span></span>](index.md)
- [<span data-ttu-id="2ed88-153">ASP.NET Core 2.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="2ed88-153">What's new in ASP.NET Core 2.2</span></span>](/aspnet/core/release-notes/aspnetcore-2.2)
- [<span data-ttu-id="2ed88-154">EF Core 2.2 の新機能</span><span class="sxs-lookup"><span data-stu-id="2ed88-154">New features in EF Core 2.2</span></span>](/ef/core/what-is-new/ef-core-2.2)
