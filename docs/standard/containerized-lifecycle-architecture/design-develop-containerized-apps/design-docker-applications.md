---
title: Docker アプリケーションを設計します。
description: トピックであるためです、マイクロ サービス アーキテクチャに詳しいガイドへの参照を検索ここでは、このガイドでない詳しく説明します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 858147883b3b4a5a5f487856028fdbfa84f6cca9
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675187"
---
# <a name="design-docker-applications"></a><span data-ttu-id="66bf8-103">Docker アプリケーションを設計します。</span><span class="sxs-lookup"><span data-stu-id="66bf8-103">Design Docker applications</span></span>

<span data-ttu-id="66bf8-104">第 1 章には、コンテナーと Docker に関する基本的な概念が導入されました。</span><span class="sxs-lookup"><span data-stu-id="66bf8-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="66bf8-105">その情報は、開始に必要な情報の基本的なレベルです。</span><span class="sxs-lookup"><span data-stu-id="66bf8-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="66bf8-106">ただし、1 つのサービスまたはコンテナーではなく複数のサービスで構成され、複雑なエンタープライズ アプリケーションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="66bf8-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="66bf8-107">これらの省略可能なユース ケースでは、オーケストレーションの概念デザイン、サービス指向アーキテクチャ (SOA) より高度なマイクロ サービスの概念とコンテナーに追加の手法を把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66bf8-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="66bf8-108">このドキュメントのスコープはマイクロ サービスに限定されませんが、Docker アプリケーションのライフ サイクルそのため、ことはできませんを参照してくださいマイクロ サービス アーキテクチャの詳細もコンテナーと Docker を使用して、定期的な SOA、バック グラウンド タスクまたはジョブ、またはできますもためモノリシック アプリケーション展開のアプローチです。</span><span class="sxs-lookup"><span data-stu-id="66bf8-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="66bf8-109">**詳細については**エンタープライズ アプリケーションとマイクロ サービス アーキテクチャの詳細については、ガイドを読む[NET マイクロ サービス。コンテナー化された .NET アプリケーション アーキテクチャ](https://docs.microsoft.com/dotnet/standard/microservices-architecture)をからダウンロードすることもできます。<https://aka.ms/MicroservicesEbook>します。</span><span class="sxs-lookup"><span data-stu-id="66bf8-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="66bf8-110">ただし、DevOps とアプリケーションのライフ サイクルに入る前に、どのようにしようとしている設計を理解し、アプリケーションと、デザインの選択肢は何を構築を必要があります。</span><span class="sxs-lookup"><span data-stu-id="66bf8-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="66bf8-111">[前へ](index.md)
>[次へ](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="66bf8-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>
