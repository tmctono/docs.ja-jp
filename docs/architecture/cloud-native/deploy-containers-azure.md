---
title: Azure でコンテナーをデプロイする
description: Azure Container Registry、Azure Kubernetes Service、Azure Dev Spaces を使用した Azure でのコンテナーのデプロイ。
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840485"
---
# <a name="deploying-containers-in-azure"></a><span data-ttu-id="af588-103">Azure でコンテナーをデプロイする</span><span class="sxs-lookup"><span data-stu-id="af588-103">Deploying containers in Azure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="af588-104">コンテナーは多くの利点を提供しますが、その1つは移植性です。</span><span class="sxs-lookup"><span data-stu-id="af588-104">Containers provide many benefits, one of which is portability.</span></span> <span data-ttu-id="af588-105">ローカルで開発およびテストした同じコンテナーを簡単に作成し、それを Azure にデプロイして、ステージング環境と運用環境でアプリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="af588-105">You can easily take the same container you've developed and tested locally and deploy it to Azure where it can run your app in staging and production environments.</span></span> <span data-ttu-id="af588-106">Azure には、コンテナーベースのアプリホスティング用のさまざまなオプションが用意されており、同様に、さまざまな方法でデプロイを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="af588-106">Azure provides a number of options for container-based app hosting and likewise supports several different means of deployment.</span></span> <span data-ttu-id="af588-107">最も一般的で柔軟性の高い方法は、コンテナーを Azure Container Registry (ACR) にデプロイすることです。これは、それらのサービスをホストするために使用するすべてのサービスからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="af588-107">The most common and most flexible approach is to deploy your containers to Azure Container Registry (ACR), where they're accessible by whatever services you wish to use to host them.</span></span> <span data-ttu-id="af588-108">Azure Web App for Containers、Azure Kubernetes Services (AKS)、および Azure Container Instance (ACI) はすべて、ACR にプッシュされたコンテナーイメージにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="af588-108">Azure Web App for Containers, Azure Kubernetes Services (AKS), and Azure Container Instance (ACI) all can access container images that have been pushed to ACR.</span></span>

## <a name="azure-container-registry"></a><span data-ttu-id="af588-109">Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="af588-109">Azure Container Registry</span></span>

<span data-ttu-id="af588-110">Azure Container Registry (ACR) を使用すると、すべてのコンテナーデプロイのイメージを構築、保存、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="af588-110">Azure Container Registry (ACR) lets you build, store, and manage images for all of your container deployments.</span></span> <span data-ttu-id="af588-111">パブリックとプライベートの両方のコンテナーレジストリがあり、そこにコンテナーをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="af588-111">There are other container registries, both public and private, to which you can deploy containers.</span></span> <span data-ttu-id="af588-112">他のオプションに対する ACR の利点は、イメージを運用環境の近くに保持して、ビルドと展開の時間を短縮できることです。</span><span class="sxs-lookup"><span data-stu-id="af588-112">The benefit of ACR over other options is that you can keep your images close to your production environment, improving build and deployment times.</span></span> <span data-ttu-id="af588-113">また、Azure リソースの残りの部分で使用するのと同じセキュリティ手順を使用してセキュリティを保護することもできます。これにより、セキュリティが向上し、資産管理作業が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="af588-113">You can also secure them using the same security procedures you use for the rest of your Azure resources, improving security and reducing asset management effort.</span></span>

<span data-ttu-id="af588-114">[コンテナーレジストリを作成するには、Azure Portal を使用](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal)するか[、Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)または[PowerShell ツール](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)を使用します。</span><span class="sxs-lookup"><span data-stu-id="af588-114">You [create a container registry using the Azure Portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) or [using the Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) or [PowerShell tools](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell).</span></span> <span data-ttu-id="af588-115">新しいコンテナーレジストリを作成するには、Azure サブスクリプション、リソースグループ、および一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="af588-115">Creating a new container registry just requires an Azure subscription, a resource group, and a unique name.</span></span> <span data-ttu-id="af588-116">図3-11 に、レジストリを作成するための基本的なオプションを示します *。レジストリ*は、azurecr.io でホストされます。</span><span class="sxs-lookup"><span data-stu-id="af588-116">Figure 3-11 shows the basic options for creating a registry, which will be hosted at *registryname*.azurecr.io.</span></span>

