---
title: まとめ
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |わかり
ms.date: 10/26/2017
ms.openlocfilehash: c7c4042b224577238ae74bd786d4803e487998e7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578485"
---
# <a name="conclusions"></a><span data-ttu-id="635d4-103">まとめ</span><span class="sxs-lookup"><span data-stu-id="635d4-103">Conclusions</span></span>

- <span data-ttu-id="635d4-104">コンテナーベースのソリューションでは、最終的にコストの節約効果が得られます。</span><span class="sxs-lookup"><span data-stu-id="635d4-104">Container-based solutions ultimately provide cost savings benefits.</span></span> <span data-ttu-id="635d4-105">コンテナーは、運用環境での依存関係の欠如によって生じる摩擦を取り除くため、デプロイの問題に対するソリューションです。</span><span class="sxs-lookup"><span data-stu-id="635d4-105">Containers are a solution to deployment problems because they remove the friction caused by an absence of dependencies in production environments.</span></span> <span data-ttu-id="635d4-106">これらの問題を削除することで、開発/テスト、DevOps、運用の各操作が大幅に改善されます。</span><span class="sxs-lookup"><span data-stu-id="635d4-106">By removing those issues, it improves Dev/Test, DevOps, and production operations significantly.</span></span>

- <span data-ttu-id="635d4-107">Docker コンテナーは、サーバー ベースのアプリケーションまたはサービスの配置の標準的な単位になっています。</span><span class="sxs-lookup"><span data-stu-id="635d4-107">A Docker container is becoming the standard unit of deployment for any server-based application or service.</span></span>

- <span data-ttu-id="635d4-108">運用環境では、orchestrator (Kubernetes など) を使用して、スケーラブルなコンテナーベースのアプリケーションをホストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="635d4-108">For production environments, you should use an orchestrator (like Kubernetes) to host scalable containers­­–based applications.</span></span>

- <span data-ttu-id="635d4-109">コンテナーをホストする Azure Vm は、小規模な開発/テスト環境をクラウドに作成するための迅速で簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="635d4-109">Azure VMs hosting containers are a fast and simple way to create small Dev/Test environments in the cloud.</span></span>

- <span data-ttu-id="635d4-110">既存のアプリケーションから Azure にリレーショナルデータベースを移行する場合、既定では Azure SQL Database Managed Instance が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="635d4-110">Azure SQL Database Managed Instance is recommended by default when migrating your relational databases from existing applications to Azure.</span></span>

- <span data-ttu-id="635d4-111">Visual Studio 2017 と Image2Docker は、Windows コンテナーで既存の .NET アプリケーションの最新化を開始するための基本的なツールです。これには、作業の開始に関する曲線を加速させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="635d4-111">Visual Studio 2017 and Image2Docker are basic tools for you to start modernizing your existing .NET applications with Windows Containers by accelerating the getting started learning curve.</span></span>

- <span data-ttu-id="635d4-112">コンテナー化されたアプリケーションを運用環境に配置するときは、Azure DevOps Services や Jenkins のように、CI/CD パイプライン用の DevOps カルチャと DevOps ツールを常に作成または採用します。</span><span class="sxs-lookup"><span data-stu-id="635d4-112">When placing containerized applications in production you will always create or adopt a DevOps culture and DevOps tools for CI/CD pipelines, like Azure DevOps Services or Jenkins.</span></span>

- <span data-ttu-id="635d4-113">Microsoft Azure は、Windows コンテナー、クラウドインフラストラクチャ、PaaS サービスを使用して既存の .NET Framework アプリケーションを最新化するための最も包括的で完全な環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="635d4-113">Microsoft Azure provides the most comprehensive and complete environment to modernize your existing .NET Framework applications with Windows Containers, cloud infrastructure and PaaS services.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="635d4-114">前へ</span><span class="sxs-lookup"><span data-stu-id="635d4-114">Previous</span></span>](walkthroughs-technical-get-started-overview.md)
