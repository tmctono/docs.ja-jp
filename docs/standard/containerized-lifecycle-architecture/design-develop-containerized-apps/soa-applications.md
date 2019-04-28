---
title: SOA アプリケーション
description: コンテナーが SOA アプリケーションの配置オプションもあることに注意してください。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: ee71873ac15246f979fd2b08d92280ba797ff6ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795404"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="96f95-103">サービス指向アプリケーション</span><span class="sxs-lookup"><span data-stu-id="96f95-103">Service-oriented applications</span></span>

<span data-ttu-id="96f95-104">サービス指向アーキテクチャ (SOA) は、人によって異なる、さまざまなものの過剰使用されている用語をしました。</span><span class="sxs-lookup"><span data-stu-id="96f95-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="96f95-105">しかし、SOA がサブシステムなど、さまざまな種類にまたは他の場合、階層として分類できる (通常 HTTP サービス) としていくつかのサービスに分解して、アプリケーションのアーキテクチャを構築することを意味、共通の基準として。</span><span class="sxs-lookup"><span data-stu-id="96f95-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="96f95-106">今日では、コンテナー イメージの依存関係すべて含まれているため、展開に関連する問題を解決する Docker コンテナーとしてそれらのサービスをデプロイできます。</span><span class="sxs-lookup"><span data-stu-id="96f95-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="96f95-107">ただし、Soa を拡大する必要がある場合、そのに基づいて 1 つのインスタンスをデプロイする場合の課題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96f95-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="96f95-108">この課題は、Docker クラスタ リング ソフトウェアまたはオーケストレーターを使用して処理できます。</span><span class="sxs-lookup"><span data-stu-id="96f95-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="96f95-109">マイクロ サービス アプローチについて説明している場合、次のセクションで詳しくオーケストレーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="96f95-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="96f95-110">Docker コンテナーは、従来のサービス指向アーキテクチャと高度なマイクロサービス アーキテクチャの両方にとって便利な機能です (ただし、必須ではありません)。</span><span class="sxs-lookup"><span data-stu-id="96f95-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="96f95-111">1 日の終わりには、コンテナーのクラスタ リング ソリューションは、両方の従来の SOA アーキテクチャとマイクロ サービスごとにそのデータ モデルが所有するより高度なマイクロ サービス アーキテクチャに便利です。</span><span class="sxs-lookup"><span data-stu-id="96f95-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="96f95-112">複数のデータベースに協力してくれたもスケール アウトできます SOA サービスによって共有モノリシック データベースでの作業ではなく、データ層。</span><span class="sxs-lookup"><span data-stu-id="96f95-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="96f95-113">ただし、データの分割に関する議論は、アーキテクチャと設計についてのみです。</span><span class="sxs-lookup"><span data-stu-id="96f95-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="96f95-114">[前へ](state-and-data-in-docker-applications.md)
>[次へ](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="96f95-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
