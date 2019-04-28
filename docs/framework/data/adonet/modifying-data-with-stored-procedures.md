---
title: ストアド プロシージャでのデータの変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 7dfd4f07ba0a0473975d87c7cd166635473344a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772100"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="abea5-102">ストアド プロシージャでのデータの変更</span><span class="sxs-lookup"><span data-stu-id="abea5-102">Modifying Data with Stored Procedures</span></span>
<span data-ttu-id="abea5-103">ストアド プロシージャは、入力パラメーターとしてデータを受け取り、出力パラメーター、結果セット、または戻り値としてデータを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="abea5-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="abea5-104">以下のサンプルでは、入力パラメーター、出力パラメーター、および戻り値が ADO.NET によってどのようにやり取りされるかを示したものです。</span><span class="sxs-lookup"><span data-stu-id="abea5-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="abea5-105">この例では、主キー列が SQL Server データベースの ID 列であるテーブルに新しいレコードを挿入しています。</span><span class="sxs-lookup"><span data-stu-id="abea5-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abea5-106">SQL Server のストアド プロシージャで、<xref:System.Data.SqlClient.SqlDataAdapter> を使用してデータを編集または削除する場合、ストアド プロシージャの定義に SET NOCOUNT ON は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="abea5-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="abea5-107">処理された行数がゼロとして返され、`DataAdapter` によってコンカレンシーの競合として解釈されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="abea5-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="abea5-108">この場合、<xref:System.Data.DBConcurrencyException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="abea5-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abea5-109">例</span><span class="sxs-lookup"><span data-stu-id="abea5-109">Example</span></span>  
 <span data-ttu-id="abea5-110">このサンプルでは、次のストアド プロシージャを使用して、新しいカテゴリを挿入する、 **Northwind** **カテゴリ**テーブル。</span><span class="sxs-lookup"><span data-stu-id="abea5-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="abea5-111">ストアド プロシージャ値を受け取り、 **CategoryName**列として、入力パラメーターと使用、SCOPE_IDENTITY() 関数の id フィールドの新しい値を取得する**CategoryID**、し、それを返す出力パラメーター。</span><span class="sxs-lookup"><span data-stu-id="abea5-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="abea5-112">RETURN ステートメントを使用して、@@ROWCOUNT挿入された行の数を返す関数。</span><span class="sxs-lookup"><span data-stu-id="abea5-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="abea5-113">上述の `InsertCategory` ストアド プロシージャを <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> の <xref:System.Data.SqlClient.SqlDataAdapter> のソースとして使用する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="abea5-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="abea5-114">`@Identity` 出力パラメーターは、<xref:System.Data.DataSet> の `Update` メソッドが呼び出され、データベースにレコードが挿入された後で <xref:System.Data.SqlClient.SqlDataAdapter> に反映されます。</span><span class="sxs-lookup"><span data-stu-id="abea5-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="abea5-115">戻り値も取得されます。</span><span class="sxs-lookup"><span data-stu-id="abea5-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abea5-116">使用する場合、<xref:System.Data.OleDb.OleDbDataAdapter>を持つパラメーターを指定する必要があります、<xref:System.Data.ParameterDirection>の**ReturnValue**のパラメーターの前に、。</span><span class="sxs-lookup"><span data-stu-id="abea5-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="abea5-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="abea5-117">See also</span></span>

- [<span data-ttu-id="abea5-118">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="abea5-118">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="abea5-119">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="abea5-119">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="abea5-120">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="abea5-120">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)
- [<span data-ttu-id="abea5-121">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="abea5-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
