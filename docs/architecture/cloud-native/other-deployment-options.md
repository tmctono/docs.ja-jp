---
title: その他のコンテナー配置オプション
description: Azure を使用したその他のコンテナーデプロイオプション
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841163"
---
# <a name="other-container-deployment-options"></a><span data-ttu-id="cf04c-103">その他のコンテナー配置オプション</span><span class="sxs-lookup"><span data-stu-id="cf04c-103">Other container deployment options</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="cf04c-104">AKS にデプロイするだけでなく、コンテナーと Azure Container Instances の Azure App Service にコンテナーをデプロイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cf04c-104">In addition to deploying to AKS, you can also deploy containers to Azure App Service for Containers and Azure Container Instances.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="cf04c-105">コンテナーの App Service に展開するのはどのような場合に適していますか。</span><span class="sxs-lookup"><span data-stu-id="cf04c-105">When does it make sense to deploy to App Service for Containers?</span></span>

<span data-ttu-id="cf04c-106">オーケストレーションを必要としない単純な実稼働アプリケーションは、コンテナーの Azure App Service に適しています。</span><span class="sxs-lookup"><span data-stu-id="cf04c-106">Simple production applications that don't require orchestration are well-suited to Azure App Service for Containers.</span></span>

## <a name="how-to-deploy-to-app-service-for-containers"></a><span data-ttu-id="cf04c-107">コンテナーの App Service にデプロイする方法</span><span class="sxs-lookup"><span data-stu-id="cf04c-107">How to deploy to App Service for Containers</span></span>

