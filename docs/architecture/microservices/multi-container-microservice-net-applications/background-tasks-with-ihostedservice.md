---
title: IHostedService と BackgroundService クラスを使ってマイクロサービスのバックグラウンド タスクを実装する
description: コンテナー化された .NET アプリケーションの .NET マイクロサービス アーキテクチャ | マイクロサービスの .NET Core でバックグラウンド タスクを実装する IHostedService と BackgroundService を使用する新しいオプションについて理解します。
ms.date: 01/07/2019
ms.openlocfilehash: ff263212536233bef85e9517442b4d7ed9eff115
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039888"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="e0579-103">IHostedService と BackgroundService クラスを使ってマイクロサービスのバックグラウンド タスクを実装する</span><span class="sxs-lookup"><span data-stu-id="e0579-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="e0579-104">バックグラウンド タスクとスケジュールされたジョブは、最終的にはマイクロサービス ベースのアプリケーションまたはあらゆる種類のアプリケーションで、実装する必要がある可能性があるものです。</span><span class="sxs-lookup"><span data-stu-id="e0579-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="e0579-105">マイクロサービス アーキテクチャを使用した場合の違いは、これらのバックグラウンド タスクをホストするために単一のマイクロサービスのプロセス/コンテナーを実装できるため、必要に応じてスケールダウンまたはスケールアップしたり、そのマイクロサービスのプロセス/コンテナーの単一のインスタンスを確実に実行させたりすることができることです。</span><span class="sxs-lookup"><span data-stu-id="e0579-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="e0579-106">これらの種類のタスクは、ホスト、アプリケーション、マイクロサービス内でホストするサービス、ロジックであるため、全体的な観点から、.NET Core では*ホステッド サービス*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="e0579-106">From a generic point of view, in .NET Core we called these type of tasks *Hosted Services*, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="e0579-107">このケースでは、ホステッド サービスは、単にバックグラウンド タスク ロジックを持つクラスを意味していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0579-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="e0579-108">.NET Core 2.0 以降では、ホステッド サービスを簡単に実装できるようにする <xref:Microsoft.Extensions.Hosting.IHostedService> という名前の新しいインターフェイスが、フレームワークによって提供されています。</span><span class="sxs-lookup"><span data-stu-id="e0579-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="e0579-109">基本的な考え方は、図 6-26 に示すように、ご利用の Web ホストまたはホストが実装されているときに、バックグラウンドで実行される複数のバックグラウンド タスク (ホステッド サービス) を登録できることです。</span><span class="sxs-lookup"><span data-stu-id="e0579-109">The basic idea is that you can register multiple background tasks (hosted services), that run in the background while your web host or host is running, as shown in the image 6-26.</span></span>

![ASP.NET Core 1.x と 2.x は、Web アプリのバックグラウンド プロセスで IWebHost をサポートしており、.NET Core 2 と 1 は、プレーンなコンソール アプリでのバックグラウンド処理に IHost をサポートしています。](./media/image26.png)

<span data-ttu-id="e0579-111">**図 6-26**。</span><span class="sxs-lookup"><span data-stu-id="e0579-111">**Figure 6-26**.</span></span> <span data-ttu-id="e0579-112">WebHost と Host で IHostedService を使用した場合の比較</span><span class="sxs-lookup"><span data-stu-id="e0579-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="e0579-113">`WebHost` と `Host` の違いに注目してください。</span><span class="sxs-lookup"><span data-stu-id="e0579-113">Note the difference made between `WebHost` and `Host`.</span></span>

<span data-ttu-id="e0579-114">ASP.NET Core 2.0 の `WebHost` (`IWebHost` を実装する基底クラス) は、MVC Web アプリや Web API サービスを実装している場合など、HTTP サーバー機能をプロセスに提供するために使用するインフラストラクチャ成果物です。</span><span class="sxs-lookup"><span data-stu-id="e0579-114">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="e0579-115">ASP.NET Core での新しいインフラストラクチャのすべての長所を提供することで、依存関係の挿入を使用、要求パイプラインなどへのミドルウェアの挿入、およびこれらの `IHostedServices` をバックグラウンド タスクに正確に使用することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="e0579-115">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the request pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="e0579-116">`Host` (`IHost` を実装する基底クラス) は .NET Core 2.1 で実装されました。</span><span class="sxs-lookup"><span data-stu-id="e0579-116">A `Host` (base class implementing `IHost`) was introduced in .NET Core 2.1.</span></span> <span data-ttu-id="e0579-117">基本的に、`Host` を使用すると、`WebHost` を使用した場合と同様のインフラストラクチャ (依存関係の挿入、ホステッド サービスなど) ができますが、このケースでは、ホストとしてシンプルでより軽量なプロセスが必要なだけで、MVC、Web API または HTTP サーバー機能は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="e0579-117">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="e0579-118">そのため、IHost を使用して特殊化されたホスト プロセスを作成してホステッド サービス以外 (`IHostedServices` をホスティングするためだけに作成されたマイクロサービスなど) は処理しないことを選択するか、または代わりに既存の ASP.NET Core `WebHost` (既存の ASP.NET Core Web API または MVC アプリ) を拡張することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e0579-118">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span>

