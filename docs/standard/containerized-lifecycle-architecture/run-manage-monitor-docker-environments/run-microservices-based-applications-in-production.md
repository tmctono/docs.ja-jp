---
title: 実稼働環境で構成される microservices ベースのアプリケーションを実行する
description: 運用環境でコンテナー ベースのアプリケーションを実行する主要なコンポーネントについて理解します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 52cf273194bff10192b06d236bda7c1cbea1abd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921590"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a><span data-ttu-id="bb2eb-103">実稼働環境で構成される microservices ベースのアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="bb2eb-103">Run composed and microservices-based applications in production environments</span></span>

<span data-ttu-id="bb2eb-104">複数のマイクロ サービスで構成されたアプリケーションは展開の複雑さを簡素化し、IT の観点から実行可能なようにするには orchestrator のクラスターをデプロイする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-104">Applications composed by multiple microservices do need to be deployed into orchestrator clusters in order to simplify the complexity of deployment and make it viable from an IT point of view.</span></span> <span data-ttu-id="bb2eb-105">オーケストレーター クラスタなしは、デプロイや、複雑なマイクロ サービス アプリケーションのスケール アウトが難しいでしょう。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-105">Without an orchestrator cluster, it would be difficult to deploy and scale out a complex microservices application.</span></span>

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a><span data-ttu-id="bb2eb-106">クラスターのオーケストレーター、スケジューラ、およびコンテナーの概要</span><span class="sxs-lookup"><span data-stu-id="bb2eb-106">Introduction to orchestrators, schedulers, and container clusters</span></span>

<span data-ttu-id="bb2eb-107">この電子書籍の前半*クラスター*と*スケジューラ*ソフトウェア アーキテクチャと開発についての説明の一部として導入されました。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-107">Earlier in this e-book, *clusters* and *schedulers* were introduced as part of the discussion on software architecture and development.</span></span> <span data-ttu-id="bb2eb-108">Kubernetes、Service Fabric は、Docker クラスターの例を示します。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-108">Kubernetes and Service Fabric are examples of Docker clusters.</span></span> <span data-ttu-id="bb2eb-109">Microsoft Azure Kubernetes サービスによって提供されるインフラストラクチャの一部としてこれらのオーケストレーターの両方を実行できます。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-109">Both of these orchestrators can run as a part of the infrastructure provided by Microsoft Azure Kubernetes Service.</span></span>

<span data-ttu-id="bb2eb-110">アプリケーションがスケール アウトされた複数のホスト システムで、各ホスト システムを管理し、基になるプラットフォームの複雑さを抽象化する機能は魅力的なものになります。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-110">When applications are scaled-out across multiple host systems, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive.</span></span> <span data-ttu-id="bb2eb-111">これがまさにオーケストレーターとスケジューラの提供内容です。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-111">That's precisely what orchestrators and schedulers provide.</span></span> <span data-ttu-id="bb2eb-112">ここで見て簡単なを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-112">Let's take a brief look at them here:</span></span>

- <span data-ttu-id="bb2eb-113">**スケジューラ**。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-113">**Schedulers**.</span></span><span data-ttu-id="bb2eb-114"> 「スケジュール」は、管理者が、特定のコンテナーを実行する方法を確立するホスト システムにサービス ファイルを読み込む機能を指します。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-114"> "Scheduling" refers to the ability for an administrator to load a service file onto a host system that establishes how to run a specific container.</span></span> <span data-ttu-id="bb2eb-115">Docker クラスター内のコンテナーの起動は、スケジュール設定と呼ばれる傾向があります。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-115">Launching containers in a Docker cluster tends to be known as scheduling.</span></span> <span data-ttu-id="bb2eb-116">一般的な意味で、サービス定義の読み込みの特定の動作を指しますスケジューリングのスケジューラはサービスに必要なすべての容量を管理するホストの init システムへのフッキング責任を負います。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-116">Although scheduling refers to the specific act of loading the service definition, in a more general sense, schedulers are responsible for hooking into a host's init system to manage services in whatever capacity needed.</span></span>

   <span data-ttu-id="bb2eb-117">クラスター スケジューラは、複数の目標: クラスターのリソースを効率的に使用して、ユーザーが指定した配置の制約を使用して、「公平に見て、」エラーに堅牢な中の程度が保留中の状態のままにしない場合に迅速にアプリケーションをスケジュール設定を使用し、常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-117">A cluster scheduler has multiple goals: using the cluster's resources efficiently, working with user-supplied placement constraints, scheduling applications rapidly to not leave them in a pending state, having a degree of "fairness," being robust to errors, and always be available.</span></span>

- <span data-ttu-id="bb2eb-118">**オーケストレーター**します。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-118">**Orchestrators**.</span></span><span data-ttu-id="bb2eb-119"> プラットフォームでは、ホストのクラスターに展開されているワークロードを複雑な複数コンテナーのライフ サイクル管理機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-119"> Platforms extend life-cycle management capabilities to complex, multi-container workloads deployed on a cluster of hosts.</span></span> <span data-ttu-id="bb2eb-120">ホスト インフラストラクチャを抽象化され、オーケストレーション ツールはユーザーをクラスター全体を 1 つの配置ターゲットとして扱う方法に付与します。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-120">By abstracting the host infrastructure, orchestration tools give users a way to treat the entire cluster as a single deployment target.</span></span>

   <span data-ttu-id="bb2eb-121">オーケストレーションのプロセスには、ツールと初期配置またはコンテナーごとの展開からのアプリケーション管理のすべての側面を自動化できるプラットフォームが含まれます。コンテナーをそのホストの正常性やパフォーマンスに応じて異なるホストに移動します。バージョン管理とローリング更新プログラム、および正常性監視のスケーリングとフェールオーバーをサポートする関数その他</span><span class="sxs-lookup"><span data-stu-id="bb2eb-121">The process of orchestration involves tooling and a platform that can automate all aspects of application management from initial placement or deployment per container; moving containers to different hosts depending on its host's health or performance; versioning and rolling updates and health monitoring functions that support scaling and failover; and many more.</span></span>

   <span data-ttu-id="bb2eb-122">オーケストレーションは、広義の用語を参照するコンテナーのスケジュール設定、クラスター管理、およびその他のホストのプロビジョニング可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-122">Orchestration is a broad term that refers to container scheduling, cluster management, and possibly the provisioning of additional hosts.</span></span>

<span data-ttu-id="bb2eb-123">オーケストレーターとスケジューラによって提供される機能が開発し、ゼロから作成する複雑なしたがって通常するベンダーによって提供されるオーケストレーション ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb2eb-123">The capabilities provided by orchestrators and schedulers are complex to develop and create from scratch, therefore you usually would want to use orchestration solutions offered by vendors.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bb2eb-124">[前へ](index.md)
>[次へ](manage-production-docker-environments.md)</span><span class="sxs-lookup"><span data-stu-id="bb2eb-124">[Previous](index.md)
[Next](manage-production-docker-environments.md)</span></span>
