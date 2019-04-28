---
title: コンテナー化アプリケーションのサービスを監視する
description: 監視コンテナー アーキテクチャの重要な側面について説明します
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4553a35c8db6cfc46187525ef2ffc65cb3ba07c9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922747"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="d2b9d-103">コンテナー化アプリケーションのサービスを監視する</span><span class="sxs-lookup"><span data-stu-id="d2b9d-103">Monitor containerized application services</span></span>

<span data-ttu-id="d2b9d-104">アプリケーションが複数のコンテナーとマイクロ サービスに分割に監視し、アプリケーション全体の動作を分析する方法を実装するが重要です。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="d2b9d-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="d2b9d-105">Azure Monitor</span></span>

<span data-ttu-id="d2b9d-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/)はライブ アプリケーションを監視する拡張可能な分析サービスです。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="d2b9d-107">検出してパフォーマンスの問題を診断し、で何が実際に実行、アプリを理解することができます。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="d2b9d-108">継続的にパフォーマンスを向上させるに役立つインテントと、サービスまたはアプリケーションの使いやすさの開発者に設計されています。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="d2b9d-109">Azure Monitor は、さまざまなプラットフォームなど、.NET、Java、Node.js とその他の多くのプラットフォームは、オンプレミスでホストされているのかクラウド内でアプリを web/サービスとスタンドアロンの両方で動作します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="d2b9d-110">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="d2b9d-110">Additional resources</span></span>

- <span data-ttu-id="d2b9d-111">**Azure Monitor の概要** \\</span><span class="sxs-lookup"><span data-stu-id="d2b9d-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="d2b9d-112">**Application Insights とは何か?**</span><span class="sxs-lookup"><span data-stu-id="d2b9d-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="d2b9d-113">**Azure Monitor のメトリックとは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="d2b9d-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="d2b9d-114">**Azure Monitor でのコンテナー監視ソリューション** \\</span><span class="sxs-lookup"><span data-stu-id="d2b9d-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="d2b9d-115">セキュリティとバックアップ サービス</span><span class="sxs-lookup"><span data-stu-id="d2b9d-115">Security and backup services</span></span>

<span data-ttu-id="d2b9d-116">大量の処理、アプリケーションおよびインフラストラクチャがビジネス上のニーズをサポートするために一流の条件を確認する必要のある詳細情報を多くのサポートのような作業があるし、する方法を作成する必要があります、状況が、マイクロ サービス領域で複雑になったアクションを実行する必要があるときに概要と詳細ビューがあります。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="d2b9d-117">Azure では、管理し、クラウドとオンプレミスの両方のリソースの 4 つの重要な側面の統一されたビューを提供するツールがあります。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="d2b9d-118">**セキュリティ**します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-118">**Security**.</span></span> <span data-ttu-id="d2b9d-119">[Azure Security Center](https://azure.microsoft.com/services/security-center/)します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="d2b9d-120">完全な可視化と仮想マシン、アプリ、ワークロードのセキュリティ制御を取得します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="d2b9d-121">セキュリティ ポリシーの管理を一元化し、既存のプロセスやツールを統合します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="d2b9d-122">高度な分析の真の脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="d2b9d-123">**バックアップ**します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-123">**Backup**.</span></span> <span data-ttu-id="d2b9d-124">[Azure Backup](https://azure.microsoft.com/services/backup/)します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="d2b9d-125">コストのかかるビジネス中断を避けるため、コンプライアンス目標を満たすおよびランサムウェアやヒューマン エラーからデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="d2b9d-126">転送中に暗号化、バックアップ データを保持します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="d2b9d-127">承認されていない使用を防ぐための多要素認証に基づいてアクセスを確認します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="d2b9d-128">**オンプレミス リソースに**します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-128">**On-premises resources**.</span></span> <span data-ttu-id="d2b9d-129">[真に一貫性のあるハイブリッド クラウド](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)します。</span><span class="sxs-lookup"><span data-stu-id="d2b9d-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d2b9d-130">[前へ](manage-production-docker-environments.md)
>[次へ](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="d2b9d-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