<span data-ttu-id="e0579-119">ビジネスと拡張性のニーズに応じて、いずれの方法にも長所と短所があります。</span><span class="sxs-lookup"><span data-stu-id="e0579-119">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="e0579-120">つまり、基本的には、バックグラウンド タスクが HTTP (IWebHost) と関係ない場合、IHost を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0579-120">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use IHost.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="e0579-121">WebHost または Host でホステッド サービスを登録する</span><span class="sxs-lookup"><span data-stu-id="e0579-121">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="e0579-122">`IHostedService` インターフェイスの使用は、`WebHost` と `Host`で非常に似ているので、詳しく見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="e0579-122">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span>

<span data-ttu-id="e0579-123">SignalR はホステッド サービスを使用している成果物の一例ですが、次のようなより単純なことにも使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-123">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

- <span data-ttu-id="e0579-124">変更を検索するデータベースをポーリングするバックグラウンド タスク。</span><span class="sxs-lookup"><span data-stu-id="e0579-124">A background task polling a database looking for changes.</span></span>
- <span data-ttu-id="e0579-125">いくつかのキャッシュを定期的に更新するスケジュールされたタスク。</span><span class="sxs-lookup"><span data-stu-id="e0579-125">A scheduled task updating some cache periodically.</span></span>
- <span data-ttu-id="e0579-126">タスクをバックグラウンド スレッドで実行することを可能にする QueueBackgroundWorkItem の実装。</span><span class="sxs-lookup"><span data-stu-id="e0579-126">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
- <span data-ttu-id="e0579-127">`ILogger` などの共通サービスを共有しながら、Web アプリのバックグラウンドでメッセージ キューからのメッセージの処理。</span><span class="sxs-lookup"><span data-stu-id="e0579-127">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
- <span data-ttu-id="e0579-128">`Task.Run()` で開始されるバックグラウンド タスク。</span><span class="sxs-lookup"><span data-stu-id="e0579-128">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="e0579-129">基本的に、IHostedService に基づいて、これらのアクションのいずれかをバックグラウンド タスクにオフロードできます。</span><span class="sxs-lookup"><span data-stu-id="e0579-129">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="e0579-130">1 つまたは複数の `IHostedServices` を `WebHost` または `Host` に追加するには、ASP.NET Core `WebHost` で標準的な DI (依存関係の挿入) を経由して (または .NET Core 2.1 以降の `Host` で) それらを登録します。</span><span class="sxs-lookup"><span data-stu-id="e0579-130">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the standard DI (dependency injection) in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1 and above).</span></span> <span data-ttu-id="e0579-131">基本的に、次のコードのように、一般的な ASP.NET WebHost から、`Startup` クラスの使い慣れた `ConfigureServices()` メソッド内でホステッド サービスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0579-131">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddSingleton<IHostedService, GracePeriodManagerService>();
    services.AddSingleton<IHostedService, MyHostedServiceB>();
    services.AddSingleton<IHostedService, MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="e0579-132">そのコードで、`GracePeriodManagerService` ホステッド サービスは eShopOnContainers の Ordering business microservice からの実際のコードですが、他の 2 つは単に追加の 2 つのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="e0579-132">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="e0579-133">`IHostedService` バックグラウンド タスクの実行は、アプリケーション (さらに言えば、ホストまたはマイクロサービス) の有効期間に合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="e0579-133">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="e0579-134">アプリケーションの起動時にタスクを登録して、いくつかの正常なアクションを行うか、アプリケーションのシャットダウン時にクリーンアップすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-134">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="e0579-135">`IHostedService` を使用しない場合は、いつでもバックグラウンド スレッドを開始して任意のタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-135">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="e0579-136">正常なクリーンアップ アクションを実行する機会を持たずにスレッドが単に強制終了されるときは、差はちょうどアプリのシャットダウン時間になります。</span><span class="sxs-lookup"><span data-stu-id="e0579-136">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>

