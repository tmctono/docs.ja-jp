---
title: クラウドの CI/CD パイプラインや DevOps ツールでアプリのライフ サイクルを最新化する
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |CI/CD パイプラインや DevOps ツール、クラウドでアプリのライフ サイクルを最新化します。
ms.date: 04/30/2018
ms.openlocfilehash: cc991bba5df3a9cd972d9a172c1a8f1035ce8c58
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758641"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="653b3-103">クラウドの CI/CD パイプラインや DevOps ツールでアプリのライフ サイクルを最新化する</span><span class="sxs-lookup"><span data-stu-id="653b3-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="653b3-104">今日の企業では、市場で競争力のある迅速なペースでイノベーションを実現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="653b3-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="653b3-105">高品質を提供するには、最新のアプリケーションには、DevOps ツールと技術革新のこの定数のサイクルを実装するために不可欠なプロセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="653b3-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="653b3-106">適切なの DevOps ツールでは、開発者は継続的なデプロイを合理化し、ユーザーの手に革新的なアプリケーションを迅速に取得します。</span><span class="sxs-lookup"><span data-stu-id="653b3-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="653b3-107">継続的インテグレーションとデプロイのプラクティスは準備されていますが、マルチ コンテナー アプリケーションを使用する場合に特にコンテナーの概要、新しい考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="653b3-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="653b3-108">Azure DevOps サービスには、継続的インテグレーションとさまざまな公式の Azure DevOps サービス展開作業を環境に複数コンテナー アプリケーションの展開がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="653b3-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- <span data-ttu-id="653b3-109">[スタンドアロンの Docker ホスト VM にデプロイ](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm)(Linux または Windows Server 2016 以降)</span><span class="sxs-lookup"><span data-stu-id="653b3-109">[Deploy to standalone Docker Host VM](https://docs.microsoft.com/azure/devops/build-release/apps/cd/deploy-docker-windowsvm) (Linux or Windows Server 2016 or later)</span></span>

- [<span data-ttu-id="653b3-110">Azure Container Service と Kubernetes にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="653b3-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="653b3-111">展開できますが、 [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)または DC/OS Azure DevOps サービス スクリプト ベースのタスクを使用しています。</span><span class="sxs-lookup"><span data-stu-id="653b3-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="653b3-112">デプロイの機敏性を促進することを続行するには、は、これらのツールは、コンテナーのワークロードでは、開発と CI/CD の解決策の選択肢を備えた優れた開発-テスト-運用デプロイのエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="653b3-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="653b3-113">図 4-12 には、Azure Container Service で Kubernetes クラスターにデプロイする継続的配置パイプラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="653b3-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Azure DevOps サービスの継続的なデプロイ パイプライン、Kubernetes クラスターへのデプロイ](./media/image12.png)

> <span data-ttu-id="653b3-115">**図 4-12。**</span><span class="sxs-lookup"><span data-stu-id="653b3-115">**Figure 4-12.**</span></span> <span data-ttu-id="653b3-116">Azure DevOps サービスの継続的なデプロイ パイプライン、Kubernetes クラスターへのデプロイ</span><span class="sxs-lookup"><span data-stu-id="653b3-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="653b3-117">[前へ](modernize-your-apps-with-monitoring-and-telemetry.md)
>[次へ](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="653b3-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
