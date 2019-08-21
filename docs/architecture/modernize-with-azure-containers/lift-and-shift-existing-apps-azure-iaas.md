---
title: 既存の .NET アプリを Azure IaaS にリフトアンドシフトする (クラウドインフラストラクチャの準備完了)
description: Azure クラウドおよび Windows コンテナーを使用して、既存の .NET アプリケーションを最新化します。
ms.date: 04/28/2018
ms.openlocfilehash: e25ddbf9b6e62c264f3f4d4580d7df3553d262ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660750"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a><span data-ttu-id="4fd89-103">既存の .NET アプリを Azure IaaS にリフトアンドシフトする (クラウドインフラストラクチャの準備完了)</span><span class="sxs-lookup"><span data-stu-id="4fd89-103">Lift and shift existing .NET apps to Azure IaaS (Cloud Infrastructure-Ready)</span></span>

> <span data-ttu-id="4fd89-104">展望:最初の手順として、オンプレミスの投資とハードウェアとネットワークのメンテナンスの総コストを削減するために、単にクラウド内の既存のアプリケーションを再ホストします。</span><span class="sxs-lookup"><span data-stu-id="4fd89-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="4fd89-105">既存のアプリケーションを azure infrastructure as a Service (iaas) プラットフォームに移行する前に、Azure の iaas に直接移行する理由を分析することが重要です。</span><span class="sxs-lookup"><span data-stu-id="4fd89-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="4fd89-106">この近代化成熟度レベルのシナリオでは、基本的に、現在のオンプレミスインフラストラクチャを引き続き使用するのではなく、クラウドで Vm の使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="4fd89-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="4fd89-107">さらに、Azure に高度な管理サービスを追加するのではなく、純粋な IaaS クラウドに移行することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4fd89-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="4fd89-108">最初の場所で IaaS を必要とするケースを特定します。</span><span class="sxs-lookup"><span data-stu-id="4fd89-108">Determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="4fd89-109">図2-1 では、クラウドインフラストラクチャ対応アプリケーションを最新化成熟度レベルで位置付けます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![クラウドインフラストラクチャ対応アプリケーションの配置](./media/image2-1.png)

> <span data-ttu-id="4fd89-111">**図 2-1**</span><span class="sxs-lookup"><span data-stu-id="4fd89-111">**Figure 2-1.**</span></span> <span data-ttu-id="4fd89-112">クラウドインフラストラクチャ対応アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="4fd89-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="4fd89-113">既存の .NET web アプリケーションを Azure IaaS に移行する理由</span><span class="sxs-lookup"><span data-stu-id="4fd89-113">Why migrate existing .NET web applications to Azure IaaS</span></span>

<span data-ttu-id="4fd89-114">最初の IaaS レベルでもクラウドに移行する主な理由は、コスト削減を実現することです。</span><span class="sxs-lookup"><span data-stu-id="4fd89-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="4fd89-115">より多くの管理されたインフラストラクチャサービスを使用することにより、組織はハードウェアメンテナンス、サーバーまたは VM のプロビジョニングとデプロイ、インフラストラクチャ管理への投資を削減できます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="4fd89-116">アプリをクラウドに移動するかどうかを決定した後、PaaS などのより高度なオプションではなく IaaS を選択する主な理由は、IaaS 環境の方が使い慣れているということです。</span><span class="sxs-lookup"><span data-stu-id="4fd89-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="4fd89-117">現在のオンプレミス環境に似た環境に移行することで、クラウドへの最短のパスを実現する、より低い学習曲線が得られます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="4fd89-118">ただし、クラウドへのパスを最も簡単にすることは、アプリケーションをクラウドで実行することによって最も大きなメリットを得られるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="4fd89-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="4fd89-119">組織では、クラウドに最適化されたクラウドネイティブの成熟度レベルで、クラウドの移行によって最も大きなメリットを得ることができます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud-Optimized and Cloud-Native maturity levels.</span></span>

<span data-ttu-id="4fd89-120">また、アプリケーションが既にクラウドで実行されている場合、IaaS 上でも、アプリケーションの最新化と再設計が容易になることが明らかになりました。</span><span class="sxs-lookup"><span data-stu-id="4fd89-120">It also has become evident that applications are easier to modernize and rearchitect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="4fd89-121">アプリケーションデータの移行は既に完了しています。</span><span class="sxs-lookup"><span data-stu-id="4fd89-121">Application data migration has already been achieved.</span></span> <span data-ttu-id="4fd89-122">また、お客様の組織はクラウドでの作業に必要なスキルを獲得し、"クラウド文化" で稼働させることができます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-122">Also, your organization will have gained skills required for working in the cloud and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="4fd89-123">PaaS ではなく IaaS に移行する場合</span><span class="sxs-lookup"><span data-stu-id="4fd89-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="4fd89-124">次のセクションでは、ほとんどが PaaS プラットフォームとサービスに基づいているクラウド向けに最適化されたアプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4fd89-124">The next sections discuss Cloud-Optimized applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="4fd89-125">これらのアプリでは、クラウドへの移行によって最も大きなメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-125">These apps give you the most benefits from migrating to the cloud.</span></span> 

