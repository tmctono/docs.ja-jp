---
title: SQL Server データベースを Azure に移行する
description: SQL Server データベースをオンプレミスの SQL Server から Azure に移行する方法について説明します。
ms.topic: how-to
ms.date: 05/27/2020
ms.openlocfilehash: 5f191cafbff3823d04e1dbd1fdf81e1157e20999
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174284"
---
# <a name="migrate-a-sql-server-database-to-azure"></a><span data-ttu-id="892f3-103">SQL Server データベースを Azure に移行する</span><span class="sxs-lookup"><span data-stu-id="892f3-103">Migrate a SQL Server database to Azure</span></span>

<span data-ttu-id="892f3-104">この記事では、SQL Server データベースを Azure に移行するための 2 つの選択肢について概説します。</span><span class="sxs-lookup"><span data-stu-id="892f3-104">This article provides a brief outline of two options for migrating a SQL Server database to Azure.</span></span> <span data-ttu-id="892f3-105">Azure では、運用 SQL Server データベースを移行するための主な選択肢が 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="892f3-105">Azure has three primary options for migrating a production SQL Server database.</span></span> <span data-ttu-id="892f3-106">この記事では、次の 2 つの選択肢を中心に説明します。</span><span class="sxs-lookup"><span data-stu-id="892f3-106">This article focuses on the following two options:</span></span>

1. <span data-ttu-id="892f3-107">[Azure VM 上の SQL Server](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview): Azure で実行されている Windows 仮想マシンにインストールされ、ホストされている SQL Server インスタンス。これは、サービスとしてのインフラストラクチャ (IaaS) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="892f3-107">[SQL Server on Azure VMs](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview): A SQL Server instance installed and hosted on a Windows Virtual Machine running in Azure, also known as Infrastructure as a Service (IaaS).</span></span>
2. <span data-ttu-id="892f3-108">[Azure SQL Database](/azure/sql-database/sql-database-technical-overview):フル マネージドの Azure SQL データベース サービス。これは、サービスとしてのプラットフォーム (PaaS) とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="892f3-108">[Azure SQL Database](/azure/sql-database/sql-database-technical-overview): A fully managed SQL database Azure service, also known as Platform as a Service (PaaS).</span></span>

<span data-ttu-id="892f3-109">それぞれに、移行前に評価する必要がある長所と短所があります。</span><span class="sxs-lookup"><span data-stu-id="892f3-109">Both come with pros and cons that you will need to evaluate before migrating.</span></span> <span data-ttu-id="892f3-110">3 番目の選択肢は、[Azure SQL Database Managed Instance](/azure/sql-database/sql-database-managed-instance) です。</span><span class="sxs-lookup"><span data-stu-id="892f3-110">The third option is [Azure SQL Database managed instances](/azure/sql-database/sql-database-managed-instance).</span></span>

## <a name="get-started"></a><span data-ttu-id="892f3-111">作業開始</span><span class="sxs-lookup"><span data-stu-id="892f3-111">Get started</span></span>

<span data-ttu-id="892f3-112">使用するサービスによっては、次の移行ガイドが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="892f3-112">The following migration guides will be useful, depending on which service you use:</span></span>

* [<span data-ttu-id="892f3-113">Azure VM の SQL Server への SQL Server データベースの移行</span><span class="sxs-lookup"><span data-stu-id="892f3-113">Migrate a SQL Server database to SQL Server in an Azure VM</span></span>](/azure/virtual-machines/windows/sql/virtual-machines-windows-migrate-sql)
* [<span data-ttu-id="892f3-114">SQL Server データベースを Azure SQL Database に移行する</span><span class="sxs-lookup"><span data-stu-id="892f3-114">Migrate your SQL Server database to Azure SQL Database</span></span>](/azure/sql-database/sql-database-migrate-your-sql-server-database)

<span data-ttu-id="892f3-115">さらに、概念説明への次のリンクが、VM の理解を深めるうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="892f3-115">Additionally, the following links to conceptual content will help you understand VMs better:</span></span>

