---
title: コンテナーとコンテナー オーケストレーターの活用
description: Azure での Docker コンテナーと Kubernetes Orchestrators 活用
ms.date: 06/30/2019
ms.openlocfilehash: 7b136ed2760ea471f42ff82d20298ff8714c6dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841763"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="8bf1e-103">コンテナーとコンテナー オーケストレーターの活用</span><span class="sxs-lookup"><span data-stu-id="8bf1e-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="8bf1e-104">コンテナーとオーケストレーター、モノリシックデプロイアプローチに共通する問題を解決するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="8bf1e-105">モノリシックデプロイに関する課題</span><span class="sxs-lookup"><span data-stu-id="8bf1e-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="8bf1e-106">従来、ほとんどのアプリケーションは1つのユニットとして展開されていました。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="8bf1e-107">このようなアプリケーションは、モノリスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="8bf1e-108">図3-1 に示すように、複数のモジュールまたはアセンブリで構成されている場合でも、アプリケーションを1つの単位としてデプロイする一般的な方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![モノリシックアーキテクチャ。](./media/monolithic-architecture.png)

<span data-ttu-id="8bf1e-110">**図 3-1**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-110">**Figure 3-1**.</span></span> <span data-ttu-id="8bf1e-111">モノリシックアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-111">Monolithic architecture.</span></span>

<span data-ttu-id="8bf1e-112">単純化の利点はありますが、モノリシックアーキテクチャはいくつかの課題に直面します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployments"></a><span data-ttu-id="8bf1e-113">展開</span><span class="sxs-lookup"><span data-stu-id="8bf1e-113">Deployments</span></span>

<span data-ttu-id="8bf1e-114">モノリシックアプリケーションに配置するには、通常、1つの小さいモジュールだけを置換する場合でも、アプリケーション全体を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-114">Deploying to monolithic applications typically requires restarting the entire application, even if only one small module is being replaced.</span></span> <span data-ttu-id="8bf1e-115">アプリケーションをホストしているマシンの数によっては、デプロイ中にダウンタイムが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-115">Depending on the number of machines hosting the application, this can result in downtime during deployments.</span></span>

### <a name="hosting"></a><span data-ttu-id="8bf1e-116">ホスト</span><span class="sxs-lookup"><span data-stu-id="8bf1e-116">Hosting</span></span>

<span data-ttu-id="8bf1e-117">モノリシックアプリケーションは、1台のコンピューターインスタンスで完全にホストされます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-117">Monolithic applications are hosted entirely on a single machine instance.</span></span> <span data-ttu-id="8bf1e-118">これには、分散アプリケーションのどのモジュールよりも高い機能を必要とするハードウェアが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-118">This may require higher-capability hardware than any module in a distributed application would need.</span></span> <span data-ttu-id="8bf1e-119">また、アプリのいずれかの部分がボトルネックになった場合は、スケールアウトするために、アプリケーション全体を追加のマシンノードにデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-119">Also, if any part of the app becomes a bottleneck, the entire application must be deployed to additional machine nodes in order to scale out.</span></span>

### <a name="environment"></a><span data-ttu-id="8bf1e-120">環境</span><span class="sxs-lookup"><span data-stu-id="8bf1e-120">Environment</span></span>

<span data-ttu-id="8bf1e-121">モノリシックアプリケーションは、通常、既存のホスティング環境 (オペレーティングシステム、インストールされているフレームワークなど) にデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-121">Monolithic applications are typically deployed into an existing hosting environment (operating system, installed frameworks, etc.).</span></span> <span data-ttu-id="8bf1e-122">この環境は、アプリケーションが開発またはテストされた環境と一致しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-122">This environment may not match the environment in which the application was developed or tested.</span></span> <span data-ttu-id="8bf1e-123">アプリケーションの環境での不整合は、モノリシック配置における一般的な問題の原因です。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-123">Inconsistencies in the application's environment are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="8bf1e-124">結合</span><span class="sxs-lookup"><span data-stu-id="8bf1e-124">Coupling</span></span>

