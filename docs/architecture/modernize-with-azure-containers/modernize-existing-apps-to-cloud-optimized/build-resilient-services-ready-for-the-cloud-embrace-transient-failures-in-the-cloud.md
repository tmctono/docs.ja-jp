---
title: クラウドのための回復力のあるサービスを構築できます。 クラウド内の一時的な障害を受け入れる
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |クラウドのための回復力のあるサービスを構築できます。 クラウド内の一時的な障害を受け入れる
ms.date: 04/30/2018
ms.openlocfilehash: 5f44029a214cf1f366fc787e27a9ac34599c4dca
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373970"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="fd00f-105">クラウドの準備が整っている回復力のあるサービスの構築:クラウド内の一時的な障害を受け入れる</span><span class="sxs-lookup"><span data-stu-id="fd00f-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="fd00f-106">回復性は、障害から回復し、引き続き機能する能力です。</span><span class="sxs-lookup"><span data-stu-id="fd00f-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="fd00f-107">回復性は、障害を回避することではなく、障害が発生したという事実を受け入れ、ダウンタイムやデータ損失を回避する方法でそれらに応答します。</span><span class="sxs-lookup"><span data-stu-id="fd00f-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="fd00f-108">回復性の目的は、障害発生後にアプリケーションを完全に機能する状態に戻すことです。</span><span class="sxs-lookup"><span data-stu-id="fd00f-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="fd00f-109">アプリケーションは、ハードウェアベースのモデルではなく、回復性のソフトウェアベースのモデルを実装する必要がある場合に、クラウドの準備ができています。</span><span class="sxs-lookup"><span data-stu-id="fd00f-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="fd00f-110">クラウドアプリケーションは、確実に発生する部分的な障害を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="fd00f-111">アプリケーションを設計または部分的にリファクタリングして、予想される部分的な障害による回復性を実現します。</span><span class="sxs-lookup"><span data-stu-id="fd00f-111">Design or partially refactor your application to achieve resiliency with expected partial failures.</span></span> <span data-ttu-id="fd00f-112">これは、一時的なネットワークの停止やノード、クラウドでクラッシュした Vm など、部分的な障害に対処するように設計されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="fd00f-113">コンテナーが orchestrator クラスター内の別のノードに移動されても、アプリケーション内で断続的にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="fd00f-114">部分的なエラーの処理</span><span class="sxs-lookup"><span data-stu-id="fd00f-114">Handling partial failure</span></span>

<span data-ttu-id="fd00f-115">クラウドベースのアプリケーションでは、部分的な障害のリスクが発生しています。</span><span class="sxs-lookup"><span data-stu-id="fd00f-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="fd00f-116">たとえば、1つの web サイトインスタンスまたはコンテナーが失敗したり、短時間に利用できなくなったり、応答しなくなったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="fd00f-117">または、単一の VM またはサーバーがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="fd00f-118">クライアントとサービスは別のプロセスであるため、サービスはクライアントの要求に適時に応答できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="fd00f-119">サービスが過負荷になり、要求に対して応答が遅くなったり、ネットワークの問題のために短時間アクセスできなくなったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-119">The service might be overloaded and respond slowly to requests, or it might not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="fd00f-120">たとえば、Azure SQL Database のデータベースにアクセスするモノリシック .NET アプリケーションについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="fd00f-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="fd00f-121">Azure SQL database またはその他のサードパーティのサービスが短時間応答しない場合 (Azure SQL データベースが別のノードまたはサーバーに移動され、数秒間応答しなくなる場合があります)、ユーザーが何らかの操作を実行しようとすると、アプリケーションがクラッシュし、表示 (される可能性があります。同時に例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="fd00f-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the same moment.</span></span>