<span data-ttu-id="cf04c-108">[コンテナーの Azure App Service](https://azure.microsoft.com/services/app-service/containers/)にデプロイするには、AZURE CONTAINER REGISTRY (ACR) と、それにアクセスするための資格情報を構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf04c-108">To deploy to [Azure App Service for Containers](https://azure.microsoft.com/services/app-service/containers/), you need to have configured an Azure Container Registry (ACR) and credentials for accessing it.</span></span> <span data-ttu-id="cf04c-109">ホストするコンテナーをレジストリにプッシュして、Azure App Service にプルできるようにします。</span><span class="sxs-lookup"><span data-stu-id="cf04c-109">Push the container you intend to host to the registry so it's available to pull into your Azure App Service.</span></span> <span data-ttu-id="cf04c-110">作成したアプリを継続的にデプロイするように構成できます。これにより、ACR で対応するイメージを更新するたびに、アプリに更新プログラムが自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="cf04c-110">Once created, you can configure the app for Continuous Deployment, which will automatically deploy updates to the app whenever you update its corresponding image in ACR.</span></span>

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a><span data-ttu-id="cf04c-111">Azure Container Instances に展開するにはどのような意味がありますか。</span><span class="sxs-lookup"><span data-stu-id="cf04c-111">When does it make sense to deploy to Azure Container Instances?</span></span>

<span data-ttu-id="cf04c-112">Azure Container Instances は、シナリオのテストに最適です。</span><span class="sxs-lookup"><span data-stu-id="cf04c-112">Azure Container Instances are best used for testing scenarios.</span></span> <span data-ttu-id="cf04c-113">クラウドでホストされているコンテナーインスタンスにアプリケーションをデプロイする高速で簡単な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf04c-113">They provide a fast, simple way to deploy an application to a cloud-hosted container instance.</span></span> <span data-ttu-id="cf04c-114">Azure Kubernetes Service によって提供されるスケーリングおよびオーケストレーション機能を必要としない場合に、アプリケーションをテストまたはデモするために使用します。</span><span class="sxs-lookup"><span data-stu-id="cf04c-114">Use them to test or demo applications when you don't require scaling and orchestration features offered by Azure Kubernetes Service.</span></span>

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a><span data-ttu-id="cf04c-115">Azure Container Instances にアプリを展開する方法</span><span class="sxs-lookup"><span data-stu-id="cf04c-115">How to deploy an app to Azure Container Instances</span></span>

<span data-ttu-id="cf04c-116">[Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/)にデプロイするには、AZURE CONTAINER REGISTRY (ACR) と、それにアクセスするための資格情報を構成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf04c-116">To deploy to [Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/), you need to have configured an Azure Container Registry (ACR) and credentials for accessing it.</span></span> <span data-ttu-id="cf04c-117">また、コンテナーイメージをレジストリにプッシュしておく必要があります。これにより、ACI にプルできます。</span><span class="sxs-lookup"><span data-stu-id="cf04c-117">You must also have previously pushed your container image to the registry, so it's available to pull into ACI.</span></span> <span data-ttu-id="cf04c-118">Azure CLI またはポータルを使用して ACI を操作できます。</span><span class="sxs-lookup"><span data-stu-id="cf04c-118">You can work with ACI using the Azure CLI or through the portal.</span></span> <span data-ttu-id="cf04c-119">Azure Container registry を使用すると、図3-14 に示すように、レジストリ内から直接、個々のコンテナーインスタンスを ACI に簡単にデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="cf04c-119">Azure Container Registries make it easy to deploy individual container instances to ACI directly from within the registry, as shown in Figure 3-14.</span></span>

![実行インスタンスの Azure Container Registry](./media/acr-runinstance-contextmenu.png)

<span data-ttu-id="cf04c-121">**図 3-14**.</span><span class="sxs-lookup"><span data-stu-id="cf04c-121">**Figure 3-14**.</span></span> <span data-ttu-id="cf04c-122">実行インスタンスの Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="cf04c-122">Azure Container Registry Run Instance</span></span>

<span data-ttu-id="cf04c-123">レジストリからコンテナーインスタンスを作成するには、通常の Azure 設定 (名前、サブスクリプション、リソースグループ、場所)、コンテナーに割り当てるメモリの量、およびリッスンするポートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf04c-123">Creating a container instance from the registry just requires you to specify the usual Azure settings (name, subscription, resource group, and location), how much memory to allocate to the container, and which port it should listen on.</span></span> <span data-ttu-id="cf04c-124">この[クイックスタートでは、Azure portal を使用して、コンテナーインスタンスを ACI にデプロイする方法を示し](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal)ます。</span><span class="sxs-lookup"><span data-stu-id="cf04c-124">This [quickstart shows how to deploy a container instance to ACI using the Azure portal](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).</span></span>

<span data-ttu-id="cf04c-125">デプロイが完了したら、新しくデプロイされたコンテナーの IP アドレスを見つけて、指定したポートを介して通信します。</span><span class="sxs-lookup"><span data-stu-id="cf04c-125">Once the deployment completes, find the newly deployed container's IP address and communicate with it over the port you specified.</span></span>

<span data-ttu-id="cf04c-126">Azure Container Instances には、Azure でコンテナーを実行する最速で簡単な方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="cf04c-126">Azure Container Instances offers the fastest, simplest way to run a container in Azure.</span></span> <span data-ttu-id="cf04c-127">App service や orchestrator を構成したり、仮想マシンに対処したりする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cf04c-127">There's no need to configure an app service or an orchestrator or to deal with virtual machines.</span></span> <span data-ttu-id="cf04c-128">ただし、単純であるため、ACI は主にテスト目的で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf04c-128">However, because of its simplicity, ACI should primarily be used for testing purposes.</span></span> <span data-ttu-id="cf04c-129">アプリケーションで自動スケーラビリティが必要な場合、複数のコンテナーが連携するように構成されている場合、またはその他の複雑な機能がある場合は、アプリをホストするために使用できるその他の適切な Azure サービスがあります。</span><span class="sxs-lookup"><span data-stu-id="cf04c-129">If your application requires automatic scalability, multiple containers configured to work together, or any additional complex features, there are other better-suited Azure services available to host your app.</span></span>

## <a name="references"></a><span data-ttu-id="cf04c-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf04c-130">References</span></span>

- [<span data-ttu-id="cf04c-131">Azure Container Instances Docs</span><span class="sxs-lookup"><span data-stu-id="cf04c-131">Azure Container Instances Docs</span></span>](https://docs.microsoft.com/azure/container-instances/)
- [<span data-ttu-id="cf04c-132">ACR からコンテナーインスタンスをデプロイする</span><span class="sxs-lookup"><span data-stu-id="cf04c-132">Deploy Container Instance from ACR</span></span>](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
><span data-ttu-id="cf04c-133">[前へ](scale-containers-serverless.md)
>[次へ](communication-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="cf04c-133">[Previous](scale-containers-serverless.md)
[Next](communication-patterns.md)</span></span>
