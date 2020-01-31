---
title: クラウドネイティブの回復性
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |クラウドネイティブの回復性
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781085"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="5b915-103">クラウドネイティブの回復性</span><span class="sxs-lookup"><span data-stu-id="5b915-103">Cloud-native resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="5b915-104">回復性とは、障害に対処するシステムの能力であり、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="5b915-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="5b915-105">エラーを回避することではありません。</span><span class="sxs-lookup"><span data-stu-id="5b915-105">It isn't about avoiding failure.</span></span> <span data-ttu-id="5b915-106">しかし、クラウドベースのシステムではこのような障害に対処する必要があり、それに対応するアプリケーションを構築することは避けられません。</span><span class="sxs-lookup"><span data-stu-id="5b915-106">But it's about accepting that failure is inevitable in cloud-based systems and building your application to respond to it.</span></span> <span data-ttu-id="5b915-107">回復性の目標は、障害発生後にアプリケーションを完全に機能する状態に戻すことです。</span><span class="sxs-lookup"><span data-stu-id="5b915-107">The end-goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="5b915-108">すべてが1つのプロセスで一緒に実行される従来のモノリシックアプリケーションとは異なり、クラウドネイティブシステムは、図6-1 に示すように分散アーキテクチャを採用しています。</span><span class="sxs-lookup"><span data-stu-id="5b915-108">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace distributed architecture as shown in Figure 6-1:</span></span>

![分散型クラウド-ネイティブ環境](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="5b915-110">**図 6-1.**</span><span class="sxs-lookup"><span data-stu-id="5b915-110">**Figure 6-1.**</span></span> <span data-ttu-id="5b915-111">分散型クラウド-ネイティブ環境</span><span class="sxs-lookup"><span data-stu-id="5b915-111">Distributed cloud-native environment</span></span>

<span data-ttu-id="5b915-112">前の図では、各クライアント、マイクロサービス、およびクラウドベースの[バッキングサービス](https://12factor.net/backing-services)が個別のプロセスとして実行され、さまざまなサーバーで実行されており、ネットワークベースの呼び出しを介して通信していることがわかります。</span><span class="sxs-lookup"><span data-stu-id="5b915-112">In the previous figure, note how each client, microservice, and cloud-based [backing service](https://12factor.net/backing-services) executes as a separate process, running across different servers, all communicating via network-based calls.</span></span>

<span data-ttu-id="5b915-113">では、どのような問題が発生する可能性がありますか。</span><span class="sxs-lookup"><span data-stu-id="5b915-113">So, what could go wrong?</span></span>

- <span data-ttu-id="5b915-114">予期しない[ネットワーク待機時間](https://www.techopedia.com/definition/8553/network-latency)。</span><span class="sxs-lookup"><span data-stu-id="5b915-114">Unexpected [network latency](https://www.techopedia.com/definition/8553/network-latency).</span></span>
- <span data-ttu-id="5b915-115">[一時的な障害](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults)(一時的なネットワーク接続エラー)。</span><span class="sxs-lookup"><span data-stu-id="5b915-115">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporary network connectivity errors).</span></span>
- <span data-ttu-id="5b915-116">実行時間の長い同期操作によるブロック。</span><span class="sxs-lookup"><span data-stu-id="5b915-116">Blocking by a long-running synchronous operation.</span></span>
- <span data-ttu-id="5b915-117">クラッシュし、再起動または移動されているホストプロセス。</span><span class="sxs-lookup"><span data-stu-id="5b915-117">A host process that has crashed and is being restarted or moved.</span></span>
- <span data-ttu-id="5b915-118">短時間応答できないオーバーロードされたマイクロサービス。</span><span class="sxs-lookup"><span data-stu-id="5b915-118">An overloaded microservice that can't respond for a short time.</span></span>
- <span data-ttu-id="5b915-119">更新またはスケーリング操作などのインフライト DevOps 操作。</span><span class="sxs-lookup"><span data-stu-id="5b915-119">An in-flight DevOps operation such as an update or scaling operation.</span></span>
- <span data-ttu-id="5b915-120">1つのノードから別のノードへのサービスの移動などの Orchestrator 操作。</span><span class="sxs-lookup"><span data-stu-id="5b915-120">An Orchestrator operation such as moving a service from one node to another.</span></span>
- <span data-ttu-id="5b915-121">汎用ハードウェアからのハードウェア障害。</span><span class="sxs-lookup"><span data-stu-id="5b915-121">Hardware failures from commodity hardware.</span></span>

<span data-ttu-id="5b915-122">クラウドベースのインフラストラクチャに分散サービスを展開すると、前の一覧の要因が非常に大きくなり、それらを処理するための防御を設計および開発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b915-122">When deploying distributed services into cloud-based infrastructure, the factors from the previous list become very real and you must architect and develop defensively to deal with them.</span></span>

<span data-ttu-id="5b915-123">小規模な分散システムでは、障害の発生頻度は低くなりますが、システムのスケールアップとスケールアウトの際に、部分的な障害が通常の動作になる点に対して、これらの問題の多くを経験することができます。</span><span class="sxs-lookup"><span data-stu-id="5b915-123">In a small-scale distributed system, failure will be less frequent, but as a system scales up and out, you can expect to experience more of these issues to a point where partial failure becomes normal operation.</span></span>

<span data-ttu-id="5b915-124">そのため、アプリケーションとインフラストラクチャは回復性を備えている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b915-124">Therefore, your application and infrastructure must be resilient.</span></span> <span data-ttu-id="5b915-125">以下のセクションでは、アプリケーションに追加できる防御手法と、ユーザーのエクスペリエンスを箇条書きにするために利用できる組み込みのクラウド機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b915-125">In the following sections, we'll explore defensive techniques that you can add to your application and built-in cloud features that you can leverage to help bullet-proof your user's experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5b915-126">[前へ](elastic-search-in-azure.md)
>[次へ](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="5b915-126">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