<span data-ttu-id="8bf1e-125">モノリシックアプリケーションでは、アプリケーションのさまざまな部分と、アプリケーションとその環境との間に大きな結合が行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-125">Monolithic applications are likely to have a great deal of coupling between different parts of the application, and between the application and its environment.</span></span> <span data-ttu-id="8bf1e-126">これにより、別の実装でスケーラビリティやスワップを向上させるために、特定のサービスまたは問題を後で考慮することが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-126">This can make it difficult to factor out a particular service or concern later, in order to increase its scalability or swap in an alternative implementation.</span></span> <span data-ttu-id="8bf1e-127">この結合によって、システムへの変更に対する潜在的な影響も大きくなるため、大規模なアプリケーションで広範囲にわたるテストが必要になります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-127">This coupling also leads to much larger potential impacts for changes to the system, requiring extensive testing in larger applications.</span></span>

### <a name="technology-choice"></a><span data-ttu-id="8bf1e-128">テクノロジの選択</span><span class="sxs-lookup"><span data-stu-id="8bf1e-128">Technology choice</span></span>

<span data-ttu-id="8bf1e-129">モノリシックアプリケーションは、1つの単位としてビルドおよび展開されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-129">Monolithic applications are built and deployed as a unit.</span></span> <span data-ttu-id="8bf1e-130">これにより、シンプルさと統一性が提供されますが、イノベーションの妨げになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-130">This offers simplicity and uniformity but can be a barrier to innovation.</span></span> <span data-ttu-id="8bf1e-131">システムの新しい機能やモジュールは、より新しいプラットフォームまたはフレームワークに適している場合がありますが、一貫性を確保し、開発とデプロイを容易にするために、アプリケーションの現在のアプローチを使用して構築される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-131">Although a new feature or module in the system might be better-suited to a more modern platform or framework, it's likely to be built using the application's current approach for the sake of consistency as well as ease of development and deployment.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="8bf1e-132">コンテナーと orchestrators はどのような利点がありますか。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-132">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="8bf1e-133">Docker は、最も一般的なコンテナー管理およびイメージングプラットフォームで、Linux および Windows 上のコンテナーをすばやく操作できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-133">Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows.</span></span> <span data-ttu-id="8bf1e-134">コンテナーは、任意のシステムで同じように動作する、再現可能な別のアプリケーション環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-134">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="8bf1e-135">これにより、クラウドネイティブアプリケーションでのアプリケーションとアプリコンポーネントの開発とホストに最適です。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-135">This makes them perfect for developing and hosting applications and app components in cloud-native applications.</span></span> <span data-ttu-id="8bf1e-136">コンテナーは相互に分離されているため、同じホストハードウェア上の2つのコンテナーが異なるバージョンのソフトウェアとオペレーティングシステムをインストールでき、依存関係によって競合が発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-136">Containers are isolated from one another, so two containers on the same host hardware can have different versions of software and even operating system installed, without the dependencies causing conflicts.</span></span>

