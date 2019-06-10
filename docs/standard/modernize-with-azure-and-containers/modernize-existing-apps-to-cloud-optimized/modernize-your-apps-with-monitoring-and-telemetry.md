---
title: 監視と製品利用統計情報でアプリを最新化する
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |監視と遠隔測定でアプリを最新化します。
ms.date: 04/30/2018
ms.openlocfilehash: 5bffb336234f63dca150acc9ef31f9efa2e3937b
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758623"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="1c33b-103">監視と製品利用統計情報でアプリを最新化する</span><span class="sxs-lookup"><span data-stu-id="1c33b-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="1c33b-104">運用環境でアプリケーションを実行するときに、アプリケーションの実行状況に関する洞察があることが重要です。</span><span class="sxs-lookup"><span data-stu-id="1c33b-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="1c33b-105">高レベルが高いでしょうか。</span><span class="sxs-lookup"><span data-stu-id="1c33b-105">Is it performing at a high level?</span></span> <span data-ttu-id="1c33b-106">ユーザー エラーが発生、または安定性と信頼性の高いアプリケーションは、ですか。</span><span class="sxs-lookup"><span data-stu-id="1c33b-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="1c33b-107">豊富なパフォーマンスの監視、強力なアラート、およびダッシュ ボード、アプリケーションが使用可能なと予期されるパフォーマンスであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c33b-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="1c33b-108">また、かどうかは、問題をすばやく確認するには、顧客の数が影響を受けてし、見つけて、問題を修正、根本原因分析、を決定できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c33b-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="1c33b-109">Application Insights を使用してアプリケーションを監視します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="1c33b-110">Application Insights は、複数のプラットフォームで作業を行う web 開発者の拡張可能なアプリケーション パフォーマンス管理 (APM) サービスです。</span><span class="sxs-lookup"><span data-stu-id="1c33b-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="1c33b-111">ライブ web アプリケーションを監視するのにには、これを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="1c33b-112">Application Insights は、パフォーマンスの異常を自動的に検出します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="1c33b-113">これには、問題の診断に役立つとで何が実際に実行、アプリの理解に役立つ強力な分析ツールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="1c33b-114">Application Insights はパフォーマンスと使いやすさを継続的に向上させるために設計されています。</span><span class="sxs-lookup"><span data-stu-id="1c33b-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="1c33b-115">さまざまなプラットフォーム、.NET、Node.js、J2EE をかどうかなどのアプリケーションに適してがオンプレミスでホストまたはクラウドで。</span><span class="sxs-lookup"><span data-stu-id="1c33b-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="1c33b-116">Application Insights は、DevOps プロセスと統合し、さまざまな開発ツールへの接続ポイントします。</span><span class="sxs-lookup"><span data-stu-id="1c33b-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="1c33b-117">図 4-10 では、Application Insights がアプリケーションを監視する方法と、ダッシュ ボードにこれらの洞察の表示の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights の監視ダッシュ ボード](./media/image10.png)