## <a name="the-ihostedservice-interface"></a><span data-ttu-id="e0579-137">IHostedService インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0579-137">The IHostedService interface</span></span>

<span data-ttu-id="e0579-138">`IHostedService` を登録すると、アプリケーションの起動時と停止時にそれぞれ、.NET Core によって `IHostedService` 型の `StartAsync()` メソッドと `StopAsync()` メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0579-138">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="e0579-139">具体的には、開始は、サーバーが起動して `IApplicationLifetime.ApplicationStarted` がトリガーされた後に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="e0579-139">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="e0579-140">.NET Core で定義されたように、`IHostedService` は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="e0579-140">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```

<span data-ttu-id="e0579-141">ご想像のとおり、以前に示したように、IHostedService の複数の実装を作成し、`ConfigureService()` メソッドでそれらを DI コンテナーに登録することができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-141">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="e0579-142">これらすべてのホステッド サービスが、アプリケーション/マイクロサービスと共に開始および停止されます。</span><span class="sxs-lookup"><span data-stu-id="e0579-142">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="e0579-143">開発者は、`StopAsync()` メソッドがホストによってトリガーされるときに、サービスの停止アクションを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0579-143">As a developer, you are responsible for handling the stopping action of your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="e0579-144">BackgroundService 基底クラスから派生したカスタムのホステッド サービス クラスを使用して IHostedService を実装する</span><span class="sxs-lookup"><span data-stu-id="e0579-144">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="e0579-145">続行して、ホステッド サービスのカスタム クラスをゼロから作成し、`IHostedService` を実装します。これは .NET Core 2.0 を使用する場合に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0579-145">You could go ahead and create your custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span>

<span data-ttu-id="e0579-146">ただし、ほとんどのバックグラウンド タスクでは、キャンセル トークンの管理およびその他の一般的な操作で同様のニーズがあるため、派生元として使用できる非常に便利な `BackgroundService` という名前の抽象基底クラスがあります (.NET Core 2.1 以降で利用できます)。</span><span class="sxs-lookup"><span data-stu-id="e0579-146">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, there is a convenient abstract base class you can derive from, named `BackgroundService` (available since .NET Core 2.1).</span></span>

<span data-ttu-id="e0579-147">そのクラスは、バックグラウンド タスクを設定するために必要な主要な作業を提供します。</span><span class="sxs-lookup"><span data-stu-id="e0579-147">That class provides the main work needed to set up the background task.</span></span>

<span data-ttu-id="e0579-148">次のコードは、.NET Core に実装されている BackgroundService 抽象基底クラスです。</span><span class="sxs-lookup"><span data-stu-id="e0579-148">The next code is the abstract BackgroundService base class as implemented in .NET Core.</span></span>

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0.
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts =
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it,
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }

    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

<span data-ttu-id="e0579-149">前の抽象基底クラスから派生する場合、データベースをポーリングして、必要に応じてイベント バスに統合イベントをパブリッシュする eShopOnContainers からの簡素化された次のコードのように、継承された実装により、独自のカスタムのホステッド サービス クラスで `ExecuteAsync()` メソッドを実装するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="e0579-149">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

