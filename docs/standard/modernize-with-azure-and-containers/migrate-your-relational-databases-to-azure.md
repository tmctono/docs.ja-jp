---
title: リレーショナル データベースを azure に移行します。
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを近代化 |リレーショナル データベースを azure に移行します。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 600c47b6b0ccaf704c8e7b638c759e990acaaacf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61812786"
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="42f47-103">リレーショナル データベースを azure に移行します。</span><span class="sxs-lookup"><span data-stu-id="42f47-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="42f47-104">ビジョン:Azure では、最も包括的なデータベースの移行を提供します。</span><span class="sxs-lookup"><span data-stu-id="42f47-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="42f47-105">Azure では、データベース サーバーを移行するには (純粋なリフト アンド シフト) IaaS Vm に直接または追加の特典、Azure SQL Database に移行できます。</span><span class="sxs-lookup"><span data-stu-id="42f47-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="42f47-106">Azure SQL Database マネージ インスタンスと完全なデータベースのサービスとしての-(DBaaS) オプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="42f47-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="42f47-107">図 3-1 は、Azure で利用可能な移行パスを複数のリレーショナル データベースには示しています。</span><span class="sxs-lookup"><span data-stu-id="42f47-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![Azure でのデータベース移行パス](./media/image3-1.png)

> <span data-ttu-id="42f47-109">**図 3-1.**</span><span class="sxs-lookup"><span data-stu-id="42f47-109">**Figure 3-1.**</span></span> <span data-ttu-id="42f47-110">Azure でのデータベース移行パス</span><span class="sxs-lookup"><span data-stu-id="42f47-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="42f47-111">Azure SQL Database マネージ インスタンスに移行するときに</span><span class="sxs-lookup"><span data-stu-id="42f47-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="42f47-112">ほとんどの場合、Azure SQL Database マネージ インスタンスは、データを Azure に移行する際に考慮する最善の選択肢になります。</span><span class="sxs-lookup"><span data-stu-id="42f47-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="42f47-113">SQL Server データベースを移行して、ほぼ 100% 確実にアプリケーションを再設計したり、データまたはデータ アクセス コードを変更する必要はありません必要がありますの場合は、Azure SQL Database のマネージ インスタンスの機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="42f47-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="42f47-114">Azure SQL Database マネージ インスタンスは、SQL Server インスタンス レベルの機能の追加要件または標準の Azure SQL データベース (1 つのデータベース モデル) で提供される機能以外の分離要件がある場合に最適なオプションが。</span><span class="sxs-lookup"><span data-stu-id="42f47-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="42f47-115">この最後の 1 つは、最も PaaS 指向の選択肢ですが、従来の SQL server の場合と同じ機能を提供していません。</span><span class="sxs-lookup"><span data-stu-id="42f47-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="42f47-116">移行では、あつれきを surface 可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-116">Migration might surface frictions.</span></span>

