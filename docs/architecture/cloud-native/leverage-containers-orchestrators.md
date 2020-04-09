---
title: コンテナーとコンテナー オーケストレーターの活用
description: Azure でのドッカー コンテナーと Kubernetes オーケストレーターの活用
ms.date: 06/30/2019
ms.openlocfilehash: 44b2fff8c9c88717d83e41a421b9817e2cc68135
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989039"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="2a7d8-103">コンテナーとコンテナー オーケストレーターの活用</span><span class="sxs-lookup"><span data-stu-id="2a7d8-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="2a7d8-104">コンテナーとオーケストレーターは、モノリシック配置アプローチに共通する問題を解決するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="2a7d8-105">モノリシック展開の課題</span><span class="sxs-lookup"><span data-stu-id="2a7d8-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="2a7d8-106">従来、ほとんどのアプリケーションは単一のユニットとしてデプロイされてきました。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="2a7d8-107">このようなアプリケーションは、モノリスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="2a7d8-108">複数のモジュールまたはアセンブリで構成されているアプリケーションを単一ユニットとして配置するこの一般的なアプローチは、図 3-1 に示すようにモノリシック アーキテクチャと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![モノリシックアーキテクチャ。](./media/monolithic-architecture.png)

<span data-ttu-id="2a7d8-110">**図 3-1**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-110">**Figure 3-1**.</span></span> <span data-ttu-id="2a7d8-111">モノリシックアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-111">Monolithic architecture.</span></span>

<span data-ttu-id="2a7d8-112">シンプルさの利点はありますが、モノリシック アーキテクチャは次のような課題に直面しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployments"></a><span data-ttu-id="2a7d8-113">デプロイメント</span><span class="sxs-lookup"><span data-stu-id="2a7d8-113">Deployments</span></span>

<span data-ttu-id="2a7d8-114">モノリシック アプリケーションにデプロイするには、通常、1 つの小さなモジュールだけを交換する場合でも、アプリケーション全体を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-114">Deploying to monolithic applications typically requires restarting the entire application, even if only one small module is being replaced.</span></span> <span data-ttu-id="2a7d8-115">アプリケーションをホストするコンピューターの数によっては、デプロイメント中にダウンタイムが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-115">Depending on the number of machines hosting the application, this can result in downtime during deployments.</span></span>

### <a name="hosting"></a><span data-ttu-id="2a7d8-116">Hosting</span><span class="sxs-lookup"><span data-stu-id="2a7d8-116">Hosting</span></span>

<span data-ttu-id="2a7d8-117">モノリシック アプリケーションは、完全に単一のコンピューター インスタンスでホストされます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-117">Monolithic applications are hosted entirely on a single machine instance.</span></span> <span data-ttu-id="2a7d8-118">この場合、分散アプリケーションのどのモジュールよりも高機能なハードウェアが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-118">This may require higher-capability hardware than any module in a distributed application would need.</span></span> <span data-ttu-id="2a7d8-119">また、アプリの一部がボトルネックになった場合は、スケール アウトするために、アプリケーション全体を追加のコンピューター ノードにデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-119">Also, if any part of the app becomes a bottleneck, the entire application must be deployed to additional machine nodes in order to scale out.</span></span>

### <a name="environment"></a><span data-ttu-id="2a7d8-120">環境</span><span class="sxs-lookup"><span data-stu-id="2a7d8-120">Environment</span></span>

<span data-ttu-id="2a7d8-121">モノリシック アプリケーションは、通常、既存のホスティング環境 (オペレーティング システム、インストールされているフレームワークなど) にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-121">Monolithic applications are typically deployed into an existing hosting environment (operating system, installed frameworks, etc.).</span></span> <span data-ttu-id="2a7d8-122">この環境は、アプリケーションが開発またはテストされた環境と一致しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-122">This environment may not match the environment in which the application was developed or tested.</span></span> <span data-ttu-id="2a7d8-123">アプリケーションの環境の不整合は、モノリシックな展開の問題の一般的な原因です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-123">Inconsistencies in the application's environment are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="2a7d8-124">結合</span><span class="sxs-lookup"><span data-stu-id="2a7d8-124">Coupling</span></span>

