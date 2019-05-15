---
title: ハイブリッド クラウド シナリオへの移行
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |ハイブリッド クラウドのシナリオへの移行します。
ms.date: 04/30/2018
ms.openlocfilehash: 04c618681c61f5584e641e0a4735e1261ab34fa3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643716"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="36f7e-103">ハイブリッド クラウド シナリオへの移行</span><span class="sxs-lookup"><span data-stu-id="36f7e-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="36f7e-104">一部の組織や企業は、Microsoft Azure などのパブリック クラウドにアプリケーションの一部または規制や独自のポリシーのための他のパブリック クラウドを移行できません。</span><span class="sxs-lookup"><span data-stu-id="36f7e-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="36f7e-105">ただし、すべての組織がパブリック クラウドとその他のアプリケーションをオンプレミスでのアプリケーションの一部がメリットが高くなります。</span><span class="sxs-lookup"><span data-stu-id="36f7e-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="36f7e-106">混在する環境がさまざまなプラットフォームやパブリック クラウドとオンプレミス環境で使用するテクノロジにより環境での過剰な複雑さを招くことができます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="36f7e-107">Microsoft では、最適なハイブリッド クラウド ソリューションを提供する、既存の資産を最適化できますいずれか、オンプレミスとパブリック クラウド中、Azure のハイブリッド クラウドでの一貫性を確保します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="36f7e-108">既存のスキルを最大化し、クラウドまたはオンプレミス、Azure Stack (オンプレミス) と Azure (パブリック クラウド) のおかげで実行できるアプリを構築するための柔軟かつ統合されたアプローチを取得できます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="36f7e-109">セキュリティに関しては、ハイブリッド クラウドの間での管理とセキュリティを一元化できます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="36f7e-110">オンプレミスへのシングル サインオンを提供することで、クラウドにデータ センターからすべての資産の制御を取得し、クラウド アプリできます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="36f7e-111">ために Active Directory、ハイブリッド クラウドを拡張および id 管理を使用して、します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="36f7e-112">最後に、配布しシームレスにデータを分析、クラウドとオンプレミスの資産に対して同じクエリ言語を使用し、適用できます分析とディープ ラーニング、azure にそのソースに関係なく、データを操作します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="36f7e-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="36f7e-113">Azure Stack</span></span>

<span data-ttu-id="36f7e-114">Azure Stack は、ハイブリッド クラウド プラットフォーム、組織のデータ センターから Azure サービスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="36f7e-115">Azure Stack は edge および接続されていない環境では、または特定のセキュリティとコンプライアンス要件を満たすように、主要なシナリオで、最新のアプリケーション用の新しいオプションをサポートするために設計されています。</span><span class="sxs-lookup"><span data-stu-id="36f7e-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="36f7e-116">図 4-13 は、Microsoft が提供する、真のハイブリッド クラウド プラットフォームの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Azure Stack と Azure での Microsoft ハイブリッド クラウド プラットフォーム](./media/image13.jpg)

> <span data-ttu-id="36f7e-118">**図 4-13。**</span><span class="sxs-lookup"><span data-stu-id="36f7e-118">**Figure 4-13.**</span></span> <span data-ttu-id="36f7e-119">Azure Stack と Azure での Microsoft ハイブリッド クラウド プラットフォーム</span><span class="sxs-lookup"><span data-stu-id="36f7e-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="36f7e-120">Azure Stack は、ニーズに合わせて、2 つのデプロイ オプションで提供されています。</span><span class="sxs-lookup"><span data-stu-id="36f7e-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="36f7e-121">Azure Stack 統合システム</span><span class="sxs-lookup"><span data-stu-id="36f7e-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="36f7e-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="36f7e-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="36f7e-123">Azure Stack 統合システム</span><span class="sxs-lookup"><span data-stu-id="36f7e-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="36f7e-124">Azure Stack 統合システムは、Microsoft とハードウェア パートナーのパートナーシップによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="36f7e-125">パートナーシップは、わかりやすくするための管理とのバランスがとれてクラウド歩調のイノベーションを実現するソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="36f7e-126">ハードウェアとソフトウェアの統合システムとして Azure Stack が提供されるため、まだクラウドの革新技術を採用することに適切な量の柔軟性と制御が表示します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="36f7e-127">Azure Stack 統合システムはまでのサイズを 4 から 12 個のノードにあり、ハードウェア パートナーと Microsoft によって共同でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="36f7e-128">Azure Stack 統合システムを使用すると、実稼働ワークロード向けの新しいシナリオを実装します。</span><span class="sxs-lookup"><span data-stu-id="36f7e-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="36f7e-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="36f7e-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="36f7e-130">Microsoft Azure Stack Development Kit は、評価し、Azure Stack の学習に使用できる Azure Stack の単一ノード デプロイです。</span><span class="sxs-lookup"><span data-stu-id="36f7e-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="36f7e-131">Api を使用して開発することができます、Azure と一貫性のあるツールを開発環境として Azure Stack Development Kit を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="36f7e-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="36f7e-132">Azure Stack Development Kit は、運用環境として使用するものではありません。</span><span class="sxs-lookup"><span data-stu-id="36f7e-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="36f7e-133">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="36f7e-133">Additional resources</span></span>

- <span data-ttu-id="36f7e-134">**Azure のハイブリッド クラウド**</span><span class="sxs-lookup"><span data-stu-id="36f7e-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="36f7e-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="36f7e-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="36f7e-136">**Windows コンテナーの active Directory サービス アカウントします。**</span><span class="sxs-lookup"><span data-stu-id="36f7e-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="36f7e-137">**Active Directory のサポートによってコンテナーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="36f7e-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="36f7e-138">**Azure Hybrid Benefit のライセンス**</span><span class="sxs-lookup"><span data-stu-id="36f7e-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="36f7e-139">[前へ](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[次へ](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="36f7e-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
