---
title: Azure Container Service (Kubernetes) に Windows コンテナーをデプロイするタイミング
description: Azure Cloud と Windows コンテナーで既存の .NET アプリケーションを最新化する | Azure コンテナー サービス (Kubernetes) に Windows コンテナーをデプロイするタイミング
ms.date: 04/30/2018
ms.openlocfilehash: 3ff51a70d4e158b831155ab4992ec32f5d98cedb
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987765"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="29436-103">Azure Container Service (Kubernetes) に Windows コンテナーをデプロイするタイミング</span><span class="sxs-lookup"><span data-stu-id="29436-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="29436-104">Azure Container Service では、一般的なオープンソース ツールとテクノロジの構成を Azure 専用に最適化します。</span><span class="sxs-lookup"><span data-stu-id="29436-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="29436-105">コンテナーとアプリケーションの構成の両方に移植性を提供するオープン ソリューションが得られます。</span><span class="sxs-lookup"><span data-stu-id="29436-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="29436-106">ユーザーはサイズ、ホストの数、オーケストレーター ツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="29436-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="29436-107">インフラストラクチャはユーザーの代わりに Azure Container Service が処理します。</span><span class="sxs-lookup"><span data-stu-id="29436-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="29436-108">Kubernetes、Docker Swarm、DC/OS など、オープンソースのオーケストレーターを既に使用している場合、コンテナー ワークロードをクラウドに移行する今までの管理方法を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29436-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="29436-109">既に精通している任意のアプリケーション管理ツールを使用し、選択したオーケストレーター用の標準 API エンドポイント経由で接続します。</span><span class="sxs-lookup"><span data-stu-id="29436-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="29436-110">Linux Docker コンテナーを使用している場合、このようなオーケストレーターはすべて成熟した環境になりますが、Windows コンテナーの場合、プレビュー状態に限られることがあります。</span><span class="sxs-lookup"><span data-stu-id="29436-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="29436-111">たとえば、Kubernetes の場合、コンテナーのサポートはネイティブです (第一級市民)。そのため、Kubernetes で Windows コンテナーを使用することは有効です (2018 年の早い時期から ACS でプレビュー)。</span><span class="sxs-lookup"><span data-stu-id="29436-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="29436-112">重要な注意事項:Kubernetes の ACS (Azure Container Service) の進化した "PaaS に近い" バージョンが AKS (Azure Kubernetes Service) です。ただし、Windows コンテナーは 2018 年の Q2 以降でもサポートされておりません。近日中にサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="29436-112">Important note: The evolved and "more PaaS" version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="29436-113">[前へ](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[次へ](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="29436-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