<span data-ttu-id="4fd89-126">既存のアプリケーションをクラウドに移行するだけの場合は、まず、Azure App Service で実行するために大幅な変更を必要としない既存のアプリケーションを特定します。</span><span class="sxs-lookup"><span data-stu-id="4fd89-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="4fd89-127">これらのアプリは、クラウドに最適化された最初の候補です。</span><span class="sxs-lookup"><span data-stu-id="4fd89-127">These apps should be the first candidates for Cloud-Optimized.</span></span> 

<span data-ttu-id="4fd89-128">その後も、Azure Kubernetes Service などの Windows コンテナーや App Service PaaS に移行できないアプリの場合は、それらを単純な plain Vm (IaaS) に移行します。</span><span class="sxs-lookup"><span data-stu-id="4fd89-128">Then, for the apps that still cannot move to Windows Containers and PaaS such as App Service or orchestrators like Azure Kubernetes Service, migrate those to simple plain VMs (IaaS).</span></span> 

<span data-ttu-id="4fd89-129">ただし、Azure で PaaS サービスを使用する場合と比べて、Vm の構成、セキュリティ保護、およびメンテナンスには、より多くの時間と IT の専門知識が必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4fd89-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="4fd89-130">Azure Virtual Machines を検討している場合は、VM 環境を修正、更新、管理するために必要な継続的なメンテナンス作業を必ず考慮してください。</span><span class="sxs-lookup"><span data-stu-id="4fd89-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="4fd89-131">Azure Virtual Machines は IaaS です。</span><span class="sxs-lookup"><span data-stu-id="4fd89-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="4fd89-132">Azure Migrate を使用して既存のアプリケーションを分析し、Azure に移行する</span><span class="sxs-lookup"><span data-stu-id="4fd89-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="4fd89-133">クラウドへの移行は困難である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4fd89-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="4fd89-134">しかし、多くの組織では、環境を深く可視化し、アプリケーション、ワークロード、データ間の密接な相互依存関係を把握することが困難になっています。</span><span class="sxs-lookup"><span data-stu-id="4fd89-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="4fd89-135">このような可視性がないと、パスの計画が困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4fd89-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="4fd89-136">移行を成功させるために必要な情報の詳細がないと、組織内で適切な会話を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="4fd89-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="4fd89-137">潜在的なコスト上の利点については十分ではありません。また、ワークロードが急激に増加したり、移行を成功させる必要があるかどうかがわかりません。</span><span class="sxs-lookup"><span data-stu-id="4fd89-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="4fd89-138">多くの組織には何もありません。</span><span class="sxs-lookup"><span data-stu-id="4fd89-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="4fd89-139">[Azure Migrate](https://aka.ms/azuremigrate)は、Azure への移行を支援するために必要なガイダンス、洞察、およびメカニズムを提供する新しいサービスです。</span><span class="sxs-lookup"><span data-stu-id="4fd89-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="4fd89-140">Azure Migrate は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4fd89-140">Azure Migrate provides:</span></span>

- <span data-ttu-id="4fd89-141">オンプレミスの仮想マシンの検出と評価</span><span class="sxs-lookup"><span data-stu-id="4fd89-141">Discovery and assessment for on-premises virtual machines</span></span>

- <span data-ttu-id="4fd89-142">多階層アプリケーションの信頼性の高い検出のための組み込みの依存関係マッピング</span><span class="sxs-lookup"><span data-stu-id="4fd89-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

- <span data-ttu-id="4fd89-143">Azure 仮想マシンへのインテリジェントなサイズ変更</span><span class="sxs-lookup"><span data-stu-id="4fd89-143">Intelligent right sizing to Azure virtual machines</span></span>

- <span data-ttu-id="4fd89-144">修復の潜在的な問題に関するガイドラインを含む互換性レポート</span><span class="sxs-lookup"><span data-stu-id="4fd89-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

