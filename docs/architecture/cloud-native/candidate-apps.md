---
title: クラウド ネイティブの候補アプリ
description: クラウドネイティブアプローチのメリットを享受するアプリケーションの種類を確認する
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805618"
---
# <a name="candidate-apps-for-cloud-native"></a><span data-ttu-id="c01de-103">クラウド ネイティブの候補アプリ</span><span class="sxs-lookup"><span data-stu-id="c01de-103">Candidate apps for cloud native</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c01de-104">ポートフォリオ内のアプリを見てください。</span><span class="sxs-lookup"><span data-stu-id="c01de-104">Look at the apps in your portfolio.</span></span> <span data-ttu-id="c01de-105">そのうちの何人がクラウドネイティブアーキテクチャの資格を得ていますか?</span><span class="sxs-lookup"><span data-stu-id="c01de-105">How many of them qualify for a cloud-native architecture?</span></span> <span data-ttu-id="c01de-106">全部ですか。</span><span class="sxs-lookup"><span data-stu-id="c01de-106">All of them?</span></span> <span data-ttu-id="c01de-107">おそらくいくつか?</span><span class="sxs-lookup"><span data-stu-id="c01de-107">Perhaps some?</span></span>

<span data-ttu-id="c01de-108">コスト/メリット分析を適用すると、クラウド ネイティブに必要な高価な値札がサポートされない可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="c01de-108">Applying a cost/benefit analysis, there's a good chance that most wouldn't support the hefty price tag required to be cloud native.</span></span> <span data-ttu-id="c01de-109">クラウド ネイティブのコストは、アプリケーションのビジネス価値をはるかに上回ります。</span><span class="sxs-lookup"><span data-stu-id="c01de-109">The cost of being cloud native would far exceed the business value of the application.</span></span>

<span data-ttu-id="c01de-110">クラウド ネイティブの候補となるアプリケーションの種類は何ですか。</span><span class="sxs-lookup"><span data-stu-id="c01de-110">What type of application might be a candidate for cloud native?</span></span>

- <span data-ttu-id="c01de-111">ビジネス機能/機能を絶えず進化させる必要がある、大規模で戦略的なエンタープライズシステム</span><span class="sxs-lookup"><span data-stu-id="c01de-111">A large, strategic enterprise system that needs to constantly evolve business capabilities/features</span></span>

- <span data-ttu-id="c01de-112">高いリリース速度を必要とするアプリケーション - 高い信頼性を持つ</span><span class="sxs-lookup"><span data-stu-id="c01de-112">An application that requires a high release velocity - with high confidence</span></span>

- <span data-ttu-id="c01de-113">システム全体を完全に再展開*することなく*、個々の機能を解放する必要があるシステム</span><span class="sxs-lookup"><span data-stu-id="c01de-113">A system with where individual features must release *without* a full redeployment of the entire system</span></span>

- <span data-ttu-id="c01de-114">異なるテクノロジー・スタックの専門知識を持つチームが開発したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c01de-114">An application developed by teams with expertise in different technology stacks</span></span>

- <span data-ttu-id="c01de-115">個別に拡張する必要があるコンポーネントを持つアプリケーション</span><span class="sxs-lookup"><span data-stu-id="c01de-115">An application with components that must scale independently</span></span>

<span data-ttu-id="c01de-116">その後、レガシーシステムがあります。</span><span class="sxs-lookup"><span data-stu-id="c01de-116">Then there are legacy systems.</span></span> <span data-ttu-id="c01de-117">新しいアプリケーションを構築したいと考えていますが、多くの場合、ビジネスにとって重要なレガシーワークロードのモダナイゼーションを担当しています。</span><span class="sxs-lookup"><span data-stu-id="c01de-117">While we'd all like to build new applications, we're often responsible for modernizing legacy workloads that are critical to the business.</span></span> <span data-ttu-id="c01de-118">時間が経つにつれて、従来のアプリケーションはマイクロサービスに分解され、コンテナ化され、最終的にはクラウドネイティブアーキテクチャに「再プラットフォーム化」される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c01de-118">Over time, a legacy application could be decomposed into microservices, containerized, and ultimately "replatformed" into a cloud-native architecture.</span></span>

