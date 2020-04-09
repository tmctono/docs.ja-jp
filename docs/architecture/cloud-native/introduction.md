---
title: クラウドネイティブなアプリケーションの概要
description: クラウド ネイティブ コンピューティングについて
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: c9ffd34ec3deb04abddbbf85a9e5a6ed2b57c8f9
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989052"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="9990d-103">クラウドネイティブなアプリケーションの概要</span><span class="sxs-lookup"><span data-stu-id="9990d-103">Introduction to cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="9990d-104">別の日、オフィスで「次の大きなこと」に取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="9990d-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="9990d-105">あなたの携帯電話が鳴ります。</span><span class="sxs-lookup"><span data-stu-id="9990d-105">Your cellphone rings.</span></span> <span data-ttu-id="9990d-106">それはあなたのフレンドリーなリクルーターです - 新しい仕事について1日2回あなたを呼び出す人。</span><span class="sxs-lookup"><span data-stu-id="9990d-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="9990d-107">しかし、今回は異なります:スタートアップ、株式、そしてたくさんの資金。</span><span class="sxs-lookup"><span data-stu-id="9990d-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="9990d-108">クラウドと最先端の技術の言及は、エッジの上にあなたをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="9990d-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="9990d-109">数週間早送りすると、今では、主要なeコマースアプリケーションを設計する設計セッションの新入社員です。</span><span class="sxs-lookup"><span data-stu-id="9990d-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="9990d-110">他の大手eコマースサイトを完成させます。</span><span class="sxs-lookup"><span data-stu-id="9990d-110">You're going to complete with other leading eCommerce sites.</span></span>

<span data-ttu-id="9990d-111">どのようにそれを構築しますか?</span><span class="sxs-lookup"><span data-stu-id="9990d-111">How will you build it?</span></span>

<span data-ttu-id="9990d-112">過去 15 年間のガイダンスに従うと、図 1.1 に示すシステムを構築する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="9990d-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![伝統的なモノリシックなデザイン](./media/monolithic-design.png)

<span data-ttu-id="9990d-114">**図 1-1**.</span><span class="sxs-lookup"><span data-stu-id="9990d-114">**Figure 1-1**.</span></span> <span data-ttu-id="9990d-115">伝統的なモノリシックなデザイン</span><span class="sxs-lookup"><span data-stu-id="9990d-115">Traditional monolithic design</span></span>

<span data-ttu-id="9990d-116">すべてのドメイン ロジックを含む大規模なコア アプリケーションを構築します。</span><span class="sxs-lookup"><span data-stu-id="9990d-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="9990d-117">これには、ID、カタログ、順序などのモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9990d-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="9990d-118">コア アプリケーションは、大規模なリレーショナル データベースと通信します。</span><span class="sxs-lookup"><span data-stu-id="9990d-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="9990d-119">コアは、HTML インターフェイスを介して機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="9990d-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="9990d-120">おめでとうございます!</span><span class="sxs-lookup"><span data-stu-id="9990d-120">Congratulations!</span></span>  <span data-ttu-id="9990d-121">モノリシック アプリケーションを作成しました。</span><span class="sxs-lookup"><span data-stu-id="9990d-121">You just created a monolithic application.</span></span>

<span data-ttu-id="9990d-122">すべてが悪いわけではありません。</span><span class="sxs-lookup"><span data-stu-id="9990d-122">Not all is bad.</span></span> <span data-ttu-id="9990d-123">モノリスはいくつかの明確な利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="9990d-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="9990d-124">たとえば、彼らは簡単です.</span><span class="sxs-lookup"><span data-stu-id="9990d-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="9990d-125">build</span><span class="sxs-lookup"><span data-stu-id="9990d-125">build</span></span>
- <span data-ttu-id="9990d-126">テスト</span><span class="sxs-lookup"><span data-stu-id="9990d-126">test</span></span>
- <span data-ttu-id="9990d-127">配置 (deploy)</span><span class="sxs-lookup"><span data-stu-id="9990d-127">deploy</span></span>
- <span data-ttu-id="9990d-128">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9990d-128">troubleshoot</span></span>
- <span data-ttu-id="9990d-129">scale</span><span class="sxs-lookup"><span data-stu-id="9990d-129">scale</span></span>

