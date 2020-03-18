---
title: 監視と製品利用統計情報でアプリを最新化する
description: Azure クラウドおよび Windows コンテナーを使用して既存の .NET アプリケーションを最新化する | 監視と製品利用統計情報でアプリを最新化する
ms.date: 04/30/2018
ms.openlocfilehash: 3d629e89a73c870d4b6396c6b1d0ecbe95b79ead
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393849"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="fe165-103">監視と製品利用統計情報でアプリを最新化する</span><span class="sxs-lookup"><span data-stu-id="fe165-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="fe165-104">運用環境でアプリケーションを実行する場合、アプリケーションのパフォーマンスについての分析情報を有していることが重要です。</span><span class="sxs-lookup"><span data-stu-id="fe165-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="fe165-105">実行レベルは高いですか。</span><span class="sxs-lookup"><span data-stu-id="fe165-105">Is it performing at a high level?</span></span> <span data-ttu-id="fe165-106">ユーザーがエラーを受け取っていますか、あるいは、アプリケーションは安定して信頼できますか。</span><span class="sxs-lookup"><span data-stu-id="fe165-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="fe165-107">確実にアプリケーションを使用でき、期待どおりに動作できるように、多機能なパフォーマンス監視、強力なアラート機能、ダッシュボードが必要です。</span><span class="sxs-lookup"><span data-stu-id="fe165-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="fe165-108">また、問題が発生した場合にすばやく表示し、影響を受けている顧客の数を特定し、根本原因の分析を実行して問題を見つけて解決する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="fe165-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="fe165-109">Application Insights を使用してアプリケーションを監視する</span><span class="sxs-lookup"><span data-stu-id="fe165-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="fe165-110">Application Insights は、複数のプラットフォームで作業する Web 開発者向けの拡張可能なアプリケーション パフォーマンス管理 (APM) サービスです。</span><span class="sxs-lookup"><span data-stu-id="fe165-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="fe165-111">このサービスを使用して、実行中の Web アプリケーションを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="fe165-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="fe165-112">Application Insights は、パフォーマンスの異常を自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="fe165-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="fe165-113">組み込まれている強力な分析ツールを使えば、問題を診断でき、ユーザーがアプリを使用して実行している操作を把握できます。</span><span class="sxs-lookup"><span data-stu-id="fe165-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="fe165-114">Application Insights は、パフォーマンスと使いやすさを継続的に改善できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="fe165-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="fe165-115">オンプレミスとクラウドのどちらでホストされているかに関係なく、.NET、Node.js、J2EE などのさまざまなプラットフォーム上のアプリに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fe165-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="fe165-116">Application Insights は、DevOps プロセスと統合され、さまざまな開発ツールへの接続ポイントを備えています。</span><span class="sxs-lookup"><span data-stu-id="fe165-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="fe165-117">図 4-10 は、Application Insights でアプリケーションを監視する方法と、その分析情報をダッシュボードに表示する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe165-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 監視ダッシュボードのスクリーンショット。](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

<span data-ttu-id="fe165-119">**図 4-10**</span><span class="sxs-lookup"><span data-stu-id="fe165-119">**Figure 4-10.**</span></span> <span data-ttu-id="fe165-120">Application Insights 監視ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="fe165-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="fe165-121">Log Analytics とそのコンテナー監視ソリューションを使用して Docker インフラストラクチャを監視する</span><span class="sxs-lookup"><span data-stu-id="fe165-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="fe165-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) は、[Microsoft Azure の全体監視ソリューション](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe165-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="fe165-123">また、[Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview) のサービスでもあります。</span><span class="sxs-lookup"><span data-stu-id="fe165-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="fe165-124">Log Analytics では、可用性とパフォーマンスを維持できるように、クラウド環境とオンプレミス環境 (オンプレミスの場合は OMS) を監視します。</span><span class="sxs-lookup"><span data-stu-id="fe165-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="fe165-125">Log Analytics を使用すると、クラウドおよびオンプレミスの環境内にあるリソースによって生成されたデータや、他の監視ツールのデータを収集し、複数のソースにわたる分析を行えます。</span><span class="sxs-lookup"><span data-stu-id="fe165-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="fe165-126">Azure インフラストラクチャ ログに関して、Log Analytics は、Azure サービスとして、他の Azure サービス ([Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor) を使用)、Azure VM、Docker コンテナー、オンプレミスまたはその他のクラウド インフラストラクチャのログとメトリック データが取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="fe165-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="fe165-127">Log Analytics では、このデータに加えて、柔軟なログ検索と、すぐに利用できる分析機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe165-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="fe165-128">複数のソースのデータ分析に使用できる豊富なツールが提供され、すべてのログに対して複雑なクエリを実行でき、指定した条件に基づいて事前に通知することができます。</span><span class="sxs-lookup"><span data-stu-id="fe165-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="fe165-129">さらにカスタム データを Log Analytics の中央リポジトリに収集して、照会および視覚化することができます。</span><span class="sxs-lookup"><span data-stu-id="fe165-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="fe165-130">また、Log Analytics の組み込みソリューションを活用して、インフラストラクチャのセキュリティと機能の分析情報をすぐに得ることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe165-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="fe165-131">Log Analytics には、任意のブラウザーで稼働する OMS ポータルまたは Azure portal を使用してアクセスでき、構成設定と複数のツールを使用して、収集されたデータの分析と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe165-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="fe165-132">Log Analytics の[コンテナー監視ソリューション](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)を使用すると、Docker と Windows のコンテナー ホストを 1 か所に表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="fe165-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="fe165-133">このソリューションは、どのコンテナーが実行中か、何のコンテナー イメージを実行中か、コンテナーがどこで実行中かを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe165-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="fe165-134">コンテナーで使用されているコマンドなど、詳細な監査情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe165-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="fe165-135">また、Docker または Windows ホストをリモートで確認しなくても、一元化されたログを表示および検索して、コンテナーのトラブルシューティングを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="fe165-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="fe165-136">ノイジー ネイバーで、ホストで過剰なリソースを使用している可能性のあるコンテナーを特定できます。</span><span class="sxs-lookup"><span data-stu-id="fe165-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="fe165-137">さらに、コンテナーについて、CPU、メモリ、ストレージ、ネットワークの使用量と、パフォーマンスに関する情報を一元的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="fe165-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="fe165-138">Windows を実行しているコンピューターでは、Windows Server、Hyper-V、Docker の各コンテナーのログを一元化して比較できます。</span><span class="sxs-lookup"><span data-stu-id="fe165-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="fe165-139">このソリューションは、次のコンテナー オーケストレーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fe165-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="fe165-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="fe165-140">Docker Swarm</span></span>

