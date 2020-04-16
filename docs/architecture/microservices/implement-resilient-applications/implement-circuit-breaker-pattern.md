---
title: サーキット ブレーカー パターンの実装
description: サーキット ブレーカー パターンを HTTP 再試行の補助システムとして実装する方法について説明します。
ms.date: 03/03/2020
ms.openlocfilehash: bebe0b4a622db928175f78f8d3e303d3d7adf170
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988886"
---
# <a name="implement-the-circuit-breaker-pattern"></a><span data-ttu-id="e3ec0-103">サーキット ブレーカー パターンを実装する</span><span class="sxs-lookup"><span data-stu-id="e3ec0-103">Implement the Circuit Breaker pattern</span></span>

<span data-ttu-id="e3ec0-104">前述のように、リモート サービスやリソースに接続を試行する際に発生し得る、復旧にどのくらい時間がかかるかわからない障害を処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-104">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="e3ec0-105">この種類の障害を処理することにより、アプリケーションの安定性と回復性が向上します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-105">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="e3ec0-106">分散環境において、リモート リソースとサービスの呼び出しは、低速なネットワーク接続やタイムアウト、あるいはリソースの応答が低速であったり、一時的に利用不可能であったりなどの、一時的な障害が原因で失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-106">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are responding slowly or are temporarily unavailable.</span></span> <span data-ttu-id="e3ec0-107">このような障害は通常しばらくすると自動的に修正されます。堅牢なクラウド アプリケーションなら "再試行パターン" などの方法でそうした障害を処理する備えができているはずです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-107">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the "Retry pattern".</span></span>

<span data-ttu-id="e3ec0-108">ただし、予期しないイベントが原因で、障害の修正に非常に長い時間がかかる状況もあり得ます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-108">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="e3ec0-109">このような障害の重大度は、部分的な接続の損失からサービスの完全な不具合まで多岐にわたります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-109">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="e3ec0-110">このような状況では、アプリケーションが成功の見込みの薄い操作を再試行し続けることは無駄かもしれません。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-110">In these situations, it might be pointless for an application to continually retry an operation that's unlikely to succeed.</span></span>

<span data-ttu-id="e3ec0-111">代わりに、アプリケーションが操作の失敗を受け入れ、失敗を処理するようにコードを書く必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-111">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="e3ec0-112">HTTP 再試行を不注意に使用すると、自分のソフトウェアにサービス拒否 ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) 攻撃が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-112">Using Http retries carelessly could result in creating a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack within your own software.</span></span> <span data-ttu-id="e3ec0-113">マイクロサービスが失敗したか、動作が遅いとき、複数のクライアントで失敗した要求の再試行が繰り返されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-113">As a microservice fails or performs slowly, multiple clients might repeatedly retry failed requests.</span></span> <span data-ttu-id="e3ec0-114">その結果、失敗を繰り返すサービスに宛てられるトラフィックが急激に増えるという危険なリスクが発生します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-114">That creates a dangerous risk of exponentially increasing traffic targeted at the failing service.</span></span>

<span data-ttu-id="e3ec0-115">そのため、試行を続けるに値しないとき、過剰な要求によって停止するように、何らかの防壁が必要になります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-115">Therefore, you need some kind of defense barrier so that excessive requests stop when it isn't worth to keep trying.</span></span> <span data-ttu-id="e3ec0-116">その防壁こそがサーキット ブレーカーです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-116">That defense barrier is precisely the circuit breaker.</span></span>