<span data-ttu-id="fd00f-122">同様のシナリオは、HTTP サービスを使用するアプリで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="fd00f-123">短時間で一時的な障害が発生しても、ネットワークまたはサービス自体がクラウドで利用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="fd00f-124">図4-9 に示されているような弾力性のあるアプリケーションでは、リソースの一時的な障害をアプリケーションが処理できるようにするための "指数バックオフによる再試行" などの手法を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="fd00f-125">また、アプリケーションで "サーキットブレーカー" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="fd00f-126">サーキットブレーカーは、アプリケーションが実際に長期間の障害である場合に、リソースにアクセスしようとするのを停止します。</span><span class="sxs-lookup"><span data-stu-id="fd00f-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="fd00f-127">サーキットブレーカーを使用することにより、アプリケーションはサービス拒否攻撃を provoking ことを回避します。</span><span class="sxs-lookup"><span data-stu-id="fd00f-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![指数バックオフによる再試行によって処理される部分的なエラー](./media/image9.png)

<span data-ttu-id="fd00f-129">**図 4-9.**</span><span class="sxs-lookup"><span data-stu-id="fd00f-129">**Figure 4-9.**</span></span> <span data-ttu-id="fd00f-130">指数バックオフによる再試行によって処理される部分的なエラー</span><span class="sxs-lookup"><span data-stu-id="fd00f-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="fd00f-131">これらの手法は、HTTP リソースとデータベースリソースの両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd00f-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="fd00f-132">図4-9 では、アプリケーションは3層アーキテクチャに基づいているため、サービスレベル (HTTP) およびデータ層レベル (TCP) でこれらの手法が必要になります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="fd00f-133">データベースに加えて1つのアプリ層のみを使用するモノリシックアプリケーション (追加のサービスやマイクロサービスがない場合) では、データベース接続レベルでの一時的なエラーの処理が十分である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="fd00f-134">このシナリオでは、データベース接続の特定の構成のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="fd00f-134">In that scenario, just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="fd00f-135">データベースにアクセスする回復力のある通信を実装する場合、使用している .NET のバージョンによっては、(たとえば、 [Entity Framework 6](/ef/ef6/fundamentals/connection-resiliency/retry-logic)以降を含む) 簡単にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd00f-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be straightforward (for example, [with Entity Framework 6 or later](/ef/ef6/fundamentals/connection-resiliency/retry-logic).</span></span> <span data-ttu-id="fd00f-136">これは、データベース接続を構成するだけの問題です)。</span><span class="sxs-lookup"><span data-stu-id="fd00f-136">It's just a matter of configuring the database connection).</span></span> <span data-ttu-id="fd00f-137">または、[一時的なエラー処理アプリケーションブロック](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50))(以前のバージョンの .net の場合) などの追加のライブラリを使用したり、独自のライブラリを実装したりする必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fd00f-137">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="fd00f-138">HTTP 再試行とサーキットブレーカーを実装する場合は、.NET の推奨事項として、.NET Framework 4.0、.NET Framework 4.5、.NET Standard 1.1 (.NET Core サポートを含む) を対象と[する、このライブラリを](https://github.com/App-vNext/Polly)使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd00f-138">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET Framework 4.0, .NET Framework 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="fd00f-139">クラウドで部分的なエラーを処理するための戦略を実装する方法については、次の参照情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd00f-139">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fd00f-140">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="fd00f-140">Additional resources</span></span>

- <span data-ttu-id="fd00f-141">**部分的なエラーを処理するための回復力のある通信の実装**</span><span class="sxs-lookup"><span data-stu-id="fd00f-141">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- <span data-ttu-id="fd00f-142">**接続の回復性と再試行ロジックの Entity Framework (バージョン6以降)**</span><span class="sxs-lookup"><span data-stu-id="fd00f-142">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- <span data-ttu-id="fd00f-143">**一時的エラー処理アプリケーションブロック**</span><span class="sxs-lookup"><span data-stu-id="fd00f-143">**The Transient Fault Handling Application Block**</span></span>

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- <span data-ttu-id="fd00f-144">**回復性の高い HTTP 通信のためのライブラリ**</span><span class="sxs-lookup"><span data-stu-id="fd00f-144">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
><span data-ttu-id="fd00f-145">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[次へ](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="fd00f-145">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
