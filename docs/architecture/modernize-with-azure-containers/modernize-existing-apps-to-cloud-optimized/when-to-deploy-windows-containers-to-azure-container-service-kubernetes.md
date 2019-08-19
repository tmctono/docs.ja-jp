---
title: Azure Container Service に Windows コンテナーを展開する場合 (つまり、Kubernetes)
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |Azure Container Service に Windows コンテナーを展開する場合 (つまり、Kubernetes)
ms.date: 04/30/2018
ms.openlocfilehash: 903082deba635dd0dfc22d0186fbc589f8d05b92
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577945"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="2cdbd-103">Azure Container Service に Windows コンテナーを展開する場合 (つまり、Kubernetes)</span><span class="sxs-lookup"><span data-stu-id="2cdbd-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="2cdbd-104">Azure Container Service は、Azure 専用の一般的なオープンソースのツールとテクノロジの構成を最適化します。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="2cdbd-105">コンテナーとアプリケーションの構成の両方で移植性を提供するオープンソリューションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="2cdbd-106">サイズ、ホスト数、および orchestrator ツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="2cdbd-107">インフラストラクチャは、Azure Container Service によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="2cdbd-108">Kubernetes、Docker の群れ、DC/OS などのオープンソースのオーケストレーター既に使用している場合は、コンテナーのワークロードをクラウドに移行するために、既存の管理方法を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="2cdbd-109">使い慣れているアプリケーション管理ツールを使用し、任意の orchestrator の標準 API エンドポイントを介して接続します。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="2cdbd-110">Linux Docker コンテナーを使用している場合は、これらのすべてのオーケストレーター成熟した環境になりますが、Windows コンテナーのプレビュー状態のみになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="2cdbd-111">たとえば、Kubernetes では、コンテナーのサポートはネイティブ (ファーストクラスの市民) であるため、Kubernetes で Windows コンテナーを使用することもできます (ACS でのプレビュー版は2018以前)。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="2cdbd-112">重要な注意:AKS (Azure Kubernetes Service) の ACS (Azure Container Service) の進化した "その他の PaaS" バージョンは Kubernetes ですが、Windows コンテナーは2018年2四半期時点ではまだサポートされていませんが、まもなくサポートされる予定です。</span><span class="sxs-lookup"><span data-stu-id="2cdbd-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2cdbd-113">[前へ](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
>[次へ](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="2cdbd-113">[Previous](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
