---
title: ASP.NET Core Web アプリ用の Azure ホスティングの推奨事項
description: ASP.NET Core および Azure での最新の Web アプリケーションの設計 | ASP.NET Web アプリ用の Azure ホスティングの推奨事項
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: a93009e66d63aa7d9c3b60951d43eafa3c351a63
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053262"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a><span data-ttu-id="12fc0-103">ASP.NET Core Web アプリ用の Azure ホスティングの推奨事項</span><span class="sxs-lookup"><span data-stu-id="12fc0-103">Azure hosting recommendations for ASP.NET Core web apps</span></span>

> <span data-ttu-id="12fc0-104">"基幹業務のリーダーはどこでも、IT 部門を通さずにクラウドからアプリケーションにアクセスし (別名 SaaS)、雑誌を購読するかのように料金を支払っています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-104">"Line-of-business leaders everywhere are bypassing IT departments to get applications from the cloud (aka SaaS) and paying for them like they would a magazine subscription.</span></span> <span data-ttu-id="12fc0-105">そして、サービスが不要になったら、無駄なくサブスクリプションを取り消すことができます。"</span><span class="sxs-lookup"><span data-stu-id="12fc0-105">And when the service is no longer required, they can cancel the subscription with no equipment left unused in the corner."</span></span>  
> <span data-ttu-id="12fc0-106">_\- Daryl Plummer、Gartner アナリスト_</span><span class="sxs-lookup"><span data-stu-id="12fc0-106">_\- Daryl Plummer, Gartner analyst_</span></span>

<span data-ttu-id="12fc0-107">Windows Azure なら、アプリケーションのニーズとアーキテクチャに応じたサポートが可能です。</span><span class="sxs-lookup"><span data-stu-id="12fc0-107">Whatever your application's needs and architecture, Windows Azure can support it.</span></span> <span data-ttu-id="12fc0-108">ホスティングのニーズは多数のサービスで構成される高度なアプリケーションの静的な Web サイトと同じくらい簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-108">Your hosting needs can be as simple as a static website to a sophisticated application made up of dozens of services.</span></span> <span data-ttu-id="12fc0-109">ASP.NET Core のモノリシックな Web アプリケーションとサポートされるサービスには、推奨されるいくつかのよく知られている構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-109">For ASP.NET Core monolithic web applications and supporting services, there are several well-known configurations that are recommended.</span></span> <span data-ttu-id="12fc0-110">この記事の推奨事項は、完全なアプリケーション、個別のプロセス、またはデータであっても、ホスティングされるリソースの種類に基づいてグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-110">The recommendations on this article are grouped based on the kind of resource to be hosted, whether full applications, individual processes, or data.</span></span>

## <a name="web-applications"></a><span data-ttu-id="12fc0-111">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="12fc0-111">Web applications</span></span>

<span data-ttu-id="12fc0-112">Web アプリケーションは次を使用してホスティングできます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-112">Web applications can be hosted with:</span></span>

- <span data-ttu-id="12fc0-113">App Service Web Apps</span><span class="sxs-lookup"><span data-stu-id="12fc0-113">App Service Web Apps</span></span>

- <span data-ttu-id="12fc0-114">コンテナー</span><span class="sxs-lookup"><span data-stu-id="12fc0-114">Containers</span></span>

- <span data-ttu-id="12fc0-115">仮想マシン (VM)</span><span class="sxs-lookup"><span data-stu-id="12fc0-115">Virtual Machines (VMs)</span></span>

<span data-ttu-id="12fc0-116">このうち、ほとんどのシナリオでお勧めできる手法が App Service Web Apps です。</span><span class="sxs-lookup"><span data-stu-id="12fc0-116">Of these, App Service Web Apps is the recommended approach for most scenarios.</span></span> <span data-ttu-id="12fc0-117">マイクロサービス アーキテクチャでは、コンテナー ベースの方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="12fc0-117">For microservice architectures, consider a container-based approach.</span></span> <span data-ttu-id="12fc0-118">アプリケーションを実行しているマシンをさらに制御する必要がある場合は、Azure Virtual Machines を検討してください。</span><span class="sxs-lookup"><span data-stu-id="12fc0-118">If you need more control over the machines running your application, consider Azure Virtual Machines.</span></span>