<span data-ttu-id="42f47-117">たとえば、インスタンス レベルの SQL Server 機能の詳細への投資を行った組織が有利 SQL マネージド インスタンスに移行します。</span><span class="sxs-lookup"><span data-stu-id="42f47-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="42f47-118">例としてインスタンス レベルの SQL Server 機能の SQL 共通言語ランタイム (CLR) 統合、SQL Server エージェント, やデータベースにまたがるクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="42f47-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="42f47-119">これらの機能のサポートは、標準の Azure SQL Database (単一データベース モデル) でご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="42f47-119">Support for these features is not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="42f47-120">また規制の厳しい業界で動作して、セキュリティのための分離を維持する必要がある組織は、SQL マネージ インスタンス モデルを選択すると便利可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="42f47-121">Azure SQL database マネージ インスタンスには、次の特徴があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="42f47-122">Azure 仮想ネットワーク経由のセキュリティ分離</span><span class="sxs-lookup"><span data-stu-id="42f47-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="42f47-123">Surface とアプリケーションの互換性、これらの機能:</span><span class="sxs-lookup"><span data-stu-id="42f47-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="42f47-124">SQL Server エージェント、SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="42f47-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="42f47-125">データベースにまたがる参照とクエリ、SQL CLR では、レプリケーション、変更データ キャプチャ (CDC)、および Service Broker</span><span class="sxs-lookup"><span data-stu-id="42f47-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="42f47-126">データベースのサイズを最大 35 TB</span><span class="sxs-lookup"><span data-stu-id="42f47-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="42f47-127">これらの機能の最低限のダウンタイムでの移行:</span><span class="sxs-lookup"><span data-stu-id="42f47-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="42f47-128">Azure Database Migration Service</span><span class="sxs-lookup"><span data-stu-id="42f47-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="42f47-129">ネイティブのバックアップと復元、およびログ配布</span><span class="sxs-lookup"><span data-stu-id="42f47-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="42f47-130">これらの機能を備えた Azure SQL database では、既存のアプリケーション データベースを移行するときに、マネージ インスタンス モデルでは、PaaS の利点のほぼ 100% for SQL Server。</span><span class="sxs-lookup"><span data-stu-id="42f47-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of PaaS for SQL Server.</span></span> <span data-ttu-id="42f47-131">マネージ インスタンスは、インスタンス レベルの機能を使用して、アプリケーションの設計を変更することがなく引き続き SQL Server 環境です。</span><span class="sxs-lookup"><span data-stu-id="42f47-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="42f47-132">マネージ インスタンスは、現在使用している SQL Server、およびクラウドでのネットワーク セキュリティの柔軟性を必要とする企業に最適では可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="42f47-133">SQL database 向けのプライベート仮想ネットワークをできるようになります。</span><span class="sxs-lookup"><span data-stu-id="42f47-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="42f47-134">Azure SQL Database に移行するタイミング</span><span class="sxs-lookup"><span data-stu-id="42f47-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="42f47-135">前述のように、標準の Azure SQL Database は、完全管理型リレーショナル DBaaS にします。</span><span class="sxs-lookup"><span data-stu-id="42f47-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="42f47-136">SQL Database は現在、世界中の 38 のデータ センター間で何百万もの実稼働データベースを管理します。</span><span class="sxs-lookup"><span data-stu-id="42f47-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="42f47-137">さまざまなアプリケーションや世界規模での高度なデータ処理を必要とするデータ量の多い最も、ミッション クリティカルなアプリケーションにするために、単純なトランザクション データの管理からのワークロードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="42f47-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="42f47-138">そのすべての PaaS 機能のための料金より- とコストの削減が最終的に、移行する標準の Azure SQL Database、"既定では choice"としてそのは basic、standard SQL データベース、およびインスタンスの追加機能がないアプリケーションがある場合。</span><span class="sxs-lookup"><span data-stu-id="42f47-138">Because of its full PaaS features, better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="42f47-139">SQL CLR 統合、SQL Server エージェント、およびデータベースにまたがるクエリを実行するように SQL Server の機能は標準の Azure SQL Database ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42f47-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="42f47-140">これらの機能が Azure SQL Database マネージ インスタンス モデルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="42f47-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="42f47-141">Azure SQL Database とは、アプリ開発者がビルドされるのみインテリジェント クラウド データベース サービスです。</span><span class="sxs-lookup"><span data-stu-id="42f47-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="42f47-142">その場で、マルチ テナント アプリを効率的に配信するためのダウンタイムなしの拡大/縮小する唯一のクラウド データベース サービスです。</span><span class="sxs-lookup"><span data-stu-id="42f47-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="42f47-143">最終的には、Azure SQL Database には、お客様はイノベーションに多くの時間が離れるし、市場投入時間、高速化します。</span><span class="sxs-lookup"><span data-stu-id="42f47-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="42f47-144">セキュリティで保護されたアプリを構築し、言語と必要なプラットフォームを使用して、SQL database に接続できます。</span><span class="sxs-lookup"><span data-stu-id="42f47-144">You can build secure apps and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="42f47-145">Azure SQL Database には次の利点があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="42f47-146">学習し、アプリに適応する組み込みのインテリジェンス (機械学習)</span><span class="sxs-lookup"><span data-stu-id="42f47-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="42f47-147">オンデマンドでのデータベースのプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="42f47-147">On-demand database provisioning</span></span>