<span data-ttu-id="8bf1e-137">さらに、コンテナーは、ソース管理にチェックインできる単純なファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-137">What’s more, containers are defined by simple files that can be checked into source control.</span></span> <span data-ttu-id="8bf1e-138">完全なサーバーとは異なり、更新プログラムの適用や追加のサービスのインストールを手動で行う必要がある仮想マシンであっても、コンテナーのインフラストラクチャを簡単にバージョン管理できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-138">Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled.</span></span> <span data-ttu-id="8bf1e-139">したがって、コンテナーで実行するように構築されたアプリは、ビルドパイプラインの一部として自動化ツールを使用して開発、テスト、および配置できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-139">Thus, apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="8bf1e-140">コンテナーは変更できません。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-140">Containers are immutable.</span></span> <span data-ttu-id="8bf1e-141">コンテナーの定義を作成したら、そのコンテナーを再作成して、まったく同じ方法で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-141">Once you have the definition of a container, you can recreate that container and it will run exactly the same way.</span></span> <span data-ttu-id="8bf1e-142">この不変性は、コンポーネントベースの設計に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-142">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="8bf1e-143">アプリケーションの一部が他の部分ほど頻繁に変更されない場合、最も頻繁に変更される部分を展開するだけで、アプリ全体を再展開するのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-143">If some parts of an application don’t change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="8bf1e-144">アプリのさまざまな機能と横断的な問題を別々の単位に分割できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-144">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="8bf1e-145">図3-2 は、モノリシックアプリが特定の機能を委任することによってコンテナーとマイクロサービスを利用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-145">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="8bf1e-146">アプリ自体のその他の機能もコンテナー化されています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-146">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="8bf1e-147">バックエンドでマイクロサービスを使用するためのモノリシックアプリの分割 ![ます。](./media/breaking-up-monolith-with-backend-microservices.png)
**図 3-2**。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-147">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="8bf1e-148">バックエンドでマイクロサービスを使用するようにモノリシックアプリを分割します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-148">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="8bf1e-149">個別のコンテナーを使用して構築されたクラウドネイティブアプリは、必要に応じてアプリケーションをほとんどまたはほとんど配置できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-149">Cloud-native apps built using separate containers benefit from the ability to deploy as much or as little of an application as needed.</span></span> <span data-ttu-id="8bf1e-150">個々のサービスは、各サービスに適切なリソースを持つノードでホストできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-150">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="8bf1e-151">各サービスが実行される環境は不変であり、開発、テスト、および運用の間で共有でき、簡単にバージョン管理できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-151">The environment each service runs in is immutable, can be shared between dev, test, and production, and can easily be versioned.</span></span> <span data-ttu-id="8bf1e-152">アプリケーションのさまざまな領域間の結合は、モノリス内のコンパイル時の依存関係ではなく、サービス間の呼び出しまたはメッセージとして明示的に行われます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-152">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="8bf1e-153">また、アプリ全体の任意の部分で、アプリの残りの部分を変更することなく、その機能に最も適したテクノロジを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-153">And any given part of the overall app can choose the technology that makes the most sense for that feature or capability without requiring changes to the rest of the app.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="8bf1e-154">スケーリングにはどのような利点がありますか。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-154">What are the scaling benefits?</span></span>

<span data-ttu-id="8bf1e-155">コンテナー上に構築されたサービスは、Kubernetes などのオーケストレーションツールによって提供されるスケーリングの利点を活用できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-155">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="8bf1e-156">設計コンテナーによって認識されるのは、それ自体だけです。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-156">By design containers only know about themselves.</span></span> <span data-ttu-id="8bf1e-157">複数のコンテナーを連携させる必要がある場合は、より高いレベルでそれらを整理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-157">Once you start to have multiple containers that need to work together, it can be worthwhile to organize them at a higher level.</span></span> <span data-ttu-id="8bf1e-158">多数のコンテナーとその共有依存関係 (ネットワーク構成など) を整理すると、その日を節約するためにオーケストレーションツールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-158">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="8bf1e-159">Kubernetes は、コンテナー化アプリケーションのデプロイ、スケーリング、および管理を自動化するように設計されたコンテナーオーケストレーションプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-159">Kubernetes is a container orchestration platform designed to automate deployment, scaling, and management of containerized applications.</span></span> <span data-ttu-id="8bf1e-160">コンテナーのグループの上に抽象化レイヤーを作成し、*ポッド*に整理します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-160">It creates an abstraction layer on top of groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="8bf1e-161">ポッドは、*ノード*と呼ばれるワーカーマシン上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-161">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="8bf1e-162">整理されたグループ全体は*クラスター*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-162">The whole organized group is referred to as a *cluster*.</span></span> <span data-ttu-id="8bf1e-163">図3-3 は、Kubernetes クラスターのさまざまなコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-163">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="8bf1e-164">Kubernetes クラスターコンポーネントを ![します。](./media/kubernetes-cluster-components.png)
**図 3-3**。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-164">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="8bf1e-165">クラスターコンポーネントを Kubernetes します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-165">Kubernetes cluster components.</span></span>

<span data-ttu-id="8bf1e-166">Kubernetes には、需要に合わせてクラスターをスケーリングするためのサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-166">Kubernetes has built-in support for scaling clusters to meet demand.</span></span> <span data-ttu-id="8bf1e-167">コンテナー化されたマイクロサービスと組み合わせることで、クラウドネイティブアプリケーションは、必要に応じて追加のリソースを使用して、需要の急増に迅速かつ効率的に対応できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-167">Combined with containerized micro-services, this provides cloud-native applications with the ability to quickly and efficiently respond to spikes in demand with additional resources when and where they're needed.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="8bf1e-168">宣言型と命令型</span><span class="sxs-lookup"><span data-stu-id="8bf1e-168">Declarative versus imperative</span></span>