### <a name="app-service-web-apps"></a><span data-ttu-id="12fc0-119">App Service Web Apps</span><span class="sxs-lookup"><span data-stu-id="12fc0-119">App Service Web Apps</span></span>

<span data-ttu-id="12fc0-120">App Service Web Apps は、Web アプリケーションのホスティングに最適化されたフル マネージド プラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-120">App Service Web Apps offers a fully managed platform optimized for hosting web applications.</span></span> <span data-ttu-id="12fc0-121">これは、サービスとしてのプラットフォーム (PaaS) 製品です。Azure がアプリの実行とスケーリングに必要なインフラストラクチャに対処するため、ビジネス ロジックに集中することができます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-121">It's a platform as a service (PaaS) offering that lets you focus on your business logic, while Azure takes care of the infrastructure needed to run and scale the app.</span></span> <span data-ttu-id="12fc0-122">App Service Web Apps の主な機能:</span><span class="sxs-lookup"><span data-stu-id="12fc0-122">Some key features of App Service Web Apps:</span></span>

- <span data-ttu-id="12fc0-123">DevOps の最適化 (継続的インテグレーションと継続的配信、複数の環境、A/B テスト、スクリプトのサポート)</span><span class="sxs-lookup"><span data-stu-id="12fc0-123">DevOps optimization (continuous integration and delivery, multiple environments, A/B testing, scripting support).</span></span>

- <span data-ttu-id="12fc0-124">グローバルなスケーリングと高可用性</span><span class="sxs-lookup"><span data-stu-id="12fc0-124">Global scale and high availability.</span></span>

- <span data-ttu-id="12fc0-125">SaaS プラットフォームとオンプレミス データへの接続</span><span class="sxs-lookup"><span data-stu-id="12fc0-125">Connections to SaaS platforms and your on-premises data.</span></span>

- <span data-ttu-id="12fc0-126">セキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="12fc0-126">Security and compliance.</span></span>

- <span data-ttu-id="12fc0-127">Visual Studio の統合</span><span class="sxs-lookup"><span data-stu-id="12fc0-127">Visual Studio integration.</span></span>

