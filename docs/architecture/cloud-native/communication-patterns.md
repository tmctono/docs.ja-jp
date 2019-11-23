---
title: クラウドネイティブの通信パターン
description: クラウドネイティブアプリケーションでの重要なサービス通信に関する考慮事項について説明します。
author: robvet
ms.date: 08/31/2019
ms.openlocfilehash: 3bda9baa516b7bd8f893e0f58bbe5e2bfde2b61d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841145"
---
# <a name="cloud-native-communication-patterns"></a><span data-ttu-id="fbd8e-103">クラウドネイティブの通信パターン</span><span class="sxs-lookup"><span data-stu-id="fbd8e-103">Cloud-native communication patterns</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="fbd8e-104">クラウドネイティブシステムを構築する場合、通信は設計上の重要な決定になります。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-104">When constructing a cloud-native system, communication becomes a significant design decision.</span></span> <span data-ttu-id="fbd8e-105">フロントエンドクライアントアプリケーションとバックエンドマイクロサービスとの通信はどのように行われるのですか。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-105">How does a front-end client application communicate with a back-end microservice?</span></span> <span data-ttu-id="fbd8e-106">バックエンドマイクロサービスが相互に通信する方法</span><span class="sxs-lookup"><span data-stu-id="fbd8e-106">How do back-end microservices communicate with each other?</span></span> <span data-ttu-id="fbd8e-107">クラウドネイティブアプリケーションで通信を実装するときに考慮する必要がある原則、パターン、およびベストプラクティスを教えてください。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-107">What are the principles, patterns, and best practices to consider when implementing communication in cloud-native applications?</span></span>

## <a name="communication-considerations"></a><span data-ttu-id="fbd8e-108">通信に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fbd8e-108">Communication considerations</span></span>

<span data-ttu-id="fbd8e-109">モノリシックアプリケーションでは、通信は簡単です。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-109">In a monolithic application, communication is straightforward.</span></span> <span data-ttu-id="fbd8e-110">コードモジュールは、サーバー上の同じ実行可能領域 (プロセス) で一緒に実行されます。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-110">The code modules execute together in the same executable space (process) on a server.</span></span> <span data-ttu-id="fbd8e-111">この方法では、すべてが共有メモリ内で実行されるため、パフォーマンスが向上する可能性がありますが、厳密に結合されたコードは、保守、進化、および拡大縮小が困難になります。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-111">This approach can have performance advantages as everything runs together in shared memory, but results in tightly coupled code that becomes difficult to maintain, evolve, and scale.</span></span>

<span data-ttu-id="fbd8e-112">クラウドネイティブシステムは、多数の小さな独立したマイクロサービスを備えたマイクロサービスベースのアーキテクチャを実装します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-112">Cloud-native systems implement a microservice-based architecture with many small, independent microservices.</span></span> <span data-ttu-id="fbd8e-113">各マイクロサービスは個別のプロセスで実行され、通常は*クラスター*にデプロイされたコンテナー内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-113">Each microservice executes in a separate process and typically runs inside a container that is deployed to a *cluster*.</span></span>

<span data-ttu-id="fbd8e-114">クラスターは、仮想マシンのプールをグループ化して、高可用性環境を形成します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-114">A cluster groups a pool of virtual machines together to form a highly available environment.</span></span> <span data-ttu-id="fbd8e-115">コンテナー化されたマイクロサービスのデプロイと管理を担当するオーケストレーションツールで管理されています。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-115">They're managed with an orchestration tool, which is responsible for deploying and managing the containerized microservices.</span></span> <span data-ttu-id="fbd8e-116">図4-1 は、完全に管理された[Azure Kubernetes サービス](https://docs.microsoft.com/azure/aks/intro-kubernetes)を使用して azure クラウドにデプロイされた[Kubernetes](https://kubernetes.io)クラスターを示しています。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-116">Figure 4-1 shows a [Kubernetes](https://kubernetes.io) cluster deployed into the Azure cloud with the fully managed [Azure Kubernetes Services](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span></span>

![Azure の Kubernetes クラスター](./media/kubernetes-cluster-in-azure.png)

<span data-ttu-id="fbd8e-118">**図 4-1**</span><span class="sxs-lookup"><span data-stu-id="fbd8e-118">**Figure 4-1**.</span></span> <span data-ttu-id="fbd8e-119">Azure の Kubernetes クラスター</span><span class="sxs-lookup"><span data-stu-id="fbd8e-119">A Kubernetes cluster in Azure</span></span>

