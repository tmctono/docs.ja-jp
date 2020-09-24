---
title: その他のコンテナー配置オプション
description: Azure を使用したその他のコンテナーデプロイオプション
ms.date: 05/13/2020
ms.openlocfilehash: 2eac822b74af636e0ab0ed24b58eb7139526f4a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163623"
---
# <a name="other-container-deployment-options"></a><span data-ttu-id="9bc02-103">その他のコンテナー配置オプション</span><span class="sxs-lookup"><span data-stu-id="9bc02-103">Other container deployment options</span></span>

<span data-ttu-id="9bc02-104">Azure Kubernetes Service (AKS) とは別に、コンテナーと Azure Container Instances の Azure App Service にコンテナーをデプロイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-104">Aside from Azure Kubernetes Service (AKS), you can also deploy containers to Azure App Service for Containers and Azure Container Instances.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="9bc02-105">コンテナーの App Service に展開するのはどのような場合に適していますか。</span><span class="sxs-lookup"><span data-stu-id="9bc02-105">When does it make sense to deploy to App Service for Containers?</span></span>

<span data-ttu-id="9bc02-106">オーケストレーションを必要としない単純な実稼働アプリケーションは、コンテナーの Azure App Service に適しています。</span><span class="sxs-lookup"><span data-stu-id="9bc02-106">Simple production applications that don't require orchestration are well suited to Azure App Service for Containers.</span></span>

## <a name="how-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="9bc02-107">コンテナーの App Service にデプロイする方法</span><span class="sxs-lookup"><span data-stu-id="9bc02-107">How to deploy to App Service for Containers</span></span>

