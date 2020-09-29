---
title: ストアド プロシージャでのデータの変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150753"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="f40de-102">ストアド プロシージャでのデータの変更</span><span class="sxs-lookup"><span data-stu-id="f40de-102">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="f40de-103">ストアド プロシージャは、入力パラメーターとしてデータを受け取り、出力パラメーター、結果セット、または戻り値としてデータを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="f40de-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="f40de-104">以下のサンプルでは、入力パラメーター、出力パラメーター、および戻り値が ADO.NET によってどのようにやり取りされるかを示したものです。</span><span class="sxs-lookup"><span data-stu-id="f40de-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="f40de-105">この例では、主キー列が SQL Server データベースの ID 列であるテーブルに新しいレコードを挿入しています。</span><span class="sxs-lookup"><span data-stu-id="f40de-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f40de-106">SQL Server のストアド プロシージャで、<xref:System.Data.SqlClient.SqlDataAdapter> を使用してデータを編集または削除する場合、ストアド プロシージャの定義に SET NOCOUNT ON は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f40de-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="f40de-107">処理された行数がゼロとして返され、`DataAdapter` によってコンカレンシーの競合として解釈されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="f40de-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="f40de-108">この場合、<xref:System.Data.DBConcurrencyException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f40de-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f40de-109">例</span><span class="sxs-lookup"><span data-stu-id="f40de-109">Example</span></span>  

 <span data-ttu-id="f40de-110">この例では、次のストアド プロシージャを使用して、**Northwind** **Categories** テーブルに新しいカテゴリを挿入します。</span><span class="sxs-lookup"><span data-stu-id="f40de-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="f40de-111">このストアド プロシージャは、**CategoryName** 列の値を入力パラメーターとして受け取り、SCOPE_IDENTITY() 関数を使用して ID フィールド **CategoryID** の新しい値を取得し、その値を出力パラメーター内に返します。</span><span class="sxs-lookup"><span data-stu-id="f40de-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="f40de-112">RETURN ステートメントは、@@ROWCOUNT 関数を使用して、挿入された行の数を返します。</span><span class="sxs-lookup"><span data-stu-id="f40de-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="f40de-113">上述の `InsertCategory` ストアド プロシージャを <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> の <xref:System.Data.SqlClient.SqlDataAdapter> のソースとして使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f40de-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="f40de-114">`@Identity` 出力パラメーターは、<xref:System.Data.DataSet> の `Update` メソッドが呼び出され、データベースにレコードが挿入された後で <xref:System.Data.SqlClient.SqlDataAdapter> に反映されます。</span><span class="sxs-lookup"><span data-stu-id="f40de-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="f40de-115">戻り値も取得されます。</span><span class="sxs-lookup"><span data-stu-id="f40de-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f40de-116"><xref:System.Data.OleDb.OleDbDataAdapter> を使用するときは、**ReturnValue** の <xref:System.Data.ParameterDirection> を含むパラメーターを、他のパラメーターより先に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f40de-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f40de-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f40de-117">See also</span></span>

- [<span data-ttu-id="f40de-118">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="f40de-118">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="f40de-119">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="f40de-119">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="f40de-120">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="f40de-120">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="f40de-121">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f40de-121">ADO.NET Overview</span></span>](ado-net-overview.md)
