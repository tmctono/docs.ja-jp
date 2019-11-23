---
title: 監視と正常性
description: 監視と正常性
ms.date: 09/23/2019
ms.openlocfilehash: 6274040318b5442478e9cc291c4f223bdf533110
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73842021"
---
# <a name="monitoring-and-health"></a><span data-ttu-id="6eddc-103">監視と正常性</span><span class="sxs-lookup"><span data-stu-id="6eddc-103">Monitoring and health</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6eddc-104">マイクロサービスとクラウドネイティブアプリケーションは、適切な DevOps プラクティスで手に入ります。</span><span class="sxs-lookup"><span data-stu-id="6eddc-104">Microservices and cloud-native applications go hand in hand with good DevOps practices.</span></span> <span data-ttu-id="6eddc-105">DevOps は多くの人にとって多くのことですが、クラウドの代弁者や DevOps エバンジェリスト Donovan Brown の方が優れた定義の1つです。</span><span class="sxs-lookup"><span data-stu-id="6eddc-105">DevOps is many things to many people but perhaps one of the better definitions comes from cloud advocate and DevOps evangelist Donovan Brown:</span></span>

<span data-ttu-id="6eddc-106">"DevOps は、エンドユーザーに価値を継続的に配信できるようにするための、人、プロセス、製品の和集合です。"</span><span class="sxs-lookup"><span data-stu-id="6eddc-106">"DevOps is the union of people, process, and products to enable continuous delivery of value to our end users."</span></span>

<span data-ttu-id="6eddc-107">残念ながら、簡潔な定義では、さらに多くのことを言う余地があります。</span><span class="sxs-lookup"><span data-stu-id="6eddc-107">Unfortunately, with terse definitions, there's always room to say more things.</span></span> <span data-ttu-id="6eddc-108">DevOps の重要なコンポーネントの1つは、運用環境で実行されているアプリケーションが正しく効率的に機能していることを確認することです。</span><span class="sxs-lookup"><span data-stu-id="6eddc-108">One of the key components of DevOps is ensuring that the applications running in production are functioning properly and efficiently.</span></span> <span data-ttu-id="6eddc-109">運用環境でアプリケーションの正常性を測定するには、サーバー、ホスト、アプリケーションから生成されるさまざまなログとメトリックを適切に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eddc-109">To gauge the health of the application in production, it's necessary to monitor the various logs and metrics being produced from the servers, hosts, and the application proper.</span></span> <span data-ttu-id="6eddc-110">クラウドネイティブアプリケーションのサポートで実行されているさまざまなサービスの数によって、個々のコンポーネントとアプリケーションの正常性を監視することが重要な課題になります。</span><span class="sxs-lookup"><span data-stu-id="6eddc-110">The number of different services running in support of a cloud-native application makes monitoring the health of individual components and the application as a whole a critical challenge.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6eddc-111">[前へ](resilient-communications.md)
>[次へ](observability-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="6eddc-111">[Previous](resilient-communications.md)
[Next](observability-patterns.md)</span></span>
