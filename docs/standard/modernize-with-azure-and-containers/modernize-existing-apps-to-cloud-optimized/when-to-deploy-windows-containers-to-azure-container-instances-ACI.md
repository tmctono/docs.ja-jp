---
title: Azure Container Instances (ACI) に Windows コンテナーを展開するタイミング
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |Azure Container Instances (ACI) に Windows コンテナーを展開するタイミング
ms.date: 04/29/2018
ms.openlocfilehash: 9bfa0688d07bd04964a1b28f688f125b5bcd2299
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638921"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="9dbb5-103">Azure Container Instances (ACI) に Windows コンテナーを展開するタイミング</span><span class="sxs-lookup"><span data-stu-id="9dbb5-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="9dbb5-104">Azure Container Instances は、主な価値提案は、すぐにコンテナーをデプロイすることができ、その環境を維持する必要はありません、基になるオペレーティング システムまたは Vm すべてに対して透過的なアップグレード/修正する必要はありませんし、展開します。コンテナーをすぐに使用できる環境にします。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="9dbb5-105">上の理由から、ACI を使用する場合のシナリオは主なシナリオのような基本的に、コンテナーを Azure Vm を使用すると、Azure Container Instances を使用する主なシナリオは。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="9dbb5-106">**開発/テスト シナリオ**</span><span class="sxs-lookup"><span data-stu-id="9dbb5-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="9dbb5-107">**タスクの自動化**</span><span class="sxs-lookup"><span data-stu-id="9dbb5-107">**Task automation**</span></span>
- <span data-ttu-id="9dbb5-108">**エージェントの CI/CD**</span><span class="sxs-lookup"><span data-stu-id="9dbb5-108">**CI/CD agents**</span></span>
- <span data-ttu-id="9dbb5-109">**小規模スケール/バッチ処理**</span><span class="sxs-lookup"><span data-stu-id="9dbb5-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="9dbb5-110">**単純な web アプリ**</span><span class="sxs-lookup"><span data-stu-id="9dbb5-110">**Simple web apps**</span></span>

<span data-ttu-id="9dbb5-111">単純な web アプリのシナリオは ACI の公正なシナリオが ACI でコンテナー イメージごとの 1 つのコンテナー インスタンスでのみ設定できる、ので高可用性はありませんをスケーラビリティが制限を考慮します。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="9dbb5-112">ただし、ACI は 1 つのコンテナー インスタンスを提供するだけであるために、インフラストラクチャと見なされます、できなくては大きなメリットを Windows Server の通常の Azure Vm と比較します。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="9dbb5-113">ACI、自己保持型の環境にのみ、コンテナーをデプロイしてそれらのコンテナーだけ支払います。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="9dbb5-114">場所を使用している Vm、コンテナーを含むほとんどのシナリオの多くにより良いプラットフォームのため、保守/更新/パッチ適用、Vm に必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="9dbb5-115">ACI を使用して簡単には、コンテナーを配置する、だけにコンテナーをデプロイする VM 環境を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="9dbb5-116">Azure Container Instances (ACI) の主な利点は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="9dbb5-117">サーバーを管理することがなくコンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-117">Run containers without managing servers</span></span>
- <span data-ttu-id="9dbb5-118">オンデマンドでのコンテナーでの機敏性を高める</span><span class="sxs-lookup"><span data-stu-id="9dbb5-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="9dbb5-119">前例のないシンプルさと速度で、クラウドへのコンテナーのデプロイ-1 つのコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="9dbb5-120">ハイパーバイザー分離を使用したセキュリティで保護されたアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9dbb5-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="9dbb5-121">つまり、ACI では、仮想マシンを管理または新しいツールを学習することがなく高速アプリを開発できます。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="9dbb5-122">クラウドで実行しているコンテナーで、アプリケーションだけになります。</span><span class="sxs-lookup"><span data-stu-id="9dbb5-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="9dbb5-123">[前へ](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [次へ](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="9dbb5-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