<span data-ttu-id="2a7d8-125">モノリシック アプリケーションは、アプリケーションのさまざまな部分間、およびアプリケーションとその環境の間で多大な結合を持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-125">Monolithic applications are likely to have a great deal of coupling between different parts of the application, and between the application and its environment.</span></span> <span data-ttu-id="2a7d8-126">これにより、スケーラビリティを向上させるため、または代替実装でスワップするために、特定のサービスや懸念事項を後で考慮することが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-126">This can make it difficult to factor out a particular service or concern later, in order to increase its scalability or swap in an alternative implementation.</span></span> <span data-ttu-id="2a7d8-127">このカップリングは、システムの変更に対する潜在的な影響を大幅に大きくし、大規模なアプリケーションでの広範なテストを必要とします。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-127">This coupling also leads to much larger potential impacts for changes to the system, requiring extensive testing in larger applications.</span></span>

### <a name="technology-choice"></a><span data-ttu-id="2a7d8-128">技術の選択</span><span class="sxs-lookup"><span data-stu-id="2a7d8-128">Technology choice</span></span>

<span data-ttu-id="2a7d8-129">モノリシック アプリケーションは、1 つの単位として構築および展開されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-129">Monolithic applications are built and deployed as a unit.</span></span> <span data-ttu-id="2a7d8-130">これは、シンプルさと均一性を提供しますが、イノベーションの障壁になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-130">This offers simplicity and uniformity but can be a barrier to innovation.</span></span> <span data-ttu-id="2a7d8-131">システムの新しい機能やモジュールは、より最新のプラットフォームやフレームワークに適しているかもしれませんが、一貫性と開発と展開の容易さのために、アプリケーションの現在のアプローチを使用して構築される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-131">Although a new feature or module in the system might be better-suited to a more modern platform or framework, it's likely to be built using the application's current approach for the sake of consistency as well as ease of development and deployment.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="2a7d8-132">コンテナやオーケストレーターのメリットは何ですか?</span><span class="sxs-lookup"><span data-stu-id="2a7d8-132">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="2a7d8-133">Docker は、最も一般的なコンテナー管理およびイメージング プラットフォームであり、Linux および Windows 上のコンテナーをすぐに操作できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-133">Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows.</span></span> <span data-ttu-id="2a7d8-134">コンテナーは、どのシステムでも同じように実行される、別々の再現可能なアプリケーション環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-134">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="2a7d8-135">これにより、クラウド ネイティブ アプリケーションでアプリケーションやアプリ コンポーネントを開発およびホストするのに最適です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-135">This makes them perfect for developing and hosting applications and app components in cloud-native applications.</span></span> <span data-ttu-id="2a7d8-136">コンテナーは互いに分離されるため、同じホスト ハードウェア上の 2 つのコンテナーに異なるバージョンのソフトウェアをインストールし、依存関係が競合を引き起こすことなくオペレーティング システムをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-136">Containers are isolated from one another, so two containers on the same host hardware can have different versions of software and even operating system installed, without the dependencies causing conflicts.</span></span>