- <span data-ttu-id="4fd89-145">データベースの検出と移行のための Azure Database Management Service との統合</span><span class="sxs-lookup"><span data-stu-id="4fd89-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="4fd89-146">Azure Migrate を使用すると、ビジネスへの影響を最小限に抑えながら、ワークロードを移行し、Azure で期待どおりに実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="4fd89-147">適切なツールとガイダンスを使用すると、重要なパフォーマンスと信頼性のニーズが満たされていることを確認しながら、投資収益率を最大限に高めることができます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="4fd89-148">図2-2 は、Azure Migrate によって実行されるすべてのサーバーとアプリケーションの接続に対する組み込みの依存関係マッピングを示しています。</span><span class="sxs-lookup"><span data-stu-id="4fd89-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![クラウドインフラストラクチャ対応アプリケーションの配置](./media/image2-2.png)

> <span data-ttu-id="4fd89-150">**図 2-2**</span><span class="sxs-lookup"><span data-stu-id="4fd89-150">**Figure 2-2.**</span></span> <span data-ttu-id="4fd89-151">クラウドインフラストラクチャ対応アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="4fd89-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="4fd89-152">Azure Site Recovery を使用して既存の Vm を Azure Vm に移行する</span><span class="sxs-lookup"><span data-stu-id="4fd89-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="4fd89-153">[Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)は、エンドツーエンドの[Azure Migrate](https://aka.ms/azuremigrate)の一部として、Azure の vm に web アプリを簡単に移行するために使用できるツールです。</span><span class="sxs-lookup"><span data-stu-id="4fd89-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="4fd89-154">Site Recovery を使用して、オンプレミスの Vm と物理サーバーを Azure にレプリケートしたり、オンプレミスのセカンダリの場所にレプリケートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="4fd89-155">サポートされている Azure VM、オンプレミスの*Hyper-v* Vm、 *VMware* VM、または Windows または Linux の物理サーバーで実行されているワークロードをレプリケートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="4fd89-156">Azure へのレプリケーションにより、セカンダリデータセンターを維持するためのコストと複雑さが解消されます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="4fd89-157">Site Recovery は、一部がオンプレミスで、一部が Azure 上にあるハイブリッド環境に対しても特に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="4fd89-158">Site Recovery は、サイトがダウンした場合に、Vm 上で実行されているアプリとオンプレミスの物理サーバーを使用できるようにすることで、ビジネス継続性を確保するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4fd89-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="4fd89-159">Vm と物理サーバーで実行されているワークロードをレプリケートして、プライマリサイトが利用できない場合にセカンダリの場所でも使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4fd89-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="4fd89-160">ワークロードは、起動して再実行されると、プライマリサイトに回復します。</span><span class="sxs-lookup"><span data-stu-id="4fd89-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="4fd89-161">図2-3 は Azure Site Recovery を使用した複数の VM の移行の実行を示しています。</span><span class="sxs-lookup"><span data-stu-id="4fd89-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![クラウドインフラストラクチャ対応アプリケーションの配置](./media/image2-3.png)

> <span data-ttu-id="4fd89-163">**図 2-3.**</span><span class="sxs-lookup"><span data-stu-id="4fd89-163">**Figure 2-3.**</span></span> <span data-ttu-id="4fd89-164">クラウドインフラストラクチャ対応アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="4fd89-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4fd89-165">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="4fd89-165">Additional resources</span></span>

- <span data-ttu-id="4fd89-166">**Azure Migrate データシート**</span><span class="sxs-lookup"><span data-stu-id="4fd89-166">**Azure Migrate Datasheet**</span></span>

    <https://aka.ms/azuremigration\_datasheet>

- <span data-ttu-id="4fd89-167">**Azure Migrate**</span><span class="sxs-lookup"><span data-stu-id="4fd89-167">**Azure Migrate**</span></span>

    <https://aka.ms/azuremigrate>

- <span data-ttu-id="4fd89-168">**Azure Migration Center**</span><span class="sxs-lookup"><span data-stu-id="4fd89-168">**Azure migration center**</span></span>

    <https://azure.microsoft.com/migration/>

- <span data-ttu-id="4fd89-169">**Site Recovery を使用した Azure への移行**</span><span class="sxs-lookup"><span data-stu-id="4fd89-169">**Migrate to Azure with Site Recovery**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- <span data-ttu-id="4fd89-170">**Azure Site Recovery サービスの概要**</span><span class="sxs-lookup"><span data-stu-id="4fd89-170">**Azure Site Recovery service overview**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- <span data-ttu-id="4fd89-171">**AWS 内の Vm の Azure Vm への移行**</span><span class="sxs-lookup"><span data-stu-id="4fd89-171">**Migrating VMs in AWS to Azure VMs**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
><span data-ttu-id="4fd89-172">[前へ](index.md)
>[次へ](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="4fd89-172">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span> <!-- Next Chapter -->