<span data-ttu-id="8bf1e-169">Kubernetes は、宣言型と命令型の両方のオブジェクト構成をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-169">Kubernetes supports both declarative and imperative object configuration.</span></span> <span data-ttu-id="8bf1e-170">命令型のアプローチには、各手順の実行方法を Kubernetes に指示するさまざまなコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-170">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="8bf1e-171">このイメージを*実行*します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-171">*Run* this image.</span></span> <span data-ttu-id="8bf1e-172">このポッドを*削除*します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-172">*Delete* this pod.</span></span> <span data-ttu-id="8bf1e-173">このポートを*公開*します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-173">*Expose* this port.</span></span> <span data-ttu-id="8bf1e-174">宣言型の方法では、*何を実行*するかについてではなく、*目的の内容*を記述した構成ファイルを使用し、目的の終了状態を達成するために何をするかを Kubernetes します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-174">With the declarative approach, you use a configuration file that describes *what you want* instead of *what to do* and Kubernetes figures out what to do to achieve the desired end state.</span></span> <span data-ttu-id="8bf1e-175">命令型コマンドを使用して既にクラスターを構成している場合は、`kubectl get svc SERVICENAME -o yaml > service.yaml`を使用して宣言マニフェストをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-175">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="8bf1e-176">これにより、次のようなマニフェストファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-176">This will produce a manifest file like this one:</span></span>

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

<span data-ttu-id="8bf1e-177">宣言型の構成を使用する場合は、構成ファイルが配置されているフォルダーに対して `kubectl diff -f FOLDERNAME` を使用してコミットする前に、変更をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-177">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="8bf1e-178">変更を適用することを確認したら、`kubectl apply -f FOLDERNAME`を実行します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-178">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="8bf1e-179">フォルダー階層を再帰的に処理する `-R` を追加します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-179">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="8bf1e-180">サービスに加えて、*配置*などの他の Kubernetes 機能に対して宣言型の構成を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-180">In addition to services, you can use declarative configuration for other Kubernetes features, such as *deployments*.</span></span> <span data-ttu-id="8bf1e-181">宣言型の配置は、配置コントローラーがクラスターリソースを更新するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-181">Declarative deployments are used by deployment controllers to update cluster resources.</span></span> <span data-ttu-id="8bf1e-182">デプロイは、新しい変更のロールアウト、負荷の増加に対応するためのスケールアップ、または以前のリビジョンへのロールバックに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-182">Deployments are used to roll out new changes, scale up to support more load, or roll back to a previous revision.</span></span> <span data-ttu-id="8bf1e-183">クラスターが不安定な場合、宣言型のデプロイによって、クラスターを自動的に目的の状態に戻すメカニズムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-183">If a cluster is unstable, declarative deployments provide a mechanism for automatically bringing the cluster back to a desired state.</span></span>

<span data-ttu-id="8bf1e-184">宣言型の構成を使用すると、アプリケーションコードと共にチェックインおよびバージョン管理できるコードとして、インフラストラクチャを表すことができます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-184">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="8bf1e-185">これにより、変更制御が改善され、ソース管理の変更に関連付けられたビルドおよび配置パイプラインを使用した継続的配置のサポートが向上します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-185">This provides improved change control and better support for continuous deployment using a build and deploy pipeline tied to source control changes.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="8bf1e-186">コンテナーと orchestrators 最適なシナリオ</span><span class="sxs-lookup"><span data-stu-id="8bf1e-186">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="8bf1e-187">次のシナリオは、コンテナーと orchestrators 使用する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-187">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="8bf1e-188">高いアップタイムとスケーラビリティを必要とするアプリケーション</span><span class="sxs-lookup"><span data-stu-id="8bf1e-188">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="8bf1e-189">アップタイムとスケーラビリティの要件が高い個々のアプリケーションは、マイクロサービス、コンテナー、および orchestrators 使用したクラウドネイティブアーキテクチャに最適です。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-189">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="8bf1e-190">これらのアプリケーションは、バージョン管理された環境を使用してコンテナーで開発でき、運用環境に移行する前に広範囲にわたってテストでき、ダウンタイムなしで運用環境にデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-190">These applications can be developed in containers using versioned environments, can be extensively tested before going to production, and can be deployed to production with zero downtime.</span></span> <span data-ttu-id="8bf1e-191">Kubernetes クラスターを使用することにより、このようなアプリはオンデマンドでスケールしたり、ノードの障害から自動的に回復したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-191">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="8bf1e-192">多数のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="8bf1e-192">Large numbers of applications</span></span>