### <a name="modernizing-legacy-apps"></a><span data-ttu-id="c01de-119">レガシーアプリの最新化</span><span class="sxs-lookup"><span data-stu-id="c01de-119">Modernizing legacy apps</span></span>

<span data-ttu-id="c01de-120">Azure[クラウドと Windows コンテナーを使用した既存の .NET アプリケーションの最新化](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)の無料の Microsoft 電子書籍では、オンプレミスのワークロードをクラウドに移行するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c01de-120">The free Microsoft e-book [Modernize existing .NET applications with Azure cloud and Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) provides guidance for migrating on-premises workloads into cloud.</span></span> <span data-ttu-id="c01de-121">図 1-10 は、レガシー アプリケーションをモダナイゼーションするための単一の万能戦略がないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="c01de-121">Figure 1-10 shows that there isn't a single, one-size-fits-all strategy for modernizing legacy applications.</span></span>

![レガシーワークロードの移行戦略](./media/strategies-for-migrating-legacy-workloads.png)

<span data-ttu-id="c01de-123">**図 1-10**.</span><span class="sxs-lookup"><span data-stu-id="c01de-123">**Figure 1-10**.</span></span> <span data-ttu-id="c01de-124">レガシーワークロードの移行戦略</span><span class="sxs-lookup"><span data-stu-id="c01de-124">Strategies for migrating legacy workloads</span></span>

