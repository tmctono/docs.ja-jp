---
title: クラウドネイティブの回復性
description: Azure 向けのクラウドネイティブ .NET アプリの設計 |クラウドネイティブの回復性
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 5c4fb261515c151fd666cc33cbb020447716c814
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163558"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="a4491-103">クラウドネイティブの回復性</span><span class="sxs-lookup"><span data-stu-id="a4491-103">Cloud-native resiliency</span></span>

<span data-ttu-id="a4491-104">回復性とは、障害に対処するシステムの能力であり、引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="a4491-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="a4491-105">エラーを回避することではなく、エラーを受け入れ、クラウドネイティブサービスを構築して応答します。</span><span class="sxs-lookup"><span data-stu-id="a4491-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="a4491-106">可能な限り短時間で完全に機能する状態に戻す必要がある。</span><span class="sxs-lookup"><span data-stu-id="a4491-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="a4491-107">すべてが1つのプロセスで一緒に実行される従来のモノリシックアプリケーションとは異なり、クラウドネイティブシステムは、図6-1 に示すように分散アーキテクチャを採用しています。</span><span class="sxs-lookup"><span data-stu-id="a4491-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![分散型クラウド-ネイティブ環境](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="a4491-109">**図 6-1.**</span><span class="sxs-lookup"><span data-stu-id="a4491-109">**Figure 6-1.**</span></span> <span data-ttu-id="a4491-110">分散型クラウド-ネイティブ環境</span><span class="sxs-lookup"><span data-stu-id="a4491-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="a4491-111">上の図では、各マイクロサービスとクラウドベースの [バッキングサービス](https://12factor.net/backing-services) は、ネットワークベースの呼び出しを介して通信する、サーバーインフラストラクチャ間で個別のプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="a4491-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="a4491-112">この環境で運用されているサービスは、さまざまな課題に対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4491-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="a4491-113">予期しないネットワーク待機時間-サービス要求が受信側と返送先に移動するまでの時間。</span><span class="sxs-lookup"><span data-stu-id="a4491-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="a4491-114">[一時的な障害](/azure/architecture/best-practices/transient-faults) -有効期間が短いネットワーク接続エラー。</span><span class="sxs-lookup"><span data-stu-id="a4491-114">[Transient faults](/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="a4491-115">実行時間の長い同期操作によってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a4491-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="a4491-116">クラッシュし、再起動または移動されているホストプロセス。</span><span class="sxs-lookup"><span data-stu-id="a4491-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="a4491-117">短時間応答できないオーバーロードされたマイクロサービス。</span><span class="sxs-lookup"><span data-stu-id="a4491-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="a4491-118">ローリングアップグレードや、あるノードから別のノードへのサービスの移動など、インフライトの orchestrator 操作。</span><span class="sxs-lookup"><span data-stu-id="a4491-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="a4491-119">ハードウェア障害。</span><span class="sxs-lookup"><span data-stu-id="a4491-119">Hardware failures.</span></span>

<span data-ttu-id="a4491-120">クラウドプラットフォームでは、これらのインフラストラクチャの多くの問題を検出し、軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="a4491-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="a4491-121">再起動したり、スケールアウトしたり、サービスを別のノードに再配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4491-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="a4491-122">ただし、このような組み込みの保護を最大限に活用するには、サービスを設計し、この動的環境において対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4491-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="a4491-123">以下のセクションでは、ダウンタイムと中断を最小限に抑えるために、サービスおよび管理されたクラウドリソースが活用できる防御手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4491-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a4491-124">[前へ](elastic-search-in-azure.md)
>[次へ](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="a4491-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
