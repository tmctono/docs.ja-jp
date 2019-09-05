---
title: Docker 実稼働環境の実行、管理、および監視
description: Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル
ms.date: 02/15/2019
ms.openlocfilehash: 900c361d5604f7fdaf41613287aa48c5381a9af7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295031"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a><span data-ttu-id="48936-103">Docker 実稼働環境の実行、管理、および監視</span><span class="sxs-lookup"><span data-stu-id="48936-103">Run, manage, and monitor Docker production environments</span></span>

<span data-ttu-id="48936-104">展望:エンタープライズ アプリケーションは可用性と拡張性が高い状態で実行する必要があります。IT 運用チームは、環境とアプリケーション自体を管理および監視できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="48936-104">Vision: Enterprise applications need to run with high availability and high scalability; IT operations need to be able to manage and monitor the environments and the applications themselves.</span></span>

<span data-ttu-id="48936-105">コンテナー化された Docker アプリケーションのライフ サイクルのこの最後の柱の焦点は、拡張性と可用性の高い (HA) 実稼働環境で、アプリケーションをどのように実行、管理、および監視するかです。</span><span class="sxs-lookup"><span data-stu-id="48936-105">This last pillar in the containerized Docker applications life cycle is centered on how you can run, manage, and monitor your applications in scalable, high availability (HA) production environments.</span></span>

<span data-ttu-id="48936-106">実稼働環境 (インフラストラクチャ アーキテクチャとプラットフォーム テクノロジ) でコンテナー化アプリケーションを実行する方法は、この電子書籍の第 1 章で取り上げた、選択したアーキテクチャと開発プラットフォームに非常に関連しており、基礎としています。</span><span class="sxs-lookup"><span data-stu-id="48936-106">The way you run your containerized applications in production (infrastructure architecture and platform technologies) is very much related and based on the chosen architecture and development platforms discussed in Chapter 1 of this e-book.</span></span>

<span data-ttu-id="48936-107">この章では、拡張性の高い、HA 分散アプリケーションを効率的に実行するために使用できる、Microsoft と他のベンダーの特定の製品と技術を確認します。それに加え、IT の観点からどのようにそれを管理し、監視するか検証します。</span><span class="sxs-lookup"><span data-stu-id="48936-107">This chapter examines specific products and technologies from Microsoft and other vendors that you can use to effectively run scalable, HA distributed applications plus how you can manage and monitor them from the IT perspective.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="48936-108">[前へ](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
>[次へ](run-microservices-based-applications-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="48936-108">[Previous](../docker-devops-workflow/create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
[Next](run-microservices-based-applications-in-production.md)</span></span>