<span data-ttu-id="fbd8e-120">クラスター全体で、マイクロサービスは Api およびメッセージングテクノロジによって相互に通信します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-120">Across the cluster, microservices communicate with each other through APIs and messaging technologies.</span></span>

<span data-ttu-id="fbd8e-121">多くの利点がありますが、マイクロサービスは無料で提供されます。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-121">While they provide many benefits, microservices are no free lunch.</span></span> <span data-ttu-id="fbd8e-122">コンポーネント間のローカルのインプロセスメソッド呼び出しがネットワーク呼び出しに置き換えられるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-122">Local in-process method calls between components are now replaced with network calls.</span></span> <span data-ttu-id="fbd8e-123">各マイクロサービスは、ネットワークプロトコルを介して通信する必要があります。これにより、システムの複雑さが増します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-123">Each microservice must communicate over a network protocol, which adds complexity to your system:</span></span>

- <span data-ttu-id="fbd8e-124">ネットワークの輻輳、待機時間、および一時的な障害は、一定の問題です。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-124">Network congestion, latency, and transient faults are a constant concern.</span></span>

- <span data-ttu-id="fbd8e-125">回復性 (失敗した要求の再試行) は不可欠です。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-125">Resiliency (that is, retrying failed requests) is essential.</span></span>

- <span data-ttu-id="fbd8e-126">一部の呼び出しは、一貫性のある状態を維持するために[べき等](https://www.restapitutorial.com/lessons/idempotency.html)である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-126">Some calls must be [idempotent](https://www.restapitutorial.com/lessons/idempotency.html) as to keep consistent state.</span></span>

- <span data-ttu-id="fbd8e-127">各マイクロサービスは、呼び出しを認証および承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-127">Each microservice must authenticate and authorize calls.</span></span>

- <span data-ttu-id="fbd8e-128">各メッセージをシリアル化してから逆シリアル化する必要があります。この場合、コストが高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-128">Each message must be serialized and then deserialized - which can be expensive.</span></span>

- <span data-ttu-id="fbd8e-129">メッセージの暗号化/復号化が重要になります。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-129">Message encryption/decryption becomes important.</span></span>

<span data-ttu-id="fbd8e-130">本「 [.Net マイクロサービス: コンテナー化された .Net アプリケーションのアーキテクチャ](https://docs.microsoft.com/dotnet/standard/microservices-architecture/)」では、Microsoft から無料で利用でき、マイクロサービスアプリケーションの通信パターンの詳細について説明しています。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-130">The book [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture/), available for free from Microsoft, provides an in-depth coverage of communication patterns for microservice applications.</span></span> <span data-ttu-id="fbd8e-131">この章では、これらのパターンの概要と、Azure クラウドで利用可能な実装オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-131">In this chapter, we provide a high-level overview of these patterns along with implementation options available in the Azure cloud.</span></span>

<span data-ttu-id="fbd8e-132">この章では、まずフロントエンドアプリケーションとバックエンドマイクロサービス間の通信に対処します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-132">In this chapter, we'll first address communication between front-end applications and back-end microservices.</span></span> <span data-ttu-id="fbd8e-133">次に、バックエンドマイクロサービスが相互に通信することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-133">We'll then look at back-end microservices communicate with each other.</span></span> <span data-ttu-id="fbd8e-134">ここでは、up and gRPC 通信テクノロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-134">We'll explore the up and gRPC communication technology.</span></span> <span data-ttu-id="fbd8e-135">最後に、サービスメッシュテクノロジを使用した革新的な新しい通信パターンについて見ていきます。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-135">Finally, we'll look new innovative communication patterns using service mesh technology.</span></span> <span data-ttu-id="fbd8e-136">また、クラウドネイティブ通信をサポートするために、Azure クラウドがさまざまな種類の*バッキングサービス*を提供する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="fbd8e-136">We'll also see how the Azure cloud provides different kinds of *backing services* to support cloud-native communication.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fbd8e-137">[前へ](other-deployment-options.md)
>[次へ](front-end-communication.md)</span><span class="sxs-lookup"><span data-stu-id="fbd8e-137">[Previous](other-deployment-options.md)
[Next](front-end-communication.md)</span></span>
