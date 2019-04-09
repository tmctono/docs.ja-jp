---
title: SQL Server の機能と ADO.NET
ms.date: 03/30/2017
ms.assetid: 2839529b-a79b-4450-be5d-07a98dbc7a0f
ms.openlocfilehash: b07f5e1e62744e4301acd64034481cf391100af8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107524"
---
# <a name="sql-server-features-and-adonet"></a><span data-ttu-id="a17c8-102">SQL Server の機能と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a17c8-102">SQL Server Features and ADO.NET</span></span>
<span data-ttu-id="a17c8-103">このセクションのトピックでは、ADO.NET を使用したデータベース アプリケーションの開発を目的とする SQL Server の機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-103">The topics in this section discuss features in SQL Server that are targeted at developing database applications using ADO.NET.</span></span>  
  
 <span data-ttu-id="a17c8-104">詳細については、次の表に示すように、使用する SQL Server のバージョンに対応した SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a17c8-104">For more information, see SQL Server Books Online for the version of SQL Server you are using, as listed in the following table.</span></span>  
  
 **<span data-ttu-id="a17c8-105">SQL Server オンライン ブック</span><span class="sxs-lookup"><span data-stu-id="a17c8-105">SQL Server Books Online</span></span>**  
  
1.  [<span data-ttu-id="a17c8-106">開発 (データベース エンジン)</span><span class="sxs-lookup"><span data-stu-id="a17c8-106">Development (Database Engine)</span></span>](https://go.microsoft.com/fwlink/?LinkId=115245)  
  
## <a name="in-this-section"></a><span data-ttu-id="a17c8-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a17c8-107">In This Section</span></span>  
 [<span data-ttu-id="a17c8-108">SQL Server のインスタンスの列挙 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="a17c8-108">Enumerating Instances of SQL Server (ADO.NET)</span></span>](../../../../../docs/framework/data/adonet/sql/enumerating-instances-of-sql-server.md)  
 <span data-ttu-id="a17c8-109">SQL Server のアクティブなインスタンスを列挙する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-109">Describes how to enumerate active instances of SQL Server.</span></span>  
  
 [<span data-ttu-id="a17c8-110">SQL Server のプロバイダー統計情報</span><span class="sxs-lookup"><span data-stu-id="a17c8-110">Provider Statistics for SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/provider-statistics-for-sql-server.md)  
 <span data-ttu-id="a17c8-111">SQL Server の実行時の統計情報の取得のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-111">Describes support for obtaining SQL Server run-time statistics.</span></span>  
  
 [<span data-ttu-id="a17c8-112">SQL Server Express ユーザー インスタンス</span><span class="sxs-lookup"><span data-stu-id="a17c8-112">SQL Server Express User Instances</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)  
 <span data-ttu-id="a17c8-113">SQL Server Express のユーザー インターフェイスのサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-113">Describes support for SQL Server Express user instances.</span></span>  
  
 [<span data-ttu-id="a17c8-114">SQL Server のデータベース ミラーリング</span><span class="sxs-lookup"><span data-stu-id="a17c8-114">Database Mirroring in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/database-mirroring-in-sql-server.md)  
 <span data-ttu-id="a17c8-115">データベース ミラーリング機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-115">Describes database mirroring functionality.</span></span>  
  
 [<span data-ttu-id="a17c8-116">SQL Server の共通言語ランタイム統合</span><span class="sxs-lookup"><span data-stu-id="a17c8-116">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 <span data-ttu-id="a17c8-117">SQL Server で共通言語ランタイム (CLR) データベース オブジェクトからデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-117">Describes how data can be accessed from within a common language runtime (CLR) database object in SQL Server.</span></span>  
  
 [<span data-ttu-id="a17c8-118">SQL Server のクエリ通知</span><span class="sxs-lookup"><span data-stu-id="a17c8-118">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 <span data-ttu-id="a17c8-119">.NET Framework アプリケーションで、データが変更されている場合に SQL Server に対して通知を要求する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-119">Describes how .NET Framework applications can request notification from SQL Server when data has changed.</span></span>  
  
 [<span data-ttu-id="a17c8-120">SQL Server でのスナップショット分離</span><span class="sxs-lookup"><span data-stu-id="a17c8-120">Snapshot Isolation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/snapshot-isolation-in-sql-server.md)  
 <span data-ttu-id="a17c8-121">トランザクション アプリケーションでのブロックの軽減を目的とする行バージョン管理機構であるスナップショット分離のサポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-121">Describes support for snapshot isolation, a row versioning mechanism designed to reduce blocking in transactional applications.</span></span>  
  
 [<span data-ttu-id="a17c8-122">高可用性障害復旧のための SqlClient サポート</span><span class="sxs-lookup"><span data-stu-id="a17c8-122">SqlClient Support for High Availability, Disaster Recovery</span></span>](../../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)  
 <span data-ttu-id="a17c8-123">高可用性ディザスター リカバリー (AlwaysOn) 可用性グループの SqlClient サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-123">Describes SqlClient support for high-availability, disaster recovery (AlwaysOn) availability groups.</span></span>  
  
 [<span data-ttu-id="a17c8-124">SqlClient による LocalDB のサポート</span><span class="sxs-lookup"><span data-stu-id="a17c8-124">SqlClient Support for LocalDB</span></span>](../../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md)  
 <span data-ttu-id="a17c8-125">LocalDB データベースの SqlClient サポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a17c8-125">Describes SqlClient support for LocalDB databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17c8-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a17c8-126">See also</span></span>

- [<span data-ttu-id="a17c8-127">ADO.NET における SQL Server データ操作</span><span class="sxs-lookup"><span data-stu-id="a17c8-127">SQL Server Data Operations in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)
- [<span data-ttu-id="a17c8-128">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="a17c8-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="a17c8-129">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a17c8-129">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="a17c8-130">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a17c8-130">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="a17c8-131">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="a17c8-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