<span data-ttu-id="2a7d8-137">さらに、コンテナーは、ソース管理にチェックインできる単純なファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-137">What's more, containers are defined by simple files that can be checked into source control.</span></span> <span data-ttu-id="2a7d8-138">フル サーバーとは異なり、更新プログラムの適用や追加サービスのインストールに手動作業を必要とする仮想マシンでも、コンテナー インフラストラクチャは簡単にバージョン管理できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-138">Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled.</span></span> <span data-ttu-id="2a7d8-139">したがって、コンテナーで実行するように構築されたアプリは、ビルド パイプラインの一部として自動化ツールを使用して開発、テスト、およびデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-139">Thus, apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="2a7d8-140">コンテナーは変更不可能です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-140">Containers are immutable.</span></span> <span data-ttu-id="2a7d8-141">コンテナーの定義が完了すると、そのコンテナーを再作成でき、まったく同じ方法で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-141">Once you have the definition of a container, you can recreate that container and it will run exactly the same way.</span></span> <span data-ttu-id="2a7d8-142">この不変性は、コンポーネントベースの設計に適しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-142">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="2a7d8-143">アプリケーションの一部が他の部分ほど頻繁に変更されない場合は、最も頻繁に変更される部分を展開できるだけで、アプリ全体を再デプロイする理由は何でしょうか。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-143">If some parts of an application don't change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="2a7d8-144">アプリのさまざまな機能と横断的な懸念は、別々のユニットに分割することができます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-144">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="2a7d8-145">図 3-2 は、モノリシック アプリが特定の機能を委任することによってコンテナーとマイクロサービスを利用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-145">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="2a7d8-146">アプリ自体の残りの機能もコンテナー化されています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-146">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="2a7d8-147">![バック エンドでマイクロサービスを使用するためにモノリシック アプリを分割します。](./media/breaking-up-monolith-with-backend-microservices.png)
**図 3-2**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-147">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="2a7d8-148">バック エンドでマイクロサービスを使用するためにモノリシック アプリを分割します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-148">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="2a7d8-149">個別のコンテナーを使用して構築されたクラウドネイティブ アプリは、必要に応じてアプリケーションをできるだけまたは少なくデプロイする機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-149">Cloud-native apps built using separate containers benefit from the ability to deploy as much or as little of an application as needed.</span></span> <span data-ttu-id="2a7d8-150">個々のサービスは、各サービスに適したリソースを持つノードでホストできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-150">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="2a7d8-151">各サービスが実行される環境は不変であり、開発、テスト、および実稼働環境で共有でき、簡単にバージョン管理できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-151">The environment each service runs in is immutable, can be shared between dev, test, and production, and can easily be versioned.</span></span> <span data-ttu-id="2a7d8-152">アプリケーションの異なる領域間の結合は、モノリス内のコンパイル時の依存関係ではなく、サービス間の呼び出しまたはメッセージとして明示的に行われます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-152">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="2a7d8-153">また、アプリ全体の任意の部分は、アプリの残りの部分に変更を加えることなく、その機能や機能に最も適したテクノロジを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-153">And any given part of the overall app can choose the technology that makes the most sense for that feature or capability without requiring changes to the rest of the app.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="2a7d8-154">スケーリングの利点は何ですか?</span><span class="sxs-lookup"><span data-stu-id="2a7d8-154">What are the scaling benefits?</span></span>

<span data-ttu-id="2a7d8-155">コンテナー上に構築されたサービスは、Kubernetes などのオーケストレーション ツールによって提供されるスケーリングの利点を活用できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-155">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="2a7d8-156">設計によってコンテナは自分自身についてしか知りません。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-156">By design containers only know about themselves.</span></span> <span data-ttu-id="2a7d8-157">一緒に動作する必要がある複数のコンテナーを作成し始めると、より高いレベルでそれらを整理する価値があります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-157">Once you start to have multiple containers that need to work together, it can be worthwhile to organize them at a higher level.</span></span> <span data-ttu-id="2a7d8-158">多数のコンテナーとその共有依存関係 (ネットワーク構成など) を整理することは、オーケストレーション ツールが 1 日を節約するために入ってくる場所です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-158">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="2a7d8-159">Kubernetes は、コンテナー化されたアプリケーションのデプロイ、スケーリング、および管理を自動化するために設計されたコンテナー オーケストレーション プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-159">Kubernetes is a container orchestration platform designed to automate deployment, scaling, and management of containerized applications.</span></span> <span data-ttu-id="2a7d8-160">コンテナのグループの上に抽象化レイヤーを作成し、*それらをポッド*に整理します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-160">It creates an abstraction layer on top of groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="2a7d8-161">ポッドは、*ノード*と呼ばれるワーカー マシンで実行されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-161">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="2a7d8-162">組織化されたグループ全体を *、クラスタ*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-162">The whole organized group is referred to as a *cluster*.</span></span> <span data-ttu-id="2a7d8-163">図 3-3 は、Kubernetes クラスターの各種コンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-163">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="2a7d8-164">![Kubernetes クラスター コンポーネント。](./media/kubernetes-cluster-components.png)
**図 3-3**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-164">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="2a7d8-165">Kubernetes クラスター コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-165">Kubernetes cluster components.</span></span>

<span data-ttu-id="2a7d8-166">Kubernetes は、需要を満たすためにクラスターをスケーリングするための組み込みサポートを備えています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-166">Kubernetes has built-in support for scaling clusters to meet demand.</span></span> <span data-ttu-id="2a7d8-167">コンテナー化されたマイクロサービスと組み合わせることで、クラウドネイティブアプリケーションは、必要なときに必要な場所で追加のリソースを使用して、需要の急増に迅速かつ効率的に対応できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-167">Combined with containerized micro-services, this provides cloud-native applications with the ability to quickly and efficiently respond to spikes in demand with additional resources when and where they're needed.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="2a7d8-168">宣言型と命令型</span><span class="sxs-lookup"><span data-stu-id="2a7d8-168">Declarative versus imperative</span></span>

