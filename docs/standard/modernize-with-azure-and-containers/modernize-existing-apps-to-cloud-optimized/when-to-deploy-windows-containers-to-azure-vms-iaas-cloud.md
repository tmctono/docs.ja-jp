---
title: Azure Vm (IaaS クラウド) に Windows コンテナーを展開するタイミング
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |Azure Vm (IaaS クラウド) に Windows コンテナーを展開するタイミング
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 8bff4297f99b6549b80604860985568445bbdc0b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625658"
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="c8fec-103">Azure Vm (IaaS クラウド) に Windows コンテナーを展開するタイミング</span><span class="sxs-lookup"><span data-stu-id="c8fec-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="c8fec-104">Windows コンテナーを使用する場合でも、組織は、Azure Vm を使用して、IaaS の取り扱いをまだしています。</span><span class="sxs-lookup"><span data-stu-id="c8fec-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="c8fec-105">負荷分散のインフラストラクチャで複数の Vm にデプロイする必要があるときに拡張性の高いアプリケーションのインフラストラクチャの操作、VM の OS 修正プログラム、およびインフラストラクチャの複雑さを処理するを意味します。</span><span class="sxs-lookup"><span data-stu-id="c8fec-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="c8fec-106">Azure VM で Windows コンテナーを使用する主なシナリオは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8fec-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

- <span data-ttu-id="c8fec-107">**開発/テスト環境**:クラウド内の VM では、開発とテストをクラウドに最適です。</span><span class="sxs-lookup"><span data-stu-id="c8fec-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="c8fec-108">迅速に作成または、環境のニーズに応じて停止できます。</span><span class="sxs-lookup"><span data-stu-id="c8fec-108">You can rapidly create or stop the environment depending on your needs.</span></span>

- <span data-ttu-id="c8fec-109">**小規模および中規模のスケーラビリティが必要な**:必要になるいくつかの Vm を運用環境のシナリオで Vm の数が少ないを管理する場合があります手頃な価格までオーケストレーターなどのより高度な PaaS 環境に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="c8fec-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

- <span data-ttu-id="c8fec-110">**既存の展開ツールを使用して実稼働環境**:これには、Vm またはベア メタル サーバー (Puppet のようなツールなど) に複雑なデプロイを行うためのツールに投資して、オンプレミス環境から移動する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8fec-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="c8fec-111">運用環境の展開手順の最小限の変更で、クラウドに移動するには、これらのツールを使用して Azure Vm にデプロイする続ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c8fec-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="c8fec-112">ただし、配置の 1 単位として展開エクスペリエンスを向上させるために Windows コンテナーを使用するがします。</span><span class="sxs-lookup"><span data-stu-id="c8fec-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c8fec-113">[前へ](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
>[次へ](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span><span class="sxs-lookup"><span data-stu-id="c8fec-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-azure-container-instances-ACI.md)</span></span>