> <span data-ttu-id="1c33b-119">**図 4-10。**</span><span class="sxs-lookup"><span data-stu-id="1c33b-119">**Figure 4-10.**</span></span> <span data-ttu-id="1c33b-120">Application Insights の監視ダッシュ ボード</span><span class="sxs-lookup"><span data-stu-id="1c33b-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="1c33b-121">Docker を Log Analytics とそのコンテナー監視ソリューション インフラストラクチャを監視します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="1c33b-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)の一部である、 [Microsoft Azure の全体監視ソリューション](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="1c33b-123">これはまた、サービス[Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="1c33b-124">Log Analytics 監視クラウドとオンプレミス環境 (オンプレミス用の OMS) の可用性とパフォーマンスを維持するためにします。</span><span class="sxs-lookup"><span data-stu-id="1c33b-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="1c33b-125">リソースが、クラウドおよびオンプレミス環境内で、複数のソースにわたる分析を提供する他の監視ツールから生成されたデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="1c33b-126">Azure インフラストラクチャのログに対する Log Analytics では、Azure のサービスとしてログとメトリックからデータを取り込む他の Azure サービス (を使用して[Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor))、Azure Vm、Docker コンテナー、およびオンプレミスまたはその他のクラウド インフラストラクチャ。</span><span class="sxs-lookup"><span data-stu-id="1c33b-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="1c33b-127">Log Analytics では、柔軟なログ検索とそのデータ出力の分析を提供します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="1c33b-128">指定した条件に基づいてことソース間でデータを分析する際、すべてのログの間で複雑なクエリがおよび、事前に通知することができます、豊富なツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="1c33b-129">中央の Log Analytics リポジトリを照会および視覚化できるにカスタム データも収集できます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="1c33b-130">セキュリティに関する洞察を即座に得るために Log Analytics の組み込みソリューションを利用し、インフラストラクチャの機能を実行することができますも。</span><span class="sxs-lookup"><span data-stu-id="1c33b-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="1c33b-131">OMS ポータルまたは任意のブラウザーで実行して、Azure portal から Log Analytics にアクセスし、構成設定にアクセスしてや複数のツールを分析し、収集されたデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="1c33b-132">[コンテナー監視ソリューション](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)Log Analytics での表示し、1 つの場所で Docker と Windows コンテナー ホストを管理します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="1c33b-133">どのコンテナーが、ソリューションを示しています、どのようなコンテナー イメージを実行して、実行されているし、コンテナーが実行されています。</span><span class="sxs-lookup"><span data-stu-id="1c33b-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="1c33b-134">コンテナーで使用されているコマンドを含む、詳細な監査情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="1c33b-135">また、コンテナーを表示および Docker または Windows ホストをリモートで表示することがなく、一元化されたログを検索してトラブルシューティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="1c33b-136">ホストで余分なリソースを簡潔にかかる可能性があるコンテナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="1c33b-137">さらに、一元的な CPU、メモリ、ストレージ、およびネットワーク使用率およびパフォーマンスについては、コンテナーを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="1c33b-138">Windows を実行するコンピューターで、集中管理し、Windows サーバーからログを比較することができます、HYPER-V、および Docker コンテナー。</span><span class="sxs-lookup"><span data-stu-id="1c33b-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="1c33b-139">ソリューションには、次のようなコンテナー オーケストレーターがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1c33b-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="1c33b-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="1c33b-140">Docker Swarm</span></span>

- <span data-ttu-id="1c33b-141">DC OS/</span><span class="sxs-lookup"><span data-stu-id="1c33b-141">DC/OS</span></span>

- <span data-ttu-id="1c33b-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="1c33b-142">Kubernetes</span></span>

- <span data-ttu-id="1c33b-143">Red Hat の OpenShift</span><span class="sxs-lookup"><span data-stu-id="1c33b-143">Red Hat OpenShift</span></span>

<span data-ttu-id="1c33b-144">図 4-11 は、さまざまなコンテナー ホストとエージェントと OMS 間の関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="1c33b-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics コンテナー監視ソリューション](./media/image11.png)

> <span data-ttu-id="1c33b-146">**図 4-11。**</span><span class="sxs-lookup"><span data-stu-id="1c33b-146">**Figure 4-11.**</span></span> <span data-ttu-id="1c33b-147">Log Analytics コンテナー監視ソリューション</span><span class="sxs-lookup"><span data-stu-id="1c33b-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="1c33b-148">Log Analytics コンテナー監視ソリューションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c33b-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="1c33b-149">1 つの場所ですべてのコンテナー ホストに関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c33b-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="1c33b-150">どのコンテナーが、どのようなイメージを実行して、実行されているし、実行しています。</span><span class="sxs-lookup"><span data-stu-id="1c33b-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="1c33b-151">コンテナー操作の監査証跡を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c33b-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="1c33b-152">表示および Docker ホストへのリモート ログインに関係なく、一元化されたログを検索してトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="1c33b-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="1c33b-153">「うるさい隣人」、可能性がありますし、ホストで余分なリソースを消費するコンテナーを検索します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="1c33b-154">一元的な CPU、メモリ、ストレージ、およびネットワーク使用率およびパフォーマンスについては、コンテナーを表示します。</span><span class="sxs-lookup"><span data-stu-id="1c33b-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1c33b-155">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="1c33b-155">Additional resources</span></span>

- <span data-ttu-id="1c33b-156">**Microsoft Azure での監視の概要**</span><span class="sxs-lookup"><span data-stu-id="1c33b-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="1c33b-157">**Application Insights とは何か?**</span><span class="sxs-lookup"><span data-stu-id="1c33b-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="1c33b-158">**Log Analytics とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="1c33b-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="1c33b-159">**Azure Monitor でのコンテナー監視ソリューション**</span><span class="sxs-lookup"><span data-stu-id="1c33b-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="1c33b-160">**Azure Monitor の概要**</span><span class="sxs-lookup"><span data-stu-id="1c33b-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="1c33b-161">**Operations Management Suite (OMS) とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="1c33b-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="1c33b-162">[前へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[次へ](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="1c33b-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
