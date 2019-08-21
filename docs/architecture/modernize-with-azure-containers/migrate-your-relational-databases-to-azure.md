---
title: リレーショナルデータベースを azure に移行する
description: Azure クラウドおよび Windows コンテナーで既存の .NET アプリケーションを最新化する |リレーショナルデータベースを azure に移行する
ms.date: 04/28/2018
ms.openlocfilehash: 982050d99aaa66cde1168a2f2fa64ed5f3e9163b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660727"
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="438c6-103">リレーショナルデータベースを azure に移行する</span><span class="sxs-lookup"><span data-stu-id="438c6-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="438c6-104">展望:Azure には、最も包括的なデータベース移行が用意されています。</span><span class="sxs-lookup"><span data-stu-id="438c6-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="438c6-105">Azure では、データベースサーバーを IaaS Vm (純粋なリフトアンドシフト) に直接移行することも、Azure SQL Database に移行して追加のメリットを提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="438c6-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="438c6-106">Azure SQL Database には、マネージインスタンスと完全なサービスとしてのデータベース (DBaaS) オプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="438c6-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="438c6-107">図3-1 は、Azure で使用できる複数のリレーショナルデータベース移行パスを示しています。</span><span class="sxs-lookup"><span data-stu-id="438c6-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![Azure でのデータベース移行パス](./media/image3-1.png)

> <span data-ttu-id="438c6-109">**図 3-1.**</span><span class="sxs-lookup"><span data-stu-id="438c6-109">**Figure 3-1.**</span></span> <span data-ttu-id="438c6-110">Azure でのデータベース移行パス</span><span class="sxs-lookup"><span data-stu-id="438c6-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="438c6-111">Azure SQL Database Managed Instance に移行する場合</span><span class="sxs-lookup"><span data-stu-id="438c6-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="438c6-112">ほとんどの場合、データを Azure に移行する際には、Azure SQL Database Managed Instance をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="438c6-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="438c6-113">SQL Server データベースを移行するときに、アプリケーションを再設計したり、データやデータアクセスコードを変更したりする必要がないという約 100% の保証が必要な場合は、Azure SQL Database の Managed Instance 機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="438c6-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="438c6-114">Azure SQL Database Managed Instance は、SQL Server インスタンスレベルの機能に対する追加の要件や、標準 Azure SQL Database (単一データベースモデル) で提供される機能を超える分離要件がある場合に最適なオプションです。</span><span class="sxs-lookup"><span data-stu-id="438c6-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="438c6-115">最後の1つは、最も PaaS 指向の選択肢ですが、従来の SQL server と同じ機能を提供するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="438c6-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="438c6-116">移行が frictions になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-116">Migration might surface frictions.</span></span>

