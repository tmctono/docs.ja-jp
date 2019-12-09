---
title: クラウドの準備が整っている回復力のあるサービスを構築する。 クラウド内の一時的な障害を受け入れる
description: Azure Cloud と Windows コンテナーを使って既存の .NET アプリケーションを最新化する | クラウドに対応する回復力のあるサービスを構築する。 クラウド内の一時的な障害を受け入れる
ms.date: 04/30/2018
ms.openlocfilehash: e516dc675ceb8def25c6d676bced0ea7f253b2d5
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711260"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="34e0a-105">クラウドの準備が整っている回復力のあるサービスの構築:クラウド内の一時的な障害を受け入れる</span><span class="sxs-lookup"><span data-stu-id="34e0a-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="34e0a-106">回復性は、障害から回復し、引き続き機能する能力です。</span><span class="sxs-lookup"><span data-stu-id="34e0a-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="34e0a-107">回復性は障害を回避することではなく、障害が発生するという事実を受け入れ、ダウンタイムまたはデータの損失を回避するようにそれらに対応することです。</span><span class="sxs-lookup"><span data-stu-id="34e0a-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="34e0a-108">回復性の目的は、障害発生後にアプリケーションを完全に機能する状態に戻すことです。</span><span class="sxs-lookup"><span data-stu-id="34e0a-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="34e0a-109">少なくとも、ハードウェアベースのモデルではなく、ソフトウェアベースの回復性のモデルを実装する場合、アプリケーションはクラウドに対応できます。</span><span class="sxs-lookup"><span data-stu-id="34e0a-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="34e0a-110">クラウド アプリケーションは、確実に発生する部分的な障害を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="34e0a-111">アプリケーションを設計または部分的にリファクタリングし、予想される部分的な障害に対する回復力を実現します。</span><span class="sxs-lookup"><span data-stu-id="34e0a-111">Design or partially refactor your application to achieve resiliency with expected partial failures.</span></span> <span data-ttu-id="34e0a-112">一時的なネットワークの停止、クラウド内のノードまたは VM のクラッシュなどの部分的な障害に対処するように設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="34e0a-113">オーケストレーター クラスタ内でコンテナーを別のノードに移動するだけでも、アプリケーション内での断続的な短いエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="34e0a-114">部分的なエラーの処理</span><span class="sxs-lookup"><span data-stu-id="34e0a-114">Handling partial failure</span></span>

<span data-ttu-id="34e0a-115">クラウドベースのアプリケーションでは、部分的な障害のリスクが常にあります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="34e0a-116">たとえば、1 つの Web サイト インスタンスまたはコンテナーに障害が発生する場合や、短時間使用不能になったり、応答しなくなったりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="34e0a-117">また、1 つの VM またはサーバーがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="34e0a-118">クライアントとサービスは別のプロセスなので、サービスがクライアントの要求に迅速に応答できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="34e0a-119">サービスが過負荷になり、要求への応答が遅くなる場合や、ネットワークの問題のために短時間アクセスできなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-119">The service might be overloaded and respond slowly to requests, or it might not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="34e0a-120">たとえば、Azure SQL Database のデータベースにアクセスするモノリシック .NET アプリケーションについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="34e0a-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="34e0a-121">Azure SQL Database またはその他のサードパーティ サービスが短時間応答しない場合 (Azure SQL Database が別のノードまたはサーバーに移動し、数秒間応答しない場合)、ユーザーが何らかのアクションを実行しようとしたとき、アプリケーションがクラッシュし、同時に例外が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the same moment.</span></span>

