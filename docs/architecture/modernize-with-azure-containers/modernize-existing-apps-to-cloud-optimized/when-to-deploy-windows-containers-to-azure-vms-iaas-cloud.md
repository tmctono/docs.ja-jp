---
title: Azure Vm (IaaS クラウド) に Windows コンテナーを展開するタイミング
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |Windows コンテナーを Azure Vm にデプロイする場合 (IaaS クラウド)
ms.date: 04/28/2018
ms.openlocfilehash: e9a2903662306b607977a7751018e24161ab80ab
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577905"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="7af43-103">Azure Vm (IaaS クラウド) に Windows コンテナーを展開するタイミング</span><span class="sxs-lookup"><span data-stu-id="7af43-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="7af43-104">組織で Azure Vm を使用している場合は、Windows コンテナーも使用している場合でも、引き続き IaaS を扱うことになります。</span><span class="sxs-lookup"><span data-stu-id="7af43-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="7af43-105">つまり、負荷分散されたインフラストラクチャ内の複数の Vm に展開する必要がある場合は、インフラストラクチャ操作、VM OS パッチ、インフラストラクチャの複雑さを、拡張性の高いアプリケーションのために処理することになります。</span><span class="sxs-lookup"><span data-stu-id="7af43-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="7af43-106">Azure VM で Windows コンテナーを使用する主なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7af43-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

- <span data-ttu-id="7af43-107">**開発/テスト環境**:クラウド内の VM は、クラウドでの開発とテストに最適です。</span><span class="sxs-lookup"><span data-stu-id="7af43-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="7af43-108">必要に応じて、環境を迅速に作成または停止できます。</span><span class="sxs-lookup"><span data-stu-id="7af43-108">You can rapidly create or stop the environment depending on your needs.</span></span>

- <span data-ttu-id="7af43-109">**小規模および中規模のスケーラビリティのニーズ**:運用環境に 2 ~ 3 個の Vm が必要になる場合がありますが、少数の Vm を管理すると、orchestrators ようなより高度な PaaS 環境に移行するまで、低価格になります。</span><span class="sxs-lookup"><span data-stu-id="7af43-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

- <span data-ttu-id="7af43-110">**既存の展開ツールを使用した運用環境**:Vm またはベアメタルサーバー (パペットや同様のツールなど) に複雑なデプロイを行うためのツールに投資しているオンプレミス環境から移行している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7af43-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="7af43-111">運用環境のデプロイ手順に最小限の変更を加えてクラウドに移行するには、引き続きこれらのツールを使用して Azure Vm にデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="7af43-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="7af43-112">ただし、展開の単位として Windows コンテナーを使用して、デプロイのエクスペリエンスを向上させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7af43-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7af43-113">[前へ](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[次へ](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="7af43-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>
