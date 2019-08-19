---
title: 監視と製品利用統計情報でアプリを最新化する
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |監視とテレメトリを使用してアプリを最新化する
ms.date: 04/30/2018
ms.openlocfilehash: 5bffb336234f63dca150acc9ef31f9efa2e3937b
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578175"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="c9e74-103">監視と製品利用統計情報でアプリを最新化する</span><span class="sxs-lookup"><span data-stu-id="c9e74-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="c9e74-104">運用環境でアプリケーションを実行する場合、アプリケーションのパフォーマンスについての洞察があることが重要です。</span><span class="sxs-lookup"><span data-stu-id="c9e74-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="c9e74-105">高レベルで実行していますか。</span><span class="sxs-lookup"><span data-stu-id="c9e74-105">Is it performing at a high level?</span></span> <span data-ttu-id="c9e74-106">ユーザーがエラーを受け取るか、アプリケーションの安定性と信頼性があるか。</span><span class="sxs-lookup"><span data-stu-id="c9e74-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="c9e74-107">アプリケーションを確実に使用し、期待どおりに実行できるように、豊富なパフォーマンス監視、強力なアラート、ダッシュボードが必要です。</span><span class="sxs-lookup"><span data-stu-id="c9e74-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="c9e74-108">また、問題が発生した場合はすばやく表示し、影響を受けている顧客の数を特定し、根本原因の分析を実行して問題を見つけて解決する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c9e74-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="c9e74-109">Application Insights を使用したアプリケーションの監視</span><span class="sxs-lookup"><span data-stu-id="c9e74-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="c9e74-110">Application Insights は、複数のプラットフォームで作業する web 開発者向けの拡張可能なアプリケーションパフォーマンス管理 (APM) サービスです。</span><span class="sxs-lookup"><span data-stu-id="c9e74-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="c9e74-111">これを使用して、ライブ web アプリケーションを監視します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="c9e74-112">Application Insights は、パフォーマンスの異常を自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="c9e74-113">これには、問題の診断に役立つ強力な分析ツールが含まれており、ユーザーがアプリで実際に実行する操作を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="c9e74-114">Application Insights は、パフォーマンスと使いやすさを継続的に向上させることができるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c9e74-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="c9e74-115">オンプレミスまたはクラウドにホストされているかどうかにかかわらず、.NET、node.js、J2EE など、さまざまなプラットフォーム上のアプリで動作します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="c9e74-116">Application Insights は、DevOps プロセスと統合され、さまざまな開発ツールへの接続ポイントを備えています。</span><span class="sxs-lookup"><span data-stu-id="c9e74-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="c9e74-117">図4-10 は、Application Insights がアプリケーションを監視する方法と、その洞察をダッシュボードに表示する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9e74-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 監視ダッシュボード](./media/image10.png)