- <span data-ttu-id="42f47-148">すべてのワークロード向けのプランの範囲</span><span class="sxs-lookup"><span data-stu-id="42f47-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="42f47-149">99.99% の可用性 SLA、0 個のメンテナンス</span><span class="sxs-lookup"><span data-stu-id="42f47-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="42f47-150">データ保護のための Geo レプリケーションと復元サービス</span><span class="sxs-lookup"><span data-stu-id="42f47-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="42f47-151">Azure SQL Database の特定時点に復元機能</span><span class="sxs-lookup"><span data-stu-id="42f47-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="42f47-152">ハイブリッドや移行など、SQL Server 2016 との互換性</span><span class="sxs-lookup"><span data-stu-id="42f47-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="42f47-153">標準の Azure SQL Database は、Azure SQL Database マネージ インスタンスよりも近い PaaS のためです。</span><span class="sxs-lookup"><span data-stu-id="42f47-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="42f47-154">管理されたクラウドからより多くのメリットになるために、標準の Azure SQL Database を優先します。</span><span class="sxs-lookup"><span data-stu-id="42f47-154">Prefer the standard Azure SQL Database because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="42f47-155">ただし、Azure SQL Database が正規の主な相違点と、オンプレミスの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="42f47-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="42f47-156">によって、既存のアプリケーションのデータベースの要件、および enterprise の要件とポリシー、その可能性がありますできない最適な選択肢、クラウドへの移行を計画する場合。</span><span class="sxs-lookup"><span data-stu-id="42f47-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="42f47-157">場合に、元の RDBMS を VM (IaaS) に移動するには</span><span class="sxs-lookup"><span data-stu-id="42f47-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="42f47-158">移行オプションの 1 つは、元のリレーショナル データベース管理システム (RDBMS) では、Oracle、IBM DB2、MySQL、PostgreSQL、または SQL Server を含む Azure VM で実行されているようなサーバーを移動します。</span><span class="sxs-lookup"><span data-stu-id="42f47-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="42f47-159">最小限の変更、またはまったく変更せずにクラウドへの移行を最速をまったく必要とする既存のアプリケーションがある場合は、クラウドで IaaS への直接の移行が公正なオプションにあります。</span><span class="sxs-lookup"><span data-stu-id="42f47-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="42f47-160">すべてのクラウドの利点を活用するために最善の方法ができない可能性がありますが、最も高速な初期パスである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="42f47-161">現時点では、Microsoft Azure がサポートする最大[331 の別のデータベース サーバー](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) IaaS Vm としてデプロイします。</span><span class="sxs-lookup"><span data-stu-id="42f47-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="42f47-162">SQL Server、Oracle、MySQL、PostgreSQL、および IBM DB2 の場合のような一般的な RDBMS および MongoDB、Cassandra、DataStax、MariaDB、Cloudera などの他の多くの NoSQL データベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="42f47-162">These include popular RDBMS like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="42f47-163">移動するは、RDBMS に Azure VM (IaaS のため)、データをクラウドに移行する最も簡単な方法があります、このアプローチには、(データベース管理者および IT プロフェッショナル) は、IT チームにかなりの投資が必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="42f47-164">企業のチームは、設定および高可用性、ディザスター リカバリー、および SQL Server の修正プログラムを管理することができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="42f47-165">このコンテキストでは、完全な管理者権限を持つ、カスタマイズされた環境も必要です。</span><span class="sxs-lookup"><span data-stu-id="42f47-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="42f47-166">VM (IaaS) として SQL Server へ移行するタイミング</span><span class="sxs-lookup"><span data-stu-id="42f47-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="42f47-167">いくつかのケースもする必要がある通常の VM と SQL Server への移行である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="42f47-168">シナリオの例では、SQL Server Reporting Services を使用する必要があるかどうかです。</span><span class="sxs-lookup"><span data-stu-id="42f47-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="42f47-169">ほとんどの場合、Azure SQL Database マネージ インスタンスを提供できますすべての SQL Server VM への移行、最後の手段を試すために、オンプレミスの SQL server から移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="42f47-170">Azure Database Migration Service を使用して、リレーショナル データベースを Azure に移行するには</span><span class="sxs-lookup"><span data-stu-id="42f47-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span> 

