---
title: SQL Server でのバルク コピー操作
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: efa13eb1633fce3b59040ef8da79dba0f6ea81d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918060"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="7d541-102">SQL Server でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="7d541-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="7d541-103">Microsoft SQL Server には、大量のファイルを SQL Server データベース内のテーブルまたはビューに一括コピーするための**bcp**という一般的なコマンドラインユーティリティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d541-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="7d541-104"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用すると、同様の機能を備えたマネージド コード ソリューションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7d541-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="7d541-105">SQL Server のテーブルにデータを読み込むには、INSERT ステートメントを使用するなどの方法もありますが、<xref:System.Data.SqlClient.SqlBulkCopy> を使用すれば他の方法よりもパフォーマンス面で大幅に有利になります。</span><span class="sxs-lookup"><span data-stu-id="7d541-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="7d541-106"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用すると、SQL Server のテーブルにのみデータを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="7d541-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="7d541-107">ただし、データ ソースについては SQL Server に限定されているわけではありません。<xref:System.Data.DataTable> インスタンスのデータの読み込み、または、<xref:System.Data.IDataReader> インスタンスによるデータの読み取りであれば、任意のデータ ソースを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7d541-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="7d541-108"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用すると、次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d541-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="7d541-109">単一のバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="7d541-109">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="7d541-110">複数のバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="7d541-110">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="7d541-111">トランザクション内でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="7d541-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d541-112">.NET Framework バージョン1.1 またはそれ以前 ( <xref:System.Data.SqlClient.SqlBulkCopy>クラスをサポートしていません) を使用している場合は、 <xref:System.Data.SqlClient.SqlCommand>オブジェクトを使用して SQL Server transact-sql **BULK INSERT**ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7d541-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d541-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7d541-113">In This Section</span></span>  
 [<span data-ttu-id="7d541-114">バルク コピー サンプルのセットアップ</span><span class="sxs-lookup"><span data-stu-id="7d541-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="7d541-115">バルク コピーの例で使用されるテーブルについて説明します。また、AdventureWorks データベースにテーブルを作成する SQL スクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="7d541-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="7d541-116">バルク コピー操作の単一実行</span><span class="sxs-lookup"><span data-stu-id="7d541-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="7d541-117"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用して、SQL Server のインスタンスにデータをバルク コピーする単一の方法を説明します。また、Transact-SQL ステートメントと <xref:System.Data.SqlClient.SqlCommand> クラスを使用したバルク コピー操作の実行方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="7d541-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="7d541-118">バルク コピー操作の複数実行</span><span class="sxs-lookup"><span data-stu-id="7d541-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="7d541-119"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用して、SQL Server のインスタンスにデータのバルク コピー操作を行う複数の方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="7d541-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="7d541-120">トランザクションとバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="7d541-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="7d541-121">トランザクション内でのバルク コピー操作の実行方法を説明します。トランザクションのコミットやロールバックの方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="7d541-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d541-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d541-122">See also</span></span>

- [<span data-ttu-id="7d541-123">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d541-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="7d541-124">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="7d541-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