```csharp
public class GracePeriodManagerService : BackgroundService
{
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        //Constructor’s parameters validations...
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() =>
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table
            // and publishing events into the Event Bus (RabbitMQ / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

<span data-ttu-id="e0579-150">eShopOnContainers のこの特定のケースでは、特定の状態を持つ注文を検索するデータベース テーブルに対してクエリを実行するアプリケーション メソッドを実行し、変更を適用するときに、イベント バスを介して統合イベントをパブリッシュします (その下で RabbitMQ または Azure Service Bus を使用できます)。</span><span class="sxs-lookup"><span data-stu-id="e0579-150">In this specific case for eShopOnContainers, it's executing an application method that's querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span>

<span data-ttu-id="e0579-151">もちろん、代わりに他の任意のビジネス バックグラウンド タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0579-151">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="e0579-152">既定では、キャンセル トークンは 5 秒のタイムアウトで設定されていますが、この値は、`IWebHostBuilder` の `UseShutdownTimeout` 拡張機能を使用して `WebHost` をビルドする際に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-152">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="e0579-153">これは、サービスが 5 秒以内にキャンセルされることが想定されていて、そうでない場合は突然強制終了される可能性が高くなることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e0579-153">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="e0579-154">次のコードでは、その時間を 10 秒に変更します。</span><span class="sxs-lookup"><span data-stu-id="e0579-154">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="e0579-155">クラス図の概要</span><span class="sxs-lookup"><span data-stu-id="e0579-155">Summary class diagram</span></span>

<span data-ttu-id="e0579-156">次の図は、IHostedServices を実装する場合のクラスとインターフェイスの概要を視覚的に示しています。</span><span class="sxs-lookup"><span data-stu-id="e0579-156">The following image shows a visual summary of the classes and interfaced involved when implementing IHostedServices.</span></span>

![クラス ダイアグラム:IWebHost と IHost は、BackgroundService から継承され、IHostedService を実装する多くのサービスをホストできます。](./media/image27.png)

<span data-ttu-id="e0579-158">**図 6-27**。</span><span class="sxs-lookup"><span data-stu-id="e0579-158">**Figure 6-27**.</span></span> <span data-ttu-id="e0579-159">IHostedService に関連する複数のクラスとインターフェイスを示すクラス図</span><span class="sxs-lookup"><span data-stu-id="e0579-159">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="e0579-160">展開に関する注意事項と習得事項</span><span class="sxs-lookup"><span data-stu-id="e0579-160">Deployment considerations and takeaways</span></span>

<span data-ttu-id="e0579-161">ASP.NET Core `WebHost` または .NET Core `Host` を展開する方法が最終的なソリューションに影響を与える可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e0579-161">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="e0579-162">たとえば、`WebHost` を IIS または正規の Azure App Service に展開する場合、アプリ プールのリサイクルが原因でホストがシャットダウンされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0579-162">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="e0579-163">ただし、ホストをコンテナーとして Kubernetes や Service Fabric などのオーケストレーターに展開する場合は、ご利用のホストのライブ インスタンスの確実な数を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-163">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="e0579-164">さらに、Azure Functions のように、これらのシナリオ用に特別に作成されたクラウド内で、他の方法を検討することができます。</span><span class="sxs-lookup"><span data-stu-id="e0579-164">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> <span data-ttu-id="e0579-165">最後になりますが、サービスを常時実行する必要があるとき、および Windows Server にデプロイする場合、Windows Service を使用できることがあります。</span><span class="sxs-lookup"><span data-stu-id="e0579-165">Finally, if you need the service to be running all the time and are deploying on a Windows Server you could use a Windows Service.</span></span>

<span data-ttu-id="e0579-166">ただし、アプリ プールに展開された `WebHost` に対しても、適用可能なアプリケーションのメモリ内キャッシュの再作成またはフラッシュのようなシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="e0579-166">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache, that would be still applicable.</span></span>

<span data-ttu-id="e0579-167">`IHostedService` インターフェイスでは、(.NET Core 2.0 の) ASP.NET Core Web アプリケーションで、または (`IHost` を使用して .NET Core 2.1 で開始する) 任意のプロセス/ホストでバックグラウンド タスクを開始する便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e0579-167">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="e0579-168">その主な利点は、ホスト自体がシャットダウンするときに、バックグラウンド タスクのコードをクリーンアップするため、適切にキャンセルする機会が得られることです。</span><span class="sxs-lookup"><span data-stu-id="e0579-168">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0579-169">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="e0579-169">Additional resources</span></span>

- <span data-ttu-id="e0579-170">**ASP.NET Core/Standard 2.0 でスケジュールされたタスクをビルドする**</span><span class="sxs-lookup"><span data-stu-id="e0579-170">**Building a scheduled task in ASP.NET Core/Standard 2.0**</span></span>  
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html>

- <span data-ttu-id="e0579-171">**ASP.NET Core 2.0 で IHostedService を実装する**</span><span class="sxs-lookup"><span data-stu-id="e0579-171">**Implementing IHostedService in ASP.NET Core 2.0**</span></span>  
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice>

- <span data-ttu-id="e0579-172">**ASP.NET Core 2.1 を使用した GenericHost サンプル**</span><span class="sxs-lookup"><span data-stu-id="e0579-172">**GenericHost Sample using ASP.NET Core 2.1**</span></span>  
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample>

>[!div class="step-by-step"]
><span data-ttu-id="e0579-173">[前へ](test-aspnet-core-services-web-apps.md)
>[次へ](implement-api-gateways-with-ocelot.md)</span><span class="sxs-lookup"><span data-stu-id="e0579-173">[Previous](test-aspnet-core-services-web-apps.md)
[Next](implement-api-gateways-with-ocelot.md)</span></span>
