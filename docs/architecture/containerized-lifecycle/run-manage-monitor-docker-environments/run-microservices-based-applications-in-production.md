---
title: 実稼働環境で構成される microservices ベースのアプリケーションを実行する
description: 運用環境でコンテナーベースのアプリケーションを実行するための主要なコンポーネントについて説明します
ms.date: 02/15/2019
ms.openlocfilehash: 69df3d39a00b91cbe59c96e5fcab841a60943bcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672919"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a><span data-ttu-id="f323e-103">実稼働環境で構成される microservices ベースのアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="f323e-103">Run composed and microservices-based applications in production environments</span></span>

<span data-ttu-id="f323e-104">複数のマイクロサービスで構成されるアプリケーションは、デプロイの複雑さを軽減し、IT の観点から実行可能にするために、オーケストレーター クラスターにデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f323e-104">Applications composed by multiple microservices do need to be deployed into orchestrator clusters in order to simplify the complexity of deployment and make it viable from an IT point of view.</span></span> <span data-ttu-id="f323e-105">オーケストレーター クラスターを使用しない場合、複雑なマイクロサービス アプリケーションのデプロイやスケールアウトが難しくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="f323e-105">Without an orchestrator cluster, it would be difficult to deploy and scale out a complex microservices application.</span></span>

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a><span data-ttu-id="f323e-106">オーケストレーター、スケジューラ、およびコンテナー クラスターの概要</span><span class="sxs-lookup"><span data-stu-id="f323e-106">Introduction to orchestrators, schedulers, and container clusters</span></span>

<span data-ttu-id="f323e-107">この電子書籍の前半で、"*クラスター*" と "*スケジューラ*" については、ソフトウェア アーキテクチャと開発に関する説明の一部として紹介しました。</span><span class="sxs-lookup"><span data-stu-id="f323e-107">Earlier in this e-book, *clusters* and *schedulers* were introduced as part of the discussion on software architecture and development.</span></span> <span data-ttu-id="f323e-108">Kubernetes と Service Fabric は、Docker クラスターの例です。</span><span class="sxs-lookup"><span data-stu-id="f323e-108">Kubernetes and Service Fabric are examples of Docker clusters.</span></span> <span data-ttu-id="f323e-109">これらのオーケストレーターはどちらも、Microsoft Azure Kubernetes Service によって提供されるインフラストラクチャの一部として実行できます。</span><span class="sxs-lookup"><span data-stu-id="f323e-109">Both of these orchestrators can run as a part of the infrastructure provided by Microsoft Azure Kubernetes Service.</span></span>

<span data-ttu-id="f323e-110">複数のホスト システム全体でアプリケーションをスケールアウトする場合に、各ホスト システムを管理し、基になるプラットフォームの複雑さを取り除く機能は魅力的になります。</span><span class="sxs-lookup"><span data-stu-id="f323e-110">When applications are scaled-out across multiple host systems, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive.</span></span> <span data-ttu-id="f323e-111">これがまさしくオーケストレーターとスケジューラが提供するものです。</span><span class="sxs-lookup"><span data-stu-id="f323e-111">That's precisely what orchestrators and schedulers provide.</span></span> <span data-ttu-id="f323e-112">ここでそれらについて簡単に見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="f323e-112">Let's take a brief look at them here:</span></span>