* [<span data-ttu-id="892f3-116">Azure 仮想マシンにおける SQL Server の高可用性とディザスター リカバリー</span><span class="sxs-lookup"><span data-stu-id="892f3-116">High availability and disaster recovery for SQL Server in Azure Virtual Machines</span></span>](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-high-availability-dr)
* [<span data-ttu-id="892f3-117">Azure Virtual Machines における SQL Server のパフォーマンスに関するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="892f3-117">Performance best practices for SQL Server in Azure Virtual Machines</span></span>](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-performance)
* [<span data-ttu-id="892f3-118">Azure Virtual Machines における SQL Server のアプリケーション パターンと開発計画</span><span class="sxs-lookup"><span data-stu-id="892f3-118">Application Patterns and Development Strategies for SQL Server in Azure Virtual Machines</span></span>](/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-app-patterns-dev-strategies)

<span data-ttu-id="892f3-119">次のリンクは、Azure SQL Database データベースの理解を深めるうえで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="892f3-119">And the following links will help you understand Azure SQL Database better:</span></span>

* [<span data-ttu-id="892f3-120">Azure SQL Database のサーバーとデータベースを作成し、管理する</span><span class="sxs-lookup"><span data-stu-id="892f3-120">Create and manage Azure SQL Database servers and databases</span></span>](/azure/sql-database/sql-database-servers-databases)
* [<span data-ttu-id="892f3-121">データベース トランザクション ユニット (DTU) とエラスティック データベース トランザクション ユニット (eDTU)</span><span class="sxs-lookup"><span data-stu-id="892f3-121">Database Transaction Units (DTUs) and elastic Database Transaction Units (eDTUs)</span></span>](/azure/sql-database/sql-database-what-is-a-dtu)
* [<span data-ttu-id="892f3-122">Azure SQL Database のリソース制限</span><span class="sxs-lookup"><span data-stu-id="892f3-122">Azure SQL Database resource limits</span></span>](/azure/sql-database/sql-database-resource-limits)

## <a name="choosing-iaas-or-paas"></a><span data-ttu-id="892f3-123">IaaS または PaaS の選択</span><span class="sxs-lookup"><span data-stu-id="892f3-123">Choosing IaaS or PaaS</span></span>

<span data-ttu-id="892f3-124">データベースの移行先を評価する際に、IaaS または PaaS のどちらがより適切かを判断します。</span><span class="sxs-lookup"><span data-stu-id="892f3-124">When evaluating where to migrate your database, determine if IaaS or PaaS is more appropriate for you.</span></span>

<span data-ttu-id="892f3-125">**次の状況に該当する場合は、Azure VM の SQL Server を選択します。**</span><span class="sxs-lookup"><span data-stu-id="892f3-125">**Choose SQL Server in Azure VMs if:**</span></span>

* <span data-ttu-id="892f3-126">変更を最小限に抑えて、データベースとアプリケーションを "リフトアンドシフト" する場合。</span><span class="sxs-lookup"><span data-stu-id="892f3-126">You are looking to "lift and shift" your database and applications with minimal to no changes.</span></span>
* <span data-ttu-id="892f3-127">データベース サーバーとそのサーバーが実行される VM を完全に制御する場合。</span><span class="sxs-lookup"><span data-stu-id="892f3-127">You prefer having full control over your database server and the VM it runs on.</span></span>
* <span data-ttu-id="892f3-128">使用する SQL Server および Windows Server のライセンスが既にある場合。</span><span class="sxs-lookup"><span data-stu-id="892f3-128">You already have SQL Server and Windows Server licenses that you intend to use.</span></span>

<span data-ttu-id="892f3-129">**次の状況に該当する場合は、Azure SQL Database を選択します。**</span><span class="sxs-lookup"><span data-stu-id="892f3-129">**Choose Azure SQL Database if:**</span></span>

* <span data-ttu-id="892f3-130">アプリケーションを最新化し、Azure の他の PaaS サービスを使用するために移行する場合。</span><span class="sxs-lookup"><span data-stu-id="892f3-130">You are looking to modernize your applications and are migrating to use other PaaS services in Azure.</span></span>
* <span data-ttu-id="892f3-131">データベース サーバーとそのサーバーが実行される VM を管理するのは望ましくない場合。</span><span class="sxs-lookup"><span data-stu-id="892f3-131">You do not wish to manage your database server and the VM it runs on.</span></span>
* <span data-ttu-id="892f3-132">SQL Server または Windows Server のライセンスがない場合、または現在のライセンスを期限切れにする場合。</span><span class="sxs-lookup"><span data-stu-id="892f3-132">You do not have SQL Server or Windows Server licenses, or you intend to let licenses you have expire.</span></span>