<span data-ttu-id="e3ec0-117">サーキット ブレーカー パターンの目的は、"再試行パターン" とは異なります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-117">The Circuit Breaker pattern has a different purpose than the "Retry pattern".</span></span> <span data-ttu-id="e3ec0-118">"再試行パターン" では、操作が最終的には成功するとの見込みをもってアプリケーションに操作を再試行させます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-118">The "Retry pattern" enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="e3ec0-119">サーキット ブレーカー パターンにより、失敗する可能性の高い操作がアプリケーションで実行されなくなります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-119">The Circuit Breaker pattern prevents an application from performing an operation that's likely to fail.</span></span> <span data-ttu-id="e3ec0-120">アプリケーションでは、これら 2 つのパターンを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-120">An application can combine these two patterns.</span></span> <span data-ttu-id="e3ec0-121">しかしながら、再試行のロジックはサーキット ブレーカーが返す例外に対応できる必要があり、障害が一時的ではないことをサーキット ブレーカーが示す場合、再試行を中止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-121">However, the retry logic should be sensitive to any exception returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implement-circuit-breaker-pattern-with-ihttpclientfactory-and-polly"></a><span data-ttu-id="e3ec0-122">`IHttpClientFactory` と Polly よるサーキット ブレーカー パターンの実装</span><span class="sxs-lookup"><span data-stu-id="e3ec0-122">Implement Circuit Breaker pattern with `IHttpClientFactory` and Polly</span></span>

<span data-ttu-id="e3ec0-123">再試行の実装と同じように、サーキット ブレーカーの推奨されるアプローチは、Polly など実績のある .NET ライブラリを活用し、`IHttpClientFactory` とネイティブ統合することです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-123">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly and its native integration with `IHttpClientFactory`.</span></span>

<span data-ttu-id="e3ec0-124">サーキット ブレーカー ポリシーをご利用の `IHttpClientFactory` の外向きミドルウェア パイプラインに追加することは、`IHttpClientFactory` の使用時、既にあるものにコードの増分を 1 つ分追加することと同じくらい簡単です。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-124">Adding a circuit breaker policy into your `IHttpClientFactory` outgoing middleware pipeline is as simple as adding a single incremental piece of code to what you already have when using `IHttpClientFactory`.</span></span>

<span data-ttu-id="e3ec0-125">HTTP 呼び出しの再試行に使用されるコードに追加する必要があるのは、ConfigureServices() メソッドから抜粋された次の増分コードで示されているように、使用するポリシーのリストにサーキット ブレーカー ポリシーを追加するコードだけです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-125">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown in the following incremental code, part of the ConfigureServices() method.</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Sample. Default lifetime is 2 minutes
        .AddHttpMessageHandler<HttpClientAuthorizationDelegatingHandler>()
        .AddPolicyHandler(GetRetryPolicy())
        .AddPolicyHandler(GetCircuitBreakerPolicy());