<span data-ttu-id="9990d-130">今日存在する多くの成功したアプリは、モノリスとして作成されました。</span><span class="sxs-lookup"><span data-stu-id="9990d-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="9990d-131">アプリはヒットし、進化し続け、反復後に繰り返し、より多くの機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="9990d-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="9990d-132">しかし、ある時点で、あなたは不快に感じ始めます。</span><span class="sxs-lookup"><span data-stu-id="9990d-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="9990d-133">あなたは、アプリケーションの制御を失う自分自身を見つける。</span><span class="sxs-lookup"><span data-stu-id="9990d-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="9990d-134">時間が経つにつれて、感情はより強くなり、最終的には**恐怖サイクル**として知られている状態に入ります。</span><span class="sxs-lookup"><span data-stu-id="9990d-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the **Fear Cycle**.</span></span>

- <span data-ttu-id="9990d-135">アプリは非常に複雑になったので、誰もそれを理解していません。</span><span class="sxs-lookup"><span data-stu-id="9990d-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="9990d-136">あなたは変更を加えることを恐れています - 各変更は意図しない、高価な副作用を持っています。</span><span class="sxs-lookup"><span data-stu-id="9990d-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="9990d-137">新機能や修正プログラムは、難しく、時間がかかり、実装にコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="9990d-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="9990d-138">各リリースは、アプリケーション全体の完全な展開が必要になる可能性があるほど小さい場合があります。</span><span class="sxs-lookup"><span data-stu-id="9990d-138">Each release as small as it may be requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="9990d-139">1 つの不安定なコンポーネントがシステム全体をクラッシュさせる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9990d-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="9990d-140">新しいテクノロジやフレームワークはオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="9990d-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="9990d-141">アジャイル配信方法論を実装するのは困難です。</span><span class="sxs-lookup"><span data-stu-id="9990d-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="9990d-142">コードベースが終わりのない「特別なケース」で悪化するにつれて、建築侵食が始まる。</span><span class="sxs-lookup"><span data-stu-id="9990d-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="9990d-143">コンサルタントは、それを書き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9990d-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="9990d-144">多くの組織は、クラウドネイティブのアプローチを採用してシステムを構築することで、モノリシックな恐怖サイクルに取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="9990d-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="9990d-145">図 1-2 は、クラウドネイティブの手法とプラクティスを適用して構築された同じシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9990d-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![クラウド ネイティブ デザイン](./media/cloud-native-design.png)

<span data-ttu-id="9990d-147">**図 1-2**.</span><span class="sxs-lookup"><span data-stu-id="9990d-147">**Figure 1-2**.</span></span> <span data-ttu-id="9990d-148">クラウドネイティブデザイン</span><span class="sxs-lookup"><span data-stu-id="9990d-148">Cloud-native design</span></span>

<span data-ttu-id="9990d-149">アプリケーションが一連の小さな分離マイクロサービスでどのように分解されているかに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9990d-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="9990d-150">各サービスは自己完結型であり、独自のコード、データ、および依存関係をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="9990d-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="9990d-151">各コンテナーは、ソフトウェア コンテナーに展開され、コンテナー オーケストレーターによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="9990d-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="9990d-152">大規模なリレーショナル データベースではなく、各サービスが所有するデータストアは、データのニーズに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="9990d-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="9990d-153">一部のサービスはリレーショナルデータベースに依存していますが、NoSQLデータベースに依存しているものもあります。</span><span class="sxs-lookup"><span data-stu-id="9990d-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="9990d-154">1 つのサービスは、その状態を分散キャッシュに格納します。</span><span class="sxs-lookup"><span data-stu-id="9990d-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="9990d-155">すべてのトラフィックが、コア バックエンド サービスへのトラフィックのルーティングと多くの横断的な問題の実施を担当する API Gateway サービスを経由してルーティングする方法に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9990d-155">Note how all traffic routes through an API Gateway service that is responsible for routing traffic to the core back-end services  and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="9990d-156">最も重要なことは、アプリケーションは、最新のクラウド プラットフォームで使用されているスケーラビリティと復元力の機能を最大限に活用することです。</span><span class="sxs-lookup"><span data-stu-id="9990d-156">Most importantly, the application takes full advantage of the scalability and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="9990d-157">クラウドネイティブコンピューティング</span><span class="sxs-lookup"><span data-stu-id="9990d-157">Cloud-native computing</span></span>

