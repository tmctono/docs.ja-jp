---
title: Windows コンテナーを Azure Container Instances (ACI) に展開する場合
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |Windows コンテナーを Azure Container Instances (ACI) に展開する場合
ms.date: 04/29/2018
ms.openlocfilehash: 3b6ae1ced9c4e01f5ab400e2575947a396064ebd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577935"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="b1f65-103">Windows コンテナーを Azure Container Instances (ACI) に展開する場合</span><span class="sxs-lookup"><span data-stu-id="b1f65-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="b1f65-104">主な価値の提案は、コンテナーをすぐにデプロイでき、その環境を維持する必要がなく、基になるオペレーティングシステムまたは Vm をアップグレード/修正する必要がないことです。これはすべて透過的で、デプロイするだけです。 Azure Container Instancesコンテナーをすぐに使用可能な環境にします。</span><span class="sxs-lookup"><span data-stu-id="b1f65-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="b1f65-105">ACI を使用する理由とシナリオは、コンテナーで Azure Vm を使用する場合の主なシナリオに似ています。基本的に、Azure Container Instances を使用する主なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1f65-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="b1f65-106">**開発/テストシナリオ**</span><span class="sxs-lookup"><span data-stu-id="b1f65-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="b1f65-107">**タスクの自動化**</span><span class="sxs-lookup"><span data-stu-id="b1f65-107">**Task automation**</span></span>
- <span data-ttu-id="b1f65-108">**CI/CD エージェント**</span><span class="sxs-lookup"><span data-stu-id="b1f65-108">**CI/CD agents**</span></span>
- <span data-ttu-id="b1f65-109">**小/小数点以下のバッチ処理**</span><span class="sxs-lookup"><span data-stu-id="b1f65-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="b1f65-110">**単純な web アプリ**</span><span class="sxs-lookup"><span data-stu-id="b1f65-110">**Simple web apps**</span></span>

<span data-ttu-id="b1f65-111">単純な web apps シナリオは、ACI の公正なシナリオですが、ACI ではコンテナーイメージごとに1つのコンテナーインスタンスしか持つことができないため、高可用性はなく、スケーラビリティも制限されています。</span><span class="sxs-lookup"><span data-stu-id="b1f65-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="b1f65-112">ただし、1つのコンテナーインスタンスだけを提供するため、ACI がインフラストラクチャと見なされる場合でも、Windows Server を使用した通常の Azure Vm と比較して大きな利点があります。</span><span class="sxs-lookup"><span data-stu-id="b1f65-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="b1f65-113">ACI を使用すると、コンテナーを自己保守環境にデプロイするだけで、これらのコンテナーに対して料金が請求されます。</span><span class="sxs-lookup"><span data-stu-id="b1f65-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="b1f65-114">Vm を管理/更新/修正する必要はありません。そのため、コンテナーで Vm を使用している可能性のあるほとんどのシナリオでは、はるかに優れたプラットフォームとなります。</span><span class="sxs-lookup"><span data-stu-id="b1f65-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="b1f65-115">ACI を使用すると、コンテナーをデプロイするだけで、コンテナーをデプロイするだけで VM 環境を作成する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="b1f65-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="b1f65-116">Azure Container Instances (ACI) の主な利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1f65-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="b1f65-117">サーバーを管理せずにコンテナーを実行する</span><span class="sxs-lookup"><span data-stu-id="b1f65-117">Run containers without managing servers</span></span>
- <span data-ttu-id="b1f65-118">コンテナーの俊敏性をオンデマンドで向上</span><span class="sxs-lookup"><span data-stu-id="b1f65-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="b1f65-119">1つのコマンドを使用して、従来よりもシンプルで高速な方法でコンテナーをクラウドにデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="b1f65-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="b1f65-120">ハイパーバイザー分離を使用したアプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="b1f65-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="b1f65-121">つまり、ACI を使用すると、仮想マシンを管理したり、新しいツールを習得したりすることなく、アプリを迅速に開発できます。</span><span class="sxs-lookup"><span data-stu-id="b1f65-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="b1f65-122">これは、クラウドで実行されているコンテナー内のアプリケーションにすぎません。</span><span class="sxs-lookup"><span data-stu-id="b1f65-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="b1f65-123">[前へ](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [次へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="b1f65-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