- <span data-ttu-id="fe165-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="fe165-141">DC/OS</span></span>

- <span data-ttu-id="fe165-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fe165-142">Kubernetes</span></span>

- <span data-ttu-id="fe165-143">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="fe165-143">Red Hat OpenShift</span></span>

<span data-ttu-id="fe165-144">図 4-11 は、さまざまなコンテナー ホストおよびエージェントと OMS の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe165-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics コンテナー監視ソリューションのスクリーンショット。](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

<span data-ttu-id="fe165-146">**図 4-11**</span><span class="sxs-lookup"><span data-stu-id="fe165-146">**Figure 4-11.**</span></span> <span data-ttu-id="fe165-147">Log Analytics コンテナー監視ソリューション</span><span class="sxs-lookup"><span data-stu-id="fe165-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="fe165-148">Log Analytics コンテナー監視ソリューションを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe165-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="fe165-149">すべてのコンテナー ホストに関する情報を 1 か所に表示します。</span><span class="sxs-lookup"><span data-stu-id="fe165-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="fe165-150">どのコンテナーが実行中か、何のイメージを実行中か、どこで実行中かを把握します。</span><span class="sxs-lookup"><span data-stu-id="fe165-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="fe165-151">コンテナー上のアクションに対する監査証跡を表示します。</span><span class="sxs-lookup"><span data-stu-id="fe165-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="fe165-152">Docker ホストにリモート ログインすることなく、一元化されたログを表示し、検索してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="fe165-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="fe165-153">"ノイジー ネイバー" で、ホストで過剰なリソースを使用している可能性のあるコンテナーを特定します。</span><span class="sxs-lookup"><span data-stu-id="fe165-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="fe165-154">コンテナーについて、CPU、メモリ、ストレージ、ネットワークの使用量と、パフォーマンスに関する情報を一元的に確認します。</span><span class="sxs-lookup"><span data-stu-id="fe165-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="fe165-155">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="fe165-155">Additional resources</span></span>

- <span data-ttu-id="fe165-156">**Microsoft Azure での監視の概要**</span><span class="sxs-lookup"><span data-stu-id="fe165-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="fe165-157">**Application Insights とは何か?**</span><span class="sxs-lookup"><span data-stu-id="fe165-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="fe165-158">**Log Analytics とは**</span><span class="sxs-lookup"><span data-stu-id="fe165-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="fe165-159">**Azure Monitor のコンテナー監視ソリューション**</span><span class="sxs-lookup"><span data-stu-id="fe165-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="fe165-160">**Azure Monitor の概要**</span><span class="sxs-lookup"><span data-stu-id="fe165-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="fe165-161">**Operations Management Suite (OMS) とは**</span><span class="sxs-lookup"><span data-stu-id="fe165-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="fe165-162">[前へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[次へ](life-cycle-ci-cd-pipelines-devops-tools.md)</span><span class="sxs-lookup"><span data-stu-id="fe165-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](life-cycle-ci-cd-pipelines-devops-tools.md)</span></span>
