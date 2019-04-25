---
title: 回復力のあるサービス、クラウドの準備をビルドします。 クラウド内の一時的な障害を受け入れる
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |回復力のあるサービス、クラウドの準備をビルドします。 クラウド内の一時的な障害を受け入れる
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 801d017457d1cdc3c8a495c8127b203380cb1d9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61811837"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a><span data-ttu-id="365ee-105">クラウドの準備が整っている回復力のあるサービスの構築:クラウド内の一時的な障害を受け入れる</span><span class="sxs-lookup"><span data-stu-id="365ee-105">Build resilient services ready for the cloud: Embrace transient failures in the cloud</span></span>

<span data-ttu-id="365ee-106">回復性は、障害から回復し、引き続き機能する能力です。</span><span class="sxs-lookup"><span data-stu-id="365ee-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="365ee-107">回復性は、障害を回避、障害が発生するという事実を受け入れてがそれに応答するダウンタイムやデータの損失を回避する方法でについてではありません。</span><span class="sxs-lookup"><span data-stu-id="365ee-107">Resiliency is not about avoiding failures, but accepting the fact that failures will occur, and then responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="365ee-108">回復性の目的は、障害発生後にアプリケーションを完全に機能する状態に戻すことです。</span><span class="sxs-lookup"><span data-stu-id="365ee-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="365ee-109">アプリケーションは、回復性のソフトウェア ベースのモデルではなく、ハードウェアに基づくモデルを実装するには、少なくとも場合は、クラウドの準備が。</span><span class="sxs-lookup"><span data-stu-id="365ee-109">Your application is ready for the cloud when, at a minimum, it implements a software-based model of resiliency, rather than a hardware-based model.</span></span> <span data-ttu-id="365ee-110">クラウド アプリケーションでは、確かに発生する部分的な障害を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-110">Your cloud application must embrace the partial failures that will certainly occur.</span></span> <span data-ttu-id="365ee-111">デザインまたは部分的に予想される部分的な障害に回復性を実現するために、アプリケーションをリファクターします。</span><span class="sxs-lookup"><span data-stu-id="365ee-111">Design or partially refactor your application to achieve resiliency with expected partial failures.</span></span> <span data-ttu-id="365ee-112">一時的なネットワーク障害、ノード、または Vm のクラウドでのクラッシュなどの部分的な障害に対処するために設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-112">It should be designed to cope with partial failures, like transient network outages and nodes, or VMs crashing in the cloud.</span></span> <span data-ttu-id="365ee-113">偶数のコンテナー オーケストレーター クラスタ内の別のノードに移動するには、アプリケーション内での断続的な短いエラー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-113">Even containers being moved to a different node within an orchestrator cluster can cause intermittent short failures within the application.</span></span>

## <a name="handling-partial-failure"></a><span data-ttu-id="365ee-114">部分的なエラーの処理</span><span class="sxs-lookup"><span data-stu-id="365ee-114">Handling partial failure</span></span>

<span data-ttu-id="365ee-115">クラウド ベースのアプリケーションでは、常につきまとう部分的な障害のリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="365ee-115">In a cloud-based application, there's an ever-present risk of partial failure.</span></span> <span data-ttu-id="365ee-116">たとえば、1 つの web サイト インスタンスまたはコンテナーが失敗する、または利用できない、または短時間応答しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-116">For instance, a single website instance or a container might fail, or it might be unavailable or unresponsive for a short time.</span></span> <span data-ttu-id="365ee-117">または、1 つの VM またはサーバーがクラッシュする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-117">Or, a single VM or server might crash.</span></span>

<span data-ttu-id="365ee-118">クライアントとサービスは個別のプロセスであるため、サービス可能性があります、クライアントの要求にタイムリーに応答することができません。</span><span class="sxs-lookup"><span data-stu-id="365ee-118">Because clients and services are separate processes, a service might not be able to respond in a timely manner to a client's request.</span></span> <span data-ttu-id="365ee-119">サービスがオーバー ロードされたされ、要求に応答が遅くまたは必要はありません、短い時間でアクセス可能なネットワークの問題により。</span><span class="sxs-lookup"><span data-stu-id="365ee-119">The service might be overloaded and respond slowly to requests, or it might not be accessible for a short time because of network issues.</span></span>