<span data-ttu-id="2a7d8-169">Kubernetes は、宣言型オブジェクトと強制オブジェクト構成の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-169">Kubernetes supports both declarative and imperative object configuration.</span></span> <span data-ttu-id="2a7d8-170">命令的なアプローチでは、Kubernetesに道の各ステップを何をすべきかを伝えるさまざまなコマンドを実行することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-170">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="2a7d8-171">このイメージを*実行*します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-171">*Run* this image.</span></span> <span data-ttu-id="2a7d8-172">このポッドを*削除*します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-172">*Delete* this pod.</span></span> <span data-ttu-id="2a7d8-173">このポート*を公開*します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-173">*Expose* this port.</span></span> <span data-ttu-id="2a7d8-174">宣言型の方法では、何をするかではなく *、必要な操作*を記述した構成ファイル*を*使用し、Kubernetes は目的の終了状態を実現するために何をすべきかを示します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-174">With the declarative approach, you use a configuration file that describes *what you want* instead of *what to do* and Kubernetes figures out what to do to achieve the desired end state.</span></span> <span data-ttu-id="2a7d8-175">強制コマンドを使用してクラスターを既に構成している場合は、 を使用`kubectl get svc SERVICENAME -o yaml > service.yaml`して宣言マニフェストをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-175">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="2a7d8-176">これにより、次のようなマニフェスト ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-176">This will produce a manifest file like this one:</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

<span data-ttu-id="2a7d8-177">宣言構成を使用する場合は、構成ファイルが配置されているフォルダーに対してを使用`kubectl diff -f FOLDERNAME`して、コミットする前に行われる変更をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-177">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="2a7d8-178">変更を適用することを確認したら、 を実行`kubectl apply -f FOLDERNAME`します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-178">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="2a7d8-179">フォルダー`-R`階層を再帰的に処理する追加。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-179">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="2a7d8-180">サービスに加えて、展開などの他の Kubernetes 機能に対して宣言型構成*を*使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-180">In addition to services, you can use declarative configuration for other Kubernetes features, such as *deployments*.</span></span> <span data-ttu-id="2a7d8-181">宣言型の展開は、クラスター リソースを更新するために配置コントローラーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-181">Declarative deployments are used by deployment controllers to update cluster resources.</span></span> <span data-ttu-id="2a7d8-182">デプロイは、新しい変更をロールアウトしたり、より多くの負荷をサポートするようにスケールアップしたり、以前のリビジョンにロールバックしたりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-182">Deployments are used to roll out new changes, scale up to support more load, or roll back to a previous revision.</span></span> <span data-ttu-id="2a7d8-183">クラスターが不安定な場合、宣言型の展開は、クラスターを希望の状態に自動的に戻すメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-183">If a cluster is unstable, declarative deployments provide a mechanism for automatically bringing the cluster back to a desired state.</span></span>

<span data-ttu-id="2a7d8-184">宣言型構成を使用すると、インフラストラクチャをアプリケーション コードと共にチェックインおよびバージョン管理できるコードとして表すことができます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-184">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="2a7d8-185">これにより、ソース管理の変更に関連付けられたビルドとデプロイのパイプラインを使用して、変更制御が強化され、継続的な配置のサポートが向上します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-185">This provides improved change control and better support for continuous deployment using a build and deploy pipeline tied to source control changes.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="2a7d8-186">コンテナーやオーケストレーターに最適なシナリオは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-186">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="2a7d8-187">次のシナリオは、コンテナーとオーケストレーターを使用するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-187">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="2a7d8-188">高い稼働時間と拡張性を必要とするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="2a7d8-188">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="2a7d8-189">高い稼働時間とスケーラビリティの要件を持つ個々のアプリケーションは、マイクロサービス、コンテナー、オーケストレーターを使用するクラウド ネイティブ アーキテクチャの理想的な候補です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-189">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="2a7d8-190">これらのアプリケーションは、バージョン管理された環境を使用してコンテナ内で開発することができ、本番環境に行く前に広範囲にテストすることができ、ダウンタイムをゼロにして本番環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-190">These applications can be developed in containers using versioned environments, can be extensively tested before going to production, and can be deployed to production with zero downtime.</span></span> <span data-ttu-id="2a7d8-191">Kubernetes クラスターを使用すると、このようなアプリは、オンデマンドで拡張し、ノードの障害から自動的に回復できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-191">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="2a7d8-192">多数のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="2a7d8-192">Large numbers of applications</span></span>

