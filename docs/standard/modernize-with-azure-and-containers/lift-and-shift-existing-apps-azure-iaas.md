---
title: リフト アンド既存の .NET アプリを Azure IaaS (クラウド インフラストラクチャの準備完了) にシフト
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 0f9ff19c8e346560960a09d3b7c52976c478f2f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651201"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a><span data-ttu-id="503e1-103">リフト アンド既存の .NET アプリを Azure IaaS (クラウド インフラストラクチャの準備完了) にシフト</span><span class="sxs-lookup"><span data-stu-id="503e1-103">Lift and shift existing .NET apps to Azure IaaS (Cloud Infrastructure-Ready)</span></span>

> <span data-ttu-id="503e1-104">ビジョン:最初の手順として、オンプレミスへの投資とハードウェアやネットワークのメンテナンスの総コストを削減するだけのリホスト、既存のアプリケーションをクラウドで。</span><span class="sxs-lookup"><span data-stu-id="503e1-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="503e1-105">入る前に*方法*a service (IaaS) プラットフォームとして Azure インフラストラクチャに既存のアプリケーションを移行することが理由を分析する重要*なぜ*IaaS に直接移行します。azure。</span><span class="sxs-lookup"><span data-stu-id="503e1-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="503e1-106">この最新化成熟度レベルにあるシナリオは、基本的に、現在のオンプレミス インフラストラクチャの使用を継続するのではなく、クラウドで Vm の使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="503e1-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="503e1-107">分析に別のポイントは*なぜ*を Azure で管理されたサービスをより高度なを追加するだけではなく純粋な IaaS クラウドに移行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="503e1-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="503e1-108">特定のケースで可能性があります、最初に IaaS を必要とします。</span><span class="sxs-lookup"><span data-stu-id="503e1-108">Determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="503e1-109">図 2-1 は、クラウド インフラストラクチャの準備完了アプリケーションを近代化の成熟度レベルで位置します。</span><span class="sxs-lookup"><span data-stu-id="503e1-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![クラウド インフラストラクチャの準備完了アプリケーションの配置](./media/image2-1.png)

> <span data-ttu-id="503e1-111">**図 2-1**</span><span class="sxs-lookup"><span data-stu-id="503e1-111">**Figure 2-1.**</span></span> <span data-ttu-id="503e1-112">クラウド インフラストラクチャの準備完了アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="503e1-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="503e1-113">Azure IaaS への既存の .NET web アプリケーションを移行する理由</span><span class="sxs-lookup"><span data-stu-id="503e1-113">Why migrate existing .NET web applications to Azure IaaS</span></span>

<span data-ttu-id="503e1-114">コストの削減を実現する主な理由は、初期の IaaS レベルでも、クラウドに移行することです。</span><span class="sxs-lookup"><span data-stu-id="503e1-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="503e1-115">その他の管理対象のインフラストラクチャ サービスを使用すると、組織はハードウェアのメンテナンス、サーバーまたは VM のプロビジョニングし展開、およびインフラストラクチャの管理への投資を下げることができます。</span><span class="sxs-lookup"><span data-stu-id="503e1-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="503e1-116">アプリをクラウドに移行する意思決定を行うと、選択する理由が IaaS PaaS が単純にするようより高度なオプションではなく、IaaS 環境の主な理由についての理解になります。</span><span class="sxs-lookup"><span data-stu-id="503e1-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="503e1-117">オンプレミス環境には、現在次のような環境への移動、クラウドに移行する最も簡単なパスを下の学習曲線を提供します。</span><span class="sxs-lookup"><span data-stu-id="503e1-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="503e1-118">ただし、クラウドに移行する最も簡単なパスを取得とは限りませんと、アプリケーションをクラウドで実行されている必要がなくなりますほとんどメリットが得れていること。</span><span class="sxs-lookup"><span data-stu-id="503e1-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="503e1-119">任意の組織には、既に導入された、クラウド最適化とクラウド ネイティブの成熟度レベルのクラウド移行の最も重要な利点を享受できます。</span><span class="sxs-lookup"><span data-stu-id="503e1-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud-Optimized and Cloud-Native maturity levels.</span></span>

<span data-ttu-id="503e1-120">なったアプリケーションが簡単に最新化して、IaaS 上であっても、クラウドで既に実行されている場合、将来再設計が明らかです。</span><span class="sxs-lookup"><span data-stu-id="503e1-120">It also has become evident that applications are easier to modernize and rearchitect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="503e1-121">アプリケーション データの移行は既に実現されています。</span><span class="sxs-lookup"><span data-stu-id="503e1-121">Application data migration has already been achieved.</span></span> <span data-ttu-id="503e1-122">組織をクラウドでの作業に必要なスキルを獲得し、"クラウド culture"で動作させること、shift キーを押しがさらに、</span><span class="sxs-lookup"><span data-stu-id="503e1-122">Also, your organization will have gained skills required for working in the cloud and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="503e1-123">Paas の代わりに IaaS に移行するときに</span><span class="sxs-lookup"><span data-stu-id="503e1-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="503e1-124">次のセクションでは、PaaS プラットフォームおよびサービスに基づくほとんどの場合、クラウドに最適化されたアプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="503e1-124">The next sections discuss Cloud-Optimized applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="503e1-125">これらのアプリを提供するからクラウドへの移行ほとんどメリットです。</span><span class="sxs-lookup"><span data-stu-id="503e1-125">These apps give you the most benefits from migrating to the cloud.</span></span> 