<span data-ttu-id="34e0a-122">HTTP サービスを使用するアプリでも、同様のシナリオが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="34e0a-123">短時間の一時的な障害の間に、ネットワークまたはサービス自体をクラウドで利用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="34e0a-124">図 4-9 に示すような回復性があるアプリケーションでは、"エクスポネンシャル バックオフを伴う再試行" などの手法を実装して、リソースの一時的な障害を処理する機会をアプリケーションに与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="34e0a-125">また、アプリケーションには "サーキット ブレーカー" も使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="34e0a-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="34e0a-126">サーキット ブレーカーを使うと、実際には長期的な障害の場合に、アプリケーションによるリソースへのアクセスを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="34e0a-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="34e0a-127">アプリケーションにサーキット ブレーカーを使用することで、アプリケーション自体へのサービス拒否攻撃の発生が回避されます。</span><span class="sxs-lookup"><span data-stu-id="34e0a-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![エクスポネンシャル バックオフによる再試行によって処理される部分的な障害の図。](./media/retry-partial-failures.png)

<span data-ttu-id="34e0a-129">**図 4-9**</span><span class="sxs-lookup"><span data-stu-id="34e0a-129">**Figure 4-9.**</span></span> <span data-ttu-id="34e0a-130">エクスポネンシャル バックオフを使用した再試行によって処理される部分的な障害</span><span class="sxs-lookup"><span data-stu-id="34e0a-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="34e0a-131">これらの手法は、HTTP リソースとデータベース リソースの両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="34e0a-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="34e0a-132">図 4-9 では、アプリケーションは 3 層アーキテクチャに基づいているため、これらの手法はサービス レベル (HTTP) およびデータ層レベル (TCP) で必要です。</span><span class="sxs-lookup"><span data-stu-id="34e0a-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="34e0a-133">データベースに加えて 1 つのアプリ層のみを使用する (追加のサービスやマイクロサービスは使用しない) モノリシック アプリケーションでは、データベース接続レベルで一時的な障害を処理するだけで十分な場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="34e0a-134">このシナリオでは、データベース接続の特定の構成のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="34e0a-134">In that scenario, just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="34e0a-135">データベースにアクセスする回復性がある通信を実装する場合、使用している .NET のバージョンによっては簡単な可能性があります (たとえば、[Entity Framework 6 以降](/ef/ef6/fundamentals/connection-resiliency/retry-logic)。</span><span class="sxs-lookup"><span data-stu-id="34e0a-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be straightforward (for example, [with Entity Framework 6 or later](/ef/ef6/fundamentals/connection-resiliency/retry-logic).</span></span> <span data-ttu-id="34e0a-136">これは、データベース接続を構成するだけの問題です)。</span><span class="sxs-lookup"><span data-stu-id="34e0a-136">It's just a matter of configuring the database connection).</span></span> <span data-ttu-id="34e0a-137">または、[一時的エラー処理アプリケーション ブロック](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (以前のバージョンの .NET の場合) などの追加のライブラリを使用したり、独自のライブラリを実装したりする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="34e0a-137">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="34e0a-138">HTTP 再試行とサーキット ブレーカーを実装する場合、.NET の推奨事項は、.NET Framework サポートを含む .NET Framework 4.0、.NET Framework 4.5、および .NET Standard 1.1 を対象とする [Polly](https://github.com/App-vNext/Polly) ライブラリを使用することです。</span><span class="sxs-lookup"><span data-stu-id="34e0a-138">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET Framework 4.0, .NET Framework 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="34e0a-139">クラウドで部分的なエラーを処理する戦略を実装する方法については、次の参照情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34e0a-139">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="34e0a-140">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="34e0a-140">Additional resources</span></span>

- <span data-ttu-id="34e0a-141">**部分的なエラーを処理するための回復性がある通信の実装**</span><span class="sxs-lookup"><span data-stu-id="34e0a-141">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- <span data-ttu-id="34e0a-142">**接続の回復性と再試行ロジックの Entity Framework (バージョン 6 以降)**</span><span class="sxs-lookup"><span data-stu-id="34e0a-142">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- <span data-ttu-id="34e0a-143">**Transient Fault Handling Application Block**</span><span class="sxs-lookup"><span data-stu-id="34e0a-143">**The Transient Fault Handling Application Block**</span></span>

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- <span data-ttu-id="34e0a-144">**回復性の高い HTTP 通信のためのライブラリ**</span><span class="sxs-lookup"><span data-stu-id="34e0a-144">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
><span data-ttu-id="34e0a-145">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[次へ](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="34e0a-145">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
