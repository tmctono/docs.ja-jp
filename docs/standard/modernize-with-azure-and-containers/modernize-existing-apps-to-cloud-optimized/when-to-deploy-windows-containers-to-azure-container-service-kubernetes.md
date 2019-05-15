---
title: Azure Container Service (つまり Kubernetes) に Windows コンテナーを展開するタイミング
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |Azure Container Service (つまり Kubernetes) に Windows コンテナーを展開するタイミング
ms.date: 04/30/2018
ms.openlocfilehash: 921767b52f2b0d80f2d31d972b65ac7551d2f7c5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643571"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a><span data-ttu-id="db3dd-103">Azure Container Service (つまり Kubernetes) に Windows コンテナーを展開するタイミング</span><span class="sxs-lookup"><span data-stu-id="db3dd-103">When to deploy Windows Containers to Azure Container Service (that is, Kubernetes)</span></span>

<span data-ttu-id="db3dd-104">Azure Container Service では、Azure 向けに人気のあるオープン ソース ツールとテクノロジの構成を最適化します。</span><span class="sxs-lookup"><span data-stu-id="db3dd-104">Azure Container Service optimizes the configuration of popular open-source tools and technologies specifically for Azure.</span></span> <span data-ttu-id="db3dd-105">コンテナーと、アプリケーションの構成の両方の移植性を提供する、開いているソリューションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db3dd-105">You get an open solution that offers portability both for your containers and for your application configuration.</span></span> <span data-ttu-id="db3dd-106">サイズ、ホスト数およびオーケストレーション ツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="db3dd-106">You select the size, the number of hosts, and the orchestrator tools.</span></span> <span data-ttu-id="db3dd-107">Azure Container Service では、インフラストラクチャを処理します。</span><span class="sxs-lookup"><span data-stu-id="db3dd-107">Azure Container Service handles the infrastructure for you.</span></span>

<span data-ttu-id="db3dd-108">Kubernetes、Docker Swarm、DC/OS などのオープン ソース オーケストレーターを使用して既に場合、は、コンテナー ワークロードをクラウドに移動する、既存の管理方法を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db3dd-108">If you are already working with open-source orchestrators like Kubernetes, Docker Swarm, or DC/OS, you don't need to change your existing management practices to move container workloads to the cloud.</span></span> <span data-ttu-id="db3dd-109">使い慣れているアプリケーションの管理ツールを使用し、好みの orchestrator の標準 API エンドポイント経由で接続します。</span><span class="sxs-lookup"><span data-stu-id="db3dd-109">Use the application management tools that you're already familiar with and connect via the standard API endpoints for the orchestrator of your choice.</span></span>

<span data-ttu-id="db3dd-110">これらすべてのオーケストレーターは、Linux Docker コンテナーなどを使用している Windows コンテナー用のプレビュー状態である可能性がありますのみ場合の完成度の高い環境です。</span><span class="sxs-lookup"><span data-stu-id="db3dd-110">All these orchestrators are mature environments if you are using Linux Docker containers, but might only be in Preview state for Windows Containers.</span></span>

<span data-ttu-id="db3dd-111">たとえば、Kubernetes では、サポートのコンテナーは Kubernetes で Windows コンテナーを使用してネイティブ (優良市民) も (2018 年初頭の時点で、ACS でプレビュー) で効果的です。</span><span class="sxs-lookup"><span data-stu-id="db3dd-111">For example, in Kubernetes, support for containers is native (first-class citizen), so using Windows Containers on Kubernetes is also effective (in preview in ACS as of early 2018).</span></span>

<span data-ttu-id="db3dd-112">重要な注意事項:進化、および"以上の PaaS"Kubernetes 用 ACS (Azure Container Service) のバージョンは、AKS (Azure Kubernetes Service)、ただし、Windows コンテナーはまだサポートされていません、第 2 四半期 2018 がまもなくサポートされます。</span><span class="sxs-lookup"><span data-stu-id="db3dd-112">Important note: The evolved and “more PaaS” version of ACS (Azure Container Service) for Kubernetes is AKS (Azure Kubernetes Service), however, Windows Containers are still not supported as of Q2 2018, but it will be supported soon.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="db3dd-113">[前へ](when-to-deploy-windows-containers-to-service-fabric.md)
>[次へ](choosing-azure-compute-options-for-container-based-applications.md)</span><span class="sxs-lookup"><span data-stu-id="db3dd-113">[Previous](when-to-deploy-windows-containers-to-service-fabric.md)
[Next](choosing-azure-compute-options-for-container-based-applications.md)</span></span>
