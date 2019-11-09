---
title: クラウドネイティブなアプリケーションの概要
description: クラウドネイティブコンピューティングについて
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: 1d3679c7f1ab940d7ab3e194c200483b63276883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841769"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="826c5-103">クラウドネイティブなアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="826c5-103">Introduction to cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="826c5-104">もう1日、オフィスでは、「次の大きなこと」に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="826c5-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="826c5-105">Cellphone リング。</span><span class="sxs-lookup"><span data-stu-id="826c5-105">Your cellphone rings.</span></span> <span data-ttu-id="826c5-106">お客様のフレンドリな採用者です。新しいジョブについて1日に2回呼び出します。</span><span class="sxs-lookup"><span data-stu-id="826c5-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="826c5-107">しかし、今回は、開始、資本、および大量の資金調達も異なります。</span><span class="sxs-lookup"><span data-stu-id="826c5-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="826c5-108">クラウドと最先端のテクノロジについては、エッジに対してお話しします。</span><span class="sxs-lookup"><span data-stu-id="826c5-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="826c5-109">数週間後、設計セッションの新しい従業員が、主要な e コマースアプリケーションを設計しています。</span><span class="sxs-lookup"><span data-stu-id="826c5-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="826c5-110">他の主要な電子商取引サイトを使用して作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="826c5-110">You're going to complete with other leading eCommerce sites.</span></span>

<span data-ttu-id="826c5-111">どのようにしてビルドするのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="826c5-111">How will you build it?</span></span>

<span data-ttu-id="826c5-112">15年前のガイダンスに従っている場合は、図1.1 に示すシステムが構築される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="826c5-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![従来のモノリシック設計](./media/monolithic-design.png)

<span data-ttu-id="826c5-114">**(図 1-1)** 。</span><span class="sxs-lookup"><span data-stu-id="826c5-114">**Figure 1-1**.</span></span> <span data-ttu-id="826c5-115">従来のモノリシック設計</span><span class="sxs-lookup"><span data-stu-id="826c5-115">Traditional monolithic design</span></span>

<span data-ttu-id="826c5-116">すべてのドメインロジックを含む大規模なコアアプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="826c5-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="826c5-117">これには、Id、カタログ、順序付けなどのモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="826c5-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="826c5-118">コアアプリは、大規模なリレーショナルデータベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="826c5-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="826c5-119">コアは、HTML インターフェイスを介して機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="826c5-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="826c5-120">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="826c5-120">Congratulations!</span></span>  <span data-ttu-id="826c5-121">モノリシックアプリケーションを作成したばかりです。</span><span class="sxs-lookup"><span data-stu-id="826c5-121">You just created a monolithic application.</span></span>

<span data-ttu-id="826c5-122">すべてが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="826c5-122">Not all is bad.</span></span> <span data-ttu-id="826c5-123">モノリスには、いくつかの異なる利点があります。</span><span class="sxs-lookup"><span data-stu-id="826c5-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="826c5-124">たとえば、次のように簡単です。</span><span class="sxs-lookup"><span data-stu-id="826c5-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="826c5-125">ビルド</span><span class="sxs-lookup"><span data-stu-id="826c5-125">build</span></span>
- <span data-ttu-id="826c5-126">テスト</span><span class="sxs-lookup"><span data-stu-id="826c5-126">test</span></span>
- <span data-ttu-id="826c5-127">.Deploy</span><span class="sxs-lookup"><span data-stu-id="826c5-127">deploy</span></span>
- <span data-ttu-id="826c5-128">解決</span><span class="sxs-lookup"><span data-stu-id="826c5-128">troubleshoot</span></span>
- <span data-ttu-id="826c5-129">スケール</span><span class="sxs-lookup"><span data-stu-id="826c5-129">scale</span></span>

