---
title: ハイブリッド クラウド シナリオへの移行
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |ハイブリッドクラウドシナリオへの移行
ms.date: 04/30/2018
ms.openlocfilehash: 5f0819495080bc29ed1239b4a7ab8af31141881b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318469"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="b6ead-103">ハイブリッド クラウド シナリオへの移行</span><span class="sxs-lookup"><span data-stu-id="b6ead-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="b6ead-104">一部の組織や企業では、規制や独自のポリシーによって、アプリケーションの一部を Microsoft Azure やその他のパブリッククラウドに移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="b6ead-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="b6ead-105">ただし、組織によっては、パブリッククラウドやその他のアプリケーションにオンプレミスのアプリケーションを配置することでメリットが得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6ead-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="b6ead-106">ただし、混在環境では、パブリッククラウドとオンプレミス環境の間で使用されるプラットフォームやテクノロジが異なるため、環境が複雑になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b6ead-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="b6ead-107">Microsoft は最適なハイブリッドクラウドソリューションを提供しています。1つは、オンプレミスとパブリッククラウドの既存の資産を最適化しながら、Azure ハイブリッドクラウドの一貫性を確保することです。</span><span class="sxs-lookup"><span data-stu-id="b6ead-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="b6ead-108">Azure Stack (オンプレミス) と Azure (パブリッククラウド) を使用して、クラウドまたはオンプレミスで実行できるアプリを構築するための柔軟で統合されたアプローチを実現できます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="b6ead-109">セキュリティに関しては、ハイブリッドクラウド全体で管理とセキュリティを一元化することができます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="b6ead-110">オンプレミスとクラウドのアプリにシングルサインオンを提供することで、データセンターからクラウドへのすべての資産を制御できます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="b6ead-111">これを実現するには、Active Directory をハイブリッドクラウドに拡張し、id 管理を使用します。</span><span class="sxs-lookup"><span data-stu-id="b6ead-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="b6ead-112">最後に、データをシームレスに分散して分析し、クラウドとオンプレミスの資産に同じクエリ言語を使用し、ソースに関係なく、データを強化するために Azure で分析とディープラーニングを適用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="b6ead-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="b6ead-113">Azure Stack</span></span>

<span data-ttu-id="b6ead-114">Azure Stack は、組織のデータセンターから Azure サービスを提供できるハイブリッドクラウドプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="b6ead-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="b6ead-115">Azure Stack は、エッジ環境や接続されていない環境など、主要なシナリオにおける最新のアプリケーションの新しいオプションをサポートするように設計されています。また、特定のセキュリティ要件やコンプライアンス要件を満たすことができます</span><span class="sxs-lookup"><span data-stu-id="b6ead-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="b6ead-116">図4-13 は、Microsoft が提供する真のハイブリッドクラウドプラットフォームの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6ead-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Azure Stack と Azure を使用した Microsoft ハイブリッドクラウドプラットフォームの図。](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="b6ead-118">**図 4-13.**</span><span class="sxs-lookup"><span data-stu-id="b6ead-118">**Figure 4-13.**</span></span> <span data-ttu-id="b6ead-119">Azure Stack と Azure を使用した Microsoft ハイブリッドクラウドプラットフォーム</span><span class="sxs-lookup"><span data-stu-id="b6ead-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="b6ead-120">Azure Stack は、ニーズに合わせて2つのデプロイオプションで提供されます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="b6ead-121">Azure Stack 統合システム</span><span class="sxs-lookup"><span data-stu-id="b6ead-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="b6ead-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="b6ead-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="b6ead-123">Azure Stack 統合システム</span><span class="sxs-lookup"><span data-stu-id="b6ead-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="b6ead-124">Azure Stack 統合システムは、Microsoft とハードウェアパートナーのパートナーシップを通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="b6ead-125">このパートナーシップにより、管理の簡略化とバランスを取るクラウドペースのイノベーションを提供するソリューションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="b6ead-126">Azure Stack はハードウェアとソフトウェアの統合システムとして提供されているので、クラウドからイノベーションを採用するだけでなく、柔軟性と制御性が適切に得られます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="b6ead-127">Azure Stack 統合システムは、4 ~ 12 のノードのサイズの範囲であり、ハードウェアパートナーと Microsoft によって共同でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b6ead-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="b6ead-128">Azure Stack 統合システムを使用して、運用環境のワークロードに新しいシナリオを実装します。</span><span class="sxs-lookup"><span data-stu-id="b6ead-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="b6ead-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="b6ead-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="b6ead-130">Microsoft Azure Stack Development Kit は、Azure Stack の単一ノードデプロイであり、Azure Stack の評価と学習に使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="b6ead-131">開発環境として Azure Stack Development Kit を使用することもできます。この環境では、Azure と一貫性のある Api とツールを使用して開発できます。</span><span class="sxs-lookup"><span data-stu-id="b6ead-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="b6ead-132">Azure Stack Development Kit は、運用環境として使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="b6ead-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b6ead-133">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="b6ead-133">Additional resources</span></span>

- <span data-ttu-id="b6ead-134">**Azure ハイブリッドクラウド**</span><span class="sxs-lookup"><span data-stu-id="b6ead-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="b6ead-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="b6ead-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="b6ead-136">**Windows コンテナーのサービスアカウントの Active Directory**</span><span class="sxs-lookup"><span data-stu-id="b6ead-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="b6ead-137">**Active Directory サポートを持つコンテナーを作成する**</span><span class="sxs-lookup"><span data-stu-id="b6ead-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="b6ead-138">**Azure ハイブリッド特典ライセンス**</span><span class="sxs-lookup"><span data-stu-id="b6ead-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="b6ead-139">[前へ](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[次へ](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b6ead-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
