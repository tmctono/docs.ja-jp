---
title: バルク コピー サンプルのセットアップ
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: 80350d112da03c00e422432ce271ca5ea3ac58ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148843"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="ab1ee-102">バルク コピー サンプルのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ab1ee-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="ab1ee-103"><xref:System.Data.SqlClient.SqlBulkCopy> クラスは、SQL Server テーブルのみにデータを書き込む場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="ab1ee-104">このトピック内のコード サンプルには、SQL Server のサンプル データベース **AdventureWorks** が使用されています。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="ab1ee-105">既存のテーブルの改変を防ぐため、コード サンプルでは、別途作成したテーブルにデータを書き込みます。このテーブルを最初に作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="ab1ee-106">**BulkCopyDemoMatchingColumns** テーブルと **BulkCopyDemoDifferentColumns** テーブルは、どちらも \*\*AdventureWorks の \*\* **Production.Products** テーブルに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="ab1ee-107">コード サンプルではこれらのテーブルを使用し、**Production.Products** テーブルからこれらのサンプル テーブルのいずれかにデータを追加します。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="ab1ee-108">**BulkCopyDemoDifferentColumns** テーブルは、ソース データからコピー先のテーブルに列をマップする方法を例示するサンプルに使用されます。**BulkCopyDemoMatchingColumns** は他のサンプルの大部分に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="ab1ee-109">1 つの <xref:System.Data.SqlClient.SqlBulkCopy> クラスを使用して複数のテーブルに書き込む方法を示すコード サンプルもあります。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="ab1ee-110">これらのサンプルでは、変換先**テーブル**として使用されます。 **BulkCopyDemoOrderDetail**</span><span class="sxs-lookup"><span data-stu-id="ab1ee-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="ab1ee-111">これらのテーブルは、**AdventureWorks** の **Sales.SalesOrderHeader** テーブルと **Sales.SalesOrderDetail** テーブルに基づいたテーブルです。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab1ee-112">**SqlBulkCopy** コード サンプルでは、**SqlBulkCopy** だけを使用した構文について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="ab1ee-113">コピー元およびコピー先のテーブルが同一の SQL Server インスタンス内に存在する場合、Transact-SQL `INSERT … SELECT` ステートメントを使用すれば簡単かつ高速にデータをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="ab1ee-114">テーブルのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ab1ee-114">Table Setup</span></span>  
 <span data-ttu-id="ab1ee-115">コード サンプルを正しく実行するために必要なテーブルを作成するには、SQL Server データベースで次の Transact-SQL ステートメントを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab1ee-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```sql
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab1ee-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab1ee-116">See also</span></span>

- [<span data-ttu-id="ab1ee-117">SQL Server での一括コピー操作</span><span class="sxs-lookup"><span data-stu-id="ab1ee-117">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="ab1ee-118">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ab1ee-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