<span data-ttu-id="8bf1e-193">その後、多数のアプリケーションを展開する組織は、コンテナーと orchestrators 利用することでメリットを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-193">Organizations that deploy and must subsequently maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="8bf1e-194">コンテナー化された環境と Kubernetes クラスターを設定する前の作業は、主に固定コストです。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-194">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="8bf1e-195">個々のアプリケーションの配置、保守、および更新には、管理する必要があるアプリケーションの数に応じてコストがかかります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-195">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications that must be maintained.</span></span> <span data-ttu-id="8bf1e-196">ごく少数のアプリケーションを除き、カスタムアプリケーションを手動で管理することの複雑さは、コンテナーと orchestrators 使用したソリューションの実装コストを超過します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-196">Beyond a certain fairly small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="8bf1e-197">コンテナーと orchestrators 使用する必要があるのはどのような場合ですか。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-197">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="8bf1e-198">12要素アプリの原則に従ってアプリケーションを構築できない場合、または、コンテナーと orchestrators 避けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-198">If you're unwilling or unable to build your application following Twelve-Factor App principles, you'll probably be better off avoiding containers and orchestrators.</span></span> <span data-ttu-id="8bf1e-199">このような場合は、先に進むことが最適な場合があります。また、場合によっては、特定の機能を別のコンテナーまたはサーバーレス機能に移すことができるハイブリッドシステムを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-199">In these cases, it may be best to move forward with a VM-based hosting platform, or possibly some hybrid system in which you can spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="8bf1e-200">開発リソース</span><span class="sxs-lookup"><span data-stu-id="8bf1e-200">Development resources</span></span>

<span data-ttu-id="8bf1e-201">このセクションでは、次のアプリケーションでコンテナーとオーケストレーター使用を開始する際に役立つ、開発リソースの簡単な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-201">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="8bf1e-202">クラウドネイティブマイクロサービスアーキテクチャアプリを設計する方法に関するガイダンスについては、「 [.Net マイクロサービス: コンテナー化された .Net アプリケーションのアーキテクチャ](https://aka.ms/microservicesebook)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-202">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="8bf1e-203">ローカル Kubernetes の開発</span><span class="sxs-lookup"><span data-stu-id="8bf1e-203">Local Kubernetes Development</span></span>

<span data-ttu-id="8bf1e-204">Kubernetes のデプロイは運用環境での優れた価値を提供しますが、ローカルで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-204">Kubernetes deployments provide great value in production environments, but you can also run them locally.</span></span> <span data-ttu-id="8bf1e-205">個々のアプリまたはマイクロサービスで個別に作業できるのはかなりの時間ですが、運用環境にデプロイしたときに実行するのと同じように、システム全体をローカルで実行できることが適切な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-205">Although much of the time it's good to be able to work on individual apps or microservices independently, sometimes it's good to be able to run the whole system locally just as it will run when deployed to production.</span></span> <span data-ttu-id="8bf1e-206">これを実現するにはいくつかの方法があります。2つは Minikube と Docker Desktop です。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-206">There are several ways to achieve this, two of which are Minikube and Docker Desktop.</span></span> <span data-ttu-id="8bf1e-207">Visual Studio には、Docker 開発用のツールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-207">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="8bf1e-208">Minikube</span><span class="sxs-lookup"><span data-stu-id="8bf1e-208">Minikube</span></span>