<span data-ttu-id="42f47-171">ターゲット データベースが Azure SQL Database、Azure SQL Database マネージ インスタンス、または Azure VM 上の SQL Server であるかどうかを Azure に SQL Server、Oracle、MySQL などのリレーショナル データベースを移行するのに Azure Database Migration Service を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="42f47-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="42f47-172">評価がレポートで、自動化されたワークフローでは、データベースを移行する前にする必要がある変更を説明します。</span><span class="sxs-lookup"><span data-stu-id="42f47-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="42f47-173">準備ができたら、サービスは、ソース データベースを Azure に移行します。</span><span class="sxs-lookup"><span data-stu-id="42f47-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="42f47-174">元の RDBMS を変更するたびに再テストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="42f47-175">また、SQL 文またはテストの結果に応じて、アプリケーション内のオブジェクト リレーショナル マッピング (ORM) コードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="42f47-176">その他のデータベース (IBM DB2 など) があり、リフト アンド シフトのアプローチを選択した場合より複雑なデータ移行を実行する意思がないを引き続き Azure では、IaaS Vm としてこれらのデータベースを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42f47-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="42f47-177">複雑なデータ移行は、新しいスキーマとさまざまなプログラミング ライブラリで別のデータベース型に移行するため、追加の作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="42f47-177">A more complex data migration will require additional effort because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="42f47-178">Azure Database Migration Service を使用してデータベースを移行する方法については、次を参照してください。 [Azure SQL Database マネージ インスタンスと Azure Database Migration Service を迅速にクラウドに](https://channel9.msdn.com/Events/Build/2017/P4008)します。</span><span class="sxs-lookup"><span data-stu-id="42f47-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42f47-179">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="42f47-179">Additional resources</span></span>

- <span data-ttu-id="42f47-180">**クラウド SQL Server オプションを選択します。Azure SQL Database (PaaS) または Azure VM (IaaS) 上の SQL Server**</span><span class="sxs-lookup"><span data-stu-id="42f47-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- <span data-ttu-id="42f47-181">**Azure SQL DB マネージ インスタンスとデータベース移行サービスで迅速にクラウドに**</span><span class="sxs-lookup"><span data-stu-id="42f47-181">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- <span data-ttu-id="42f47-182">**SQL Server データベースのクラウド内の SQL Database への移行**</span><span class="sxs-lookup"><span data-stu-id="42f47-182">**SQL Server database migration to SQL Database in the cloud**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- <span data-ttu-id="42f47-183">**Azure SQL Database**</span><span class="sxs-lookup"><span data-stu-id="42f47-183">**Azure SQL Database**</span></span>

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- <span data-ttu-id="42f47-184">**Virtual machines における SQL Server**</span><span class="sxs-lookup"><span data-stu-id="42f47-184">**SQL Server on virtual machines**</span></span>

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> <span data-ttu-id="42f47-185">[前へ](lift-and-shift-existing-apps-azure-iaas.md)
> [次へ](modernize-existing-apps-to-cloud-optimized/index.md)</span><span class="sxs-lookup"><span data-stu-id="42f47-185">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](modernize-existing-apps-to-cloud-optimized/index.md)</span></span>
