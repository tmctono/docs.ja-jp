---
title: DataAdapter パラメーター
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: 772763b5927ca845d6c2ccba50382652e410ae4f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951240"
---
# <a name="dataadapter-parameters"></a><span data-ttu-id="93f1b-102">DataAdapter パラメーター</span><span class="sxs-lookup"><span data-stu-id="93f1b-102">DataAdapter Parameters</span></span>
<span data-ttu-id="93f1b-103"><xref:System.Data.Common.DbDataAdapter> には 4 つのプロパティがあり、データ ソースからデータを取得したりデータ ソースのデータを更新したりするために使用されます。<xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> プロパティは、データ ソースのデータを返します。<xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>、<xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>、および <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> の各プロパティは、データ ソースの変更を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-103">The <xref:System.Data.Common.DbDataAdapter> has four properties that are used to retrieve data from and update data to the data source: the <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> property returns data from the data source; and the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> , <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, and <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> properties are used to manage changes at the data source.</span></span> <span data-ttu-id="93f1b-104">`SelectCommand` プロパティは、`Fill` の `DataAdapter` メソッドを呼び出す前に設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="93f1b-104">The `SelectCommand` property must be set before you call the `Fill` method of the `DataAdapter`.</span></span> <span data-ttu-id="93f1b-105">`InsertCommand`、`UpdateCommand`、`DeleteCommand` の各プロパティは、`Update` 内のデータに加えられた変更に応じて、`DataAdapter` の <xref:System.Data.DataTable> メソッドを呼び出す前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93f1b-105">The `InsertCommand`, `UpdateCommand`, or `DeleteCommand` properties must be set before the `Update` method of the `DataAdapter` is called, depending on what changes were made to the data in the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="93f1b-106">たとえば、行が追加された場合には、`InsertCommand` を呼び出す前に `Update` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93f1b-106">For example, if rows have been added, the `InsertCommand` must be set before you call `Update`.</span></span> <span data-ttu-id="93f1b-107">`Update` によって挿入行、更新行、または削除行が処理されるとき、`DataAdapter` でそれぞれの `Command` プロパティが使用され、アクションが処理されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-107">When `Update` is processing an inserted, updated, or deleted row, the `DataAdapter` uses the respective `Command` property to process the action.</span></span> <span data-ttu-id="93f1b-108">変更された行に関する現在の情報が `Command` コレクションを経由して `Parameters` オブジェクトに渡されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-108">Current information about the modified row is passed to the `Command` object through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="93f1b-109">データソースで行を更新する場合は、UPDATE ステートメントを呼び出します。このステートメントでは、一意の識別子を使用して、更新するテーブル内の行を識別します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-109">When you update a row at the data source, you call the UPDATE statement, which uses a unique identifier to identify the row in the table to be updated.</span></span> <span data-ttu-id="93f1b-110">一意識別子は、一般には主キー フィールドの値です。</span><span class="sxs-lookup"><span data-stu-id="93f1b-110">The unique identifier is typically the value of a primary key field.</span></span> <span data-ttu-id="93f1b-111">UPDATE ステートメントでは、次の Transact-SQL ステートメントに示すように、一意識別子と更新する列および値の両方を含むパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-111">The UPDATE statement uses parameters that contain both the unique identifier and the columns and values to be updated, as shown in the following Transact-SQL statement.</span></span>  
  
