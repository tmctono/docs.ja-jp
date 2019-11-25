---
title: コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
description: Azure Cloud および Windows コンテナーで既存の .NET アプリケーションを最新化する |コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
ms.date: 05/04/2018
ms.openlocfilehash: 079c9c5ca02b6dc75214d63cb59afdead03d3190
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2019
ms.locfileid: "73737001"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="882d1-103">コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択</span><span class="sxs-lookup"><span data-stu-id="882d1-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="882d1-104">前のセクションを読まれたらお気づきのように、Azure は複数の選択肢を提供するオープン クラウドです。</span><span class="sxs-lookup"><span data-stu-id="882d1-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="882d1-105">ニーズに最適なものを使用できますが、ここにはコンテナー化されたアプリケーションに使用する製品やテクノロジに関する質問も表示されます。</span><span class="sxs-lookup"><span data-stu-id="882d1-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="882d1-106">*既定の*推奨事項として、このガイダンスで推奨される主な条件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="882d1-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="882d1-107">**単一モノリシック アプリ:** Azure App Service を選ぶ</span><span class="sxs-lookup"><span data-stu-id="882d1-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="882d1-108">**n 層アプリ:** バックエンド サービスが 1 つまたは少数の場合は、Azure Kubernetes Service (AKS) や App Service などのオーケストレーターを選択する</span><span class="sxs-lookup"><span data-stu-id="882d1-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS) or App Service if you have a single or a few back-end services</span></span>
- <span data-ttu-id="882d1-109">**マイクロサービス:** AKS または Azure Web Apps for Containers を選ぶ</span><span class="sxs-lookup"><span data-stu-id="882d1-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="882d1-110">**サーバーレス関数とイベント ハンドラー:** Azure Functions を選ぶ</span><span class="sxs-lookup"><span data-stu-id="882d1-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="882d1-111">**大規模なバッチ:** Azure Batch を選ぶ</span><span class="sxs-lookup"><span data-stu-id="882d1-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="882d1-112">しかし、この推奨事項は、特定のアプリケーションのニーズと特性によって製品の選択が異なるため、完全には信じないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="882d1-112">However, this recommendation should be taken with a pinch of salt, as the product's selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="882d1-113">すべてのアプリケーションが同様の種類のように見えても、すべてが同じというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="882d1-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="882d1-114">アプリケーションのニーズをより詳しく分析した後、選択した製品が違っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="882d1-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="882d1-115">しかし、出発点として、特定の優先順位に基づいて評価とテストを開始できる最初のガイダンスを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="882d1-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="882d1-116">図 1 では、さまざまな種類のアプリの内訳と Azure ホスティングの理想的なシナリオを確認できます。</span><span class="sxs-lookup"><span data-stu-id="882d1-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![さまざまなアプリに最適な Azure ホスティング シナリオの表。](./media/choosing-azure-compute-options-for-container-based-applications/azure-hosting-scenarios-for-apps.png)

> [!div class="step-by-step"]
> <span data-ttu-id="882d1-118">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [次へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="882d1-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
