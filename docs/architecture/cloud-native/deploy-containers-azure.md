---
title: Azure でコンテナーをデプロイする
description: Azure Container Registry、Azure Kubernetes Service、Azure Dev Spaces を使用した Azure でのコンテナーのデプロイ。
ms.date: 04/13/2020
ms.openlocfilehash: ba2854323ee0f1394a3cff0dd3756cb3c7c32d5b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614150"
---
# <a name="deploying-containers-in-azure"></a><span data-ttu-id="7f85b-103">Azure でコンテナーをデプロイする</span><span class="sxs-lookup"><span data-stu-id="7f85b-103">Deploying containers in Azure</span></span>

<span data-ttu-id="7f85b-104">この章と第1章では、コンテナーについて説明しました。</span><span class="sxs-lookup"><span data-stu-id="7f85b-104">We've discussed containers in this chapter and in chapter 1.</span></span> <span data-ttu-id="7f85b-105">コンテナーは、移植性など、クラウドネイティブアプリケーションに多くの利点を提供していることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="7f85b-105">We've seen that containers provide many benefits to cloud-native applications, including portability.</span></span> <span data-ttu-id="7f85b-106">Azure クラウドでは、ステージング環境と運用環境の間で同じコンテナー化されたサービスをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-106">In the Azure cloud, you can deploy the same containerized services across staging and production environments.</span></span> <span data-ttu-id="7f85b-107">Azure には、コンテナー化されたワークロードをホストするためのいくつかのオプションがあります</span><span class="sxs-lookup"><span data-stu-id="7f85b-107">Azure provides several options for hosting these containerized workloads:</span></span>

- <span data-ttu-id="7f85b-108">Azure Kubernetes Services (AKS)</span><span class="sxs-lookup"><span data-stu-id="7f85b-108">Azure Kubernetes Services (AKS)</span></span>
- <span data-ttu-id="7f85b-109">Azure Container Instance (ACI)</span><span class="sxs-lookup"><span data-stu-id="7f85b-109">Azure Container Instance (ACI)</span></span>
- <span data-ttu-id="7f85b-110">コンテナー用の Azure Web Apps</span><span class="sxs-lookup"><span data-stu-id="7f85b-110">Azure Web Apps for Containers</span></span>

## <a name="azure-container-registry"></a><span data-ttu-id="7f85b-111">Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="7f85b-111">Azure Container Registry</span></span>

<span data-ttu-id="7f85b-112">マイクロサービスをコンテナー化するときは、まずビルドコンテナー "image" になります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-112">When containerizing a microservice, you first a build container "image."</span></span> <span data-ttu-id="7f85b-113">イメージは、サービスコード、依存関係、およびランタイムのバイナリ表現です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-113">The image is a binary representation of the service code, dependencies, and runtime.</span></span> <span data-ttu-id="7f85b-114">Docker API からコマンドを使用してイメージを手動で作成することもできますが、 `Docker Build` 自動化されたビルドプロセスの一部として作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-114">While you can manually create an image using the `Docker Build` command from the Docker API, a better approach is to create it as part of an automated build process.</span></span>

<span data-ttu-id="7f85b-115">作成されると、コンテナーイメージはコンテナーレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-115">Once created, container images are stored in container registries.</span></span> <span data-ttu-id="7f85b-116">コンテナーイメージを作成、保存、および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-116">They enable you to build, store, and manage container images.</span></span> <span data-ttu-id="7f85b-117">パブリックとプライベートの両方で、使用可能なレジストリが多数あります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-117">There are many registries available, both public and private.</span></span> <span data-ttu-id="7f85b-118">Azure Container Registry (ACR) は、Azure クラウドで完全に管理されたコンテナーレジストリサービスです。</span><span class="sxs-lookup"><span data-stu-id="7f85b-118">Azure Container Registry (ACR) is a fully managed container registry service in the Azure cloud.</span></span> <span data-ttu-id="7f85b-119">Azure ネットワーク内にイメージが保持されるため、Azure container hosts にデプロイする時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-119">It persists your images inside the Azure network, reducing the time to deploy them to Azure container hosts.</span></span> <span data-ttu-id="7f85b-120">また、他の Azure リソースに使用するのと同じセキュリティと id の手順を使用してセキュリティを保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-120">You can also secure them using the same security and identity procedures that you use for other Azure resources.</span></span>