<span data-ttu-id="c01de-125">重要でないモノリシック アプリは、リフト アンド シフト ([クラウド インフラストラクチャ対応](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)) の移行のメリットが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="c01de-125">Monolithic apps that are non-critical largely benefit from a quick lift-and-shift ([Cloud Infrastructure-Ready](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)) migration.</span></span> <span data-ttu-id="c01de-126">ここでは、オンプレミスのワークロードは変更されずにクラウドベースの VM に再ホストされます。</span><span class="sxs-lookup"><span data-stu-id="c01de-126">Here, the on-premises workload is rehosted to a cloud-based VM, without changes.</span></span> <span data-ttu-id="c01de-127">このアプローチでは[、IaaS (サービスとしてのインフラストラクチャ) モデルを](https://azure.microsoft.com/overview/what-is-iaas/)使用します。</span><span class="sxs-lookup"><span data-stu-id="c01de-127">This approach uses the [IaaS (Infrastructure as a Service) model](https://azure.microsoft.com/overview/what-is-iaas/).</span></span> <span data-ttu-id="c01de-128">Azure には、このような移行を容易にするための[Azure 移行](https://azure.microsoft.com/services/azure-migrate/)[、Azure サイトの回復](https://azure.microsoft.com/services/site-recovery/) [、Azure データベース移行サービス](https://azure.microsoft.com/campaigns/database-migration/)などのいくつかのツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c01de-128">Azure includes several tools such as [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/), and [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) to make such a move easier.</span></span> <span data-ttu-id="c01de-129">この戦略ではコストをいくらか節約できますが、このようなアプリケーションは通常、クラウド コンピューティングのメリットを引き出して活用するように設計されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="c01de-129">While this strategy can yield some cost savings, such applications typically weren't architected to unlock and leverage the benefits of cloud computing.</span></span>

<span data-ttu-id="c01de-130">ビジネスにとって重要なモノリシック アプリは、リフト アンド シフト (*クラウド最適化*) の移行の強化によって恩恵を受けることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="c01de-130">Monolithic apps that are critical to the business oftentimes benefit from an enhanced lift-and-shift (*Cloud Optimized*) migration.</span></span> <span data-ttu-id="c01de-131">このアプローチには、アプリケーションのコア アーキテクチャを変更することなく、主要なクラウド サービスを有効にするデプロイの最適化が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c01de-131">This approach includes deployment optimizations that enable key cloud services - without changing the core architecture of the application.</span></span> <span data-ttu-id="c01de-132">たとえば、アプリケーションを[コンテナー化](https://docs.microsoft.com/virtualization/windowscontainers/about/)し、このガイドで後述する[Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/)などのコンテナー オーケストレーターにデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="c01de-132">For example, you might [containerize](https://docs.microsoft.com/virtualization/windowscontainers/about/) the application and deploy it to a container orchestrator, like [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), discussed later in this book.</span></span> <span data-ttu-id="c01de-133">クラウドに入ると、アプリケーションはデータベース、メッセージ キュー、監視、分散キャッシュなどの他のクラウド サービスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c01de-133">Once in the cloud, the application could consume other cloud services such as databases, message queues, monitoring, and distributed caching.</span></span>

<span data-ttu-id="c01de-134">最後に、戦略的なエンタープライズ機能を実行するモノリシック アプリは、この書籍の主題である*クラウドネイティブ*アプローチのメリットを最も高くします。</span><span class="sxs-lookup"><span data-stu-id="c01de-134">Finally, monolithic apps that perform strategic enterprise functions might best benefit from a *Cloud-Native* approach, the subject of this book.</span></span> <span data-ttu-id="c01de-135">このアプローチは、敏捷性と速度を提供します。</span><span class="sxs-lookup"><span data-stu-id="c01de-135">This approach provides agility and velocity.</span></span> <span data-ttu-id="c01de-136">しかし、コードの再プラットフォーム化、再設計、および書き換えが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c01de-136">But, it comes at a cost of replatforming, rearchitecting, and rewriting code.</span></span>

<span data-ttu-id="c01de-137">クラウドネイティブのアプローチが適切であると考える場合は、組織で決定を合理化します。</span><span class="sxs-lookup"><span data-stu-id="c01de-137">If you and your team believe a cloud-native approach is appropriate, it behooves you to rationalize the decision with your organization.</span></span> <span data-ttu-id="c01de-138">クラウドネイティブアプローチで解決されるビジネス上の問題は何ですか?</span><span class="sxs-lookup"><span data-stu-id="c01de-138">What exactly is the business problem that a cloud-native approach will solve?</span></span> <span data-ttu-id="c01de-139">ビジネス ニーズとどのように連携するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="c01de-139">How would it align with business needs?</span></span>

- <span data-ttu-id="c01de-140">信頼性の高い機能の迅速なリリース?</span><span class="sxs-lookup"><span data-stu-id="c01de-140">Rapid releases of features with increased confidence?</span></span>

- <span data-ttu-id="c01de-141">きめ細かなスケーラビリティ - リソースのより効率的な使用法</span><span class="sxs-lookup"><span data-stu-id="c01de-141">Fine-grained scalability - more efficient usage of resources?</span></span>

- <span data-ttu-id="c01de-142">システムの回復性が向上しましたか?</span><span class="sxs-lookup"><span data-stu-id="c01de-142">Improved system resiliency?</span></span>

- <span data-ttu-id="c01de-143">システムパフォーマンスの改善</span><span class="sxs-lookup"><span data-stu-id="c01de-143">Improved system performance?</span></span>

- <span data-ttu-id="c01de-144">操作の可視性を高めますか?</span><span class="sxs-lookup"><span data-stu-id="c01de-144">More visibility into operations?</span></span>

- <span data-ttu-id="c01de-145">開発プラットフォームとデータストアをブレンドして、仕事に最適なツールに到達しますか?</span><span class="sxs-lookup"><span data-stu-id="c01de-145">Blend development platforms and data stores to arrive at the best tool for the job?</span></span>

- <span data-ttu-id="c01de-146">将来性に関するアプリケーション投資?</span><span class="sxs-lookup"><span data-stu-id="c01de-146">Future-proof application investment?</span></span>

<span data-ttu-id="c01de-147">適切な移行戦略は、組織の優先順位と対象とするシステムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="c01de-147">The right migration strategy depends on organizational priorities and the systems you're targeting.</span></span> <span data-ttu-id="c01de-148">多くの場合、モノリシック アプリケーションをクラウド最適化したり、粒度の粗いサービスを N 層アプリに追加したりする方がコスト効率が高い場合があります。</span><span class="sxs-lookup"><span data-stu-id="c01de-148">For many, it may be more cost effective to cloud-optimize a monolithic application or add coarse-grained services to an N-Tier app.</span></span> <span data-ttu-id="c01de-149">このような場合でも、Azure App Service が提供するクラウド PaaS 機能のような機能を最大限に活用できます。</span><span class="sxs-lookup"><span data-stu-id="c01de-149">In these cases, you can still make full use of cloud PaaS capabilities like the ones offered by Azure App Service.</span></span>

## <a name="summary"></a><span data-ttu-id="c01de-150">まとめ</span><span class="sxs-lookup"><span data-stu-id="c01de-150">Summary</span></span>

<span data-ttu-id="c01de-151">この章では、クラウドネイティブコンピューティングについて紹介しました。</span><span class="sxs-lookup"><span data-stu-id="c01de-151">In this chapter, we introduced cloud-native computing.</span></span> <span data-ttu-id="c01de-152">クラウド ネイティブ アプリケーションを駆動する主要な機能と共に定義を提供しました。</span><span class="sxs-lookup"><span data-stu-id="c01de-152">We provided a definition along with the key capabilities that drive a cloud-native application.</span></span> <span data-ttu-id="c01de-153">この投資と労力を正当化するアプリケーションの種類を見ました。</span><span class="sxs-lookup"><span data-stu-id="c01de-153">We looked at the types of applications that might justify this investment and effort.</span></span>

<span data-ttu-id="c01de-154">この後の導入で、クラウドネイティブについてより詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="c01de-154">With the introduction behind, we now dive into a much more detailed look at cloud native.</span></span>

### <a name="references"></a><span data-ttu-id="c01de-155">References</span><span class="sxs-lookup"><span data-stu-id="c01de-155">References</span></span>

- [<span data-ttu-id="c01de-156">クラウド ネイティブ コンピューティングの基礎</span><span class="sxs-lookup"><span data-stu-id="c01de-156">Cloud Native Computing Foundation</span></span>](https://www.cncf.io/)

- [<span data-ttu-id="c01de-157">.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c01de-157">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="c01de-158">Azure クラウドと Windows コンテナーを使用して既存の .NET アプリケーションを最新化する</span><span class="sxs-lookup"><span data-stu-id="c01de-158">Modernize existing .NET applications with Azure cloud and Windows Containers</span></span>](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [<span data-ttu-id="c01de-159">コーネリア・デイビスによるクラウドネイティブパターン</span><span class="sxs-lookup"><span data-stu-id="c01de-159">Cloud Native Patterns by Cornelia Davis</span></span>](https://www.manning.com/books/cloud-native-patterns)

- [<span data-ttu-id="c01de-160">12要素アプリケーションを超えて</span><span class="sxs-lookup"><span data-stu-id="c01de-160">Beyond the Twelve-Factor Application</span></span>](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [<span data-ttu-id="c01de-161">コードとしてのインフラストラクチャとは</span><span class="sxs-lookup"><span data-stu-id="c01de-161">What is Infrastructure as Code</span></span>](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [<span data-ttu-id="c01de-162">Uber エンジニアリングのマイクロデプロイ:自信を持って毎日展開</span><span class="sxs-lookup"><span data-stu-id="c01de-162">Uber Engineering's Micro Deploy: Deploying Daily with Confidence</span></span>](https://eng.uber.com/micro-deploy/)

- [<span data-ttu-id="c01de-163">ネットフリックスがコードを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c01de-163">How Netflix Deploys Code</span></span>](https://www.infoq.com/news/2013/06/netflix/)

- [<span data-ttu-id="c01de-164">WeChat マイクロサービスのスケーリングの過負荷制御</span><span class="sxs-lookup"><span data-stu-id="c01de-164">Overload Control for Scaling WeChat Microservices</span></span>](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
><span data-ttu-id="c01de-165">[前へ](definition.md)
>[次へ](introduce-eshoponcontainers-reference-app.md)</span><span class="sxs-lookup"><span data-stu-id="c01de-165">[Previous](definition.md)
[Next](introduce-eshoponcontainers-reference-app.md)</span></span>