<span data-ttu-id="365ee-120">たとえば、Azure SQL Database のデータベースにアクセスするモノリシック .NET アプリケーションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="365ee-120">For example, consider a monolithic .NET application that accesses a database in Azure SQL Database.</span></span> <span data-ttu-id="365ee-121">Azure SQL データベースまたはその他のサード パーティのサービスがについて簡単に応答していない場合 (Azure SQL データベースを別のノードやサーバーに移動される可能性および数秒応答できません) は、時間、アプリケーションがクラッシュする場合、ユーザーが任意のアクションを実行しようとすると、および表示w 同じ時間に例外を発生します。</span><span class="sxs-lookup"><span data-stu-id="365ee-121">If the Azure SQL database or any other third-party service is unresponsive for a brief time (an Azure SQL database might be moved to a different node or server, and be unresponsive for a few seconds), when the user tries to do any action, the application might crash and show an exception at the same moment.</span></span>

<span data-ttu-id="365ee-122">同様のシナリオには、HTTP サービスを使用するアプリで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-122">A similar scenario might occur in an app that consumes HTTP services.</span></span> <span data-ttu-id="365ee-123">ネットワークまたはサービス自体できない可能性があります、クラウドで、短い一時的な障害の発生時にします。</span><span class="sxs-lookup"><span data-stu-id="365ee-123">The network or the service itself might not be available in the cloud during a short, transient failure.</span></span>

<span data-ttu-id="365ee-124">図 4-9 に示すような回復力のあるアプリケーションでは、アプリケーションのリソースの一時的なエラーを処理する機会を提供する「指数関数的バックオフによる再試行」などの手法を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-124">A resilient application like the one shown in Figure 4-9 should implement techniques like "retries with exponential backoff" to give the application an opportunity to handle transient failures in resources.</span></span> <span data-ttu-id="365ee-125">また、「サーキット ブレーカー」をアプリケーションで使用することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="365ee-125">You also should use "circuit breakers" in your applications.</span></span> <span data-ttu-id="365ee-126">サーキット ブレーカーは、実際に長期的な障害の場合、リソースにアクセスしようとしてからアプリケーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="365ee-126">A circuit breaker stops an application from trying to access a resource when it's actually a long-term failure.</span></span> <span data-ttu-id="365ee-127">サーキット ブレーカーを使用すると、アプリケーションを富んだ自体をサービス拒否攻撃を回避できます。</span><span class="sxs-lookup"><span data-stu-id="365ee-127">By using a circuit breaker, the application avoids provoking a denial of service to itself.</span></span>

![指数関数的バックオフによる再試行によって処理される部分的な障害](./media/image9.png)

> <span data-ttu-id="365ee-129">**図 4-9 です。**</span><span class="sxs-lookup"><span data-stu-id="365ee-129">**Figure 4-9.**</span></span> <span data-ttu-id="365ee-130">指数関数的バックオフによる再試行によって処理される部分的な障害</span><span class="sxs-lookup"><span data-stu-id="365ee-130">Partial failures handled by retries with exponential backoff</span></span>

<span data-ttu-id="365ee-131">HTTP リソースとデータベース リソースの両方に、これらの手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="365ee-131">You can use these techniques both in HTTP resources and in database resources.</span></span> <span data-ttu-id="365ee-132">図 4-9 では、アプリケーションはこれらの手法は、サービス レベル (HTTP) とデータ層 (TCP) を作成する必要があるため、3 層アーキテクチャに基づきます。</span><span class="sxs-lookup"><span data-stu-id="365ee-132">In Figure 4-9, the application is based on a 3-tier architecture, so you need these techniques at the services level (HTTP) and at the data tier level (TCP).</span></span> <span data-ttu-id="365ee-133">(その他のサービスまたはマイクロ サービス) のデータベースだけでなく、1 つのアプリ レベルのみを使用してモノリシック アプリケーションをデータベースの接続レベルで一時的な障害を処理する可能性があります十分。</span><span class="sxs-lookup"><span data-stu-id="365ee-133">In a monolithic application that uses only a single app tier in addition to the database (no additional services or microservices), handling transient failures at the database connection level might be enough.</span></span> <span data-ttu-id="365ee-134">このシナリオでは、特定のデータベース接続の構成だけが必要です。</span><span class="sxs-lookup"><span data-stu-id="365ee-134">In that scenario, just a particular configuration of the database connection is required.</span></span>