<span data-ttu-id="892f3-133">一連のシナリオに基づく各サービスの違いを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="892f3-133">The following table describes differences between each service based on a set of scenarios.</span></span>

| <span data-ttu-id="892f3-134">シナリオ</span><span class="sxs-lookup"><span data-stu-id="892f3-134">Scenario</span></span> | <span data-ttu-id="892f3-135">Azure VM の SQL Server</span><span class="sxs-lookup"><span data-stu-id="892f3-135">SQL Server in Azure VMs</span></span> | <span data-ttu-id="892f3-136">Azure SQL データベース</span><span class="sxs-lookup"><span data-stu-id="892f3-136">Azure SQL Database</span></span> |
|----------|-------------------------|--------------------|
| <span data-ttu-id="892f3-137">移行</span><span class="sxs-lookup"><span data-stu-id="892f3-137">Migration</span></span> | <span data-ttu-id="892f3-138">データベースの最小限の変更が必要です。</span><span class="sxs-lookup"><span data-stu-id="892f3-138">Requires minimal changes to your database.</span></span> | <span data-ttu-id="892f3-139">[Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595) によって Azure SQL で利用できないと判断された機能を使用する場合や、ローカルにインストールされた実行可能ファイルなどの他の依存関係がある場合、データベースの変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="892f3-139">May require changes to your database if you use features unavailable in Azure SQL, as determined by the [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595), or if you have other dependencies such as locally installed executables.</span></span>|
| <span data-ttu-id="892f3-140">可用性、復旧、アップグレードの管理</span><span class="sxs-lookup"><span data-stu-id="892f3-140">Managing availability, recovery, and upgrades</span></span> | <span data-ttu-id="892f3-141">可用性と復旧は手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="892f3-141">Availability and recovery are configured manually.</span></span> <span data-ttu-id="892f3-142">アップグレードは、[VM Scale Sets](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) を使用して自動化できます。</span><span class="sxs-lookup"><span data-stu-id="892f3-142">Upgrades can be automated with [VM Scale Sets](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade).</span></span> | <span data-ttu-id="892f3-143">自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="892f3-143">Automatically managed for you.</span></span> |
| <span data-ttu-id="892f3-144">基になる OS 構成</span><span class="sxs-lookup"><span data-stu-id="892f3-144">Underlying OS configuration</span></span> | <span data-ttu-id="892f3-145">手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="892f3-145">Manual configuration.</span></span> | <span data-ttu-id="892f3-146">自動的に管理されます。</span><span class="sxs-lookup"><span data-stu-id="892f3-146">Automatically managed for you.</span></span> |
| <span data-ttu-id="892f3-147">データベース サイズの管理</span><span class="sxs-lookup"><span data-stu-id="892f3-147">Managing database size</span></span> | <span data-ttu-id="892f3-148">SQL Server インスタンスごとに最大 256 TB のストレージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="892f3-148">Supports up to 256 TB of storage per SQL Server instance.</span></span> | <span data-ttu-id="892f3-149">行方向のパーティション分割が必要になるまでに 8 TB のストレージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="892f3-149">Supports 8 TB of storage before needing a horizontal partition.</span></span> |
| <span data-ttu-id="892f3-150">コストの管理</span><span class="sxs-lookup"><span data-stu-id="892f3-150">Managing costs</span></span> | <span data-ttu-id="892f3-151">SQL Server ライセンスのコスト、Windows Server ライセンスのコスト、VM のコスト (コア数、RAM、ストレージに基づく) を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="892f3-151">You must manage SQL Server license costs, Windows Server license costs, and VM costs (based on cores, RAM, and storage).</span></span> | <span data-ttu-id="892f3-152">([eDTU または DTU](/azure/sql-database/sql-database-what-is-a-dtu)、ストレージ、データベースの数 (エラスティック プールを使用している場合) に基づいて) サービス コストを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="892f3-152">You must manage service costs (based on [eDTUs or DTUs](/azure/sql-database/sql-database-what-is-a-dtu), storage, and number of databases if using an elastic pool).</span></span> <span data-ttu-id="892f3-153">また、SLA のコストも管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="892f3-153">You must also manage the cost of any SLA.</span></span> |

