---
title: コンテナー化されたアプリケーションのサービスを監視します。
description: 監視コンテナー アーキテクチャの重要な側面について説明します
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 925db543617deb28590cf6631ebbda3ee96836c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975746"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="3d262-103">コンテナー化されたアプリケーションのサービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="3d262-103">Monitor containerized application services</span></span>

<span data-ttu-id="3d262-104">アプリケーションが複数のコンテナーとマイクロ サービスに分割に監視し、アプリケーション全体の動作を分析する方法を実装するが重要です。</span><span class="sxs-lookup"><span data-stu-id="3d262-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="microsoft-application-insights"></a><span data-ttu-id="3d262-105">Microsoft Application Insights</span><span class="sxs-lookup"><span data-stu-id="3d262-105">Microsoft Application Insights</span></span>

<span data-ttu-id="3d262-106">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview)はライブ アプリケーションを監視する拡張可能な分析サービスです。</span><span class="sxs-lookup"><span data-stu-id="3d262-106">[Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="3d262-107">検出してパフォーマンスの問題を診断し、で何が実際に実行、アプリを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="3d262-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="3d262-108">継続的にパフォーマンスを向上させるに役立つインテントと、サービスまたはアプリケーションの使いやすさの開発者に設計されています。</span><span class="sxs-lookup"><span data-stu-id="3d262-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="3d262-109">Application Insights は、さまざまなプラットフォームなど、.NET、Java、Node.js とその他の多くのプラットフォームは、オンプレミスでホストされているのかクラウド内でアプリを web/サービスとスタンドアロンの両方で動作します。</span><span class="sxs-lookup"><span data-stu-id="3d262-109">Application Insights works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="analyzing-docker-apps-in-qa-environments-using-application-insights"></a><span data-ttu-id="3d262-110">Application Insights を使用して、QA 環境での Docker アプリの分析</span><span class="sxs-lookup"><span data-stu-id="3d262-110">Analyzing Docker apps in QA environments using Application Insights</span></span>

<span data-ttu-id="3d262-111">Docker に関連して、ライフ サイクル イベントと Application Insights 上の Docker コンテナーからパフォーマンス カウンターをグラフにできます。</span><span class="sxs-lookup"><span data-stu-id="3d262-111">As it pertains to Docker, you can chart life-cycle events and performance counters from Docker containers on Application Insights.</span></span> <span data-ttu-id="3d262-112">だけを実行する必要があります、 [Application Insights の Docker イメージ](https://hub.docker.com/r/microsoft/applicationinsights/)ように、ホストし、コンテナーは他の Docker イメージの場合と同様のホストのパフォーマンス カウンターを表示します。</span><span class="sxs-lookup"><span data-stu-id="3d262-112">You just need to run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) as a container in your host, and it will display performance counters for the host as well as for the other Docker images.</span></span> <span data-ttu-id="3d262-113">この Application Insights の Docker イメージ (図 6-1) のパフォーマンスとの Docker ホスト (つまり、Linux Vm)、Docker コンテナーを実行しているアプリケーションのアクティビティに関するテレメトリを収集することで、コンテナー化アプリケーションを監視することに役立ちます内にします。</span><span class="sxs-lookup"><span data-stu-id="3d262-113">This Application Insights Docker image (Figure 6-1) helps you to monitor your containerized applications by collecting telemetry about the performance and activity of your Docker host (that is, your Linux VMs), Docker containers and the applications running within them.</span></span>

![例](./media/image1.png)

<span data-ttu-id="3d262-115">**図 6-1**。</span><span class="sxs-lookup"><span data-stu-id="3d262-115">**Figure 6-1**.</span></span> <span data-ttu-id="3d262-116">Application Insights の Docker ホストとコンテナーの監視</span><span class="sxs-lookup"><span data-stu-id="3d262-116">Application Insights monitoring Docker hosts and containers</span></span>

<span data-ttu-id="3d262-117">実行すると、 [Application Insights の Docker イメージ](https://hub.docker.com/r/microsoft/applicationinsights/)次のメリットの Docker ホストで。</span><span class="sxs-lookup"><span data-stu-id="3d262-117">When you run the [Application Insights Docker image](https://hub.docker.com/r/microsoft/applicationinsights/) on your Docker host, you benefit from the following:</span></span>

- <span data-ttu-id="3d262-118">ライフ サイクル ホストで実行されているすべてのコンテナーに関する製品利用統計情報: 開始、停止、および具合です。</span><span class="sxs-lookup"><span data-stu-id="3d262-118">Life-cycle telemetry about all the containers running on the host—start, stop, and so on.</span></span>

- <span data-ttu-id="3d262-119">すべてのコンテナーのパフォーマンス カウンター:CPU、メモリ、ネットワークの使用状況、および詳細。</span><span class="sxs-lookup"><span data-stu-id="3d262-119">Performance counters for all the containers: CPU, memory, network usage, and more.</span></span>

- <span data-ttu-id="3d262-120">インストールされている場合[Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net)コンテナーで実行されているアプリでこれらのアプリのすべてのテレメトリがコンテナーとホスト マシンを識別する追加のプロパティが。</span><span class="sxs-lookup"><span data-stu-id="3d262-120">If you also installed [Application Insights SDK](https://docs.microsoft.com/azure/application-insights/app-insights-asp-net) in the apps running in the containers, all the telemetry of those apps will have additional properties identifying the container and host machine.</span></span> <span data-ttu-id="3d262-121">そのため、たとえば、1 つ以上のホストで実行されているアプリのインスタンスがあれば、簡単にことができますをホストして、アプリのテレメトリをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="3d262-121">So, for example, if you have instances of an app running in more than one host, you'll easily be able to filter your app telemetry by host.</span></span>

### <a name="setting-up-application-insights-to-monitor-docker-applications-and-docker-hosts"></a><span data-ttu-id="3d262-122">アプリケーションの Docker および Docker ホストを監視するための Application Insights の設定</span><span class="sxs-lookup"><span data-stu-id="3d262-122">Setting up Application Insights to monitor Docker applications and Docker hosts</span></span>

<span data-ttu-id="3d262-123">Application Insights リソースを作成するには、次の一覧に記事の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="3d262-123">To create an Application Insights resource, follow the instructions in the articles presented in the list that follows.</span></span> <span data-ttu-id="3d262-124">Azure ポータルを必要なスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d262-124">Azure portal will create the necessary script for you.</span></span>

- <span data-ttu-id="3d262-125">**Application Insights で Docker アプリケーションを監視します。** \\</span><span class="sxs-lookup"><span data-stu-id="3d262-125">**Monitor Docker applications in Application Insights:** \\</span></span>
  <https://docs.microsoft.com/azure/application-insights/app-insights-docker>

- <span data-ttu-id="3d262-126">**Docker Hub や GitHub にある application Insights の Docker イメージ:** \\</span><span class="sxs-lookup"><span data-stu-id="3d262-126">**Application Insights Docker image at Docker Hub and GitHub:** \\</span></span>
  <span data-ttu-id="3d262-127"><https://hub.docker.com/r/microsoft/applicationinsights/> および \\</span><span class="sxs-lookup"><span data-stu-id="3d262-127"><https://hub.docker.com/r/microsoft/applicationinsights/> and \\</span></span>
  <https://github.com/Microsoft/ApplicationInsights-Docker>

- <span data-ttu-id="3d262-128">**ASP.NET web アプリおよび ASP.NET Core 用の Application Insights を設定します。** \\</span><span class="sxs-lookup"><span data-stu-id="3d262-128">**Set up Application Insights for ASP.NET web apps and ASP.NET Core:** \\</span></span>
  <https://docs.microsoft.com/azure/application-insights/app-insights-asp-net>

- <span data-ttu-id="3d262-129">**Web ページ用の application Insights:**</span><span class="sxs-lookup"><span data-stu-id="3d262-129">**Application Insights for web pages:**</span></span>  
  <https://docs.microsoft.com/azure/application-insights/app-insights-javascript>

## <a name="security-backup-and-monitoring-services"></a><span data-ttu-id="3d262-130">セキュリティ、バックアップ、およびサービスの監視</span><span class="sxs-lookup"><span data-stu-id="3d262-130">Security, backup, and monitoring services</span></span>

<span data-ttu-id="3d262-131">大量の処理、アプリケーションおよびインフラストラクチャがビジネス上のニーズをサポートするために一流の条件を確認する必要のある詳細情報を多くのサポートのような作業があるし、する方法を作成する必要があります、状況が、マイクロ サービス領域で複雑になったアクションを実行する必要があるときに概要と詳細ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="3d262-131">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="3d262-132">Azure では、管理し、クラウドとオンプレミスの両方のリソースの 4 つの重要な側面の統一されたビューを提供するツールがあります。</span><span class="sxs-lookup"><span data-stu-id="3d262-132">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="3d262-133">**セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="3d262-133">**Security**.</span></span> <span data-ttu-id="3d262-134">[Azure Security Center](https://azure.microsoft.com/services/security-center/)します。</span><span class="sxs-lookup"><span data-stu-id="3d262-134">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="3d262-135">完全な可視化と仮想マシン、アプリ、ワークロードのセキュリティ制御を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d262-135">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="3d262-136">セキュリティ ポリシーの管理を一元化し、既存のプロセスやツールを統合します。</span><span class="sxs-lookup"><span data-stu-id="3d262-136">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="3d262-137">高度な分析の真の脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="3d262-137">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="3d262-138">**バックアップ**します。</span><span class="sxs-lookup"><span data-stu-id="3d262-138">**Backup**.</span></span> <span data-ttu-id="3d262-139">[Azure Backup](https://azure.microsoft.com/services/backup/)します。</span><span class="sxs-lookup"><span data-stu-id="3d262-139">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="3d262-140">コストのかかるビジネス中断を避けるため、コンプライアンス目標を満たすおよびランサムウェアやヒューマン エラーからデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="3d262-140">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="3d262-141">転送中に暗号化、バックアップ データを保持します。</span><span class="sxs-lookup"><span data-stu-id="3d262-141">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="3d262-142">承認されていない使用を防ぐための多要素認証に基づいてアクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="3d262-142">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="3d262-143">**監視**します。</span><span class="sxs-lookup"><span data-stu-id="3d262-143">**Monitoring**.</span></span> <span data-ttu-id="3d262-144">[Azure monitoring](https://azure.microsoft.com/solutions/monitoring/)、 [Log Analytics](https://azure.microsoft.com/services/log-analytics/)、および[Application Insights](https://azure.microsoft.com/services/application-insights/)します。</span><span class="sxs-lookup"><span data-stu-id="3d262-144">With [Azure monitoring](https://azure.microsoft.com/solutions/monitoring/), [Log Analytics](https://azure.microsoft.com/services/log-analytics/), and [Application Insights](https://azure.microsoft.com/services/application-insights/).</span></span>
  - <span data-ttu-id="3d262-145">正常性と、Azure のワークロード、アプリケーション、およびインフラストラクチャのパフォーマンスには、完全な可視性を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d262-145">Get full visibility into the health and performance of your Azure workloads, apps, and infrastructure.</span></span>
  - <span data-ttu-id="3d262-146">任意のソースからデータを収集し、仮想マシン、コンテナー、およびアプリケーションに豊富な分析情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="3d262-146">Collect data from any source and get rich insights into your virtual machines, containers, and applications.</span></span>
  - <span data-ttu-id="3d262-147">対話型クエリとフルテキスト検索を使用して必要な情報を検索します。</span><span class="sxs-lookup"><span data-stu-id="3d262-147">Find the information you need using interactive queries and full-text search.</span></span> 
  - <span data-ttu-id="3d262-148">根本原因の分析と機械学習アルゴリズムなどの高度な分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d262-148">Perform root-cause analysis with advanced analytics, including machine learning algorithms.</span></span>

- <span data-ttu-id="3d262-149">**オンプレミス リソースに**します。</span><span class="sxs-lookup"><span data-stu-id="3d262-149">**On-premises resources**.</span></span> <span data-ttu-id="3d262-150">[真に一貫性のあるハイブリッド クラウド](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)します。</span><span class="sxs-lookup"><span data-stu-id="3d262-150">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3d262-151">[前へ](manage-production-docker-environments.md)
>[次へ](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="3d262-151">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