<span data-ttu-id="2a7d8-193">多数のアプリケーションを展開し、その後も維持する必要がある組織は、コンテナーとオーケストレーターの恩恵を受けることができます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-193">Organizations that deploy and must subsequently maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="2a7d8-194">コンテナ化環境と Kubernetes クラスターのセットアップに関する先行作業は、主に固定コストです。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-194">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="2a7d8-195">個々のアプリケーションの展開、保守、および更新には、保守する必要があるアプリケーションの数によって異なるコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-195">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications that must be maintained.</span></span> <span data-ttu-id="2a7d8-196">一定の数のアプリケーションを超えて、カスタム アプリケーションを手動で維持する複雑さは、コンテナーとオーケストレーターを使用してソリューションを実装するコストを超えています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-196">Beyond a certain fairly small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="2a7d8-197">コンテナーとオーケストレーターの使用を避ける必要がある場合</span><span class="sxs-lookup"><span data-stu-id="2a7d8-197">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="2a7d8-198">12 要素アプリの原則に従ってアプリケーションを作成したくない場合や、ビルドできない場合は、コンテナーやオーケストレーターを避けた方が良いでしょう。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-198">If you're unwilling or unable to build your application following Twelve-Factor App principles, you'll probably be better off avoiding containers and orchestrators.</span></span> <span data-ttu-id="2a7d8-199">このような場合は、VM ベースのホスティング プラットフォーム、または特定の機能を個別のコンテナーまたはサーバーレス機能に分割できるハイブリッド システムを使用して、次の手順を進めるのが最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-199">In these cases, it may be best to move forward with a VM-based hosting platform, or possibly some hybrid system in which you can spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="2a7d8-200">開発リソース</span><span class="sxs-lookup"><span data-stu-id="2a7d8-200">Development resources</span></span>

<span data-ttu-id="2a7d8-201">このセクションでは、次のアプリケーションでコンテナーとオーケストレーターを使用する際に役立つ開発リソースの簡単な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-201">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="2a7d8-202">クラウド ネイティブ マイクロサービス アーキテクチャ アプリを設計する方法に関するガイダンスをお探しの場合は、このマニュアルの付属の[「.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ](https://aka.ms/microservicesebook)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-202">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="2a7d8-203">地元のクベルネテス開発</span><span class="sxs-lookup"><span data-stu-id="2a7d8-203">Local Kubernetes Development</span></span>

<span data-ttu-id="2a7d8-204">Kubernetes の導入は、運用環境で大きな価値を提供しますが、ローカルで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-204">Kubernetes deployments provide great value in production environments, but you can also run them locally.</span></span> <span data-ttu-id="2a7d8-205">多くの場合、個々のアプリやマイクロサービスを個別に操作できることは良いことですが、運用環境に展開する場合と同じように、システム全体をローカルで実行できることがあります。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-205">Although much of the time it's good to be able to work on individual apps or microservices independently, sometimes it's good to be able to run the whole system locally just as it will run when deployed to production.</span></span> <span data-ttu-id="2a7d8-206">これを達成するにはいくつかの方法があり、そのうちの2つはMinikubeとDockerデスクトップです。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-206">There are several ways to achieve this, two of which are Minikube and Docker Desktop.</span></span> <span data-ttu-id="2a7d8-207">また、ドッカー開発用のツールも提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-207">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="2a7d8-208">Minikube</span><span class="sxs-lookup"><span data-stu-id="2a7d8-208">Minikube</span></span>