<span data-ttu-id="503e1-126">既存のアプリケーションをクラウドに移行するだけが目的の場合は、まず、Azure App Service で実行する大幅な変更を必要とせず、既存のアプリケーションを特定します。</span><span class="sxs-lookup"><span data-stu-id="503e1-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="503e1-127">これらのアプリが行う最有力候補にする必要がありますクラウドに最適化されました。</span><span class="sxs-lookup"><span data-stu-id="503e1-127">These apps should be the first candidates for Cloud-Optimized.</span></span> 

<span data-ttu-id="503e1-128">アプリをまだことはできませんを移動 Windows コンテナーと PaaS など、App Service または Azure Service Fabric、などのオーケストレーターされた単純なプレーンな Vm (IaaS) に移行します。</span><span class="sxs-lookup"><span data-stu-id="503e1-128">Then, for the apps that still cannot move to Windows Containers and PaaS such as App Service or orchestrators like Azure Service Fabric, migrate those to simple plain VMs (IaaS).</span></span> 

<span data-ttu-id="503e1-129">ただし、正しく構成、セキュリティ保護、および Vm の保守が必要であるさらに多くの時間と IT の専門知識と比較して、Azure で PaaS サービスの使用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="503e1-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="503e1-130">Azure Virtual Machines を検討している場合の修正、更新、および VM 環境を管理するための継続的なメンテナンス労力を考慮することを確認します。</span><span class="sxs-lookup"><span data-stu-id="503e1-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="503e1-131">Azure Virtual Machines は、IaaS です。</span><span class="sxs-lookup"><span data-stu-id="503e1-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="503e1-132">Azure Migrate を使用して分析し、既存のアプリケーションを Azure に移行</span><span class="sxs-lookup"><span data-stu-id="503e1-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="503e1-133">クラウドへの移行は必ずしも難しくはありません。</span><span class="sxs-lookup"><span data-stu-id="503e1-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="503e1-134">多くの組織が、環境とアプリケーション、ワークロード、およびデータ間の緊密な依存関係に詳細な可視性を取得する - 開始するのに苦労します。</span><span class="sxs-lookup"><span data-stu-id="503e1-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="503e1-135">その可視性、なしは、道筋を計画する困難なことができます。</span><span class="sxs-lookup"><span data-stu-id="503e1-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="503e1-136">移行を成功させるために必要な内容の詳細については、なし、組織内で、適切な会話ことはできません。</span><span class="sxs-lookup"><span data-stu-id="503e1-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="503e1-137">考えられる利点、コストの話が不明またはワークロードのだけリフト アンド シフトだったかどうかまたは正常に移行する重要な作業のやり直しが必要になります。</span><span class="sxs-lookup"><span data-stu-id="503e1-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="503e1-138">無理は多くの組織で問題ありません。</span><span class="sxs-lookup"><span data-stu-id="503e1-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="503e1-139">[Azure Migrate](https://aka.ms/azuremigrate)ガイダンス、洞察、および Azure への移行を支援するために必要なメカニズムを提供する新しいサービスです。</span><span class="sxs-lookup"><span data-stu-id="503e1-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="503e1-140">Azure Migrate を提供します。</span><span class="sxs-lookup"><span data-stu-id="503e1-140">Azure Migrate provides:</span></span>

- <span data-ttu-id="503e1-141">検出と、オンプレミスの仮想マシンの評価</span><span class="sxs-lookup"><span data-stu-id="503e1-141">Discovery and assessment for on-premises virtual machines</span></span>

- <span data-ttu-id="503e1-142">多階層アプリケーションの信頼性の高い検出用の組み込みの依存関係マッピング</span><span class="sxs-lookup"><span data-stu-id="503e1-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

- <span data-ttu-id="503e1-143">Azure 仮想マシンへのインテリジェントな適切なサイズ変更</span><span class="sxs-lookup"><span data-stu-id="503e1-143">Intelligent right sizing to Azure virtual machines</span></span>

- <span data-ttu-id="503e1-144">互換性の潜在的な問題を修復するためのガイドラインでレポートの作成</span><span class="sxs-lookup"><span data-stu-id="503e1-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

- <span data-ttu-id="503e1-145">データベースの検出と移行のための Azure Database Management Service との統合</span><span class="sxs-lookup"><span data-stu-id="503e1-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="503e1-146">Azure Migrate では、ワークロードの移行、ビジネスに影響を最小限および Azure で想定どおりに実行できる状況を回避できます。</span><span class="sxs-lookup"><span data-stu-id="503e1-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="503e1-147">適切なツールとガイダンスでは、最大の重要なパフォーマンスを確保しながら投資回収を実現でき、信頼性の要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="503e1-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="503e1-148">図 2-2 では、Azure Migrate によって実行されるすべてのサーバーとアプリケーションの接続の組み込みの依存関係マッピングを示します。</span><span class="sxs-lookup"><span data-stu-id="503e1-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![クラウド インフラストラクチャの準備完了アプリケーションの配置](./media/image2-2.png)

> <span data-ttu-id="503e1-150">**図 2-2 です。**</span><span class="sxs-lookup"><span data-stu-id="503e1-150">**Figure 2-2.**</span></span> <span data-ttu-id="503e1-151">クラウド インフラストラクチャの準備完了アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="503e1-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="503e1-152">Azure Site Recovery を使用して Azure Vm に、既存の Vm を移行するには</span><span class="sxs-lookup"><span data-stu-id="503e1-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="503e1-153">エンド ツー エンドの一部として[Azure Migrate](https://aka.ms/azuremigrate)、 [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)は、web アプリを Azure で Vm を簡単に移行するために使用できるツールです。</span><span class="sxs-lookup"><span data-stu-id="503e1-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="503e1-154">オンプレミスの Vm と物理サーバーを Azure にレプリケートする、またはセカンダリ オンプレミスの場所にこれらをレプリケートするには、Site Recovery を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="503e1-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="503e1-155">オンプレミス上で、サポートされている Azure VM で実行されているワークロードをレプリケートすることもできます*HYPER-V* VM の*VMware* VM、または Windows または Linux の物理サーバー。</span><span class="sxs-lookup"><span data-stu-id="503e1-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="503e1-156">Azure へのレプリケーションでは、コストとセカンダリ データ センターの管理の複雑さがなくなります。</span><span class="sxs-lookup"><span data-stu-id="503e1-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="503e1-157">Site Recovery が部分的であるハイブリッド環境向けでも、オンプレミスと Azure の一部にします。</span><span class="sxs-lookup"><span data-stu-id="503e1-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="503e1-158">Site Recovery により、Vm で実行されているアプリを保持することでビジネス継続性を確保し、オンプレミスで使用可能な物理サーバー、サイトがダウンした場合。</span><span class="sxs-lookup"><span data-stu-id="503e1-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="503e1-159">したまま利用可能なセカンダリの場所にプライマリ サイトが利用できない場合は、Vm と物理サーバーで実行されているワークロードをレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="503e1-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="503e1-160">ワークロードを再実行して、プライマリ サイトが稼働状態を回復します。</span><span class="sxs-lookup"><span data-stu-id="503e1-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="503e1-161">図 2-3 は、Azure Site Recovery を使用して、複数の仮想マシンの移行の実行を示しています。</span><span class="sxs-lookup"><span data-stu-id="503e1-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![クラウド インフラストラクチャの準備完了アプリケーションの配置](./media/image2-3.png)

> <span data-ttu-id="503e1-163">**図 2-3。**</span><span class="sxs-lookup"><span data-stu-id="503e1-163">**Figure 2-3.**</span></span> <span data-ttu-id="503e1-164">クラウド インフラストラクチャの準備完了アプリケーションの配置</span><span class="sxs-lookup"><span data-stu-id="503e1-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="503e1-165">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="503e1-165">Additional resources</span></span>

- <span data-ttu-id="503e1-166">**Azure Migrate のデータシート**</span><span class="sxs-lookup"><span data-stu-id="503e1-166">**Azure Migrate Datasheet**</span></span>

    <https://aka.ms/azuremigration\_datasheet>

- <span data-ttu-id="503e1-167">**Azure Migrate します。**</span><span class="sxs-lookup"><span data-stu-id="503e1-167">**Azure Migrate**</span></span>

    <https://aka.ms/azuremigrate>

- <span data-ttu-id="503e1-168">**Azure 移行センター**</span><span class="sxs-lookup"><span data-stu-id="503e1-168">**Azure migration center**</span></span>

    <https://azure.microsoft.com/migration/>

- <span data-ttu-id="503e1-169">**Site Recovery を使用した Azure への移行します。**</span><span class="sxs-lookup"><span data-stu-id="503e1-169">**Migrate to Azure with Site Recovery**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- <span data-ttu-id="503e1-170">**Azure Site Recovery サービスの概要**</span><span class="sxs-lookup"><span data-stu-id="503e1-170">**Azure Site Recovery service overview**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- <span data-ttu-id="503e1-171">**Azure Vm への aws Vm の移行**</span><span class="sxs-lookup"><span data-stu-id="503e1-171">**Migrating VMs in AWS to Azure VMs**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
><span data-ttu-id="503e1-172">[前へ](index.md)
>[次へ](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="503e1-172">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span>
