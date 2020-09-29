---
title: SQL Server でのバルク コピー操作
description: SqlBulkCopy クラスを使用して、大きなファイルを SQL Server データベースのテーブルまたはビューに一括コピーするマネージド コード ソリューションを作成する方法について説明します。
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 43d63f3671ea8ff05da3e10580c2784fa3aae581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197432"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="b06a8-103">SQL Server でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="b06a8-103">Bulk Copy Operations in SQL Server</span></span>

<span data-ttu-id="b06a8-104">Microsoft SQL Server には、SQL Server データベースのテーブルまたはビューに大きなファイルを高速で一括コピーするための、**bcp** という一般的なコマンド ライン ユーティリティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b06a8-104">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="b06a8-105"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用すると、同様の機能を提供するマネージ コード ソリューションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b06a8-105">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="b06a8-106">SQL Server のテーブルにデータを読み込むには、INSERT ステートメントを使用するなどの方法もありますが、<xref:System.Data.SqlClient.SqlBulkCopy> を使用すれば他の方法よりもパフォーマンス面で大幅に有利になります。</span><span class="sxs-lookup"><span data-stu-id="b06a8-106">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="b06a8-107"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用すると、SQL Server のテーブルにのみデータを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b06a8-107">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="b06a8-108">ただし、データ ソースについては SQL Server に限定されているわけではありません。<xref:System.Data.DataTable> インスタンスのデータの読み込み、または、<xref:System.Data.IDataReader> インスタンスによるデータの読み取りであれば、任意のデータ ソースを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b06a8-108">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="b06a8-109"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用すると、次のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b06a8-109">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="b06a8-110">単一のバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="b06a8-110">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="b06a8-111">複数のバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="b06a8-111">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="b06a8-112">トランザクション内でのバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="b06a8-112">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b06a8-113"><xref:System.Data.SqlClient.SqlBulkCopy> クラスがサポートされていない、バージョン 1.1 以前の .NET Framework では、<xref:System.Data.SqlClient.SqlCommand> オブジェクトを使用して、SQL Server Transact-SQL **BULK INSERT** ステートメントを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b06a8-113">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b06a8-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b06a8-114">In This Section</span></span>  

 [<span data-ttu-id="b06a8-115">バルク コピー サンプルのセットアップ</span><span class="sxs-lookup"><span data-stu-id="b06a8-115">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="b06a8-116">バルク コピーの例で使用されるテーブルについて説明します。また、AdventureWorks データベースにテーブルを作成する SQL スクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="b06a8-116">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="b06a8-117">バルク コピー操作の単一実行</span><span class="sxs-lookup"><span data-stu-id="b06a8-117">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="b06a8-118"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用して、SQL Server のインスタンスにデータをバルク コピーする単一の方法を説明します。また、Transact-SQL ステートメントと <xref:System.Data.SqlClient.SqlCommand> クラスを使用したバルク コピー操作の実行方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="b06a8-118">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="b06a8-119">バルク コピー操作の複数実行</span><span class="sxs-lookup"><span data-stu-id="b06a8-119">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="b06a8-120"><xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用して、SQL Server のインスタンスにデータのバルク コピー操作を行う複数の方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="b06a8-120">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="b06a8-121">トランザクションとバルク コピー操作</span><span class="sxs-lookup"><span data-stu-id="b06a8-121">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="b06a8-122">トランザクション内でのバルク コピー操作の実行方法を説明します。トランザクションのコミットやロールバックの方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="b06a8-122">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06a8-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="b06a8-123">See also</span></span>

- [<span data-ttu-id="b06a8-124">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b06a8-124">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="b06a8-125">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="b06a8-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
