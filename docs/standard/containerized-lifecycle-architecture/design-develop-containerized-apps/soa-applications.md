---
title: SOA アプリケーション
description: コンテナーが SOA アプリケーションの配置オプションもあることに注意してください。
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644757"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="d7c9a-103">サービス指向アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d7c9a-103">Service-oriented applications</span></span>

<span data-ttu-id="d7c9a-104">サービス指向アーキテクチャ (SOA) は、人によって異なる、さまざまなものの過剰使用されている用語をしました。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="d7c9a-105">しかし、SOA がサブシステムなど、さまざまな種類にまたは他の場合、階層として分類できる (通常 HTTP サービス) としていくつかのサービスに分解して、アプリケーションのアーキテクチャを構築することを意味、共通の基準として。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="d7c9a-106">今日では、コンテナー イメージの依存関係すべて含まれているため、展開に関連する問題を解決する Docker コンテナーとしてそれらのサービスをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="d7c9a-107">ただし、Soa を拡大する必要がある場合、そのに基づいて 1 つのインスタンスをデプロイする場合の課題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="d7c9a-108">この課題は、Docker クラスタ リング ソフトウェアまたはオーケストレーターを使用して処理できます。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="d7c9a-109">マイクロ サービス アプローチについて説明している場合、次のセクションで詳しくオーケストレーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="d7c9a-110">Docker コンテナーは、従来のサービス指向アーキテクチャと高度なマイクロサービス アーキテクチャの両方にとって便利な機能です (ただし、必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="d7c9a-111">1 日の終わりには、コンテナーのクラスタ リング ソリューションは、両方の従来の SOA アーキテクチャとマイクロ サービスごとにそのデータ モデルが所有するより高度なマイクロ サービス アーキテクチャに便利です。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="d7c9a-112">複数のデータベースに協力してくれたもスケール アウトできます SOA サービスによって共有モノリシック データベースでの作業ではなく、データ層。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="d7c9a-113">ただし、データの分割に関する議論は、アーキテクチャと設計についてのみです。</span><span class="sxs-lookup"><span data-stu-id="d7c9a-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d7c9a-114">[前へ](state-and-data-in-docker-applications.md)
>[次へ](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="d7c9a-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
