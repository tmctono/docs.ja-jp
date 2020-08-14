---
title: SOA アプリケーション
description: コンテナーも SOA アプリケーションの便利なデプロイ オプションになる可能性があることを留意してください。
ms.date: 08/06/2020
ms.openlocfilehash: 5cc616eaf3be31ae704320df6ec54deed9529989
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915262"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="3bf89-103">サービス指向アプリケーション</span><span class="sxs-lookup"><span data-stu-id="3bf89-103">Service-oriented applications</span></span>

<span data-ttu-id="3bf89-104">サービス指向アーキテクチャ (SOA) は乱用されている用語であり、人によって異なる意味で使われています。</span><span class="sxs-lookup"><span data-stu-id="3bf89-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="3bf89-105">ただし、共通の基準としての SOA は、アプリケーションのアーキテクチャをサブシステムなどのさまざまな種類、場合によっては階層に分類できるいくつかのサービス (通常は HTTP サービス) に分解して、アプリケーションを構築することを意味します。</span><span class="sxs-lookup"><span data-stu-id="3bf89-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="3bf89-106">現在では、これらのサービスを Docker コンテナーとしてデプロイできます。依存関係のすべてがコンテナー イメージに含まれているため、デプロイ関連の問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="3bf89-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="3bf89-107">ただし、SOA をスケールアウトする必要がある場合、1 つのインスタンスに基づいてデプロイしている場合は課題にぶつかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3bf89-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="3bf89-108">この課題は、Docker クラスタリング ソフトウェアまたはオーケストレーターを使用して対処できます。</span><span class="sxs-lookup"><span data-stu-id="3bf89-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="3bf89-109">次のセクションでは、マイクロサービスのアプローチを説明するときに、オーケストレーターについてさらに詳しく見ていきます。</span><span class="sxs-lookup"><span data-stu-id="3bf89-109">You'll get to look at orchestrators in greater detail in the next section, when you explore microservices approaches.</span></span>

<span data-ttu-id="3bf89-110">Docker コンテナーは、従来のサービス指向アーキテクチャと高度なマイクロサービス アーキテクチャの両方にとって便利な機能です (ただし、必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="3bf89-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="3bf89-111">結局のところ、コンテナー クラスタリング ソリューションは、従来の SOA アーキテクチャと、各マイクロサービスがデータ モデルを所有するより高度なマイクロサービス アーキテクチャの両方に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3bf89-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="3bf89-112">また、複数のデータベースがあるため、SOA サービスで共有されているモノリシック データベースを扱う代わりに、データ層をスケールアウトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3bf89-112">And thanks to multiple databases, you can also scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="3bf89-113">ただし、データの分割に関する説明は、純粋にアーキテクチャと設計に関するものです。</span><span class="sxs-lookup"><span data-stu-id="3bf89-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3bf89-114">[前へ](state-and-data-in-docker-applications.md)
>[次へ](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="3bf89-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
