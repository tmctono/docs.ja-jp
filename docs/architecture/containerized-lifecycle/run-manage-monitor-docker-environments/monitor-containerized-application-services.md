---
title: コンテナー化アプリケーションのサービスを監視する
description: コンテナー アーキテクチャのモニターに関する重要な側面をいくつか説明します
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68673459"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="a85af-103">コンテナー化アプリケーションのサービスを監視する</span><span class="sxs-lookup"><span data-stu-id="a85af-103">Monitor containerized application services</span></span>

<span data-ttu-id="a85af-104">アプリケーションを複数のコンテナーとマイクロサービスに分割し、アプリケーション全体の動作を監視および分析する方法を持つことが重要です。</span><span class="sxs-lookup"><span data-stu-id="a85af-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="a85af-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="a85af-105">Azure Monitor</span></span>

<span data-ttu-id="a85af-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) は、ライブ アプリケーションを監視する拡張可能な分析サービスです。</span><span class="sxs-lookup"><span data-stu-id="a85af-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="a85af-107">パフォーマンスの問題の検出と診断や、ユーザーがアプリを使用して実際に実行する操作の理解に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a85af-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="a85af-108">開発者向けに設計されており、サービスやアプリケーションのパフォーマンスと使いやすさを継続的に向上させることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a85af-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="a85af-109">Azure Monitor は、オンプレミスまたはクラウドでホストされている .NET、Java、Node.js などのさまざまなプラットフォーム上で、Web/サービスとスタンドアロン アプリの両方と連携します。</span><span class="sxs-lookup"><span data-stu-id="a85af-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a85af-110">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="a85af-110">Additional resources</span></span>

- <span data-ttu-id="a85af-111">**Azure Monitor の概要** </span><span class="sxs-lookup"><span data-stu-id="a85af-111">**Overview of Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="a85af-112">**Application Insights とは何か?**</span><span class="sxs-lookup"><span data-stu-id="a85af-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="a85af-113">**Azure Monitor のメトリック**</span><span class="sxs-lookup"><span data-stu-id="a85af-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="a85af-114">**Azure Monitor のコンテナー監視ソリューション** </span><span class="sxs-lookup"><span data-stu-id="a85af-114">**Container Monitoring solution in Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="a85af-115">セキュリティとバックアップ サービス</span><span class="sxs-lookup"><span data-stu-id="a85af-115">Security and backup services</span></span>

<span data-ttu-id="a85af-116">アプリケーションとインフラストラクチャが確実にビジネス ニーズをサポートできる最高の状態になるようにするには、多くのサポートの雑事と対処する必要がある細かいことが数多くあります。また、マイクロサービス分野では状況がより複雑になるので、行動を起こす必要があるときには、包括的なビューと詳細なビューを両方持つ方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="a85af-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="a85af-117">Azure には、クラウドおよびオンプレミス リソースの両方の 4 つの重要な側面を管理し、統一されたビューを提供するためのツールがあります。</span><span class="sxs-lookup"><span data-stu-id="a85af-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="a85af-118">**セキュリティ**。</span><span class="sxs-lookup"><span data-stu-id="a85af-118">**Security**.</span></span> <span data-ttu-id="a85af-119">[Azure Security Center](https://azure.microsoft.com/services/security-center/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a85af-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="a85af-120">仮想マシン、アプリ、ワークロードのセキュリティを完全に可視化し、制御します。</span><span class="sxs-lookup"><span data-stu-id="a85af-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="a85af-121">セキュリティ ポリシーの管理を一元化し、既存のプロセスとツールを統合します。</span><span class="sxs-lookup"><span data-stu-id="a85af-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="a85af-122">高度な分析で実際の脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="a85af-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="a85af-123">**バックアップ**。</span><span class="sxs-lookup"><span data-stu-id="a85af-123">**Backup**.</span></span> <span data-ttu-id="a85af-124">[Azure Backup](https://azure.microsoft.com/services/backup/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a85af-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="a85af-125">コストのかかるビジネスの中断を回避し、コンプライアンスの目標を達成し、ランサムウェアやヒューマン エラーからデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="a85af-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="a85af-126">バックアップ データを転送中および保存中に暗号化します。</span><span class="sxs-lookup"><span data-stu-id="a85af-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="a85af-127">不正使用を防ぐために、多要素認証に基づくアクセスを確保します。</span><span class="sxs-lookup"><span data-stu-id="a85af-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="a85af-128">**オンプレミスのリソース**。</span><span class="sxs-lookup"><span data-stu-id="a85af-128">**On-premises resources**.</span></span> <span data-ttu-id="a85af-129">[本当に一貫性が高いハイブリッド クラウド](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a85af-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a85af-130">[前へ](manage-production-docker-environments.md)
>[次へ](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="a85af-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