<span data-ttu-id="9990d-158">んん。。。「*クラウド ネイティブ*」という用語を使用しました。</span><span class="sxs-lookup"><span data-stu-id="9990d-158">Hmm... We just used the term, "*Cloud Native*."</span></span> <span data-ttu-id="9990d-159">最初に「それはどういう意味ですか?」</span><span class="sxs-lookup"><span data-stu-id="9990d-159">You first thought might be, "What exactly does that mean?"</span></span> <span data-ttu-id="9990d-160">ソフトウェアベンダーが、より多くのものを販売するためにでっち上げた別の業界の流行語?</span><span class="sxs-lookup"><span data-stu-id="9990d-160">Another industry buzzword concocted by software vendors to market more stuff?"</span></span>

<span data-ttu-id="9990d-161">幸いなことに、それははるかに異なっており、うまくいけば、この本はあなたを説得するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9990d-161">Fortunately it's far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="9990d-162">クラウドネイティブは、ソフトウェア業界の推進傾向となっています。</span><span class="sxs-lookup"><span data-stu-id="9990d-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="9990d-163">これは、大規模で複雑なシステムの構築、最新のソフトウェア開発の実践、技術、クラウドインフラストラクチャを最大限に活用するアプローチを構築することを考える新しい方法です。</span><span class="sxs-lookup"><span data-stu-id="9990d-163">It's a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="9990d-164">このアプローチによって、システムの設計、実装、展開、運用の方法が変わります。</span><span class="sxs-lookup"><span data-stu-id="9990d-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="9990d-165">私たちの業界を動かす継続的な誇大宣伝とは異なり、クラウドネイティブは"*本物*"です。</span><span class="sxs-lookup"><span data-stu-id="9990d-165">Unlike the continuous hype that drives our industry, cloud native is "*for-real*".</span></span> <span data-ttu-id="9990d-166">300以上の大企業のコンソーシアムである[クラウドネイティブコンピューティング財団](https://www.cncf.io/)(CNCF)は、クラウドネイティブコンピューティングをテクノロジーとクラウドスタック全体でユビキタスにするためのチャーターを持っています。</span><span class="sxs-lookup"><span data-stu-id="9990d-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="9990d-167">最も影響力のあるオープンソースグループの1つとして、GitHubで最も急成長しているオープンソースプロジェクトの多くをホストしています。</span><span class="sxs-lookup"><span data-stu-id="9990d-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="9990d-168">彼らは[、Kubernetes、](https://kubernetes.io/)[プロメテウス](https://prometheus.io/)、[ヘルム](https://helm.sh/)、[エンボイ](https://www.envoyproxy.io/)[、gRPC](https://grpc.io/)などのプロジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9990d-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="9990d-169">CNCFはオープンソースとベンダー中立性のエコシステムを促進します。</span><span class="sxs-lookup"><span data-stu-id="9990d-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="9990d-170">そのリードに従って、クラウドネイティブの原則、パターン、およびベスト プラクティスを提示します。</span><span class="sxs-lookup"><span data-stu-id="9990d-170">Following that lead, we present cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="9990d-171">同時に、クラウド ネイティブ システムを構築するために Microsoft Azure クラウドで利用できるサービスとインフラストラクチャについても説明します。</span><span class="sxs-lookup"><span data-stu-id="9990d-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span>

<span data-ttu-id="9990d-172">では、クラウドネイティブとは何でしょうか?</span><span class="sxs-lookup"><span data-stu-id="9990d-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="9990d-173">座ってリラックスして、この新しい世界を探検するのを手伝ってみよう。</span><span class="sxs-lookup"><span data-stu-id="9990d-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9990d-174">[前へ](index.md)
>[次へ](definition.md)</span><span class="sxs-lookup"><span data-stu-id="9990d-174">[Previous](index.md)
[Next](definition.md)</span></span>