<span data-ttu-id="826c5-130">現在存在する正常なアプリの多くはモノリスとして作成されました。</span><span class="sxs-lookup"><span data-stu-id="826c5-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="826c5-131">アプリはヒットし、継続的に進化し続け、イテレーション後にイテレーションを追加して、さらに多くの機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="826c5-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="826c5-132">しかし、ある時点で不快感を感じ始めます。</span><span class="sxs-lookup"><span data-stu-id="826c5-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="826c5-133">アプリケーションの制御が失われていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="826c5-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="826c5-134">時間がオンになると、気がより大きくなり、最終的には、**恐怖サイクル**と呼ばれる状態になります。</span><span class="sxs-lookup"><span data-stu-id="826c5-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the **Fear Cycle**.</span></span>

- <span data-ttu-id="826c5-135">アプリが非常に複雑になり、1人のユーザーがそれを理解することは overwhelmingly ありません。</span><span class="sxs-lookup"><span data-stu-id="826c5-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="826c5-136">変更を懸念しています。変更は、意図せず、コストのかかる副作用があります。</span><span class="sxs-lookup"><span data-stu-id="826c5-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="826c5-137">新機能と修正プログラムは、複雑になり、時間がかかり、実装にコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="826c5-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="826c5-138">各リリースでは、アプリケーション全体の完全な展開が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="826c5-138">Each release as small as it may be requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="826c5-139">不安定なコンポーネントの1つは、システム全体をクラッシュさせる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="826c5-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="826c5-140">新しいテクノロジとフレームワークはオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="826c5-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="826c5-141">アジャイル配信方法論を実装することは困難です。</span><span class="sxs-lookup"><span data-stu-id="826c5-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="826c5-142">アーキテクチャ erosion は、をコードベース悪化として設定します。</span><span class="sxs-lookup"><span data-stu-id="826c5-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="826c5-143">コンサルタントによって、再作成するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="826c5-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="826c5-144">多くの組織は、システムを構築するためのクラウドネイティブアプローチを採用することで、モノリシックな懸念サイクルに取り組んできました。</span><span class="sxs-lookup"><span data-stu-id="826c5-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="826c5-145">図1-2 は、クラウドネイティブの手法とプラクティスを適用して構築された同じシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="826c5-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![クラウドネイティブ設計](./media/cloud-native-design.png)

<span data-ttu-id="826c5-147">**図 1-2**.</span><span class="sxs-lookup"><span data-stu-id="826c5-147">**Figure 1-2**.</span></span> <span data-ttu-id="826c5-148">クラウドネイティブ設計</span><span class="sxs-lookup"><span data-stu-id="826c5-148">Cloud-native design</span></span>

<span data-ttu-id="826c5-149">小さな分離マイクロサービスのセットにわたってアプリケーションがどのように分解されるかに注意してください。</span><span class="sxs-lookup"><span data-stu-id="826c5-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="826c5-150">各サービスは自己完結型であり、独自のコード、データ、および依存関係をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="826c5-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="826c5-151">各は、ソフトウェアコンテナーに展開され、コンテナー orchestrator によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="826c5-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="826c5-152">大規模なリレーショナルデータベースの代わりに、各サービスが独自のデータストアを所有しています。この種類は、データのニーズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="826c5-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="826c5-153">一部のサービスはリレーショナルデータベースに依存しますが、他のサービスは NoSQL データベースに依存します。</span><span class="sxs-lookup"><span data-stu-id="826c5-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="826c5-154">1つのサービスでは、その状態が分散キャッシュに格納されます。</span><span class="sxs-lookup"><span data-stu-id="826c5-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="826c5-155">すべてのトラフィックが、コアバックエンドサービスへのトラフィックのルーティングを担当する API ゲートウェイサービスを介してルーティングされ、さまざまな横断的懸念が適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="826c5-155">Note how all traffic routes through an API Gateway service that is responsible for routing traffic to the core back-end services  and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="826c5-156">最も重要なのは、アプリケーションは、最新のクラウドプラットフォームで検出されたスケーラビリティと回復性の機能を最大限に活用することです。</span><span class="sxs-lookup"><span data-stu-id="826c5-156">Most importantly, the application takes full advantage of the scalability and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="826c5-157">クラウドネイティブコンピューティング</span><span class="sxs-lookup"><span data-stu-id="826c5-157">Cloud-native computing</span></span>