<span data-ttu-id="9bc02-108">[コンテナーの Azure App Service](https://azure.microsoft.com/services/app-service/containers/)にデプロイするには、AZURE CONTAINER REGISTRY (ACR) インスタンスと、それにアクセスするための資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="9bc02-108">To deploy to [Azure App Service for Containers](https://azure.microsoft.com/services/app-service/containers/), you'll need an Azure Container Registry (ACR) instance and credentials to access it.</span></span> <span data-ttu-id="9bc02-109">コンテナーイメージを ACR リポジトリにプッシュして、Azure App Service に取り込むことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="9bc02-109">Push your container image to the ACR repository so it can pulled into your Azure App Service.</span></span> <span data-ttu-id="9bc02-110">完了すると、アプリを継続的にデプロイするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-110">Once complete, you can configure the app for Continuous Deployment.</span></span> <span data-ttu-id="9bc02-111">これにより、ACR でイメージが変更されるたびに更新が自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-111">Doing so will automatically deploy updates whenever the image changes in ACR.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a><span data-ttu-id="9bc02-112">Azure Container Instances に展開するにはどのような意味がありますか。</span><span class="sxs-lookup"><span data-stu-id="9bc02-112">When does it make sense to deploy to Azure Container Instances?</span></span>

<span data-ttu-id="9bc02-113">[Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) を使用すると、仮想マシンまたはクラスターを設定しなくても、管理されたサーバーレスクラウド環境で Docker コンテナーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-113">[Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) enables you to run Docker containers in a managed, serverless cloud environment, without having to set up virtual machines or clusters.</span></span> <span data-ttu-id="9bc02-114">分離されたコンテナーで実行できる短時間のワークロードに適したソリューションです。</span><span class="sxs-lookup"><span data-stu-id="9bc02-114">It's a great solution for short-running workloads that can run in an isolated container.</span></span> <span data-ttu-id="9bc02-115">単純なサービス、テストシナリオ、タスクオートメーション、およびビルドジョブについては、ACI を検討してください。</span><span class="sxs-lookup"><span data-stu-id="9bc02-115">Consider ACI for simple services, testing scenarios, task automation, and build jobs.</span></span> <span data-ttu-id="9bc02-116">ACI は、コンテナーインスタンスをスピンアップし、タスクを実行してから、スピンダウンします。</span><span class="sxs-lookup"><span data-stu-id="9bc02-116">ACI spins-up a container instance, performs the task, and then spins it down.</span></span>

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a><span data-ttu-id="9bc02-117">Azure Container Instances にアプリを展開する方法</span><span class="sxs-lookup"><span data-stu-id="9bc02-117">How to deploy an app to Azure Container Instances</span></span>

<span data-ttu-id="9bc02-118">[Azure Container Instances (ACI)](/azure/container-instances/)にデプロイするには、AZURE CONTAINER REGISTRY (ACR) と、それにアクセスするための資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="9bc02-118">To deploy to [Azure Container Instances (ACI)](/azure/container-instances/), you need an Azure Container Registry (ACR) and credentials for accessing it.</span></span> <span data-ttu-id="9bc02-119">コンテナーイメージをリポジトリにプッシュすると、ACI にプルできるようになります。</span><span class="sxs-lookup"><span data-stu-id="9bc02-119">Once you push your container image to the repository, it's available to pull into ACI.</span></span> <span data-ttu-id="9bc02-120">Azure portal またはコマンドラインインターフェイスを使用して ACI を操作できます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-120">You can work with ACI using the Azure portal or command-line interface.</span></span> <span data-ttu-id="9bc02-121">ACR は、ACI との緊密な統合を提供します。</span><span class="sxs-lookup"><span data-stu-id="9bc02-121">ACR provides tight integration with ACI.</span></span> <span data-ttu-id="9bc02-122">図3-14 は、個々のコンテナーイメージを ACR にプッシュする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9bc02-122">Figure 3-14 shows how to push an individual container image to ACR.</span></span>

![実行インスタンスの Azure Container Registry](./media/acr-runinstance-contextmenu.png)

<span data-ttu-id="9bc02-124">**図 3-14**.</span><span class="sxs-lookup"><span data-stu-id="9bc02-124">**Figure 3-14**.</span></span> <span data-ttu-id="9bc02-125">実行インスタンスの Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="9bc02-125">Azure Container Registry Run Instance</span></span>

<span data-ttu-id="9bc02-126">ACI にインスタンスを作成することは、迅速に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-126">Creating an instance in ACI can be done quickly.</span></span> <span data-ttu-id="9bc02-127">イメージレジストリ、Azure リソースグループの情報、割り当てるメモリの量、およびリッスンするポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="9bc02-127">Specify the image registry, Azure resource group information, the amount of memory to allocate, and the port on which to listen.</span></span> <span data-ttu-id="9bc02-128">この [クイックスタートでは、Azure portal を使用して、コンテナーインスタンスを ACI にデプロイする方法を示し](/azure/container-instances/container-instances-quickstart-portal)ます。</span><span class="sxs-lookup"><span data-stu-id="9bc02-128">This [quickstart shows how to deploy a container instance to ACI using the Azure portal](/azure/container-instances/container-instances-quickstart-portal).</span></span>

<span data-ttu-id="9bc02-129">デプロイが完了したら、新しくデプロイされたコンテナーの IP アドレスを見つけて、指定したポートを介して通信します。</span><span class="sxs-lookup"><span data-stu-id="9bc02-129">Once the deployment completes, find the newly deployed container's IP address and communicate with it over the port you specified.</span></span>

<span data-ttu-id="9bc02-130">Azure Container Instances は、Azure でシンプルなコンテナーワークロードを実行する最速の方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="9bc02-130">Azure Container Instances offers the fastest way to run simple container workloads in Azure.</span></span> <span data-ttu-id="9bc02-131">App service、orchestrator、または仮想マシンを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9bc02-131">You don't need to configure an app service, orchestrator, or virtual machine.</span></span> <span data-ttu-id="9bc02-132">完全なコンテナーオーケストレーション、サービス検出、自動スケール、または調整アップグレードが必要なシナリオでは、Azure Kubernetes Service (AKS) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9bc02-132">For scenarios where you require full container orchestration, service discovery, automatic scaling, or coordinated upgrades, we recommend Azure Kubernetes Service (AKS).</span></span>

## <a name="references"></a><span data-ttu-id="9bc02-133">References</span><span class="sxs-lookup"><span data-stu-id="9bc02-133">References</span></span>

- [<span data-ttu-id="9bc02-134">Kubernetes とは</span><span class="sxs-lookup"><span data-stu-id="9bc02-134">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="9bc02-135">Minikube を使用した Kubernetes のインストール</span><span class="sxs-lookup"><span data-stu-id="9bc02-135">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="9bc02-136">MiniKube vs Docker デスクトップ</span><span class="sxs-lookup"><span data-stu-id="9bc02-136">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="9bc02-137">Visual Studio Tools for Docker</span><span class="sxs-lookup"><span data-stu-id="9bc02-137">Visual Studio Tools for Docker</span></span>](/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)
- [<span data-ttu-id="9bc02-138">サーバーレスコールドスタートについて</span><span class="sxs-lookup"><span data-stu-id="9bc02-138">Understanding serverless cold start</span></span>](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [<span data-ttu-id="9bc02-139">事前に準備した med-v Azure Functions インスタンス</span><span class="sxs-lookup"><span data-stu-id="9bc02-139">Pre-warmed Azure Functions instances</span></span>](/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [<span data-ttu-id="9bc02-140">カスタム イメージを使用して Linux で関数を作成する</span><span class="sxs-lookup"><span data-stu-id="9bc02-140">Create a function on Linux using a custom image</span></span>](/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="9bc02-141">Docker コンテナーで Azure Functions を実行する</span><span class="sxs-lookup"><span data-stu-id="9bc02-141">Run Azure Functions in a Docker Container</span></span>](https://markheath.net/post/azure-functions-docker)
- [<span data-ttu-id="9bc02-142">カスタム イメージを使用して Linux で関数を作成する</span><span class="sxs-lookup"><span data-stu-id="9bc02-142">Create a function on Linux using a custom image</span></span>](/azure/azure-functions/functions-create-function-linux-custom-image)
- [<span data-ttu-id="9bc02-143">Kubernetes イベントドリブン自動スケールを使用した Azure Functions</span><span class="sxs-lookup"><span data-stu-id="9bc02-143">Azure Functions with Kubernetes Event Driven Autoscaling</span></span>](/azure/azure-functions/functions-kubernetes-keda)
- [<span data-ttu-id="9bc02-144">カナリアリリース</span><span class="sxs-lookup"><span data-stu-id="9bc02-144">Canary Release</span></span>](https://martinfowler.com/bliki/CanaryRelease.html)
- [<span data-ttu-id="9bc02-145">VS Code での Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="9bc02-145">Azure Dev Spaces with VS Code</span></span>](/azure/dev-spaces/quickstart-netcore)
- [<span data-ttu-id="9bc02-146">Visual Studio での Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="9bc02-146">Azure Dev Spaces with Visual Studio</span></span>](/azure/dev-spaces/quickstart-netcore-visualstudio)
- [<span data-ttu-id="9bc02-147">複数のノードプールの AKS</span><span class="sxs-lookup"><span data-stu-id="9bc02-147">AKS Multiple Node Pools</span></span>](/azure/aks/use-multiple-node-pools)
- [<span data-ttu-id="9bc02-148">AKS クラスターオートスケーラー</span><span class="sxs-lookup"><span data-stu-id="9bc02-148">AKS Cluster Autoscaler</span></span>](/azure/aks/cluster-autoscaler)
- [<span data-ttu-id="9bc02-149">チュートリアル: AKS でのアプリケーションのスケーリング</span><span class="sxs-lookup"><span data-stu-id="9bc02-149">Tutorial: Scale applications in AKS</span></span>](/azure/aks/tutorial-kubernetes-scale)
- [<span data-ttu-id="9bc02-150">Azure Functions のスケールとホスティング</span><span class="sxs-lookup"><span data-stu-id="9bc02-150">Azure Functions scale and hosting</span></span>](/azure/azure-functions/functions-scale)
- [<span data-ttu-id="9bc02-151">Azure Container Instances Docs</span><span class="sxs-lookup"><span data-stu-id="9bc02-151">Azure Container Instances Docs</span></span>](/azure/container-instances/)
- [<span data-ttu-id="9bc02-152">ACR からコンテナーインスタンスをデプロイする</span><span class="sxs-lookup"><span data-stu-id="9bc02-152">Deploy Container Instance from ACR</span></span>](/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
><span data-ttu-id="9bc02-153">[前へ](scale-containers-serverless.md)
>[次へ](communication-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="9bc02-153">[Previous](scale-containers-serverless.md)
[Next](communication-patterns.md)</span></span>
