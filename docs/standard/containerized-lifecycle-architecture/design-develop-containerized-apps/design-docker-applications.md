---
title: Docker アプリケーションの設計
description: トピックであるためです、マイクロ サービス アーキテクチャに詳しいガイドへの参照を検索ここでは、このガイドでない詳しく説明します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1d49f7509c0a12edfe375486429147e8fd240b2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799347"
---
# <a name="design-docker-applications"></a><span data-ttu-id="e110f-103">Docker アプリケーションの設計</span><span class="sxs-lookup"><span data-stu-id="e110f-103">Design Docker applications</span></span>

<span data-ttu-id="e110f-104">第 1 章には、コンテナーと Docker に関する基本的な概念が導入されました。</span><span class="sxs-lookup"><span data-stu-id="e110f-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="e110f-105">その情報は、開始に必要な情報の基本的なレベルです。</span><span class="sxs-lookup"><span data-stu-id="e110f-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="e110f-106">ただし、1 つのサービスまたはコンテナーではなく複数のサービスで構成され、複雑なエンタープライズ アプリケーションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e110f-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="e110f-107">これらの省略可能なユース ケースでは、オーケストレーションの概念デザイン、サービス指向アーキテクチャ (SOA) より高度なマイクロ サービスの概念とコンテナーに追加の手法を把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e110f-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="e110f-108">このドキュメントのスコープはマイクロ サービスに限定されませんが、Docker アプリケーションのライフ サイクルそのため、ことはできませんを参照してくださいマイクロ サービス アーキテクチャの詳細もコンテナーと Docker を使用して、定期的な SOA、バック グラウンド タスクまたはジョブ、またはできますもためモノリシック アプリケーション展開のアプローチです。</span><span class="sxs-lookup"><span data-stu-id="e110f-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="e110f-109">**詳細については**エンタープライズ アプリケーションとマイクロ サービス アーキテクチャの詳細については、ガイドを読む[NET マイクロ サービス。コンテナー化された .NET アプリケーション アーキテクチャ](../../microservices-architecture/index.md)をからダウンロードすることもできます。<https://aka.ms/MicroservicesEbook>します。</span><span class="sxs-lookup"><span data-stu-id="e110f-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices-architecture/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="e110f-110">ただし、DevOps とアプリケーションのライフ サイクルに入る前に、どのようにしようとしている設計を理解し、アプリケーションと、デザインの選択肢は何を構築を必要があります。</span><span class="sxs-lookup"><span data-stu-id="e110f-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e110f-111">[前へ](index.md)
>[次へ](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="e110f-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>