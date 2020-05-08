---
title: Docker アプリケーションの設計
description: このガイドではマイクロサービスについて詳しく説明していないため、ここでそのトピックについての詳しいガイドへの参照を確認してください。
ms.date: 02/15/2019
ms.openlocfilehash: b8a08658ec6c3df3e1aed596a0240223768dd647
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738462"
---
# <a name="design-docker-applications"></a><span data-ttu-id="220c4-103">Docker アプリケーションの設計</span><span class="sxs-lookup"><span data-stu-id="220c4-103">Design Docker applications</span></span>

<span data-ttu-id="220c4-104">第 1 章では、コンテナーと Docker に関する基本的な概念を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="220c4-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="220c4-105">その情報は、開始するために必要な基本レベルの情報です。</span><span class="sxs-lookup"><span data-stu-id="220c4-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="220c4-106">しかし、エンタープライズ アプリケーションは、複雑で、1 つのサービスやコンテナーではなく、複数のサービスで構成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="220c4-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="220c4-107">こうしたオプションのユース ケースでは、サービス指向アーキテクチャ (SOA) や高度なマイクロサービスの概念とコンテナー オーケストレーションの概念などの追加の設計アプローチを理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="220c4-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="220c4-108">このドキュメントの範囲は、マイクロサービスだけでなく、Docker アプリケーションのライフサイクルにも限定されないので、マイクロサービス アーキテクチャについては詳しく説明しません。通常の SOA、バック グラウンド タスクまたはジョブ、またはモノリシック アプリケーション デプロイ アプローチでもコンテナーや Docker を使用できるためです。</span><span class="sxs-lookup"><span data-stu-id="220c4-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you can also use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="220c4-109">**詳細** エンタープライズ アプリケーションとマイクロサービス アーキテクチャの詳細については、「[.NET マイクロサービス:コンテナー化された .NET アプリケーションのアーキテクチャ](../../microservices/index.md)」ガイドを参照してください。これも <https://aka.ms/MicroservicesEbook> からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="220c4-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="220c4-110">しかし、アプリケーション ライフサイクルと DevOps に進む前に、アプリケーションを設計して構築する方法と、設計の選択肢について理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="220c4-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="220c4-111">[前へ](index.md)
>[次へ](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="220c4-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