<span data-ttu-id="af588-117">コンテナーレジストリを作成 ![には](./media/create-container-registry.png)
**図 3-11**をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="af588-117">![Create container registry](./media/create-container-registry.png)
**Figure 3-11**.</span></span> <span data-ttu-id="af588-118">コンテナーレジストリの作成</span><span class="sxs-lookup"><span data-stu-id="af588-118">Create container registry</span></span>

<span data-ttu-id="af588-119">レジストリを作成したら、それを使用する前に認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af588-119">Once you've created a registry, you'll need to authenticate with it before you can use it.</span></span> <span data-ttu-id="af588-120">通常は、Azure CLI コマンドを使用してレジストリにログインします。</span><span class="sxs-lookup"><span data-stu-id="af588-120">Typically, you'll log into the registry using the Azure CLI command:</span></span>

```azurecli
az acr login --name *registryname*
```

<span data-ttu-id="af588-121">Azure Container Registry でレジストリを作成したら、docker コマンドを使用してコンテナーイメージをそこにプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="af588-121">Once you've created a registry in Azure Container Registry, you can use docker commands to push container images to it.</span></span> <span data-ttu-id="af588-122">ただし、これを行う前に、まず、ACR ログインサーバーの完全修飾名 (URL) でイメージにタグを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="af588-122">Before you can do so, however, you must first tag your image with the fully qualified name (URL) of your ACR login server.</span></span> <span data-ttu-id="af588-123">これは、azurecr.io と*いう形式になります。*</span><span class="sxs-lookup"><span data-stu-id="af588-123">This will have the format *registryname*.azurecr.io.</span></span>

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="af588-124">イメージにタグを付けたら、`docker push` コマンドを使用して、ACR インスタンスにイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="af588-124">After you've tagged the image, you use the `docker push` command to push the image to your ACR instance.</span></span>

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="af588-125">イメージをレジストリにプッシュした後、次のコマンドを使用して、ローカルの Docker 環境からイメージを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af588-125">After you push an image to the registry, it's a good idea to remove the image from your local Docker environment, using this command:</span></span>

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="af588-126">開発者は、自分のマシンからコンテナーレジストリに直接プッシュすることはめったにありません。</span><span class="sxs-lookup"><span data-stu-id="af588-126">Developers should rarely push directly from their machines to a container registry.</span></span> <span data-ttu-id="af588-127">代わりに、Azure DevOps などのツールで定義されたビルドパイプラインをこのプロセスに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af588-127">Instead, a build pipeline defined in a tool like Azure DevOps should be responsible for this process.</span></span> <span data-ttu-id="af588-128">詳細については、「[クラウド-ネイティブ DevOps](devops.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af588-128">Learn more in the [Cloud-Native DevOps chapter](devops.md).</span></span>

## <a name="azure-kubernetes-service"></a><span data-ttu-id="af588-129">Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="af588-129">Azure Kubernetes Service</span></span>