<span data-ttu-id="365ee-135">回復力のある通信を使用している .NET のバージョンに応じて、データベースへのアクセスを実装するときに簡単なできます (たとえば、 [Entity Framework 6 以降](/ef/ef6/fundamentals/connection-resiliency/retry-logic)します。</span><span class="sxs-lookup"><span data-stu-id="365ee-135">When implementing resilient communications that access the database, depending on the version of .NET you are using, it can be straightforward (for example, [with Entity Framework 6 or later](/ef/ef6/fundamentals/connection-resiliency/retry-logic).</span></span> <span data-ttu-id="365ee-136">データベース接続を構成するだけで済みます)。</span><span class="sxs-lookup"><span data-stu-id="365ee-136">It's just a matter of configuring the database connection).</span></span> <span data-ttu-id="365ee-137">またはなどの他のライブラリを使用する必要があります、 [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (以前のバージョンの .NET)、独自のライブラリを実装します。</span><span class="sxs-lookup"><span data-stu-id="365ee-137">Or, you might need to use additional libraries like the [Transient Fault Handling Application Block](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (for earlier versions of .NET), or even implement your own library.</span></span>

<span data-ttu-id="365ee-138">使用する .NET の推奨事項は、HTTP の再試行、サーキット ブレーカーを実装する場合、 [Polly](https://github.com/App-vNext/Polly)ライブラリで、.NET Framework 4.0、.NET Framework 4.5、および .NET Core のサポートを含む .NET Standard 1.1 を対象とします。</span><span class="sxs-lookup"><span data-stu-id="365ee-138">When implementing HTTP retries and circuit breakers, the recommendation for .NET is to use the [Polly](https://github.com/App-vNext/Polly) library, which targets .NET Framework 4.0, .NET Framework 4.5, and .NET Standard 1.1, which includes .NET Core support.</span></span>

<span data-ttu-id="365ee-139">クラウドでの部分的な障害を処理するための戦略を実装する方法については、次の参照を参照してください。</span><span class="sxs-lookup"><span data-stu-id="365ee-139">To learn how to implement strategies for handling partial failures in the cloud, see the following references.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="365ee-140">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="365ee-140">Additional resources</span></span>

-   <span data-ttu-id="365ee-141">**部分的なエラーを処理するために回復力のある通信を実装します。**</span><span class="sxs-lookup"><span data-stu-id="365ee-141">**Implementing resilient communication to handle partial failure**</span></span>

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   <span data-ttu-id="365ee-142">**Entity Framework 接続の回復性と再試行ロジック (バージョン 6 以降)**</span><span class="sxs-lookup"><span data-stu-id="365ee-142">**Entity Framework connection resiliency and retry logic (version 6 and later)**</span></span>

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

-   <span data-ttu-id="365ee-143">**Transient Fault Handling Application Block**</span><span class="sxs-lookup"><span data-stu-id="365ee-143">**The Transient Fault Handling Application Block**</span></span>

-   <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

-   <span data-ttu-id="365ee-144">**回復力のある HTTP 通信 Polly ライブラリ**</span><span class="sxs-lookup"><span data-stu-id="365ee-144">**Polly library for resilient HTTP communication**</span></span>

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
><span data-ttu-id="365ee-145">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[次へ](modernize-your-apps-with-monitoring-and-telemetry.md)</span><span class="sxs-lookup"><span data-stu-id="365ee-145">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](modernize-your-apps-with-monitoring-and-telemetry.md)</span></span>