```sql
UPDATE Customers SET CompanyName = @CompanyName   
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
> <span data-ttu-id="93f1b-112">パラメーターのプレースホルダーの構文はデータ ソースに依存します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-112">The syntax for parameter placeholders depends on the data source.</span></span> <span data-ttu-id="93f1b-113">次に、SQL Server のデータ ソースのプレースホルダーの例を示します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-113">This example shows placeholders for a SQL Server data source.</span></span> <span data-ttu-id="93f1b-114"><xref:System.Data.OleDb> パラメーターおよび <xref:System.Data.Odbc> パラメーターのプレースホルダーとして、疑問符 (?) を使用します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-114">Use question mark (?) placeholders for <xref:System.Data.OleDb> and <xref:System.Data.Odbc> parameters.</span></span>  
  
 <span data-ttu-id="93f1b-115">この Visual Basic 例では、 `CompanyName`フィールドは、が`@CustomerID`パラメーターの値と`@CompanyName` `CustomerID`等しい行のパラメーターの値によって更新されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-115">In this Visual Basic example, the `CompanyName` field is updated with the value of the `@CompanyName` parameter for the row where `CustomerID` equals the value of the `@CustomerID` parameter.</span></span> <span data-ttu-id="93f1b-116">パラメーターは、 <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> <xref:System.Data.SqlClient.SqlParameter>オブジェクトのプロパティを使用して、変更された行から情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-116">The parameters retrieve information from the modified row using the <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> property of the <xref:System.Data.SqlClient.SqlParameter> object.</span></span> <span data-ttu-id="93f1b-117">前のサンプル UPDATE ステートメントのパラメーターを次に示します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-117">The following are the parameters for the previous sample UPDATE statement.</span></span> <span data-ttu-id="93f1b-118">このコードは、変数 `adapter` が有効な <xref:System.Data.SqlClient.SqlDataAdapter> オブジェクトを表すことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="93f1b-118">The code assumes that the variable `adapter` represents a valid <xref:System.Data.SqlClient.SqlDataAdapter> object.</span></span>  
  
```vb
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 <span data-ttu-id="93f1b-119">`Parameters` コレクションの `Add` メソッドは、パラメーター名、データ型、サイズ (その型に適用可能な場合)、および <xref:System.Data.Common.DbParameter.SourceColumn%2A> の名前を `DataTable` から受け取ります。</span><span class="sxs-lookup"><span data-stu-id="93f1b-119">The `Add` method of the `Parameters` collection takes the name of the parameter, the data type, the size (if applicable to the type), and the name of the <xref:System.Data.Common.DbParameter.SourceColumn%2A> from the `DataTable`.</span></span> <span data-ttu-id="93f1b-120"><xref:System.Data.Common.DbParameter.SourceVersion%2A> パラメーターの `@CustomerID` が `Original` に設定されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="93f1b-120">Notice that the <xref:System.Data.Common.DbParameter.SourceVersion%2A> of the `@CustomerID` parameter is set to `Original`.</span></span> <span data-ttu-id="93f1b-121">この設定により、変更された <xref:System.Data.DataRow> で 1 つまたは複数の識別列の値が変更されている場合に、データ ソース内の既存の行が確実に更新されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-121">This guarantees that the existing row in the data source is updated if the value of the identifying column or columns has been changed in the modified <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="93f1b-122">識別列の値が変更されている場合、`Original` 行の値がデータ ソースの現在の値と一致し、`Current` 行の値に更新済みの値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-122">In that case, the `Original` row value would match the current value at the data source, and the `Current` row value would contain the updated value.</span></span> <span data-ttu-id="93f1b-123">`SourceVersion` パラメーターの `@CompanyName` は設定されていないため、既定値である `Current` の行の値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-123">The `SourceVersion` for the `@CompanyName` parameter is not set and uses the default, `Current` row value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93f1b-124">の`Fill`操作`DataAdapter` と`Get`のメソッドの両方について、.NETFramework型は.NETFrameworkデータプロバイダーから返された型から推論されます。`DataReader`</span><span class="sxs-lookup"><span data-stu-id="93f1b-124">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the type returned from the .NET Framework data provider.</span></span> <span data-ttu-id="93f1b-125">Microsoft SQL Server、OLE DB、および ODBC データ型の推論された .NET Framework 型およびアクセサーメソッドについては、「 [ADO.NET のデータ型のマッピング](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93f1b-125">The inferred .NET Framework types and accessor methods for Microsoft SQL Server, OLE DB, and ODBC data types are described in [Data Type Mappings in ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md).</span></span>  
  
## <a name="parametersourcecolumn-parametersourceversion"></a><span data-ttu-id="93f1b-126">Parameter.SourceColumn、Parameter.SourceVersion</span><span class="sxs-lookup"><span data-stu-id="93f1b-126">Parameter.SourceColumn, Parameter.SourceVersion</span></span>  
 <span data-ttu-id="93f1b-127">`SourceColumn` および `SourceVersion` が、引数として `Parameter` コンストラクターに渡されるか、既存の `Parameter` のプロパティとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-127">The `SourceColumn` and `SourceVersion` may be passed as arguments to the `Parameter` constructor, or set as properties of an existing `Parameter`.</span></span> <span data-ttu-id="93f1b-128">`SourceColumn` は、<xref:System.Data.DataColumn> の値の取得先である <xref:System.Data.DataRow> の `Parameter` の名前です。</span><span class="sxs-lookup"><span data-stu-id="93f1b-128">The `SourceColumn` is the name of the <xref:System.Data.DataColumn> from the <xref:System.Data.DataRow> where the value of the `Parameter` will be retrieved.</span></span> <span data-ttu-id="93f1b-129">`SourceVersion` により、`DataRow` で値の取得に使用される `DataAdapter` のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-129">The `SourceVersion` specifies the `DataRow` version that the `DataAdapter` uses to retrieve the value.</span></span>  
  
 <span data-ttu-id="93f1b-130"><xref:System.Data.DataRowVersion> で使用できる `SourceVersion` 列挙型の値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-130">The following table shows the <xref:System.Data.DataRowVersion> enumeration values available for use with `SourceVersion`.</span></span>  
  
|<span data-ttu-id="93f1b-131">DataRowVersion 列挙定数</span><span class="sxs-lookup"><span data-stu-id="93f1b-131">DataRowVersion Enumeration</span></span>|<span data-ttu-id="93f1b-132">説明</span><span class="sxs-lookup"><span data-stu-id="93f1b-132">Description</span></span>|  
|--------------------------------|-----------------|  
|`Current`|<span data-ttu-id="93f1b-133">このパラメーターは列の現在の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-133">The parameter uses the current value of the column.</span></span> <span data-ttu-id="93f1b-134">既定値です。</span><span class="sxs-lookup"><span data-stu-id="93f1b-134">This is the default.</span></span>|  
|`Default`|<span data-ttu-id="93f1b-135">このパラメーターには列の `DefaultValue` を使用します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-135">The parameter uses the `DefaultValue` of the column.</span></span>|  
|`Original`|<span data-ttu-id="93f1b-136">このパラメーターは列の元の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-136">The parameter uses the original value of the column.</span></span>|  
|`Proposed`|<span data-ttu-id="93f1b-137">このパラメーターは提示された値を使用します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-137">The parameter uses a proposed value.</span></span>|  
  
 <span data-ttu-id="93f1b-138">次のセクションの `SqlClient` コード サンプルでは、<xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 列を 2 つのパラメーター `CustomerID` (`SourceColumn`) および `@CustomerID` (`SET CustomerID = @CustomerID`) の `@OldCustomerID` として使用する `WHERE CustomerID = @OldCustomerID` のパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-138">The `SqlClient` code example in the next section defines a parameter for an <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> in which the `CustomerID` column is used as a `SourceColumn` for two parameters: `@CustomerID` (`SET CustomerID = @CustomerID`), and `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span></span> <span data-ttu-id="93f1b-139">パラメーターを使用して、 **CustomerID**列をの`DataRow`現在の値に更新します。 `@CustomerID`</span><span class="sxs-lookup"><span data-stu-id="93f1b-139">The `@CustomerID` parameter is used to update the **CustomerID** column to the current value in the `DataRow`.</span></span> <span data-ttu-id="93f1b-140">その結果`CustomerID` `SourceVersion` 、が`Current`であるが使用されます。 `SourceColumn`</span><span class="sxs-lookup"><span data-stu-id="93f1b-140">As a result, the `CustomerID` `SourceColumn` with a `SourceVersion` of `Current` is used.</span></span> <span data-ttu-id="93f1b-141">`@OldCustomerID`パラメーターは、データソースの現在の行を識別するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-141">The `@OldCustomerID` parameter is used to identify the current row in the data source.</span></span> <span data-ttu-id="93f1b-142">一致する列の値がその行の `Original` バージョンで見つかったため、`SourceColumn` が `CustomerID` である同じ `SourceVersion` (`Original`) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-142">Because the matching column value is found in the `Original` version of the row, the same `SourceColumn` (`CustomerID`) with a `SourceVersion` of `Original` is used.</span></span>  
  
## <a name="working-with-sqlclient-parameters"></a><span data-ttu-id="93f1b-143">SqlClient パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="93f1b-143">Working with SqlClient Parameters</span></span>  
 <span data-ttu-id="93f1b-144">次のコード サンプルでは、データベースから追加のスキーマ情報を取得するために <xref:System.Data.SqlClient.SqlDataAdapter> を作成し、<xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> を <xref:System.Data.MissingSchemaAction.AddWithKey> に設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-144">The following example demonstrates how to create a <xref:System.Data.SqlClient.SqlDataAdapter> and set the <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> to <xref:System.Data.MissingSchemaAction.AddWithKey> in order to retrieve additional schema information from the database.</span></span> <span data-ttu-id="93f1b-145"><xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A> プロパティ、<xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> プロパティ、<xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> プロパティ、および <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> プロパティが設定され、各プロパティに対応する <xref:System.Data.SqlClient.SqlParameter> オブジェクトが <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-145">The <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties set and their corresponding <xref:System.Data.SqlClient.SqlParameter> objects added to the <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection.</span></span> <span data-ttu-id="93f1b-146">このメソッドは `SqlDataAdapter` オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-146">The method returns a `SqlDataAdapter` object.</span></span>  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a><span data-ttu-id="93f1b-147">OleDb パラメーターのプレースホルダー</span><span class="sxs-lookup"><span data-stu-id="93f1b-147">OleDb Parameter Placeholders</span></span>  
 <span data-ttu-id="93f1b-148"><xref:System.Data.OleDb.OleDbDataAdapter> オブジェクトと <xref:System.Data.Odbc.OdbcDataAdapter> オブジェクトの場合は、疑問符 (?) のプレースホルダーを使用してパラメーターを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93f1b-148">For the <xref:System.Data.OleDb.OleDbDataAdapter> and <xref:System.Data.Odbc.OdbcDataAdapter> objects, you must use question mark (?) placeholders to identify the parameters.</span></span>  
  
```vb  
Dim selectSQL As String = _  
  "SELECT CustomerID, CompanyName FROM Customers " & _  
  "WHERE CountryRegion = ? AND City = ?"  
Dim insertSQL AS String = _  
  "INSERT INTO Customers (CustomerID, CompanyName) VALUES (?, ?)"  
Dim updateSQL AS String = _  
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " & _  
  WHERE CustomerID = ?"  
Dim deleteSQL As String = "DELETE FROM Customers WHERE CustomerID = ?"  
```  
  
```csharp  
string selectSQL =   
  "SELECT CustomerID, CompanyName FROM Customers " +  
  "WHERE CountryRegion = ? AND City = ?";  
string insertSQL =   
  "INSERT INTO Customers (CustomerID, CompanyName) " +  
  "VALUES (?, ?)";  
string updateSQL =   
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " +  
  "WHERE CustomerID = ? ";  
string deleteSQL = "DELETE FROM Customers WHERE CustomerID = ?";  
```  
  
 <span data-ttu-id="93f1b-149">パラメーターとして使用されるクエリ ステートメントは、作成する必要のある入力パラメーターおよび出力パラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-149">The parameterized query statements define which input and output parameters must be created.</span></span> <span data-ttu-id="93f1b-150">パラメーターを作成するには、`Parameters.Add` メソッドまたは `Parameter` コンストラクターを使用して、列名、データ型、およびサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-150">To create a parameter, use the `Parameters.Add` method or the `Parameter` constructor to specify the column name, data type, and size.</span></span> <span data-ttu-id="93f1b-151">`Integer` などの組み込みのデータ型の場合は、サイズを指定する必要はありません。サイズを指定する場合、既定のサイズを指定することになります。</span><span class="sxs-lookup"><span data-stu-id="93f1b-151">For intrinsic data types, such as `Integer`, you do not have to include the size, or you can specify the default size.</span></span>  
  
 <span data-ttu-id="93f1b-152">次のコード サンプルでは、SQL ステートメントのパラメーターを作成した後、`DataSet` にデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="93f1b-152">The following code example creates the parameters for a SQL statement and then fills a `DataSet`.</span></span>  
  
## <a name="oledb-example"></a><span data-ttu-id="93f1b-153">OleDb の例</span><span class="sxs-lookup"><span data-stu-id="93f1b-153">OleDb Example</span></span>  
  
```vb  
' Assumes that connection is a valid OleDbConnection object.  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter   
  
Dim selectCMD AS OleDbCommand = New OleDbCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add parameters and set values.  
selectCMD.Parameters.Add( _  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add( _  
  "@City", OleDbType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OleDbConnection object.  
OleDbDataAdapter adapter = new OleDbDataAdapter();  
  
OleDbCommand selectCMD = new OleDbCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
// Add parameters and set values.  
selectCMD.Parameters.Add(  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add(  
  "@City", OleDbType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
## <a name="odbc-parameters"></a><span data-ttu-id="93f1b-154">Odbc パラメーター</span><span class="sxs-lookup"><span data-stu-id="93f1b-154">Odbc Parameters</span></span>  
  
```vb  
' Assumes that connection is a valid OdbcConnection object.  
Dim adapter As OdbcDataAdapter = New OdbcDataAdapter  
  
Dim selectCMD AS OdbcCommand = New OdbcCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OdbcConnection object.  
OdbcDataAdapter adapter = new OdbcDataAdapter();  
  
OdbcCommand selectCMD = new OdbcCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
//Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="93f1b-155">パラメーター名がパラメーターに指定されていない場合、パラメーターには、"Parameter1" から始まるパラメーター*N*の増分既定名が指定されます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-155">If a parameter name is not supplied for a parameter, the parameter is given an incremental default name of Parameter*N* *,* starting with "Parameter1".</span></span> <span data-ttu-id="93f1b-156">パラメーター名を指定するときは 、パラメーター名の名前付け規則を使用しないことをお勧めします。これは、 `ParameterCollection`指定した名前が内の既存の既定のパラメーター名と競合する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="93f1b-156">We recommend that you avoid the Parameter*N* naming convention when you supply a parameter name, because the name that you supply might conflict with an existing default parameter name in the `ParameterCollection`.</span></span> <span data-ttu-id="93f1b-157">指定した名前が既に存在する場合は、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="93f1b-157">If the supplied name already exists, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f1b-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="93f1b-158">See also</span></span>

- [<span data-ttu-id="93f1b-159">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="93f1b-159">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="93f1b-160">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="93f1b-160">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="93f1b-161">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="93f1b-161">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="93f1b-162">ストアド プロシージャでのデータの変更</span><span class="sxs-lookup"><span data-stu-id="93f1b-162">Modifying Data with Stored Procedures</span></span>](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="93f1b-163">ADO.NET でのデータ型のマッピング</span><span class="sxs-lookup"><span data-stu-id="93f1b-163">Data Type Mappings in ADO.NET</span></span>](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="93f1b-164">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="93f1b-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