<span data-ttu-id="2a7d8-209">ミニクベとは何ですか?</span><span class="sxs-lookup"><span data-stu-id="2a7d8-209">What is Minikube?</span></span> <span data-ttu-id="2a7d8-210">Minikubeプロジェクトは、「MinikubeはmacOS、Linux、およびWindows上でローカルKubernetesクラスタを実装しています」と述べています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-210">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="2a7d8-211">その主な目標は、「地元のKubernetesアプリケーション開発のための最良のツールであり、適合するすべてのKubernetes機能をサポートすることです。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-211">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="2a7d8-212">Minikubeのインストールは、Dockerとは別ですが、Minikubeは、Dockerデスクトップがサポートするのとは異なるハイパーバイザーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-212">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="2a7d8-213">現在、Minikubeでは以下の Kubernetes 機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-213">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="2a7d8-214">DNS</span><span class="sxs-lookup"><span data-stu-id="2a7d8-214">DNS</span></span>
- <span data-ttu-id="2a7d8-215">ノードポート</span><span class="sxs-lookup"><span data-stu-id="2a7d8-215">NodePorts</span></span>
- <span data-ttu-id="2a7d8-216">構成マップとシークレット</span><span class="sxs-lookup"><span data-stu-id="2a7d8-216">ConfigMaps and secrets</span></span>
- <span data-ttu-id="2a7d8-217">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="2a7d8-217">Dashboards</span></span>
- <span data-ttu-id="2a7d8-218">コンテナー ランタイム: ドッカー、rkt、CRI-O、およびコンテナー化</span><span class="sxs-lookup"><span data-stu-id="2a7d8-218">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="2a7d8-219">コンテナネットワークインタフェース(CNI)の有効化</span><span class="sxs-lookup"><span data-stu-id="2a7d8-219">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="2a7d8-220">イングレス</span><span class="sxs-lookup"><span data-stu-id="2a7d8-220">Ingress</span></span>

<span data-ttu-id="2a7d8-221">Minikubeをインストールした後、イメージをダウンロードしてローカル Kubernetes クラスターを起動する`minikube start`コマンドを実行することで、すぐに使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-221">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="2a7d8-222">クラスターが起動したら、標準の Kubernetes`kubectl`コマンドを使用してクラスターと対話します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-222">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="2a7d8-223">Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="2a7d8-223">Docker Desktop</span></span>

<span data-ttu-id="2a7d8-224">また、WindowsのDockerデスクトップから直接Kubernetesを使用して作業することができます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-224">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="2a7d8-225">Windows コンテナーを使用している場合は、これが唯一のオプションであり、Windows 以外のコンテナーにも最適です。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-225">This is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="2a7d8-226">標準の Docker デスクトップ構成アプリは、Docker デスクトップから実行されている Kubernetes を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-226">The standard Docker Desktop configuration app is used to configure Kubernetes running from Docker Desktop.</span></span>

