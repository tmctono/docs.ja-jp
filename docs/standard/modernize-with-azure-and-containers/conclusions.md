---
title: まとめ
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |結論
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 62a9a38ccbe696c34ef799b574c0f5a95bc8f726
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628328"
---
# <a name="conclusions"></a><span data-ttu-id="4e5a8-103">まとめ</span><span class="sxs-lookup"><span data-stu-id="4e5a8-103">Conclusions</span></span>

- <span data-ttu-id="4e5a8-104">コンテナー ベースのソリューションは、最終的にはコスト削減のメリットを提供します。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-104">Container-based solutions ultimately provide cost savings benefits.</span></span> <span data-ttu-id="4e5a8-105">コンテナーは、運用環境での依存関係の欠落によって引き起こされる不整合を削除するための展開に関する問題の解決策です。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-105">Containers are a solution to deployment problems because they remove the friction caused by an absence of dependencies in production environments.</span></span> <span data-ttu-id="4e5a8-106">これらの問題を削除して、開発/テスト、DevOps、および運用操作大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-106">By removing those issues, it improves Dev/Test, DevOps, and production operations significantly.</span></span>

- <span data-ttu-id="4e5a8-107">Docker コンテナーは、サーバー ベースのアプリケーションまたはサービスの配置の標準的な単位になっています。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-107">A Docker container is becoming the standard unit of deployment for any server-based application or service.</span></span>

- <span data-ttu-id="4e5a8-108">運用環境では、拡張性の高い Windows コンテナー ベースのアプリケーションをホストする (Service Fabric、または Kubernetes) などのオーケストレーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-108">For production environments, you should use an orchestrator (like Service Fabric or Kubernetes) to host scalable Windows Containers­­–based applications.</span></span>

- <span data-ttu-id="4e5a8-109">コンテナーをホストする azure Vm は、クラウドで小規模な開発/テスト環境を作成する高速で簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-109">Azure VMs hosting containers are a fast and simple way to create small Dev/Test environments in the cloud.</span></span>

- <span data-ttu-id="4e5a8-110">既存のアプリケーションを Azure から、リレーショナル データベースを移行する場合に、既定で azure SQL Database マネージ インスタンスがお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-110">Azure SQL Database Managed Instance is recommended by default when migrating your relational databases from existing applications to Azure.</span></span>

- <span data-ttu-id="4e5a8-111">Visual Studio 2017 と Image2Docker は、作業の開始の学習曲線を向上させることにより、Windows コンテナーで既存の .NET アプリケーションを最新化を開始するための基本的なツールです。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-111">Visual Studio 2017 and Image2Docker are basic tools for you to start modernizing your existing .NET applications with Windows Containers by accelerating the getting started learning curve.</span></span>

- <span data-ttu-id="4e5a8-112">実稼働環境でコンテナー化されたアプリケーションを配置するときに作成または DevOps の文化と CI/CD パイプラインで、Azure DevOps サービスや Jenkins などの DevOps ツールを採用するは常に。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-112">When placing containerized applications in production you will always create or adopt a DevOps culture and DevOps tools for CI/CD pipelines, like Azure DevOps Services or Jenkins.</span></span>

- <span data-ttu-id="4e5a8-113">Microsoft Azure では、Windows コンテナー、クラウド インフラストラクチャおよび PaaS サービスで、既存の .NET Framework アプリケーションを近代化する最も包括的な完全な環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e5a8-113">Microsoft Azure provides the most comprehensive and complete environment to modernize your existing .NET Framework applications with Windows Containers, cloud infrastructure and PaaS services.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="4e5a8-114">前へ</span><span class="sxs-lookup"><span data-stu-id="4e5a8-114">Previous</span></span>](walkthroughs-technical-get-started-overview.md)