<span data-ttu-id="892f3-154">この 2 つの違いの詳細については、[Azure SQL での適切なデプロイ オプションの選択](/azure/sql-database/sql-database-paas-vs-sql-server-iaas)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="892f3-154">To learn more about the differences between the two, see [Choose the right deployment option in Azure SQL](/azure/sql-database/sql-database-paas-vs-sql-server-iaas).</span></span>

## <a name="faq"></a><span data-ttu-id="892f3-155">よくあるご質問</span><span class="sxs-lookup"><span data-stu-id="892f3-155">FAQ</span></span>

* <span data-ttu-id="892f3-156">**SQL Server Management Studio や SQL Server Reporting Services (SSRS) などのツールは、Azure VM の SQL Server または Azure SQL Database で引き続き使用できますか?**</span><span class="sxs-lookup"><span data-stu-id="892f3-156">**Can I still use tools such as SQL Server Management Studio and SQL Server Reporting Services (SSRS) with SQL Server in Azure VMs or Azure SQL Database?**</span></span>

    <span data-ttu-id="892f3-157">はい。</span><span class="sxs-lookup"><span data-stu-id="892f3-157">Yes.</span></span> <span data-ttu-id="892f3-158">Microsoft SQL ツールはすべてどちらのサービスでも機能します。</span><span class="sxs-lookup"><span data-stu-id="892f3-158">All Microsoft SQL tooling works with both services.</span></span> <span data-ttu-id="892f3-159">SSRS は Azure SQL Database には含まれていませんが、このツールを Azure VM で実行し、データベース インスタンスを参照することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="892f3-159">SSRS is not part of Azure SQL Database, though, and it's recommended that you run it in an Azure VM and then point it to your database instance.</span></span>

* <span data-ttu-id="892f3-160">**PaaS に移行したいのですが、データベースに互換性があるのかどうかがわかりません。役立つツールはありますか?**</span><span class="sxs-lookup"><span data-stu-id="892f3-160">**I want to go PaaS but I'm not sure if my database is compatible. Are there tools to help?**</span></span>

    <span data-ttu-id="892f3-161">はい。</span><span class="sxs-lookup"><span data-stu-id="892f3-161">Yes.</span></span> <span data-ttu-id="892f3-162">[Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595) は、Azure SQL Database への移行の一環として使用されるツールです。</span><span class="sxs-lookup"><span data-stu-id="892f3-162">The [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595) is a tool that is used as a part of migrating to Azure SQL Database.</span></span> <span data-ttu-id="892f3-163">[Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) は、IaaS または PaaS で使用できるプレビュー サービスです。</span><span class="sxs-lookup"><span data-stu-id="892f3-163">The [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) is a preview service that you can use for either IaaS or PaaS.</span></span>

* <span data-ttu-id="892f3-164">**コストを見積もることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="892f3-164">**Can I estimate costs?**</span></span>

    <span data-ttu-id="892f3-165">はい。</span><span class="sxs-lookup"><span data-stu-id="892f3-165">Yes.</span></span> <span data-ttu-id="892f3-166">[Azure 料金計算ツール](https://azure.microsoft.com/pricing/calculator/)を使用して、VM やデータベース サービスなど、すべての Azure サービスのコストを見積もることができます。</span><span class="sxs-lookup"><span data-stu-id="892f3-166">The [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/) can be used for estimating costs for all Azure services, including VMs and database services.</span></span>

## <a name="next-steps"></a><span data-ttu-id="892f3-167">次の手順</span><span class="sxs-lookup"><span data-stu-id="892f3-167">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="892f3-168">適切な Azure ホスティング オプションの選択</span><span class="sxs-lookup"><span data-stu-id="892f3-168">Choose the right Azure hosting option</span></span>](choose.md)
