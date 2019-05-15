---
title: Docker アプリケーションの外側のループ DevOps ワークフローの手順
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
ms.date: 02/15/2019
ms.openlocfilehash: 9fdc5acfd375e4f2266859f061ef1c854286b914
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644983"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a><span data-ttu-id="ae51a-103">コンテナーで.NET Core 2.0 アプリケーション用の Azure DevOps Services で CI/CD パイプラインを作成し、Kubernetes クラスターにデプロイする</span><span class="sxs-lookup"><span data-stu-id="ae51a-103">Creating CI/CD pipelines in Azure DevOps Services for a .NET Core 2.0 application on Containers and deploying to a Kubernetes cluster</span></span>

<span data-ttu-id="ae51a-104">図 5-12 でコードの管理、コードのコンパイルをカバーするエンド ツー エンド DevOps シナリオを参照できます、Docker イメージを構築、Docker レジストリと最後に Azure での Kubernetes クラスターに展開する Docker イメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="ae51a-104">In Figure 5-12 you can see the end-to-end DevOps scenario covering the code management, code compilation, Docker images build, Docker images push to a Docker registry and finally the deployment to a Kubernetes cluster in Azure.</span></span>

![ワークフロー:開発用コンピューターで開始します。](media/docker-workflow-ci-cd-aks.png)

<span data-ttu-id="ae51a-107">**図 5-12**</span><span class="sxs-lookup"><span data-stu-id="ae51a-107">**Figure 5-12**.</span></span> <span data-ttu-id="ae51a-108">Docker イメージを作成して、Azure で Kubernetes クラスターへのデプロイの CI/CD シナリオ</span><span class="sxs-lookup"><span data-stu-id="ae51a-108">CI/CD scenario creating Docker images and deploying to a Kubernetes cluster in Azure</span></span>

<span data-ttu-id="ae51a-109">(Docker Hub や Azure Container Registry) などの Docker レジストリを使用して 2 つのパイプライン、ビルド/CI、およびリリース/CD が接続されていることを強調表示に重要です。</span><span class="sxs-lookup"><span data-stu-id="ae51a-109">It is important to highlight that the two pipelines, build/CI, and release/CD, are connected through the Docker Registry (such as Docker Hub or Azure Container Registry).</span></span> <span data-ttu-id="ae51a-110">Docker レジストリでは、Docker を使用しない従来の CI/CD プロセスと比較する主な相違点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ae51a-110">The Docker registry is one of the main differences compared to a traditional CI/CD process without Docker.</span></span>

<span data-ttu-id="ae51a-111">図 5-13 に示すように、最初のフェーズは、ビルド/CI パイプラインにします。</span><span class="sxs-lookup"><span data-stu-id="ae51a-111">As shown in Figure 5-13, the first phase is the build/CI pipeline.</span></span> <span data-ttu-id="ae51a-112">Azure DevOps サービスでは、コードをコンパイル、Docker イメージを作成およびそれらを Docker Hub や Azure Container Registry のような Docker レジストリにプッシュされるビルド/CI パイプラインを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae51a-112">In Azure DevOps Services you can create build/CI pipelines that will compile the code, create the Docker images, and push them to a Docker Registry like Docker Hub or Azure Container Registry.</span></span>

![Azure DevOps、ビルド プロセスのタスク定義のブラウザー ビュー。](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

<span data-ttu-id="ae51a-114">**図 5-13**</span><span class="sxs-lookup"><span data-stu-id="ae51a-114">**Figure 5-13**.</span></span> <span data-ttu-id="ae51a-115">Azure DevOps Docker イメージをビルドし、Docker レジストリにイメージをプッシュのビルド/CI パイプライン</span><span class="sxs-lookup"><span data-stu-id="ae51a-115">Build/CI pipeline in Azure DevOps building Docker images and pushing images to a Docker registry</span></span>

<span data-ttu-id="ae51a-116">2 番目のフェーズでは、展開/リリース パイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae51a-116">The second phase is to create a deployment/release pipeline.</span></span> <span data-ttu-id="ae51a-117">Azure DevOps サービスで、図 5-14 に示すように、Azure DevOps サービス、Kubernetes タスクを使用して Kubernetes クラスターを対象とするデプロイ パイプラインを簡単に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ae51a-117">In Azure DevOps Services, you can easily create a deployment pipeline targeting a Kubernetes cluster by using the Kubernetes tasks for Azure DevOps Services, as shown in Figure 5-14.</span></span>

![Azure DevOps, のブラウザー ビューは、タスクの定義を Kubernetes にデプロイします。](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

<span data-ttu-id="ae51a-119">**図 5-14**</span><span class="sxs-lookup"><span data-stu-id="ae51a-119">**Figure 5-14**.</span></span> <span data-ttu-id="ae51a-120">Azure DevOps サービスが Kubernetes クラスターに展開するリリース/CD パイプライン</span><span class="sxs-lookup"><span data-stu-id="ae51a-120">Release/CD pipeline in Azure DevOps Services deploying to a Kubernetes cluster</span></span>

> [!チュートリアル]<span data-ttu-id="ae51a-121"> eShopModernized を Kubernetes にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="ae51a-121"> Deploying eShopModernized to Kubernetes:</span></span>
>
> <span data-ttu-id="ae51a-122">Azure DevOps CI/CD パイプラインの詳細なチュートリアルについては、Kubernetes に展開するこの投稿を表示します \。</span><span class="sxs-lookup"><span data-stu-id="ae51a-122">For a detailed walkthrough of Azure DevOps CI/CD pipelines deploying to Kubernetes, see this post: \\</span></span>
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
><span data-ttu-id="ae51a-123">[前へ](docker-application-outer-loop-devops-workflow.md)
>[次へ](../run-manage-monitor-docker-environments/index.md)</span><span class="sxs-lookup"><span data-stu-id="ae51a-123">[Previous](docker-application-outer-loop-devops-workflow.md)
[Next](../run-manage-monitor-docker-environments/index.md)</span></span>
