---
title: コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |コンテナーベースのアプリケーションのための Azure コンピューティングプラットフォームの選択
ms.date: 05/04/2018
ms.openlocfilehash: 54c5945326fb8a50a39c50552a413580926da2c7
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331965"
---
# <a name="choosing-azure-compute-platforms-for-container-based-applications"></a><span data-ttu-id="cab40-103">コンテナー ベース アプリケーション用の Azure コンピューティング プラットフォームの選択</span><span class="sxs-lookup"><span data-stu-id="cab40-103">Choosing Azure compute platforms for container-based applications</span></span>

<span data-ttu-id="cab40-104">前のセクションを読んだ後、Azure は複数の選択肢を提供するオープンクラウドです。</span><span class="sxs-lookup"><span data-stu-id="cab40-104">As you have noticed after reading the previous sections, Azure is an open cloud that offers multiple choices.</span></span> <span data-ttu-id="cab40-105">ニーズに最適なものを使用できますが、コンテナー化されたアプリケーションに使用する製品やテクノロジに関する質問も表示されます。</span><span class="sxs-lookup"><span data-stu-id="cab40-105">You can use the best fit for your needs, however, it also surfaces questions about what product/technology you should use for your containerized applications.</span></span>

<span data-ttu-id="cab40-106">*既定*の推奨事項として、このガイダンスで推奨される主な基準は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cab40-106">As a *by-default* recommendation, the following is the main criteria recommended in this guidance:</span></span>

- <span data-ttu-id="cab40-107">**単一モノリシックアプリ:** Azure App Service の選択</span><span class="sxs-lookup"><span data-stu-id="cab40-107">**Single monolithic app:** Choose Azure App Service</span></span>
- <span data-ttu-id="cab40-108">**N 層アプリ:** バックエンドサービスが1つでも少ない場合でも、Azure Kubernetes Service (AKS) や App Service などのオーケストレーター選択できます。</span><span class="sxs-lookup"><span data-stu-id="cab40-108">**N-Tier app:** Choose orchestrators such as Azure Kubernetes Service (AKS)or App Service if you have a single or few back-end services</span></span>
- <span data-ttu-id="cab40-109">**マイクロサービス**コンテナーに対して AKS または Azure Web Apps を選択する</span><span class="sxs-lookup"><span data-stu-id="cab40-109">**Microservices:** Choose AKS or Azure Web Apps for Containers</span></span>
- <span data-ttu-id="cab40-110">**サーバーレス関数 & イベントハンドラー:** Azure Functions の選択</span><span class="sxs-lookup"><span data-stu-id="cab40-110">**Serverless functions & event handlers:** Choose Azure Functions</span></span>
- <span data-ttu-id="cab40-111">**大規模なバッチ:** Azure Batch の選択</span><span class="sxs-lookup"><span data-stu-id="cab40-111">**Large-scale Batch:** Choose Azure Batch</span></span>

<span data-ttu-id="cab40-112">ただし、この推奨事項は、特定のアプリケーションのニーズと特性に応じて製品の選択が変化するため、salt のピンチを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cab40-112">However, this recommendation should be taken with a pinch of salt, as the product’s selection will depend on your specific application’s needs and characteristics.</span></span> <span data-ttu-id="cab40-113">すべてのアプリケーションが同じであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="cab40-113">Not all applications are the same even when initially they might look similar types.</span></span>

<span data-ttu-id="cab40-114">アプリケーションのニーズをより詳しく分析した後、選択された製品が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cab40-114">After a deeper analysis of the application’s needs, the product selected could be different.</span></span> <span data-ttu-id="cab40-115">ただし、出発点として、特定の優先順位に基づいて評価とテストを開始できる最初のガイダンスを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cab40-115">But, as a starting point, it is good to have initial guidance from where you can start evaluating and testing based on certain priority.</span></span>

<span data-ttu-id="cab40-116">図1では、さまざまな種類のアプリの内訳と、Azure ホスティングの理想的なシナリオを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cab40-116">In Figure 1, you can see a breakdown of different kinds of apps and their ideal Azure hosting scenarios.</span></span>

![図 1](./media/image8.5.png)

> [!div class="step-by-step"]
> <span data-ttu-id="cab40-118">[前へ](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
> [次へ](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="cab40-118">[Previous](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Next](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)</span></span>