<span data-ttu-id="af588-130">コンテナーベースのアプリケーションに複数のコンテナーが含まれている場合、ほとんどの場合、Kubernetes などの*orchestrator*を使用してコンテナー間の相互作用を定義し、管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af588-130">If your container-based application involves multiple containers, you'll most likely want to define and manage the interactions between the containers using an *orchestrator* like Kubernetes.</span></span> <span data-ttu-id="af588-131">ACR にコンテナーイメージをデプロイすると、Azure Kubernetes Services を簡単に構成して、ACR から更新されたイメージを自動的にデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="af588-131">Once you've deployed your container images to ACR, you can easily configure Azure Kubernetes Services to automatically deploy updated images from ACR.</span></span> <span data-ttu-id="af588-132">完全な CI/CD パイプラインが配置されているので、更新プログラムを迅速にデプロイするときのリスクを最小限に抑えるために、[カナリアリリース](https://martinfowler.com/bliki/CanaryRelease.html)戦略を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="af588-132">With a full CI/CD pipeline in place, you can configure a [canary release](https://martinfowler.com/bliki/CanaryRelease.html) strategy to minimize the risk involved when rapidly deploying updates.</span></span> <span data-ttu-id="af588-133">アプリの新しいバージョンは、最初に運用環境で構成され、トラフィックはルーティングされません。その後、少数のユーザーが、新しくデプロイされたバージョンのアプリにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="af588-133">The new version of the app is initially configured in production with no traffic routed to it, and then a small number of users are routed to the newly-deployed version of the app.</span></span> <span data-ttu-id="af588-134">新しいバージョンのソフトウェアの信頼性を高めるために、新しいバージョンのインスタンスの数が増え、以前のバージョンのインスタンスが廃止されています。</span><span class="sxs-lookup"><span data-stu-id="af588-134">As the team gains confidence in the new version of the software, more instances of the new version are rolled out and the previous version's instances are retired.</span></span> <span data-ttu-id="af588-135">AKS は、このスタイルのデプロイを簡単にサポートします。</span><span class="sxs-lookup"><span data-stu-id="af588-135">AKS easily supports this style of deployment.</span></span>

<span data-ttu-id="af588-136">Azure のほとんどのリソースと同様に、ポータルを使用して、またはコマンドラインツールや、ヘルムや Terraform などのインフラストラクチャ自動化ツールを使用して、Azure Kubernetes クラスターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="af588-136">As with most resources in Azure, you can create Azure Kubernetes clusters using the portal or using command line tools or infrastructure automation tools like Helm or Terraform.</span></span> <span data-ttu-id="af588-137">新しいクラスターの使用を開始するには、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af588-137">To get started with a new cluster, you need to provide the following information:</span></span>

- <span data-ttu-id="af588-138">Azure サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="af588-138">Azure subscription</span></span>
- <span data-ttu-id="af588-139">リソース グループ</span><span class="sxs-lookup"><span data-stu-id="af588-139">Resource group</span></span>
- <span data-ttu-id="af588-140">クラスター名の Kubernetes</span><span class="sxs-lookup"><span data-stu-id="af588-140">Kubernetes cluster name</span></span>
- <span data-ttu-id="af588-141">Region</span><span class="sxs-lookup"><span data-stu-id="af588-141">Region</span></span>
- <span data-ttu-id="af588-142">Kubernetes のバージョン</span><span class="sxs-lookup"><span data-stu-id="af588-142">Kubernetes version</span></span>
- <span data-ttu-id="af588-143">DNS 名のプレフィックス</span><span class="sxs-lookup"><span data-stu-id="af588-143">DNS name prefix</span></span>
- <span data-ttu-id="af588-144">ノードサイズ</span><span class="sxs-lookup"><span data-stu-id="af588-144">Node size</span></span>
- <span data-ttu-id="af588-145">ノード数</span><span class="sxs-lookup"><span data-stu-id="af588-145">Node count</span></span>

<span data-ttu-id="af588-146">作業を開始するには、この情報で十分です。</span><span class="sxs-lookup"><span data-stu-id="af588-146">This information is sufficient to get started.</span></span> <span data-ttu-id="af588-147">Azure Portal での作成プロセスの一環として、クラスターの次の機能のオプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="af588-147">As part of the creation process in the Azure Portal, you can also configure options for the following features of your cluster:</span></span>

- <span data-ttu-id="af588-148">[スケール]</span><span class="sxs-lookup"><span data-stu-id="af588-148">Scale</span></span>
- <span data-ttu-id="af588-149">認証</span><span class="sxs-lookup"><span data-stu-id="af588-149">Authentication</span></span>
- <span data-ttu-id="af588-150">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="af588-150">Networking</span></span>
- <span data-ttu-id="af588-151">監視</span><span class="sxs-lookup"><span data-stu-id="af588-151">Monitoring</span></span>
- <span data-ttu-id="af588-152">Tags</span><span class="sxs-lookup"><span data-stu-id="af588-152">Tags</span></span>