```

<span data-ttu-id="e3ec0-126">`AddPolicyHandler()` メソッドは、使用される `HttpClient` オブジェクトにポリシーを追加するものです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-126">The `AddPolicyHandler()` method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="e3ec0-127">この場合、サーキット ブレーカーの Polly のポリシーを追加しています。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-127">In this case, it's adding a Polly policy for a circuit breaker.</span></span>

<span data-ttu-id="e3ec0-128">手法のモジュール性を高める目的で、次のコードに示すように、`GetCircuitBreakerPolicy()` という名前の別個のメソッド内でサーキット ブレーカー ポリシーが定義されています。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-128">To have a more modular approach, the Circuit Breaker Policy is defined in a separate method called `GetCircuitBreakerPolicy()`, as shown in the following code:</span></span>

```csharp
static IAsyncPolicy<HttpResponseMessage> GetCircuitBreakerPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .CircuitBreakerAsync(5, TimeSpan.FromSeconds(30));
}
```

<span data-ttu-id="e3ec0-129">上記のコード例では、HTTP 要求の再試行時、エラーが連続して 5 つ発生したとき、サーキットを中断する (またはオープン状態にする) ようにサーキット ブレーカー ポリシーが構成されています。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-129">In the code example above, the circuit breaker policy is configured so it breaks or opens the circuit when there have been five consecutive faults when retrying the Http requests.</span></span> <span data-ttu-id="e3ec0-130">それが発生すると、サーキットは 30 秒間中断されます。その間、呼び出しは実際に配置されるのではなく、サーキット ブレーカーが働いてすぐに失敗します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-130">When that happens, the circuit will break for 30 seconds: in that period, calls will be failed immediately by the circuit-breaker rather than actually be placed.</span></span>  <span data-ttu-id="e3ec0-131">[関連する例外および HTTP 状態コード](/aspnet/core/fundamentals/http-requests#handle-transient-faults) は、ポリシーによって自動的にエラーとして解釈されます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-131">The policy automatically interprets [relevant exceptions and HTTP status codes](/aspnet/core/fundamentals/http-requests#handle-transient-faults) as faults.</span></span>  

<span data-ttu-id="e3ec0-132">サーキット ブレーカーは、HTTP 呼び出しを実行しているクライアント アプリケーションまたはサービスとは別の環境にデプロイされている特定のリソースに問題がある場合に、要求をフォールバック インフラストラクチャにリダイレクトするためにも使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-132">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you had issues in a particular resource that's deployed in a different environment than the client application or service that's performing the HTTP call.</span></span> <span data-ttu-id="e3ec0-133">こうすれば、バックエンドのマイクロサービスのみに影響を与え、クライアント アプリケーションには影響を与えないデータセンターの停止が生じた場合に、クライアント アプリケーションはフォールバック サービスにリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-133">That way, if there's an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="e3ec0-134">Polly では、この[フェールオーバー ポリシー](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) シナリオを自動化するための新しいポリシーが計画されています。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-134">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="e3ec0-135">これらすべての機能は、位置を意識することなく Azure に自動的にフェールオーバーを管理させるのとは対照的に、フェールオーバーを .NET コード内から管理する場合のためのものです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-135">All those features are for cases where you're managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

<span data-ttu-id="e3ec0-136">使用という観点からは、HttpClient を使用するとき、ここで新しいものは何も追加する必要がありません。前のセクションで示したように、`HttpClient` と `IHttpClientFactory` の使用時とコードが同じであるからです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-136">From a usage point of view, when using HttpClient, there’s no need to add anything new here because the code is the same than when using `HttpClient` with `IHttpClientFactory`, as shown in previous sections.</span></span>

## <a name="test-http-retries-and-circuit-breakers-in-eshoponcontainers"></a><span data-ttu-id="e3ec0-137">eShopOnContainers 内で HTTP の再試行とサーキット ブレーカーをテストする</span><span class="sxs-lookup"><span data-stu-id="e3ec0-137">Test Http retries and circuit breakers in eShopOnContainers</span></span>

<span data-ttu-id="e3ec0-138">Docker ホスト内で eShopOnContainers ソリューションを起動する場合、このソリューションは複数のコンテナーを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-138">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="e3ec0-139">SQL Server コンテナーなど、一部のコンテナーは起動と初期化が低速です。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-139">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="e3ec0-140">eShopOnContainers アプリケーションを Docker に初めてデプロイする場合は、イメージとデータベースを設定する必要があるため、特にそのようになります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-140">This is especially true the first time you deploy the eShopOnContainers application into Docker because it needs to set up the images and the database.</span></span> <span data-ttu-id="e3ec0-141">一部のコンテナーは他のコンテナーより起動が低速だという事実により、以前のセクションで説明したように docker-compose レベルでコンテナー間の依存関係を設定している場合であっても、残りのサービスによる初期化時の HTTP 例外のスローが引き起こされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-141">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="e3ec0-142">コンテナー間の docker-compose 依存関係は、プロセス レベルだけのものです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-142">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="e3ec0-143">コンテナーのエントリ ポイント プロセスは起動されても、SQL Server はクエリに対して準備ができていないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-143">The container's entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="e3ec0-144">結果としてエラーの連鎖が生じ、アプリケーションがその特定のコンテナーを利用しようとするときに例外が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-144">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="e3ec0-145">また、起動時のこのタイプのエラーは、アプリケーションをクラウドに展開する際に生じることもあります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-145">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="e3ec0-146">その場合、オーケストレーターは、クラスターのノード全体でコンテナーの数を分散させる際に、コンテナーを 1 つのノードまたは VM から別の場所に移動することがあります (つまり、新しいインスタンスを起動する)。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-146">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster's nodes.</span></span>

<span data-ttu-id="e3ec0-147">すべてのコンテナーを起動するとき、'eShopOnContainers' では、上記の再試行パターンを利用してこれらの問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-147">The way 'eShopOnContainers' solves those issues when starting all the containers is by using the Retry pattern illustrated earlier.</span></span>

### <a name="test-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="e3ec0-148">eShopOnContainers 内でサーキット ブレーカーをテストする</span><span class="sxs-lookup"><span data-stu-id="e3ec0-148">Test the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="e3ec0-149">いくつかの方法でサーキットを中断し/オープン状態にし、eShopOnContainers でテストできます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-149">There are a few ways you can break/open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="e3ec0-150">1 つの方法は、サーキット ブレーカー ポリシーで許可する再試行の数を 1 まで減らし、ソリューション全体を Docker に再展開することです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-150">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="e3ec0-151">再試行を 1 回にすることで、デプロイ中に HTTP 要求が失敗し、サーキット ブレーカーがオープン状態になって、エラーが発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-151">With a single retry, there's a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="e3ec0-152">もう 1 つの方法は、**Basket** マイクロサービス内に実装されているカスタムのミドルウェアを使用することです。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-152">Another option is to use custom middleware that's implemented in the **Basket** microservice.</span></span> <span data-ttu-id="e3ec0-153">このミドルウェアが有効な場合、すべての HTTP 要求を捕捉し、状態コード 500 を返します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-153">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="e3ec0-154">次のように、"failing" URI に GET 要求を実行してミドルウェアを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-154">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

- `GET http://localhost:5103/failing`\
  <span data-ttu-id="e3ec0-155">この要求は、ミドルウェアの現在の状態を返します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-155">This request returns the current state of the middleware.</span></span> <span data-ttu-id="e3ec0-156">ミドルウェアが有効な場合、要求は状態コード 500 を返します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-156">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="e3ec0-157">ミドルウェアが無効の場合、応答はありません。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-157">If the middleware is disabled, there's no response.</span></span>