> <span data-ttu-id="c9e74-119">**図 4-10.**</span><span class="sxs-lookup"><span data-stu-id="c9e74-119">**Figure 4-10.**</span></span> <span data-ttu-id="c9e74-120">Application Insights 監視ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="c9e74-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="c9e74-121">Log Analytics とそのコンテナー監視ソリューションを使用して Docker インフラストラクチャを監視する</span><span class="sxs-lookup"><span data-stu-id="c9e74-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="c9e74-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)は、 [Microsoft Azure 監視ソリューション全体](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)の一部です。</span><span class="sxs-lookup"><span data-stu-id="c9e74-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="c9e74-123">また、 [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)のサービスでもあります。</span><span class="sxs-lookup"><span data-stu-id="c9e74-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="c9e74-124">Log Analytics は、クラウドおよびオンプレミスの環境 (OMS の場合) を監視して、可用性とパフォーマンスを維持します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="c9e74-125">クラウドとオンプレミスの環境内のリソースによって生成されたデータを収集し、その他の監視ツールから、複数のソースにわたる分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="c9e74-126">Azure インフラストラクチャログに関しては、Log Analytics azure サービスとして、他の Azure サービス ( [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)経由)、azure Vm、Docker コンテナー、オンプレミスまたはその他のクラウドインフラストラクチャのログとメトリックデータを取り込みします。</span><span class="sxs-lookup"><span data-stu-id="c9e74-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="c9e74-127">Log Analytics は、このデータの上に柔軟なログ検索と、すぐに利用できる分析機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="c9e74-128">これには、ソース全体のデータの分析に使用できる豊富なツールが用意されています。また、すべてのログに対して複雑なクエリを実行でき、指定された条件に基づいて事前にアラートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="c9e74-129">中央の Log Analytics リポジトリでカスタムデータを収集することもできます。この場合、クエリと視覚化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="c9e74-130">また、Log Analytics 組み込みソリューションを活用して、インフラストラクチャのセキュリティと機能についてすぐに洞察を得ることもできます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="c9e74-131">OMS ポータルまたは任意のブラウザーで実行されている Azure portal を使用して Log Analytics にアクセスできます。また、構成設定や複数のツールにアクセスして、収集したデータを分析して操作することができます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="c9e74-132">Log Analytics の[コンテナー監視ソリューション](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)を使用すると、Docker および Windows コンテナーホストを1か所で表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="c9e74-133">このソリューションでは、どのコンテナーが実行されているか、どのコンテナーイメージが実行されているか、コンテナーが実行されている場所が示されます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="c9e74-134">コンテナーで使用されているコマンドなど、詳細な監査情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="c9e74-135">また、Docker または Windows ホストをリモートで表示することなく、集中管理されたログを表示および検索して、コンテナーのトラブルシューティングを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="c9e74-136">ノイズが発生し、ホスト上のリソースを消費している可能性のあるコンテナーを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="c9e74-137">また、コンテナーの CPU、メモリ、ストレージ、およびネットワークの集中的な使用率とパフォーマンス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="c9e74-138">Windows を実行しているコンピューターでは、Windows Server、Hyper-v、および Docker コンテナーのログを一元化して比較することができます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="c9e74-139">このソリューションでは、次のコンテナー orchestrators サポートされています。</span><span class="sxs-lookup"><span data-stu-id="c9e74-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="c9e74-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="c9e74-140">Docker Swarm</span></span>

- <span data-ttu-id="c9e74-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="c9e74-141">DC/OS</span></span>

- <span data-ttu-id="c9e74-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c9e74-142">Kubernetes</span></span>

- <span data-ttu-id="c9e74-143">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="c9e74-143">Red Hat OpenShift</span></span>

<span data-ttu-id="c9e74-144">図4-11 は、さまざまなコンテナーホストとエージェントおよび OMS 間の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="c9e74-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics コンテナー監視ソリューション](./media/image11.png)

> <span data-ttu-id="c9e74-146">**図 4-11.**</span><span class="sxs-lookup"><span data-stu-id="c9e74-146">**Figure 4-11.**</span></span> <span data-ttu-id="c9e74-147">Log Analytics コンテナー監視ソリューション</span><span class="sxs-lookup"><span data-stu-id="c9e74-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="c9e74-148">Log Analytics Container Monitoring ソリューションを使用して、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c9e74-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="c9e74-149">1つの場所にあるすべてのコンテナーホストに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="c9e74-150">実行中のコンテナー、実行されているイメージ、および実行されている場所を把握します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="c9e74-151">コンテナーに対するアクションについては、監査証跡を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9e74-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="c9e74-152">Docker ホストへのリモートログインを行わずに、一元化されたログを表示して検索することによってトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="c9e74-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="c9e74-153">"ノイズの多い近隣ノード" であり、ホスト上で過剰なリソースを消費している可能性のあるコンテナーを検索します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="c9e74-154">コンテナーの CPU、メモリ、ストレージ、およびネットワークの集中的な使用状況とパフォーマンス情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9e74-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="c9e74-155">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="c9e74-155">Additional resources</span></span>

- <span data-ttu-id="c9e74-156">**Microsoft Azure での監視の概要**</span><span class="sxs-lookup"><span data-stu-id="c9e74-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="c9e74-157">**Application Insights とは何か?**</span><span class="sxs-lookup"><span data-stu-id="c9e74-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="c9e74-158">**Log Analytics とは**</span><span class="sxs-lookup"><span data-stu-id="c9e74-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="c9e74-159">**Azure Monitor のコンテナー監視ソリューション**</span><span class="sxs-lookup"><span data-stu-id="c9e74-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="c9e74-160">**Azure Monitor の概要**</span><span class="sxs-lookup"><span data-stu-id="c9e74-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="c9e74-161">**Operations Management Suite (OMS) とは**</span><span class="sxs-lookup"><span data-stu-id="c9e74-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="c9e74-162">[前へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[次へ](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="c9e74-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