<span data-ttu-id="af588-153">この[クイックスタートでは、Azure portal を使用して AKS クラスターをデプロイ](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="af588-153">This [quickstart walks through deploying an AKS cluster using the Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).</span></span>

## <a name="azure-dev-spaces"></a><span data-ttu-id="af588-154">Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="af588-154">Azure Dev Spaces</span></span>

<span data-ttu-id="af588-155">複雑な Kubernetes クラスターでは、をホストするために大量のリソースが必要になることがあります。これにより、開発者は、アプリケーション全体を1台のコンピューター (特にラップトップ) で実行することが難しくなります。</span><span class="sxs-lookup"><span data-stu-id="af588-155">Complex Kubernetes clusters can require significant resources to host, which can make it difficult for developers to run the entire application on a single machine (especially a laptop).</span></span> <span data-ttu-id="af588-156">Azure Dev Spaces は、Azure でホストされている独自のバージョンの Azure Kubernetes クラスターを開発者が操作できるようにすることで、このソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="af588-156">Azure Dev Spaces offers a solution to this by allowing developers to work with their own versions of Azure Kubernetes clusters hosted in Azure.</span></span> <span data-ttu-id="af588-157">Azure Dev Spaces は、AKS を使用してマイクロサービスベースのアプリケーションの開発を容易にするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="af588-157">Azure Dev Spaces is designed to ease development of microservice-based applications using AKS.</span></span>

<span data-ttu-id="af588-158">Azure Dev Spaces の価値を理解するために、Microsoft Azure でコンテナーの Gabe Monroy PM の潜在顧客からこの引用を共有しましょう。</span><span class="sxs-lookup"><span data-stu-id="af588-158">To understand the value of Azure Dev Spaces, let me share this quotation from Gabe Monroy, PM Lead of Containers at Microsoft Azure:</span></span>

<span data-ttu-id="af588-159">"多くのコンポーネントで構成される複雑なマイクロサービスアプリケーションで、それぞれ独自の構成サービスとバッキングサービスを備えた、新しい従業員がバグを修正しようとしているとします。</span><span class="sxs-lookup"><span data-stu-id="af588-159">"Imagine you are a new employee trying to fix a bug in a complex microservices application consisting of dozens of components, each with their own configuration and backing services.</span></span> <span data-ttu-id="af588-160">使用を開始するには、ローカル開発環境を構成して、IDE のセットアップ、ツールチェーンの構築、コンテナー化されたサービスの依存関係、ローカルの Kubernetes 環境、バッキングサービスのモックなどの運用を模倣できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af588-160">To get started, you must configure your local development environment so that it can mimic production including setting up your IDE, building tool chain, containerized service dependencies, a local Kubernetes environment, mocks for backing services, and more.</span></span> <span data-ttu-id="af588-161">開発環境の設定に関連する時間があれば、最初のバグを修正するには数日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af588-161">With all the time involved setting up your development environment, fixing that first bug could take days.</span></span>

> <span data-ttu-id="af588-162">または、Dev Spaces と AKS を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="af588-162">Or you could use Dev Spaces and AKS."</span></span>

<span data-ttu-id="af588-163">Azure Dev Spaces を操作するプロセスには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="af588-163">The process for working with Azure Dev Spaces involves the following steps:</span></span>

1. <span data-ttu-id="af588-164">開発領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="af588-164">Create the dev space.</span></span>
2. <span data-ttu-id="af588-165">ルートの dev space を構成します。</span><span class="sxs-lookup"><span data-stu-id="af588-165">Configure the root dev space.</span></span>
3. <span data-ttu-id="af588-166">(独自のバージョンのシステムの) 子の開発領域を構成します。</span><span class="sxs-lookup"><span data-stu-id="af588-166">Configure a child dev space (for your own version of the system).</span></span>
4. <span data-ttu-id="af588-167">Dev 空間に接続します。</span><span class="sxs-lookup"><span data-stu-id="af588-167">Connect to the dev space.</span></span>

<span data-ttu-id="af588-168">これらの手順はすべて、Azure CLI と新しい `azds` コマンドラインツールを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="af588-168">All of these steps can be performed using the Azure CLI and new  `azds` command line tools.</span></span> <span data-ttu-id="af588-169">たとえば、特定の Kubernetes クラスター用に新しい Azure Dev Space を作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="af588-169">For example, to create a new Azure Dev Space for a given Kubernetes cluster, you would use a command like this one:</span></span>

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

<span data-ttu-id="af588-170">次に、[`azds prep`] コマンドを使用して、アプリケーションを実行するために必要な Docker およびヘルムグラフの資産を生成できます。</span><span class="sxs-lookup"><span data-stu-id="af588-170">Next, you can use the `azds prep` command to generate the necessary Docker and Helm chart assets for running the application.</span></span> <span data-ttu-id="af588-171">次に、`azds up`を使用して AKS でコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="af588-171">Then you run your code in AKS using `azds up`.</span></span> <span data-ttu-id="af588-172">このコマンドを初めて実行すると、ヘルムグラフがインストールされ、指示に従ってコンテナーがビルドおよび配置されます。</span><span class="sxs-lookup"><span data-stu-id="af588-172">The first time you run this command, the Helm chart will be installed, and the container(s) will be built and deployed according to your instructions.</span></span> <span data-ttu-id="af588-173">初回実行時には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="af588-173">This may take a few minutes the first time it's run.</span></span> <span data-ttu-id="af588-174">ただし、変更を行った後、`azds space select` を使用して独自の子開発領域に接続し、分離された子開発領域に更新プログラムをデプロイしてデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="af588-174">However, after you make changes, you can connect to your own child dev space using `azds space select` and then deploy and debug your updates in your isolated child dev space.</span></span> <span data-ttu-id="af588-175">開発領域を準備して実行すると、`azds up` コマンドを再発行することによって更新を送信できます。または、Visual Studio または Visual Studio Code の組み込みツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="af588-175">Once you have your dev space up and running, you can send updates to it by re-issuing the `azds up` command or you can use built-in tooling in Visual Studio or Visual Studio Code.</span></span> <span data-ttu-id="af588-176">VS Code では、コマンドパレットを使用して、開発領域に接続します。</span><span class="sxs-lookup"><span data-stu-id="af588-176">With VS Code, you use the command palette to connect to your dev space.</span></span> <span data-ttu-id="af588-177">図3-12 は、Visual Studio で Azure Dev Spaces を使用して web アプリケーションを起動する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="af588-177">Figure 3-12 shows how to launch your web application using Azure Dev Spaces in Visual Studio.</span></span>

<span data-ttu-id="af588-178">Visual Studio で Azure Dev Spaces に接続 ![には](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**図 3-12**をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="af588-178">![Connect to Azure Dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Figure 3-12**.</span></span> <span data-ttu-id="af588-179">Visual Studio での Azure Dev Spaces への接続</span><span class="sxs-lookup"><span data-stu-id="af588-179">Connect to Azure Dev Spaces in Visual Studio</span></span>

## <a name="references"></a><span data-ttu-id="af588-180">参照</span><span class="sxs-lookup"><span data-stu-id="af588-180">References</span></span>

- [<span data-ttu-id="af588-181">カナリアリリース</span><span class="sxs-lookup"><span data-stu-id="af588-181">Canary Release</span></span>](https://martinfowler.com/bliki/CanaryRelease.html)
- [<span data-ttu-id="af588-182">VS Code での Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="af588-182">Azure Dev Spaces with VS Code</span></span>](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [<span data-ttu-id="af588-183">Visual Studio での Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="af588-183">Azure Dev Spaces with Visual Studio</span></span>](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
><span data-ttu-id="af588-184">[前へ](combine-containers-serverless-approaches.md)
>[次へ](scale-containers-serverless.md)</span><span class="sxs-lookup"><span data-stu-id="af588-184">[Previous](combine-containers-serverless-approaches.md)
[Next](scale-containers-serverless.md)</span></span>