<span data-ttu-id="438c6-117">たとえば、インスタンスレベルの SQL Server 機能に対してディープな投資を行った組織は、SQL Managed Instance に移行することでメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="438c6-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="438c6-118">インスタンスレベルの SQL Server 機能の例としては、SQL 共通言語ランタイム (CLR) の統合、SQL Server エージェント、データベース間のクエリなどがあります。</span><span class="sxs-lookup"><span data-stu-id="438c6-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="438c6-119">これらの機能のサポートは、standard Azure SQL Database (単一データベースモデル) では使用できません。</span><span class="sxs-lookup"><span data-stu-id="438c6-119">Support for these features is not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="438c6-120">高度に規制された業界で運営され、セキュリティのために分離を維持する必要がある組織では、SQL Managed Instance モデルを選択することによってメリットが得られる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="438c6-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="438c6-121">Azure SQL Database の Managed Instance には、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="438c6-122">Azure Virtual Network を使用したセキュリティの分離</span><span class="sxs-lookup"><span data-stu-id="438c6-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="438c6-123">アプリケーション画面の互換性: 次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="438c6-124">SQL Server エージェントと SQL Server プロファイラー</span><span class="sxs-lookup"><span data-stu-id="438c6-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="438c6-125">複数データベースにまたがる参照とクエリ、SQL CLR、レプリケーション、変更データキャプチャ (CDC)、および Service Broker</span><span class="sxs-lookup"><span data-stu-id="438c6-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="438c6-126">最大 35 TB のデータベースサイズ</span><span class="sxs-lookup"><span data-stu-id="438c6-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="438c6-127">次の機能を備えた、最小限のダウンタイムの移行。</span><span class="sxs-lookup"><span data-stu-id="438c6-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="438c6-128">Azure Database Migration Service</span><span class="sxs-lookup"><span data-stu-id="438c6-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="438c6-129">ネイティブのバックアップと復元、およびログ配布</span><span class="sxs-lookup"><span data-stu-id="438c6-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="438c6-130">これらの機能を使用すると、既存のアプリケーションデータベースを Azure SQL Database に移行するときに、Managed Instance モデルは SQL Server の PaaS の利点の約 100% を提供します。</span><span class="sxs-lookup"><span data-stu-id="438c6-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of PaaS for SQL Server.</span></span> <span data-ttu-id="438c6-131">Managed Instance は SQL Server 環境であり、アプリケーションの設計を変更することなく、インスタンスレベルの機能を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="438c6-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="438c6-132">Managed Instance は、現在 SQL Server を使用しており、クラウドでのネットワークセキュリティに柔軟性を必要とする企業に最適です。</span><span class="sxs-lookup"><span data-stu-id="438c6-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="438c6-133">これは、SQL データベースのプライベート仮想ネットワークのようなものです。</span><span class="sxs-lookup"><span data-stu-id="438c6-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="438c6-134">Azure SQL Database に移行する場合</span><span class="sxs-lookup"><span data-stu-id="438c6-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="438c6-135">前述のように、標準の Azure SQL Database は完全に管理されたリレーショナル DBaaS です。</span><span class="sxs-lookup"><span data-stu-id="438c6-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="438c6-136">SQL Database、世界中の38データセンターで、数百万の実稼働データベースを現在管理しています。</span><span class="sxs-lookup"><span data-stu-id="438c6-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="438c6-137">これは、単純なトランザクションデータの管理から、グローバルな規模で高度なデータ処理を必要とするデータを大量に消費するミッションクリティカルなアプリケーションを実行するための、さまざまなアプリケーションとワークロードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="438c6-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="438c6-138">PaaS の完全な機能により、価格が向上し、最終的にコストが削減されます。 basic、standard SQL database、および追加のインスタンス機能を使用しないアプリケーションがある場合は、標準の Azure SQL Database に移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="438c6-138">Because of its full PaaS features, better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="438c6-139">SQL CLR 統合、SQL Server エージェント、データベース間クエリなどの SQL Server 機能は、標準 Azure SQL Database ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="438c6-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="438c6-140">これらの機能は、Azure SQL Database Managed Instance モデルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="438c6-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="438c6-141">Azure SQL Database は、アプリ開発者向けに構築された唯一のインテリジェントなクラウドデータベースサービスです。</span><span class="sxs-lookup"><span data-stu-id="438c6-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="438c6-142">また、マルチテナントアプリを効率的に配信できるように、ダウンタイムを発生させることなく、すぐに拡張できるクラウドデータベースサービスでもあります。</span><span class="sxs-lookup"><span data-stu-id="438c6-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="438c6-143">最終的には、Azure SQL Database イノベーションに時間がかかり、市場投入までの時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="438c6-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="438c6-144">お好みの言語とプラットフォームを使用して、セキュリティで保護されたアプリを構築し、SQL database に接続できます。</span><span class="sxs-lookup"><span data-stu-id="438c6-144">You can build secure apps and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="438c6-145">Azure SQL Database には、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="438c6-146">アプリを学習して適応する組み込みのインテリジェンス (machine learning)</span><span class="sxs-lookup"><span data-stu-id="438c6-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="438c6-147">オンデマンドのデータベースプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="438c6-147">On-demand database provisioning</span></span>

- <span data-ttu-id="438c6-148">あらゆるワークロードに対応する幅広いプラン</span><span class="sxs-lookup"><span data-stu-id="438c6-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="438c6-149">99.99% の可用性 SLA、ゼロメンテナンス</span><span class="sxs-lookup"><span data-stu-id="438c6-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="438c6-150">データ保護のための Geo レプリケーションと復元サービス</span><span class="sxs-lookup"><span data-stu-id="438c6-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="438c6-151">Azure SQL Database ポイントインタイムリストア機能</span><span class="sxs-lookup"><span data-stu-id="438c6-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="438c6-152">ハイブリッドおよび移行を含む SQL Server 2016 との互換性</span><span class="sxs-lookup"><span data-stu-id="438c6-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="438c6-153">標準 Azure SQL Database は、Azure SQL Database Managed Instance よりも PaaS に近いです。</span><span class="sxs-lookup"><span data-stu-id="438c6-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="438c6-154">管理されたクラウドからさらに利点を得られるため、標準の Azure SQL Database をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="438c6-154">Prefer the standard Azure SQL Database because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="438c6-155">ただし、Azure SQL Database には、通常の SQL Server インスタンスとオンプレミスのインスタンスの主な違いがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="438c6-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="438c6-156">既存のアプリケーションのデータベース要件、およびエンタープライズの要件とポリシーによっては、クラウドへの移行を計画するときに最適な選択肢とは言えない場合があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="438c6-157">元の RDBMS を VM (IaaS) に移行する場合</span><span class="sxs-lookup"><span data-stu-id="438c6-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="438c6-158">移行オプションの1つは、Oracle、IBM DB2、MySQL、PostgreSQL、SQL Server など、元のリレーショナルデータベース管理システム (RDBMS) を、Azure VM 上で実行されている同様のサーバーに移動することです。</span><span class="sxs-lookup"><span data-stu-id="438c6-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="438c6-159">最小限の変更でクラウドへの移行を最速で行う必要がある既存のアプリケーションがある場合、またはまったく変更を加えていない場合は、クラウドで IaaS に直接移行することが公正な選択肢となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="438c6-160">クラウドの利点をすべて活用するのは最善の方法ではないかもしれませんが、ほとんどの場合、最速の初期パスです。</span><span class="sxs-lookup"><span data-stu-id="438c6-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="438c6-161">現時点では、Microsoft Azure は、IaaS Vm としてデプロイされた最大[331 の異なるデータベースサーバー](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all)をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="438c6-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="438c6-162">これには、SQL Server、Oracle、MySQL、PostgreSQL、IBM DB2 などの一般的な RDBMS や、MongoDB、Cassandra、DataNoSQL x、MariaDB、Cloudera などの他の多くのデータベースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="438c6-162">These include popular RDBMS like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="438c6-163">RDBMS を Azure VM に移動する方法は、データをクラウドに移行する最速の方法である場合があります (IaaS であるため)。この方法では、IT チーム (データベース管理者および IT プロフェッショナル) に多大な投資を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="438c6-164">エンタープライズチームは、SQL Server の高可用性、ディザスターリカバリー、修正プログラムの適用をセットアップして管理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="438c6-165">また、このコンテキストには、完全な管理者権限を持つカスタマイズされた環境も必要です。</span><span class="sxs-lookup"><span data-stu-id="438c6-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="438c6-166">VM として SQL Server に移行する場合 (IaaS)</span><span class="sxs-lookup"><span data-stu-id="438c6-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="438c6-167">通常の VM として SQL Server に移行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="438c6-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="438c6-168">例として、SQL Server Reporting Services を使用する必要がある場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="438c6-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="438c6-169">ただし、ほとんどの場合、Azure SQL Database Managed Instance は、オンプレミスの SQL server から移行するために必要なすべてを提供できます。そのため、SQL Server VM への移行は、最後の手段として行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="438c6-170">Azure Database Migration Service を使用してリレーショナルデータベースを Azure に移行する</span><span class="sxs-lookup"><span data-stu-id="438c6-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span> 