- <span data-ttu-id="f323e-113">**スケジューラ**。</span><span class="sxs-lookup"><span data-stu-id="f323e-113">**Schedulers**.</span></span><span data-ttu-id="f323e-114"> "スケジューリング" とは、管理者が、特定のコンテナーの実行方法を確立するホスト システムにサービス ファイルを読み込む機能を表します。</span><span class="sxs-lookup"><span data-stu-id="f323e-114"> "Scheduling" refers to the ability for an administrator to load a service file onto a host system that establishes how to run a specific container.</span></span> <span data-ttu-id="f323e-115">Docker クラスター内のコンテナーの起動は、スケジューリングと呼ばれる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="f323e-115">Launching containers in a Docker cluster tends to be known as scheduling.</span></span> <span data-ttu-id="f323e-116">スケジューリングとは、サービス定義の読み込みの特定の動作を指しますが、より一般的な意味では、スケジューラは必要とされる容量に関係なく、サービスを管理するために、ホストの init システムへのフックを担当します。</span><span class="sxs-lookup"><span data-stu-id="f323e-116">Although scheduling refers to the specific act of loading the service definition, in a more general sense, schedulers are responsible for hooking into a host's init system to manage services in whatever capacity needed.</span></span>

   <span data-ttu-id="f323e-117">クラスター スケジューラには、クラスターのリソースの効率的な使用、ユーザーが指定した配置の制約の処理、アプリケーションが保留状態で放置されないためのそれらの迅速なスケジューリング、一定の "公平性" の保持、エラーに対する堅牢性、常に使用可能であることなど、多くの目標があります。</span><span class="sxs-lookup"><span data-stu-id="f323e-117">A cluster scheduler has multiple goals: using the cluster's resources efficiently, working with user-supplied placement constraints, scheduling applications rapidly to not leave them in a pending state, having a degree of "fairness," being robust to errors, and always be available.</span></span>

- <span data-ttu-id="f323e-118">**オーケストレーター**。</span><span class="sxs-lookup"><span data-stu-id="f323e-118">**Orchestrators**.</span></span><span data-ttu-id="f323e-119"> プラットフォームでは、ライフサイクル管理機能が、ホストのクラスターにデプロイされている複雑な複数コンテナーのワークロードに拡張されます。</span><span class="sxs-lookup"><span data-stu-id="f323e-119"> Platforms extend life-cycle management capabilities to complex, multi-container workloads deployed on a cluster of hosts.</span></span> <span data-ttu-id="f323e-120">ホスト インフラストラクチャを抽象化することで、ユーザーはオーケストレーション ツールにより、クラスター全体を 1 つのデプロイ ターゲットとして扱う方法が得られます。</span><span class="sxs-lookup"><span data-stu-id="f323e-120">By abstracting the host infrastructure, orchestration tools give users a way to treat the entire cluster as a single deployment target.</span></span>

   <span data-ttu-id="f323e-121">オーケストレーションのプロセスには、コンテナーごとの初期配置やデプロイから、ホストの正常性やパフォーマンスに応じたコンテナーの別ホストへの移動、スケーリングとフェールオーバーをサポートするバージョン管理およびローリング更新および正常性監視機能など、アプリケーション管理のあらゆる側面を自動化できるツールとプラットフォームが関わります。</span><span class="sxs-lookup"><span data-stu-id="f323e-121">The process of orchestration involves tooling and a platform that can automate all aspects of application management from initial placement or deployment per container; moving containers to different hosts depending on its host's health or performance; versioning and rolling updates and health monitoring functions that support scaling and failover; and many more.</span></span>

   <span data-ttu-id="f323e-122">オーケストレーションとは、コンテナー スケジューリング、クラスター管理、および追加ホストのプロビジョニングなども表す広義の用語です。</span><span class="sxs-lookup"><span data-stu-id="f323e-122">Orchestration is a broad term that refers to container scheduling, cluster management, and possibly the provisioning of additional hosts.</span></span>

<span data-ttu-id="f323e-123">オーケストレーターとスケジューラによって提供される機能は、最初から開発および作成することが複雑であるため、通常、ベンダーによって提供されるオーケストレーション ソリューションを使用することを考慮します。</span><span class="sxs-lookup"><span data-stu-id="f323e-123">The capabilities provided by orchestrators and schedulers are complex to develop and create from scratch, therefore you usually would want to use orchestration solutions offered by vendors.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f323e-124">[前へ](index.md)
>[次へ](manage-production-docker-environments.md)</span><span class="sxs-lookup"><span data-stu-id="f323e-124">[Previous](index.md)
[Next](manage-production-docker-environments.md)</span></span>