<span data-ttu-id="826c5-158">んん。。。ここでは、「*クラウドネイティブ*」という用語を使用していました。</span><span class="sxs-lookup"><span data-stu-id="826c5-158">Hmm... We just used the term, "*Cloud Native*."</span></span> <span data-ttu-id="826c5-159">まず、"これは何を意味するのでしょうか" と考えています。</span><span class="sxs-lookup"><span data-stu-id="826c5-159">You first thought might be, “What exactly does that mean?”</span></span> <span data-ttu-id="826c5-160">もう1つの業界流行 concocted は、ソフトウェアベンダーによってさらに市場を拡大しています。」</span><span class="sxs-lookup"><span data-stu-id="826c5-160">Another industry buzzword concocted by software vendors to market more stuff?”</span></span>

<span data-ttu-id="826c5-161">幸いなことに、この書籍はお客様を説得するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="826c5-161">Fortunately it’s far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="826c5-162">クラウドのネイティブは、ソフトウェア業界の推進傾向になっています。</span><span class="sxs-lookup"><span data-stu-id="826c5-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="826c5-163">これは、大規模で複雑なシステムを構築するための新しい方法であり、最新のソフトウェア開発プラクティス、テクノロジ、およびクラウドインフラストラクチャを最大限に活用するアプローチです。</span><span class="sxs-lookup"><span data-stu-id="826c5-163">It’s a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="826c5-164">このアプローチは、システムの設計、実装、展開、および運用化の方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="826c5-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="826c5-165">業界を促進する継続的な誇大広告とは異なり、クラウドネイティブは "*real*" です。</span><span class="sxs-lookup"><span data-stu-id="826c5-165">Unlike the continuous hype that drives our industry, cloud native is “*for-real*.”</span></span> <span data-ttu-id="826c5-166">クラウドネイティブコンピューティングをテクノロジとクラウドスタック全体で広く利用できるようにするために、300の主要企業のコンソーシアムである[クラウドネイティブコンピューティングファンデーション](https://www.cncf.io/)(cncf) について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="826c5-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="826c5-167">最も影響力の高いオープンソースグループの1つとして、GitHub で急速に成長するオープンソースプロジェクトの多くをホストしています。</span><span class="sxs-lookup"><span data-stu-id="826c5-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="826c5-168">これには、 [Kubernetes](https://kubernetes.io/)、 [prometheus](https://prometheus.io/)、[ヘルム](https://helm.sh/)、[エンボイ](https://www.envoyproxy.io/)、 [grpc](https://grpc.io/)などのプロジェクトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="826c5-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="826c5-169">CNCF は、オープンソースとベンダーニュートラルのエコシステムを促進します。</span><span class="sxs-lookup"><span data-stu-id="826c5-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="826c5-170">その後、クラウドネイティブの原則、パターン、およびテクノロジに依存しないベストプラクティスを紹介します。</span><span class="sxs-lookup"><span data-stu-id="826c5-170">Following that lead, we present cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="826c5-171">同時に、クラウドネイティブシステムを構築するために Microsoft Azure クラウドで利用できるサービスとインフラストラクチャについても説明します。</span><span class="sxs-lookup"><span data-stu-id="826c5-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span>

<span data-ttu-id="826c5-172">クラウドネイティブとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="826c5-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="826c5-173">戻ってリラックスし、この新しい世界を探検してみてください。</span><span class="sxs-lookup"><span data-stu-id="826c5-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="826c5-174">[前へ](index.md)
>[次へ](definition.md)</span><span class="sxs-lookup"><span data-stu-id="826c5-174">[Previous](index.md)
[Next](definition.md)</span></span>