<span data-ttu-id="7f85b-121">Azure Container Registry を作成するには、 [Azure portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal)、 [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)、または[PowerShell ツール](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-121">You create an Azure Container Registry using the [Azure portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), [Azure CLI](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli), or [PowerShell tools](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell).</span></span> <span data-ttu-id="7f85b-122">Azure でのレジストリの作成は簡単です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-122">Creating a registry in Azure is simple.</span></span> <span data-ttu-id="7f85b-123">これには、Azure サブスクリプション、リソースグループ、および一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-123">It requires an Azure subscription, resource group, and a unique name.</span></span> <span data-ttu-id="7f85b-124">図3-11 は、でホストされるレジストリを作成するための基本的なオプションを示して `registryname.azurecr.io` います。</span><span class="sxs-lookup"><span data-stu-id="7f85b-124">Figure 3-11 shows the basic options for creating a registry, which will be hosted at `registryname.azurecr.io`.</span></span>

![コンテナー レジストリを作成する](./media/create-container-registry.png)

<span data-ttu-id="7f85b-126">**図 3-11**.</span><span class="sxs-lookup"><span data-stu-id="7f85b-126">**Figure 3-11**.</span></span> <span data-ttu-id="7f85b-127">コンテナー レジストリを作成する</span><span class="sxs-lookup"><span data-stu-id="7f85b-127">Create container registry</span></span>

<span data-ttu-id="7f85b-128">レジストリを作成したら、それを使用する前に認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-128">Once you've created the registry, you'll need to authenticate with it before you can use it.</span></span> <span data-ttu-id="7f85b-129">通常は、Azure CLI コマンドを使用してレジストリにログインします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-129">Typically, you'll log into the registry using the Azure CLI command:</span></span>

```azurecli
az acr login --name *registryname*
```

<span data-ttu-id="7f85b-130">認証が完了したら、docker コマンドを使用してコンテナーイメージをプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-130">Once authenticated, you can use docker commands to push container images to it.</span></span> <span data-ttu-id="7f85b-131">ただし、これを行う前に、ACR ログインサーバーの完全修飾名 (URL) でイメージにタグを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-131">Before you can do so, however, you must tag your image with the fully qualified name (URL) of your ACR login server.</span></span> <span data-ttu-id="7f85b-132">*Registryname*. azurecr.io の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-132">It will have the format *registryname*.azurecr.io.</span></span>

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="7f85b-133">イメージにタグを付けたら、コマンドを使用し `docker push` て、ACR インスタンスにイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-133">After you've tagged the image, you use the `docker push` command to push the image to your ACR instance.</span></span>

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="7f85b-134">イメージをレジストリにプッシュした後、次のコマンドを使用して、ローカルの Docker 環境からイメージを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-134">After you push an image to the registry, it's a good idea to remove the image from your local Docker environment, using this command:</span></span>

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

<span data-ttu-id="7f85b-135">ベストプラクティスとして、開発者はイメージをコンテナーレジストリに手動でプッシュしないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-135">As a best practice, developers shouldn't manually push images to a container registry.</span></span> <span data-ttu-id="7f85b-136">代わりに、GitHub や Azure DevOps などのツールで定義されたビルドパイプラインをこのプロセスに対して行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-136">Instead, a build pipeline defined in a tool like GitHub or Azure DevOps should be responsible for this process.</span></span> <span data-ttu-id="7f85b-137">詳細については、「[クラウド-ネイティブ DevOps](devops.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f85b-137">Learn more in the [Cloud-Native DevOps chapter](devops.md).</span></span>

## <a name="acr-tasks"></a><span data-ttu-id="7f85b-138">ACR タスク</span><span class="sxs-lookup"><span data-stu-id="7f85b-138">ACR Tasks</span></span>

<span data-ttu-id="7f85b-139">[ACR タスク](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview)は、Azure Container Registry から使用できる一連の機能です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-139">[ACR Tasks](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) is a set of features available from the Azure Container Registry.</span></span> <span data-ttu-id="7f85b-140">Azure クラウドでコンテナーイメージを構築および管理することによって、[内部ループの開発サイクル](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow)を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-140">It extends your [inner-loop development cycle](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) by building and managing container images in the Azure cloud.</span></span> <span data-ttu-id="7f85b-141">開発用コンピューター上でを呼び出すのではなく、 `docker build` `docker push` クラウド内の ACR タスクによって自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-141">Instead of invoking a `docker build` and `docker push` locally on your development machine, they're automatically handled by ACR Tasks in the cloud.</span></span>

<span data-ttu-id="7f85b-142">次の AZ CLI コマンドは、両方ともコンテナーイメージを構築し、ACR にプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-142">The following AZ CLI command both builds a container image and pushes it to ACR:</span></span>

```azurecli
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container regsitry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

<span data-ttu-id="7f85b-143">前のコマンドブロックからわかるように、開発用コンピューターに Docker Desktop をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f85b-143">As you can see from the previous command block, there's no need to install Docker Desktop on your development machine.</span></span> <span data-ttu-id="7f85b-144">また、ACR タスクトリガーを構成して、ソースコードと基本イメージの更新の両方でコンテナーイメージを再構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-144">Additionally, you can configure ACR Task triggers to rebuild containers images on both source code and base image updates.</span></span>

## <a name="azure-kubernetes-service"></a><span data-ttu-id="7f85b-145">Azure Kubernetes Service</span><span class="sxs-lookup"><span data-stu-id="7f85b-145">Azure Kubernetes Service</span></span>

<span data-ttu-id="7f85b-146">この章では、Azure Kubernetes Service (AKS) について説明しました。</span><span class="sxs-lookup"><span data-stu-id="7f85b-146">We discussed Azure Kubernetes Service (AKS) at length in this chapter.</span></span> <span data-ttu-id="7f85b-147">コンテナー化されたクラウドネイティブアプリケーションを管理する事実上のコンテナー orchestrator であることがわかりました。</span><span class="sxs-lookup"><span data-stu-id="7f85b-147">We've seen that it's the de facto container orchestrator managing containerized cloud-native applications.</span></span>

<span data-ttu-id="7f85b-148">ACR などのレジストリにイメージをデプロイしたら、自動的にプルおよびデプロイされるように AKS を構成できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-148">Once you deploy an image to a registry, such as ACR, you can configure AKS to automatically pull and deploy it.</span></span> <span data-ttu-id="7f85b-149">CI/CD パイプラインが配置されている場合は、更新プログラムを迅速に展開するときのリスクを最小限に抑えるために、[カナリアリリース](https://martinfowler.com/bliki/CanaryRelease.html)戦略を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-149">With a CI/CD pipeline in place, you might configure a  [canary release](https://martinfowler.com/bliki/CanaryRelease.html) strategy to minimize the risk involved when rapidly deploying updates.</span></span> <span data-ttu-id="7f85b-150">アプリの新しいバージョンは、最初に運用環境で構成され、トラフィックはルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="7f85b-150">The new version of the app is initially configured in production with no traffic routed to it.</span></span> <span data-ttu-id="7f85b-151">その後、システムは、新しく展開されたバージョンにユーザーの小さな割合をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-151">Then, the system will route a small percentage of users to the newly deployed version.</span></span> <span data-ttu-id="7f85b-152">新しいバージョンではチームが自信を持っているため、より多くのインスタンスをロールアウトし、古いものを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-152">As the team gains confidence in the new version, it can roll out more instances and retire the old.</span></span> <span data-ttu-id="7f85b-153">AKS は、このスタイルのデプロイを簡単にサポートします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-153">AKS easily supports this style of deployment.</span></span>

<span data-ttu-id="7f85b-154">Azure のほとんどのリソースと同様に、ポータル、コマンドライン、または、ヘルムや Terraform などの自動化ツールを使用して、Azure Kubernetes サービスクラスターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-154">As with most resources in Azure, you can create an Azure Kubernetes Service cluster using the portal, command-line, or automation tools like Helm or Terraform.</span></span> <span data-ttu-id="7f85b-155">新しいクラスターの使用を開始するには、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-155">To get started with a new cluster, you need to provide the following information:</span></span>

- <span data-ttu-id="7f85b-156">Azure サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="7f85b-156">Azure subscription</span></span>
- <span data-ttu-id="7f85b-157">Resource group</span><span class="sxs-lookup"><span data-stu-id="7f85b-157">Resource group</span></span>
- <span data-ttu-id="7f85b-158">Kubernetes クラスター名</span><span class="sxs-lookup"><span data-stu-id="7f85b-158">Kubernetes cluster name</span></span>
- <span data-ttu-id="7f85b-159">リージョン</span><span class="sxs-lookup"><span data-stu-id="7f85b-159">Region</span></span>
- <span data-ttu-id="7f85b-160">Kubernetes バージョン</span><span class="sxs-lookup"><span data-stu-id="7f85b-160">Kubernetes version</span></span>
- <span data-ttu-id="7f85b-161">DNS 名プレフィックス</span><span class="sxs-lookup"><span data-stu-id="7f85b-161">DNS name prefix</span></span>
- <span data-ttu-id="7f85b-162">ノード サイズ</span><span class="sxs-lookup"><span data-stu-id="7f85b-162">Node size</span></span>
- <span data-ttu-id="7f85b-163">ノード数</span><span class="sxs-lookup"><span data-stu-id="7f85b-163">Node count</span></span>

<span data-ttu-id="7f85b-164">作業を開始するには、この情報で十分です。</span><span class="sxs-lookup"><span data-stu-id="7f85b-164">This information is sufficient to get started.</span></span> <span data-ttu-id="7f85b-165">Azure portal の作成プロセスの一環として、クラスターの次の機能のオプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-165">As part of the creation process in the Azure portal, you can also configure options for the following features of your cluster:</span></span>

- <span data-ttu-id="7f85b-166">スケール</span><span class="sxs-lookup"><span data-stu-id="7f85b-166">Scale</span></span>
- <span data-ttu-id="7f85b-167">認証</span><span class="sxs-lookup"><span data-stu-id="7f85b-167">Authentication</span></span>
- <span data-ttu-id="7f85b-168">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="7f85b-168">Networking</span></span>
- <span data-ttu-id="7f85b-169">監視</span><span class="sxs-lookup"><span data-stu-id="7f85b-169">Monitoring</span></span>
- <span data-ttu-id="7f85b-170">タグ</span><span class="sxs-lookup"><span data-stu-id="7f85b-170">Tags</span></span>

<span data-ttu-id="7f85b-171">この[クイックスタートでは、Azure portal を使用して AKS クラスターをデプロイ](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal)する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-171">This [quickstart walks through deploying an AKS cluster using the Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).</span></span>

## <a name="azure-dev-spaces"></a><span data-ttu-id="7f85b-172">Azure Dev Spaces</span><span class="sxs-lookup"><span data-stu-id="7f85b-172">Azure Dev Spaces</span></span>

<span data-ttu-id="7f85b-173">クラウドネイティブアプリケーションは、大規模で複雑な拡張が可能で、大量のコンピューティングリソースを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-173">Cloud-native applications can quickly grow large and complex, requiring significant compute resources to run.</span></span> <span data-ttu-id="7f85b-174">このようなシナリオでは、アプリケーション全体を開発用コンピューター (特にラップトップ) でホストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7f85b-174">In these scenarios, the entire application can't be hosted on a development machine (especially a laptop).</span></span> <span data-ttu-id="7f85b-175">Azure Dev Spaces は、AKS を使用してこの問題に対処するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7f85b-175">Azure Dev Spaces is designed to address this problem using AKS.</span></span> <span data-ttu-id="7f85b-176">開発者は、AKS 開発クラスターでアプリケーションの残りの部分をホストしながら、ローカルバージョンのサービスを操作できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-176">It enables developers to work with a local version of their services while hosting the rest of the application in an AKS development cluster.</span></span>

<span data-ttu-id="7f85b-177">開発者は、コンテナー化されたアプリケーション全体を含む AKS クラスターで実行中の (開発) インスタンスを共有します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-177">Developers share a running (development) instance in an AKS cluster that contains the entire containerized application.</span></span> <span data-ttu-id="7f85b-178">ただし、ユーザーは自分のコンピューターに設定されている個人用のスペースを使用して、サービスをローカルに開発します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-178">But they use personal spaces set up on their machine to locally develop their services.</span></span> <span data-ttu-id="7f85b-179">準備ができたら、依存関係をレプリケートせずに、AKS クラスターでエンドツーエンドのテストを行います。</span><span class="sxs-lookup"><span data-stu-id="7f85b-179">When ready, they test from end-to-end in the AKS cluster - without replicating dependencies.</span></span> <span data-ttu-id="7f85b-180">Azure Dev Spaces は、ローカルコンピューターから AKS のサービスとコードをマージします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-180">Azure Dev Spaces merges code from the local machine with services in AKS.</span></span> <span data-ttu-id="7f85b-181">開発者は、Visual Studio または Visual Studio Code を使用して、Kubernetes 内で直接コードをすばやく反復処理し、デバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-181">Developers can rapidly iterate and debug code directly in Kubernetes using Visual Studio or Visual Studio Code.</span></span>

<span data-ttu-id="7f85b-182">Azure Dev Spaces の価値を理解するために、Microsoft Azure でコンテナーの Gabe Monroy PM の潜在顧客からこの引用を共有しましょう。</span><span class="sxs-lookup"><span data-stu-id="7f85b-182">To understand the value of Azure Dev Spaces, let me share this quotation from Gabe Monroy, PM Lead of Containers at Microsoft Azure:</span></span>

> <span data-ttu-id="7f85b-183">「新しい従業員が、多数のコンポーネントで構成される複雑なマイクロサービスアプリケーションでバグを修正しようとしていて、それぞれ独自の構成サービスとバックアップサービスを備えているとします。</span><span class="sxs-lookup"><span data-stu-id="7f85b-183">"Imagine you're a new employee trying to fix a bug in a complex microservices application consisting of dozens of components, each with their own configuration and backing services.</span></span> <span data-ttu-id="7f85b-184">使用を開始するには、ローカル開発環境を構成して、IDE のセットアップ、ツールチェーンの構築、コンテナー化されたサービスの依存関係、ローカルの Kubernetes 環境、バッキングサービスのモックなどの運用を模倣できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-184">To get started, you must configure your local development environment so that it can mimic production including setting up your IDE, building tool chain, containerized service dependencies, a local Kubernetes environment, mocks for backing services, and more.</span></span> <span data-ttu-id="7f85b-185">開発環境の設定に関連する時間があれば、最初のバグを修正するには数日かかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-185">With all the time involved setting up your development environment, fixing that first bug could take days.</span></span>
> <span data-ttu-id="7f85b-186">または、Dev Spaces と AKS を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-186">Or you could use Dev Spaces and AKS."</span></span>

<span data-ttu-id="7f85b-187">Azure Dev Spaces を操作するプロセスには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-187">The process for working with Azure Dev Spaces involves the following steps:</span></span>

1. <span data-ttu-id="7f85b-188">開発領域を作成します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-188">Create the dev space.</span></span>
2. <span data-ttu-id="7f85b-189">ルートの dev space を構成します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-189">Configure the root dev space.</span></span>
3. <span data-ttu-id="7f85b-190">(独自のバージョンのシステムの) 子の開発領域を構成します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-190">Configure a child dev space (for your own version of the system).</span></span>
4. <span data-ttu-id="7f85b-191">Dev 空間に接続します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-191">Connect to the dev space.</span></span>

<span data-ttu-id="7f85b-192">これらの手順はすべて、Azure CLI と新しいコマンドラインツールを使用して実行でき `azds` ます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-192">All of these steps can be performed using the Azure CLI and new  `azds` command-line tools.</span></span> <span data-ttu-id="7f85b-193">たとえば、特定の Kubernetes クラスター用に新しい Azure Dev Space を作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-193">For example, to create a new Azure Dev Space for a given Kubernetes cluster, you would use a command like this one:</span></span>

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

<span data-ttu-id="7f85b-194">次に、コマンドを使用して、 `azds prep` アプリケーションを実行するために必要な Docker およびヘルムグラフ資産を生成できます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-194">Next, you can use the `azds prep` command to generate the necessary Docker and Helm chart assets for running the application.</span></span> <span data-ttu-id="7f85b-195">次に、を使用して AKS でコードを実行し `azds up` ます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-195">Then you run your code in AKS using `azds up`.</span></span> <span data-ttu-id="7f85b-196">このコマンドを初めて実行すると、ヘルムグラフがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-196">The first time you run this command, the Helm chart will be installed.</span></span> <span data-ttu-id="7f85b-197">コンテナーは、指示に従ってビルドおよびデプロイされます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-197">The containers will be built and deployed according to your instructions.</span></span> <span data-ttu-id="7f85b-198">このタスクが初めて実行されたときに、数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="7f85b-198">This task may take a few minutes the first time it's run.</span></span> <span data-ttu-id="7f85b-199">ただし、変更を行った後は、を使用して独自の子開発領域に接続して `azds space select` から、分離された子開発領域に更新プログラムをデプロイしてデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-199">However, after you make changes, you can connect to your own child dev space using `azds space select` and then deploy and debug your updates in your isolated child dev space.</span></span> <span data-ttu-id="7f85b-200">開発領域が稼働状態になったら、コマンドを再発行して更新プログラムを送信する `azds up` か、Visual Studio または Visual Studio Code の組み込みツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7f85b-200">Once you have your dev space up and running, you can send updates to it by reissuing the `azds up` command or you can use built-in tooling in Visual Studio or Visual Studio Code.</span></span> <span data-ttu-id="7f85b-201">VS Code では、コマンドパレットを使用して、開発領域に接続します。</span><span class="sxs-lookup"><span data-stu-id="7f85b-201">With VS Code, you use the command palette to connect to your dev space.</span></span> <span data-ttu-id="7f85b-202">図3-12 は、Visual Studio で Azure Dev Spaces を使用して web アプリケーションを起動する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7f85b-202">Figure 3-12 shows how to launch your web application using Azure Dev Spaces in Visual Studio.</span></span>

<span data-ttu-id="7f85b-203">![Visual Studio の Azure Dev Spaces に接続 ](./media/azure-dev-spaces-visual-studio-launchsettings.png)
 **図 3-12**。</span><span class="sxs-lookup"><span data-stu-id="7f85b-203">![Connect to Azure Dev Spaces in Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**Figure 3-12**.</span></span> <span data-ttu-id="7f85b-204">Visual Studio での Azure Dev Spaces への接続</span><span class="sxs-lookup"><span data-stu-id="7f85b-204">Connect to Azure Dev Spaces in Visual Studio</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7f85b-205">[前へ](combine-containers-serverless-approaches.md)
>[次へ](scale-containers-serverless.md)</span><span class="sxs-lookup"><span data-stu-id="7f85b-205">[Previous](combine-containers-serverless-approaches.md)
[Next](scale-containers-serverless.md)</span></span>