- <span data-ttu-id="12fc0-128">[Web App for Containers](https://azure.microsoft.com/services/app-service/containers/) を利用した Linux および Windows コンテナーのサポート。</span><span class="sxs-lookup"><span data-stu-id="12fc0-128">Support for Linux and Windows containers via [Web App for Containers](https://azure.microsoft.com/services/app-service/containers/).</span></span>

<span data-ttu-id="12fc0-129">Azure App Service は、ほとんどの Web アプリに最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="12fc0-129">Azure App Service is the best choice for most web apps.</span></span> <span data-ttu-id="12fc0-130">デプロイと管理はプラットフォームに統合されており、サイトは高い負荷を処理できるように素早くスケーリングでき、組み込みの負荷分散とトラフィック マネージャーが高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-130">Deployment and management are integrated into the platform, sites can scale quickly to handle high traffic loads, and the built-in load balancing and traffic manager provide high availability.</span></span> <span data-ttu-id="12fc0-131">オンライン移行ツールを使用して既存のサイトを簡単に Azure App Service に移動したり、Web アプリケーション ギャラリーからオープンソース アプリを使用したり、選択したフレームワークとツールを使用して新しいサイトを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-131">You can move existing sites to Azure App Service easily with an online migration tool, use an open-source app from the Web Application Gallery, or create a new site using the framework and tools of your choice.</span></span> <span data-ttu-id="12fc0-132">Web ジョブ機能により、バックグラウンド ジョブ処理を App Service Web アプリに簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-132">The WebJobs feature makes it easy to add background job processing to your App Service web app.</span></span>

### <a name="azure-kubernetes-service"></a><span data-ttu-id="12fc0-133">Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="12fc0-133">Azure Kubernetes Service</span></span>

<span data-ttu-id="12fc0-134">Azure Kubernetes Service (AKS) は、ホストされている Kubernetes 環境を管理するサービスで、コンテナー オーケストレーションの専門知識がなくても、コンテナー化したアプリケーションのデプロイと管理をすばやく簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-134">Azure Kubernetes Service (AKS) manages your hosted Kubernetes environment, making it quick and easy to deploy and manage containerized applications without container orchestration expertise.</span></span> <span data-ttu-id="12fc0-135">また、アプリケーションをオフラインにせずに、オンデマンドでリソースのプロビジョニング、アップグレード、スケーリングを実行できるため、継続的に行う操作と保守の負担も解消されます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-135">It also eliminates the burden of ongoing operations and maintenance by provisioning, upgrading, and scaling resources on demand, without taking your applications offline.</span></span>

<span data-ttu-id="12fc0-136">AKS では、Azure に対する責任の多くをオフロードすることによって、Kubernetes クラスターの管理における複雑な運用のオーバーヘッドを削減します。</span><span class="sxs-lookup"><span data-stu-id="12fc0-136">AKS reduces the complexity and operational overhead of managing a Kubernetes cluster by offloading much of that responsibility to Azure.</span></span> <span data-ttu-id="12fc0-137">ホストされている Kubernetes サービスとして、Azure では、正常性の監視や保守などの重要なタスクが処理されます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-137">As a hosted Kubernetes service, Azure handles critical tasks like health monitoring and maintenance for you.</span></span> <span data-ttu-id="12fc0-138">また、マスターではなく、クラスター内のエージェント ノードのみの料金を支払います。</span><span class="sxs-lookup"><span data-stu-id="12fc0-138">Also, you pay only for the agent nodes within your clusters, not for the masters.</span></span> <span data-ttu-id="12fc0-139">マネージド Kubernetes サービスとして、AKS では次が提供されます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-139">As a managed Kubernetes service, AKS provides:</span></span>

- <span data-ttu-id="12fc0-140">自動化された Kubernetes バージョンのアップグレードと修正。</span><span class="sxs-lookup"><span data-stu-id="12fc0-140">Automated Kubernetes version upgrades and patching.</span></span>
- <span data-ttu-id="12fc0-141">簡単なクラスターのスケーリング。</span><span class="sxs-lookup"><span data-stu-id="12fc0-141">Easy cluster scaling.</span></span>
- <span data-ttu-id="12fc0-142">自己復旧のホストされているコントロール プレーン (マスター)。</span><span class="sxs-lookup"><span data-stu-id="12fc0-142">Self-healing hosted control plane (masters).</span></span>
- <span data-ttu-id="12fc0-143">コストの削減 - 実行中のエージェント プール ノードの料金のみを支払う。</span><span class="sxs-lookup"><span data-stu-id="12fc0-143">Cost savings - pay only for running agent pool nodes.</span></span>

<span data-ttu-id="12fc0-144">Azure で AKS クラスター内のノードの管理を処理することで、クラスターのアップグレードなど、多くのタスクを手動で実行する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="12fc0-144">With Azure handling the management of the nodes in your AKS cluster, you no longer need to perform many tasks manually, like cluster upgrades.</span></span> <span data-ttu-id="12fc0-145">Azure ではこれらの重要な保守タスクが処理されるため、AKS ではクラスターへの直接アクセスを提供しません (SSH の使用など)。</span><span class="sxs-lookup"><span data-stu-id="12fc0-145">Because Azure handles these critical maintenance tasks for you, AKS doesn't provide direct access (such as with SSH) to the cluster.</span></span>

### <a name="azure-virtual-machines"></a><span data-ttu-id="12fc0-146">Azure Virtual Machines</span><span class="sxs-lookup"><span data-stu-id="12fc0-146">Azure Virtual Machines</span></span>

<span data-ttu-id="12fc0-147">既存のアプリケーションにおいて App Service で実行するための大幅な変更が必要になった場合は、クラウドへの移行を簡略化するために Virtual Machines を選択できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-147">If you have an existing application that would require substantial modifications to run in App Service, you could choose Virtual Machines in order to simplify migrating to the cloud.</span></span> <span data-ttu-id="12fc0-148">ただし、Azure App Service と比較すると、VM の構成、セキュリティ保護、保守を正しく行うには、さらなる時間と IT の専門知識が必要になります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-148">However, correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to Azure App Service.</span></span> <span data-ttu-id="12fc0-149">Azure Virtual Machines を検討している場合は、現在の VM 環境のパッチ適用、更新、管理に必要な、継続的な保守作業を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="12fc0-149">If you're considering Azure Virtual Machines, make sure you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="12fc0-150">Azure 仮想マシンはサービスとしてのインフラストラクチャ (IaaS) であり、App Service は PaaS です。</span><span class="sxs-lookup"><span data-stu-id="12fc0-150">Azure Virtual Machines is infrastructure as a service (IaaS), while App Service is PaaS.</span></span> <span data-ttu-id="12fc0-151">また、アプリを Windows Container として Web App for Containers にデプロイすることが、シナリオにとって有効なオプションになり得るかどうかも検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-151">You should also consider whether deploying your app as a Windows Container to Web App for Containers might be a viable option for your scenario.</span></span>

## <a name="logical-processes"></a><span data-ttu-id="12fc0-152">論理プロセス</span><span class="sxs-lookup"><span data-stu-id="12fc0-152">Logical processes</span></span>

<span data-ttu-id="12fc0-153">アプリケーションから分離できる個々の論理プロセスは、Azure Functions に関係なく "サーバーレス" な方法でデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-153">Individual logical processes that can be decoupled from the rest of the application may be deployed independently to Azure Functions in a "serverless" manner.</span></span> <span data-ttu-id="12fc0-154">Azure Functions では、アプリケーションまたはインフラストラクチャの実行を気にせずに、特定の問題で必要なコードのみを記述できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-154">Azure Functions lets you just write the code you need for a given problem, without worrying about the application or infrastructure to run it.</span></span> <span data-ttu-id="12fc0-155">C\#、F\#、Node.js、Python、PHP などのさまざまなプログラミング言語を選択できるため、当面のタスクに対して最も生産性の高い言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-155">You can choose from a variety of programming languages, including C\#, F\#, Node.js, Python, and PHP, allowing you to pick the most productive language for the task at hand.</span></span> <span data-ttu-id="12fc0-156">ほとんどのクラウドベースのソリューションと同様、使用した時間に対してのみ料金を支払います。Azure Functions は必要に応じて確実にスケール アップされます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-156">Like most cloud-based solutions, you pay only for the amount of time your use, and you can trust Azure Functions to scale up as needed.</span></span>

## <a name="data"></a><span data-ttu-id="12fc0-157">データ</span><span class="sxs-lookup"><span data-stu-id="12fc0-157">Data</span></span>

<span data-ttu-id="12fc0-158">Azure はさまざまなデータ記憶域のオプションを提供しているため、アプリケーションが対象となるデータに適したデータ プロバイダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-158">Azure offers a wide variety of data storage options, so that your application can use the appropriate data provider for the data in question.</span></span>

<span data-ttu-id="12fc0-159">トランザクションに基づくリレーショナル データの場合、Azure SQL Database が最も適しています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-159">For transactional, relational data, Azure SQL Databases are the best option.</span></span> <span data-ttu-id="12fc0-160">高パフォーマンスの読み取りが多くのデータの場合、Azure SQL Database に基づく Redis キャッシュが適しています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-160">For high performance read-mostly data, a Redis cache backed by an Azure SQL Database is a good solution.</span></span>

<span data-ttu-id="12fc0-161">構造化されていない JSON データは、SQL Database 列から Azure Storage の Blob またはテーブル、DocumentDB まで、さまざまな方法で格納できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-161">Unstructured JSON data can be stored in a variety of ways, from SQL Database columns to Blobs or Tables in Azure Storage, to DocumentDB.</span></span> <span data-ttu-id="12fc0-162">このうち、DocumentDB がクエリ機能では最も優れており、クエリのサポートを必要とする JSON ベースのドキュメントが多数ある場合は、このオプションが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-162">Of these, DocumentDB offers the best querying functionality, and is the recommended option for large numbers of JSON-based documents that must support querying.</span></span>

<span data-ttu-id="12fc0-163">アプリケーションの動作を調整するために使用する一時的なコマンドベースの、またはイベントベースのデータでは、Azure Service Bus または Azure Storage キューを使用できます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-163">Transient command- or event-based data used to orchestrate application behavior can use Azure Service Bus or Azure Storage Queues.</span></span> <span data-ttu-id="12fc0-164">Azure Storage Bus はより柔軟性に優れているため、アプリケーション内、およびアプリケーション間で重要なメッセージをやり取りする場合に推奨されるサービスです。</span><span class="sxs-lookup"><span data-stu-id="12fc0-164">Azure Storage Bus offers more flexibility and is the recommended service for non-trivial messaging within and between applications.</span></span>

## <a name="architecture-recommendations"></a><span data-ttu-id="12fc0-165">アーキテクチャに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="12fc0-165">Architecture recommendations</span></span>

<span data-ttu-id="12fc0-166">アプリケーションの要件で、アーキテクチャについて指示している必要があります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-166">Your application's requirements should dictate its architecture.</span></span> <span data-ttu-id="12fc0-167">利用できるさまざまな Azure サービスが多くあります。</span><span class="sxs-lookup"><span data-stu-id="12fc0-167">There are many different Azure services available.</span></span> <span data-ttu-id="12fc0-168">適切なサービスを選ぶことが重要です。</span><span class="sxs-lookup"><span data-stu-id="12fc0-168">Choosing the right one is an important decision.</span></span> <span data-ttu-id="12fc0-169">Microsoft では、一般的なシナリオに最適化された典型的なアーキテクチャを特定できるように、参照アーキテクチャのギャラリーを提供しています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-169">Microsoft offers a gallery of reference architectures to help identify typical architectures optimized for common scenarios.</span></span> <span data-ttu-id="12fc0-170">アプリケーションの要件に最も近い、または少なくとも使い始めに適している参照アーキテクチャを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="12fc0-170">You may find a reference architecture that maps closely to your application's requirements, or at least offers a starting point.</span></span>

<span data-ttu-id="12fc0-171">図 11-2 は、参照アーキテクチャの例です。</span><span class="sxs-lookup"><span data-stu-id="12fc0-171">Figure 11-2 shows an example reference architecture.</span></span> <span data-ttu-id="12fc0-172">この図は、マーケティングに最適化された Sitecore コンテンツ管理システム Web サイトに推奨されるアーキテクチャの手法を示しています。</span><span class="sxs-lookup"><span data-stu-id="12fc0-172">This diagram describes a recommended architecture approach for a Sitecore content management system website optimized for marketing.</span></span>

![](./media/image11-2.png)

<span data-ttu-id="12fc0-173">**図 11-1**</span><span class="sxs-lookup"><span data-stu-id="12fc0-173">**Figure 11-1.**</span></span> <span data-ttu-id="12fc0-174">Sitecore マーケティング Web サイトの参照アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="12fc0-174">Sitecore marketing website reference architecture.</span></span>

<span data-ttu-id="12fc0-175">**参照 – Azure のホスティングの推奨事項**</span><span class="sxs-lookup"><span data-stu-id="12fc0-175">**References – Azure hosting recommendations**</span></span>

- <span data-ttu-id="12fc0-176">Azure ソリューション アーキテクチャ\\</span><span class="sxs-lookup"><span data-stu-id="12fc0-176">Azure Solution Architectures\\</span></span>
  <https://azure.microsoft.com/solutions/architecture/>

- <span data-ttu-id="12fc0-177">Azure の開発者ガイド\\</span><span class="sxs-lookup"><span data-stu-id="12fc0-177">Azure Developer Guide\\</span></span>
  <https://azure.microsoft.com/campaigns/developer-guide/>

- <span data-ttu-id="12fc0-178">Web Apps の概要\\</span><span class="sxs-lookup"><span data-stu-id="12fc0-178">Web Apps overview\\</span></span>
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- <span data-ttu-id="12fc0-179">Web App for Containers\\</span><span class="sxs-lookup"><span data-stu-id="12fc0-179">Web App for Containers\\</span></span>
  <https://azure.microsoft.com/services/app-service/containers/>

- <span data-ttu-id="12fc0-180">Azure Kubernetes Service (AKS) の概要\\</span><span class="sxs-lookup"><span data-stu-id="12fc0-180">Introduction to Azure Kubernetes Service (AKS)\\</span></span>
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[<span data-ttu-id="12fc0-181">前へ</span><span class="sxs-lookup"><span data-stu-id="12fc0-181">Previous</span></span>](development-process-for-azure.md)
