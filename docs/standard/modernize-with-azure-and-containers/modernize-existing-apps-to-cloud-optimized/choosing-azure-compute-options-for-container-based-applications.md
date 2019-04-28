---
title: コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/04/2018
ms.openlocfilehash: f251aecfeaf2421a5cecf218577369963bc736fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61811760"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="fba7f-103">コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択</span><span class="sxs-lookup"><span data-stu-id="fba7f-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="fba7f-104">前のセクションを読むことがわかりました、Azure は、複数の選択肢を提供するオープン クラウドです。</span><span class="sxs-lookup"><span data-stu-id="fba7f-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="fba7f-105">ただし、これも明らかになります、コンテナー化アプリケーションを使用する必要があります製品/テクノロジに関する質問、ニーズに最適を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fba7f-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="fba7f-106">として、*既定*、推奨事項を次にこのガイドで推奨されている主要な基準。</span><span class="sxs-lookup"><span data-stu-id="fba7f-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="fba7f-107">**1 つのモノリシック アプリ:** Azure App Service を選択します。</span><span class="sxs-lookup"><span data-stu-id="fba7f-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="fba7f-108">**N 層アプリ:** 1 つまたはいくつかのバックエンド サービスがある場合は、Azure Kubernetes Service (AKS)、Service Fabric (SF) または App Service などのオーケストレーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="fba7f-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS), Service Fabric (SF) or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="fba7f-109">**Linux のマイクロ サービス:** AKS と Kubernetes を選択します。</span><span class="sxs-lookup"><span data-stu-id="fba7f-109">**Linux microservices:** Choose AKS/Kubernetes</span></span>
- <span data-ttu-id="fba7f-110">**Windows のマイクロ サービス:** Service Fabric を選択します。</span><span class="sxs-lookup"><span data-stu-id="fba7f-110">**Windows microservices:** Choose Service Fabric</span></span>
- <span data-ttu-id="fba7f-111">**サーバーレス関数 (&) のイベント ハンドラー:** Azure Functions を選択します。</span><span class="sxs-lookup"><span data-stu-id="fba7f-111">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="fba7f-112">**大規模なバッチの場合:** Azure Batch を選択します。</span><span class="sxs-lookup"><span data-stu-id="fba7f-112">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="fba7f-113">製品の選択は、特定のアプリケーションのニーズと特性に依存するようにこの推奨事項にわずかな salt、従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fba7f-113">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="fba7f-114">すべてのアプリケーションは、最初に類似した種類を検索する場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="fba7f-114">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="fba7f-115">さらに詳しく分析のアプリケーションのニーズに応じて、後に選択されている製品が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fba7f-115">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="fba7f-116">評価を開始からの初期のガイダンスもよいが、開始点として、特定の優先順位に基づくテストします。</span><span class="sxs-lookup"><span data-stu-id="fba7f-116">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="fba7f-117">次の図より詳細な意思決定テーブル中にグローバルを分析できます。</span><span class="sxs-lookup"><span data-stu-id="fba7f-117">In the next figure, you can analyze a more global while detailed decision table.</span></span>

![](./media/image8.5.png)

<span data-ttu-id="fba7f-118">通知方法 (Windows と OS の基になります。Linux) では、一部のオーケストレーターはより完成度の高い Linux コンテナーやその他の Windows コンテナーで、意思決定係数こともできます。</span><span class="sxs-lookup"><span data-stu-id="fba7f-118">Notice how the underlying OS (Windows vs. Linux) can also be a decision factor as some orchestrators are more mature on Linux containers and other on Windows containers.</span></span> <span data-ttu-id="fba7f-119">たとえば、Linux コンテナーでは、Service Fabric では未完成ですが、Kubernetes (Azure での AKS) で非常に成熟しました。</span><span class="sxs-lookup"><span data-stu-id="fba7f-119">For instance, Linux containers are very mature in Kubernetes (AKS in Azure) but less mature on Service Fabric.</span></span> <span data-ttu-id="fba7f-120">その一方で、Windows コンテナーは、(2017 年 5 月にリリースされた) Service Fabric でさらに成熟した AKS では未完成です。</span><span class="sxs-lookup"><span data-stu-id="fba7f-120">On the other hand, Windows Containers are more mature in Service Fabric (released in May 2017) and less mature in AKS.</span></span>

<span data-ttu-id="fba7f-121">ただし、OS の成熟度でそれらの相違点は今後のフェードインし複数のプラットフォームは比較可能な OS の成熟度られ、意思決定をアプリケーションが必要になるか、各プラットフォームのエコシステムに基づく特定の機能に基づく基本設定の詳細に配置されます。理由があります。</span><span class="sxs-lookup"><span data-stu-id="fba7f-121">However, those differences in OS maturity will fade in the future and multiple platforms will have comparable OS maturity and the decision will lay more on preferences based on specific features your application might need or based on each platform's ecosystem reasons.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="fba7f-122">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [次へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="fba7f-122">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