- `GET http://localhost:5103/failing?enable`\
  <span data-ttu-id="e3ec0-158">この要求はミドルウェアを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-158">This request enables the middleware.</span></span>

- `GET http://localhost:5103/failing?disable`\
  <span data-ttu-id="e3ec0-159">この要求はミドルウェアを無効にします。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-159">This request disables the middleware.</span></span>

<span data-ttu-id="e3ec0-160">たとえば、アプリケーションが実行されたら、任意のブラウザーで次の URI を使用して要求を実行することにより、ミドルウェアを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-160">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="e3ec0-161">注文マイクロサービスにはポート 5103 を使用することにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-161">Note that the ordering microservice uses port 5103.</span></span>

`http://localhost:5103/failing?enable`

<span data-ttu-id="e3ec0-162">その後、図 8-5 に示されているように、URI `http://localhost:5103/failing` を使用して状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-162">You can then check the status using the URI `http://localhost:5103/failing`, as shown in Figure 8-5.</span></span>

![失敗したミドルウェアのシミュレーションの状態を確認するスクリーンショット。](./media/implement-circuit-breaker-pattern/failing-middleware-simulation.png)

<span data-ttu-id="e3ec0-164">**図 8-5**</span><span class="sxs-lookup"><span data-stu-id="e3ec0-164">**Figure 8-5**.</span></span> <span data-ttu-id="e3ec0-165">"failing" ASP.NET ミドルウェアの状態を確認している。この場合は無効。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-165">Checking the state of the "Failing" ASP.NET middleware – In this case, disabled.</span></span>