<span data-ttu-id="8bf1e-209">Minikube とは</span><span class="sxs-lookup"><span data-stu-id="8bf1e-209">What is Minikube?</span></span> <span data-ttu-id="8bf1e-210">Minikube プロジェクトでは、"Minikube は macOS、Linux、および Windows でローカルの Kubernetes クラスターを実装しています" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-210">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="8bf1e-211">主な目的は、"ローカル Kubernetes アプリケーションの開発に最適なツールであり、Kubernetes のすべての機能をサポートすることです。" ということです。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-211">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="8bf1e-212">Minikube のインストールは Docker とは分離されていますが、Minikube は Docker デスクトップでサポートされるのとは異なるハイパーバイザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-212">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="8bf1e-213">現在、Minikube では次の Kubernetes 機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-213">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="8bf1e-214">DNS</span><span class="sxs-lookup"><span data-stu-id="8bf1e-214">DNS</span></span>
- <span data-ttu-id="8bf1e-215">NodePorts</span><span class="sxs-lookup"><span data-stu-id="8bf1e-215">NodePorts</span></span>
- <span data-ttu-id="8bf1e-216">ConfigMaps とシークレット</span><span class="sxs-lookup"><span data-stu-id="8bf1e-216">ConfigMaps and secrets</span></span>
- <span data-ttu-id="8bf1e-217">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="8bf1e-217">Dashboards</span></span>
- <span data-ttu-id="8bf1e-218">コンテナーランタイム: Docker、rkt、CRI、および格納されている</span><span class="sxs-lookup"><span data-stu-id="8bf1e-218">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="8bf1e-219">コンテナーネットワークインターフェイスを有効にする (CNI)</span><span class="sxs-lookup"><span data-stu-id="8bf1e-219">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="8bf1e-220">フィルタリング</span><span class="sxs-lookup"><span data-stu-id="8bf1e-220">Ingress</span></span>

<span data-ttu-id="8bf1e-221">Minikube をインストールしたら、イメージをダウンロードしてローカル Kubernetes クラスターを開始する `minikube start` コマンドを実行して、すぐに使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-221">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="8bf1e-222">クラスターを起動したら、標準の Kubernetes `kubectl` コマンドを使用して、クラスターと対話します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-222">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="8bf1e-223">Docker デスクトップ</span><span class="sxs-lookup"><span data-stu-id="8bf1e-223">Docker Desktop</span></span>

<span data-ttu-id="8bf1e-224">Windows の Docker デスクトップから直接 Kubernetes を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-224">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="8bf1e-225">これは、Windows コンテナーを使用している場合の唯一のオプションであり、Windows 以外のコンテナーにも適しています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-225">This is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="8bf1e-226">Docker Desktop から実行される Kubernetes を構成するには、標準の Docker デスクトップ構成アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-226">The standard Docker Desktop configuration app is used to configure Kubernetes running from Docker Desktop.</span></span>

