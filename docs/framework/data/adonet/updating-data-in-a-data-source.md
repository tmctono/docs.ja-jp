---
title: データ ソースのデータの更新
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 6b0234337c85ace0797d75b72560ccb55635daae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177268"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="317ff-102">データ ソースのデータの更新</span><span class="sxs-lookup"><span data-stu-id="317ff-102">Updating Data in a Data Source</span></span>

<span data-ttu-id="317ff-103">データを変更する SQL ステートメント (INSERT、UPDATE、DELETE など) は行を返しません。</span><span class="sxs-lookup"><span data-stu-id="317ff-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="317ff-104">同様に、多くのストアド プロシージャは、アクションを実行しても行を返しません。</span><span class="sxs-lookup"><span data-stu-id="317ff-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="317ff-105">行を返さないコマンドを実行するには、適切な SQL コマンドを使用して **Command** オブジェクトを作成し、必要な **Parameters** を含む **Connection** を作成します。</span><span class="sxs-lookup"><span data-stu-id="317ff-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="317ff-106">**Command** オブジェクトの **ExecuteNonQuery** メソッドでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="317ff-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="317ff-107">**ExecuteNonQuery** メソッドからは、実行されたステートメントまたはストアド プロシージャの影響を受けた行数を表す整数が返されます。</span><span class="sxs-lookup"><span data-stu-id="317ff-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="317ff-108">複数のステートメントが実行された場合は、実行された各ステートメントの影響を受けたレコードの合計を示す値が返されます。</span><span class="sxs-lookup"><span data-stu-id="317ff-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="317ff-109">例</span><span class="sxs-lookup"><span data-stu-id="317ff-109">Example</span></span>  

 <span data-ttu-id="317ff-110">INSERT ステートメントを実行して、**ExecuteNonQuery** でデータベースにレコードを挿入するコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="317ff-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="317ff-111">「[カタログ操作の実行](performing-catalog-operations.md)」と同じコードで作成されたストアド プロシージャを実行するコードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="317ff-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="317ff-112">ストアド プロシージャは行を返さないため **ExecuteNonQuery** メソッドが使用されていますが、ストアド プロシージャは入力パラメーターを受け取り、出力パラメーターと戻り値を返します。</span><span class="sxs-lookup"><span data-stu-id="317ff-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="317ff-113"><xref:System.Data.OleDb.OleDbCommand> オブジェクトの場合は、最初に **Parameters** コレクションに **ReturnValue** パラメーターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="317ff-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="317ff-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="317ff-114">See also</span></span>

- [<span data-ttu-id="317ff-115">コマンドを使用したデータ変更</span><span class="sxs-lookup"><span data-stu-id="317ff-115">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="317ff-116">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="317ff-116">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="317ff-117">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="317ff-117">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="317ff-118">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="317ff-118">ADO.NET Overview</span></span>](ado-net-overview.md)