<span data-ttu-id="e3ec0-166">この時点で Basket マイクロサービスは、呼び出すたびに状態コード 500 を返します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-166">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="e3ec0-167">ミドルウェアを実行したら、MVC Web アプリから注文してみることができます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-167">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="e3ec0-168">要求は失敗するため、サーキットがオープン状態になります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-168">Because the requests fail, the circuit will open.</span></span>

<span data-ttu-id="e3ec0-169">次の例では、MVC Web アプリが、注文のためのロジック内に catch ブロックを含んでいることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-169">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span>  <span data-ttu-id="e3ec0-170">コードがサーキット オープンの例外を捕捉すると、ユーザーに待機を促すメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-170">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            var user = _appUserParser.Parse(HttpContext.User);
            //Http requests using the Typed Client (Service Agent)
            var vm = await _basketSvc.GetBasket(user);
            return View(vm);
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode
            HandleBrokenCircuitException();
        }
        return View();
    }

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

<span data-ttu-id="e3ec0-171">次に概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-171">Here's a summary.</span></span> <span data-ttu-id="e3ec0-172">再試行ポリシーは、HTTP 要求の実行を数回試行し、HTTP エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-172">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="e3ec0-173">再試行回数がサーキット ブレーカー ポリシーに設定された最大回数に達すると (この場合は 5 回)、アプリケーションは BrokenCircuitException をスローします。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-173">When the number of retries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="e3ec0-174">結果として、図 8-6 に示されているようなメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-174">The result is a friendly message, as shown in Figure 8-6.</span></span>

![バスケット サービスが機能しないというエラーを含む MVC Web アプリのスクリーンショット。](./media/implement-circuit-breaker-pattern/basket-service-inoperative.png)

<span data-ttu-id="e3ec0-176">**図 8-6**</span><span class="sxs-lookup"><span data-stu-id="e3ec0-176">**Figure 8-6**.</span></span> <span data-ttu-id="e3ec0-177">サーキット ブレーカーが UI にエラーを返している</span><span class="sxs-lookup"><span data-stu-id="e3ec0-177">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="e3ec0-178">サーキットをいつオープン状態にするか/中断するかに関して、別のロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-178">You can implement different logic for when to open/break the circuit.</span></span> <span data-ttu-id="e3ec0-179">または、フォールバック データセンターか冗長バックエンド システムがある場合、他のバックエンド マイクロサービスに対して HTTP 要求を試行することができます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-179">Or you can try an HTTP request against a different back-end microservice if there's a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="e3ec0-180">最後に、`CircuitBreakerPolicy` の別の可能性として、`Isolate` (サーキットを強制的にオープン状態にし、オープン状態を維持する) と `Reset` (もう一度クローズド状態にする) を使用する方法があります。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-180">Finally, another possibility for the `CircuitBreakerPolicy` is to use `Isolate` (which forces open and holds open the circuit) and `Reset` (which closes it again).</span></span> <span data-ttu-id="e3ec0-181">これらは、ポリシーに対して Isolate と Reset を直接呼び出すユーティリティ HTTP エンドポイントを構築するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-181">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span>  <span data-ttu-id="e3ec0-182">このような HTTP エンドポイントは、アップグレードしたい場合など、ダウンストリーム システムを一時的に分離するために運用環境で適切な安全性を保つために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-182">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="e3ec0-183">または、障害が発生する恐れがあるダウンストリーム システムを保護するために手動でサーキットを切断することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3ec0-183">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e3ec0-184">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="e3ec0-184">Additional resources</span></span>

- <span data-ttu-id="e3ec0-185">**サーキット ブレーカー パターン**</span><span class="sxs-lookup"><span data-stu-id="e3ec0-185">**Circuit Breaker pattern**</span></span>\
  [https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker](/azure/architecture/patterns/circuit-breaker)

>[!div class="step-by-step"]
><span data-ttu-id="e3ec0-186">[前へ](implement-http-call-retries-exponential-backoff-polly.md)
>[次へ](monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="e3ec0-186">[Previous](implement-http-call-retries-exponential-backoff-polly.md)
[Next](monitor-app-health.md)</span></span>