<span data-ttu-id="438c6-171">Azure Database Migration Service を使用して、SQL Server、Oracle、MySQL などのリレーショナルデータベースを Azure に移行することができます。これは、ターゲットデータベースが Azure VM 上で Azure SQL Database、Azure SQL Database Managed Instance、SQL Server のいずれであるかに関係ありません。</span><span class="sxs-lookup"><span data-stu-id="438c6-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="438c6-172">自動ワークフローと評価レポートを使用すると、データベースを移行する前に必要な変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="438c6-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="438c6-173">準備が整うと、サービスはソースデータベースを Azure に移行します。</span><span class="sxs-lookup"><span data-stu-id="438c6-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="438c6-174">元の RDBMS を変更するたびに、再テストが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="438c6-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="438c6-175">また、テスト結果に応じて、アプリケーションの SQL 文またはオブジェクトリレーショナルマッピング (ORM) コードを変更することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="438c6-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="438c6-176">他のデータベース (IBM DB2 など) があり、リフトアンドシフトアプローチを選択した場合は、より複雑なデータ移行を実行する場合を除き、これらのデータベースを Azure の IaaS Vm として引き続き使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="438c6-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="438c6-177">より複雑なデータ移行では、新しいスキーマと異なるプログラミングライブラリを使用して別の種類のデータベースに移行するため、追加の作業が必要になります。</span><span class="sxs-lookup"><span data-stu-id="438c6-177">A more complex data migration will require additional effort because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="438c6-178">Azure Database Migration Service を使用してデータベースを移行する方法については、「 [Azure SQL Database Managed Instance と Azure Database Migration Service を使用したクラウドへの迅速なアクセス](https://channel9.msdn.com/Events/Build/2017/P4008)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="438c6-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="438c6-179">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="438c6-179">Additional resources</span></span>

- <span data-ttu-id="438c6-180">**クラウド SQL Server オプションを選択してください:Azure VM (IaaS) での Azure SQL Database (PaaS) または SQL Server**</span><span class="sxs-lookup"><span data-stu-id="438c6-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- <span data-ttu-id="438c6-181">**Azure SQL DB Managed Instance と Database Migration Service により、クラウドに迅速にアクセスできます**</span><span class="sxs-lookup"><span data-stu-id="438c6-181">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- <span data-ttu-id="438c6-182">**SQL Server データベースのクラウド内の SQL Database への移行**</span><span class="sxs-lookup"><span data-stu-id="438c6-182">**SQL Server database migration to SQL Database in the cloud**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- <span data-ttu-id="438c6-183">**Azure SQL Database**</span><span class="sxs-lookup"><span data-stu-id="438c6-183">**Azure SQL Database**</span></span>

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- <span data-ttu-id="438c6-184">**仮想マシンでの SQL Server**</span><span class="sxs-lookup"><span data-stu-id="438c6-184">**SQL Server on virtual machines**</span></span>

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> <span data-ttu-id="438c6-185">[前へ](lift-and-shift-existing-apps-azure-iaas.md)
> [次へ](modernize-existing-apps-to-cloud-optimized/index.md)</span><span class="sxs-lookup"><span data-stu-id="438c6-185">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](modernize-existing-apps-to-cloud-optimized/index.md)</span></span> <!-- Next Chapter -->
