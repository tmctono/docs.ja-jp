---
title: クラウドの CI/CD パイプラインや DevOps ツールでアプリのライフ サイクルを最新化する
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |クラウドで CI/CD パイプラインと DevOps ツールを使用してアプリのライフサイクルを最新化する
ms.date: 04/30/2018
ms.openlocfilehash: fb4bfab4a891e9c8a73867f18cb8249775f9b7b9
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578165"
---
# <a name="modernize-your-apps-lifecycle-with-cicd-pipelines-and-devops-tools-in-the-cloud"></a><span data-ttu-id="ffc43-103">クラウドの CI/CD パイプラインや DevOps ツールでアプリのライフ サイクルを最新化する</span><span class="sxs-lookup"><span data-stu-id="ffc43-103">Modernize your app's lifecycle with CI/CD pipelines and DevOps tools in the cloud</span></span>

<span data-ttu-id="ffc43-104">今日の企業は、市場で競争力を高めるために、迅速にイノベーションを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ffc43-104">Today’s businesses need to innovate at a rapid pace to be competitive in the marketplace.</span></span> <span data-ttu-id="ffc43-105">高品質で最新のアプリケーションを提供するには、このような革新的なイノベーションサイクルを実装するうえで不可欠な DevOps ツールとプロセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ffc43-105">Delivering high-quality, modern applications requires DevOps tools and processes that are critical to implement this constant cycle of innovation.</span></span> <span data-ttu-id="ffc43-106">適切な DevOps ツールを使用すると、開発者は継続的なデプロイを効率化し、革新的なアプリケーションをより迅速にユーザーに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ffc43-106">With the right DevOps tools, developers can streamline continuous deployment and get innovative applications into the hands of users more quickly.</span></span>

<span data-ttu-id="ffc43-107">継続的な統合とデプロイの方法は適切に確立されていますが、コンテナーの導入には、特に複数コンテナーアプリケーションを使用している場合に、新しい考慮事項が導入されています。</span><span class="sxs-lookup"><span data-stu-id="ffc43-107">Although continuous integration and deployment practices are well established, the introduction of containers introduces new considerations, particularly when you are working with multi-container applications.</span></span>

<span data-ttu-id="ffc43-108">Azure DevOps Services は、公式の Azure DevOps Services 展開タスクを使用して、さまざまな環境への複数コンテナーアプリケーションの継続的インテグレーションと継続的なデプロイをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ffc43-108">Azure DevOps Services supports continuous integration and deployment of multi-container applications to a variety of environments through the official Azure DevOps Services deployment tasks:</span></span>

- [<span data-ttu-id="ffc43-109">Azure Web App for Containers へのデプロイ</span><span class="sxs-lookup"><span data-stu-id="ffc43-109">Deploy to an Azure Web App for Containers</span></span>](https://docs.microsoft.com/azure/devops/pipelines/apps/cd/deploy-docker-webapp?view=azure-devops)

- [<span data-ttu-id="ffc43-110">Azure Container Service へのデプロイ– Kubernetes</span><span class="sxs-lookup"><span data-stu-id="ffc43-110">Deploy to Azure Container Service – Kubernetes</span></span>](https://docs.microsoft.com/azure/devops/build-release/apps/cd/azure/deploy-container-kubernetes)

<span data-ttu-id="ffc43-111">ただし、Azure DevOps Services スクリプトベースのタスクを使用して、 [Docker の群れ](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/)や DC/OS にデプロイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ffc43-111">But you also can deploy to [Docker Swarm](https://blogs.msdn.microsoft.com/jcorioland/2016/11/29/full-ci-cd-pipeline-to-deploy-multi-containers-application-on-azure-container-service-docker-swarm-using-visual-studio-team-services/) or DC/OS by using Azure DevOps Services script-based tasks.</span></span>

<span data-ttu-id="ffc43-112">デプロイの機敏性を維持するために、これらのツールは、開発および CI/CD ソリューションを選択して、コンテナーのワークロードに対して優れた開発からテスト環境へのデプロイエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ffc43-112">To continue facilitating deployment agility, these tools provide excellent dev-to-test-to-production deployment experiences for container workloads, with a choice of development and CI/CD solutions.</span></span>

<span data-ttu-id="ffc43-113">図4-12 は、Azure Container Service で Kubernetes クラスターにデプロイする継続的なデプロイパイプラインを示しています。</span><span class="sxs-lookup"><span data-stu-id="ffc43-113">Figure 4-12 shows a continuous deployment pipeline that deploys to a Kubernetes cluster in Azure Container Service.</span></span>

![Kubernetes クラスターにデプロイする継続的デプロイパイプラインの Azure DevOps Services](./media/image12.png)

> <span data-ttu-id="ffc43-115">**図 4-12.**</span><span class="sxs-lookup"><span data-stu-id="ffc43-115">**Figure 4-12.**</span></span> <span data-ttu-id="ffc43-116">Kubernetes クラスターにデプロイする継続的デプロイパイプラインの Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="ffc43-116">Azure DevOps Services continuous deployment pipeline, deploying to a Kubernetes cluster</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ffc43-117">[前へ](modernize-your-apps-with-monitoring-and-telemetry.md)
>[次へ](migrate-to-hybrid-cloud-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="ffc43-117">[Previous](modernize-your-apps-with-monitoring-and-telemetry.md)
[Next](migrate-to-hybrid-cloud-scenarios.md)</span></span>