![Docker Desktop での Kubernetes の構成](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="8bf1e-228">**図 3-4**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-228">**Figure 3-4**.</span></span> <span data-ttu-id="8bf1e-229">Docker Desktop で Kubernetes を構成しています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-229">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="8bf1e-230">Docker Desktop は、コンテナー化されたアプリをローカルで構成して実行するための最も一般的なツールです。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-230">Docker Desktop is already the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="8bf1e-231">Docker Desktop を使用する場合は、実稼働環境にデプロイする Docker コンテナーイメージのまったく同じセットに対してローカルで開発できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-231">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="8bf1e-232">Docker Desktop は、コンテナー化されたアプリをローカルで "ビルド、テスト、および出荷" するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-232">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="8bf1e-233">イメージが Azure Container Registry や Docker Hub などのイメージレジストリに配布されると、Azure Kubernetes Service (AKS) などのサービスは運用環境でアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-233">Once the images have been shipped to an image registry like Azure Container Registry or Docker Hub, then services like Azure Kubernetes Service (AKS) manage the application in production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="8bf1e-234">Visual Studio Docker ツール</span><span class="sxs-lookup"><span data-stu-id="8bf1e-234">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="8bf1e-235">Visual Studio では、web アプリケーションの Docker 開発をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-235">Visual Studio supports Docker development for web applications.</span></span> <span data-ttu-id="8bf1e-236">新しい ASP.NET Core アプリケーションを作成するときに、図3-5 に示すように、プロジェクト作成プロセスの一部として Docker サポートを使用して構成するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-236">When you create a new ASP.NET Core application, you're given the option to configure it with Docker support as part of the project creation process, as shown in Figure 3-5.</span></span>

![Visual Studio による Docker サポートの有効化](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="8bf1e-238">**図 3-5**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-238">**Figure 3-5**.</span></span> <span data-ttu-id="8bf1e-239">Visual Studio による Docker サポートの有効化</span><span class="sxs-lookup"><span data-stu-id="8bf1e-239">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="8bf1e-240">このオプションを選択すると、プロジェクトはルートに `Dockerfile` を使用して作成され、Docker コンテナーでアプリをビルドしてホストするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-240">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="8bf1e-241">図3-6 に、Dockerfile の例を示します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-241">An example Dockerfile is shown in Figure 3-6.</span></span>

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

<span data-ttu-id="8bf1e-242">**図 3-6**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-242">**Figure 3-6**.</span></span> <span data-ttu-id="8bf1e-243">Visual Studio によって生成された Dockerfile</span><span class="sxs-lookup"><span data-stu-id="8bf1e-243">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="8bf1e-244">アプリを実行するときの既定の動作は、Docker も使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-244">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="8bf1e-245">図3-7 は、Docker サポートを追加して作成された新しい ASP.NET Core プロジェクトで使用できるさまざまな実行オプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-245">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![Visual Studio Docker の実行オプション](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="8bf1e-247">**図 3-7**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-247">**Figure 3-7**.</span></span> <span data-ttu-id="8bf1e-248">Visual Studio Docker の実行オプション</span><span class="sxs-lookup"><span data-stu-id="8bf1e-248">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="8bf1e-249">[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/)には、ローカル開発に加えて、複数の開発者が Azure 内で独自の Kubernetes 構成を操作するための便利な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-249">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="8bf1e-250">図3-7 に示すように、Azure Dev Spaces でアプリケーションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-250">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="8bf1e-251">作成時に ASP.NET Core アプリケーションに Docker サポートを追加しない場合は、後でいつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-251">If you don't add Docker support to your ASP.NET Core application when you create it, you can always add it later.</span></span> <span data-ttu-id="8bf1e-252">図3-8 に示すように、Visual Studio ソリューションエクスプローラーからプロジェクトを右クリックし、[Add > Docker Support] \ ( **Docker サポート**の**追加**\) を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-252">From the Visual Studio Solution Explorer, right click on the project and select **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![Visual Studio による Docker サポートの追加](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="8bf1e-254">**図 3-8**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-254">**Figure 3-8**.</span></span> <span data-ttu-id="8bf1e-255">Visual Studio による Docker サポートの追加</span><span class="sxs-lookup"><span data-stu-id="8bf1e-255">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="8bf1e-256">Docker サポートに加えて、図3-8 に示すコンテナーオーケストレーションのサポートも追加できます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-256">In addition to Docker support, you can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="8bf1e-257">既定では、orchestrator は Kubernetes とヘルムを使用します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-257">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="8bf1e-258">Orchestrator を選択すると、`azds.yaml` ファイルがプロジェクトルートに追加され、アプリケーションを構成して Kubernetes に配置するために使用されるヘルムグラフを含む `charts` フォルダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-258">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="8bf1e-259">図3-9 に、新しいプロジェクトで生成されるファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="8bf1e-259">Figure 3-9 shows the resulting files in a new project.</span></span>

![Visual Studio の Orchestrator サポートの追加](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="8bf1e-261">**図 3-9**.</span><span class="sxs-lookup"><span data-stu-id="8bf1e-261">**Figure 3-9**.</span></span> <span data-ttu-id="8bf1e-262">Visual Studio の Orchestrator サポートの追加</span><span class="sxs-lookup"><span data-stu-id="8bf1e-262">Visual Studio Add Orchestrator Support</span></span>

## <a name="references"></a><span data-ttu-id="8bf1e-263">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bf1e-263">References</span></span>

- [<span data-ttu-id="8bf1e-264">Kubernetes とは</span><span class="sxs-lookup"><span data-stu-id="8bf1e-264">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="8bf1e-265">Minikube を使用した Kubernetes のインストール</span><span class="sxs-lookup"><span data-stu-id="8bf1e-265">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="8bf1e-266">MiniKube vs Docker デスクトップ</span><span class="sxs-lookup"><span data-stu-id="8bf1e-266">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="8bf1e-267">Visual Studio Tools for Docker</span><span class="sxs-lookup"><span data-stu-id="8bf1e-267">Visual Studio Tools for Docker</span></span>](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
><span data-ttu-id="8bf1e-268">[前へ](scale-applications.md)
>[次へ](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="8bf1e-268">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
