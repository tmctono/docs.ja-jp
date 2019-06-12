---
title: コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
ms.date: 05/04/2018
ms.openlocfilehash: 64ae542e006bf7a5d7a0be08fe1cff9770552a77
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833851"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="7324b-103">コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択</span><span class="sxs-lookup"><span data-stu-id="7324b-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="7324b-104">前のセクションを読むことがわかりました、Azure は、複数の選択肢を提供するオープン クラウドです。</span><span class="sxs-lookup"><span data-stu-id="7324b-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="7324b-105">ただし、これも明らかになります、コンテナー化アプリケーションを使用する必要があります製品/テクノロジに関する質問、ニーズに最適を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7324b-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="7324b-106">として、*既定*、推奨事項を次にこのガイドで推奨されている主要な基準。</span><span class="sxs-lookup"><span data-stu-id="7324b-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="7324b-107">**1 つのモノリシック アプリ:** Azure App Service を選択します。</span><span class="sxs-lookup"><span data-stu-id="7324b-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="7324b-108">**N 層アプリ:** 1 つまたはいくつかのバックエンド サービスがある場合は、Azure Kubernetes Service (AKS) または App Service などのオーケストレーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="7324b-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="7324b-109">**マイクロ サービス:** AKS または Azure Web アプリ コンテナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7324b-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="7324b-110">**サーバーレス関数 (&) のイベント ハンドラー:** Azure Functions を選択します。</span><span class="sxs-lookup"><span data-stu-id="7324b-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="7324b-111">**大規模なバッチの場合:** Azure Batch を選択します。</span><span class="sxs-lookup"><span data-stu-id="7324b-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="7324b-112">製品の選択は、特定のアプリケーションのニーズと特性に依存するようにこの推奨事項にわずかな salt、従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7324b-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="7324b-113">すべてのアプリケーションは、最初に類似した種類を検索する場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="7324b-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="7324b-114">さらに詳しく分析のアプリケーションのニーズに応じて、後に選択されている製品が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7324b-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="7324b-115">評価を開始からの初期のガイダンスもよいが、開始点として、特定の優先順位に基づくテストします。</span><span class="sxs-lookup"><span data-stu-id="7324b-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="7324b-116">次の図には、アプリとホスティングのシナリオに最適ですが Azure のさまざまな種類の内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7324b-116">In the next figure, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="7324b-117">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [次へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="7324b-117">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