![Docker デスクトップでの Kubernetes の構成](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="2a7d8-228">**図 3-4**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-228">**Figure 3-4**.</span></span> <span data-ttu-id="2a7d8-229">Docker デスクトップでの Kubernetes の構成。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-229">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="2a7d8-230">Docker Desktop は、コンテナー化されたアプリをローカルで構成および実行するための最も一般的なツールです。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-230">Docker Desktop is already the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="2a7d8-231">Docker Desktop を使用する場合、運用環境にデプロイする Docker コンテナー イメージのセットとまったく同じセットに対して、ローカルで開発できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-231">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="2a7d8-232">Docker Desktop は、コンテナー化されたアプリをローカルに "ビルド、テスト、および出荷" するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-232">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="2a7d8-233">イメージが Azure コンテナー レジストリや Docker Hub などのイメージ レジストリに出荷されると、Azure Kubernetes サービス (AKS) などのサービスは、運用環境でアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-233">Once the images have been shipped to an image registry like Azure Container Registry or Docker Hub, then services like Azure Kubernetes Service (AKS) manage the application in production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="2a7d8-234">ビジュアルスタジオドッカーツーリング</span><span class="sxs-lookup"><span data-stu-id="2a7d8-234">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="2a7d8-235">Visual Studio は、Web アプリケーションの Docker 開発をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-235">Visual Studio supports Docker development for web applications.</span></span> <span data-ttu-id="2a7d8-236">新しい ASP.NET Core アプリケーションを作成する場合、プロジェクト作成プロセスの一環として Docker サポートを使用して構成するオプションが表示されます (図 3-5 を参照)。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-236">When you create a new ASP.NET Core application, you're given the option to configure it with Docker support as part of the project creation process, as shown in Figure 3-5.</span></span>

![ドッカーサポートを有効にする](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="2a7d8-238">**図 3-5**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-238">**Figure 3-5**.</span></span> <span data-ttu-id="2a7d8-239">ドッカーサポートを有効にする</span><span class="sxs-lookup"><span data-stu-id="2a7d8-239">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="2a7d8-240">このオプションを選択すると、プロジェクトは、そのルートに`Dockerfile`作成され、Docker コンテナーでアプリをビルドおよびホストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-240">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="2a7d8-241">図 3-6 に Dockerfile の例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-241">An example Dockerfile is shown in Figure 3-6.</span></span>

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

<span data-ttu-id="2a7d8-242">**図 3-6**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-242">**Figure 3-6**.</span></span> <span data-ttu-id="2a7d8-243">生成されたドッカーファイル</span><span class="sxs-lookup"><span data-stu-id="2a7d8-243">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="2a7d8-244">アプリの実行時の既定の動作は、Docker を使用するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-244">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="2a7d8-245">図 3-7 は、Docker サポートを追加して作成された新しいASP.NETコア プロジェクトから利用できるさまざまな実行オプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-245">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![ビジュアル スタジオ ドッカー実行オプション](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="2a7d8-247">**図 3-7**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-247">**Figure 3-7**.</span></span> <span data-ttu-id="2a7d8-248">ビジュアル スタジオ ドッカー実行オプション</span><span class="sxs-lookup"><span data-stu-id="2a7d8-248">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="2a7d8-249">[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/)は、ローカル開発に加えて、複数の開発者が Azure 内で独自の Kubernetes 構成を操作するための便利な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-249">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="2a7d8-250">図 3-7 に示すように、Azure Dev Spaces でアプリケーションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-250">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="2a7d8-251">作成時に ASP.NET Core アプリケーションに Docker サポートを追加しない場合は、後でいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-251">If you don't add Docker support to your ASP.NET Core application when you create it, you can always add it later.</span></span> <span data-ttu-id="2a7d8-252">図 3-8 に示すように、Visual Studio ソリューション エクスプローラーでプロジェクトを右クリックし **、[Docker サポート**の**追加** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-252">From the Visual Studio Solution Explorer, right click on the project and select **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![ビジュアル スタジオ追加ドッカー サポート](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="2a7d8-254">**図 3-8**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-254">**Figure 3-8**.</span></span> <span data-ttu-id="2a7d8-255">ビジュアル スタジオ追加ドッカー サポート</span><span class="sxs-lookup"><span data-stu-id="2a7d8-255">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="2a7d8-256">Docker サポートに加えて、図 3-8 に示すように、コンテナー オーケストレーション サポートを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-256">In addition to Docker support, you can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="2a7d8-257">既定では、オーケストレーターは、Kubernetes と Helm を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-257">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="2a7d8-258">オーケストレーターを選択すると、`azds.yaml`プロジェクトルートにファイルが追加され、アプリケーションを`charts`Kubernetes に構成およびデプロイするために使用される Helm チャートを含むフォルダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-258">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="2a7d8-259">図 3-9 は、新しいプロジェクトで作成されたファイルを示しています。</span><span class="sxs-lookup"><span data-stu-id="2a7d8-259">Figure 3-9 shows the resulting files in a new project.</span></span>

![ビジュアル スタジオ 追加オーケストレーターのサポート](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="2a7d8-261">**図 3-9**.</span><span class="sxs-lookup"><span data-stu-id="2a7d8-261">**Figure 3-9**.</span></span> <span data-ttu-id="2a7d8-262">ビジュアル スタジオ 追加オーケストレーターのサポート</span><span class="sxs-lookup"><span data-stu-id="2a7d8-262">Visual Studio Add Orchestrator Support</span></span>

## <a name="references"></a><span data-ttu-id="2a7d8-263">References</span><span class="sxs-lookup"><span data-stu-id="2a7d8-263">References</span></span>

- [<span data-ttu-id="2a7d8-264">Kubernetes とは</span><span class="sxs-lookup"><span data-stu-id="2a7d8-264">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="2a7d8-265">ミニクベでのKubernetesのインストール</span><span class="sxs-lookup"><span data-stu-id="2a7d8-265">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="2a7d8-266">ミニクベ対ドッカーデスクトップ</span><span class="sxs-lookup"><span data-stu-id="2a7d8-266">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="2a7d8-267">Visual Studio Tools for Docker</span><span class="sxs-lookup"><span data-stu-id="2a7d8-267">Visual Studio Tools for Docker</span></span>](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
><span data-ttu-id="2a7d8-268">[前へ](scale-applications.md)
>[次へ](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="2a7d8-268">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
