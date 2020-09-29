---
title: テーブル値パラメーター
description: テーブル値パラメーターを使用することにより、複数行のデータをクライアント アプリケーションから SQL Server にマーシャリングする方法について説明します。
ms.date: 10/12/2018
dev_langs:
- csharp
- vb
ms.assetid: 370c16d5-db7b-43e3-945b-ccaab35b739b
ms.openlocfilehash: ea063b333ea0680071b880f26753bfd74b71d80f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91188877"
---
# <a name="table-valued-parameters"></a><span data-ttu-id="10aef-103">テーブル値パラメーター</span><span class="sxs-lookup"><span data-stu-id="10aef-103">Table-Valued Parameters</span></span>

<span data-ttu-id="10aef-104">テーブル値パラメーターを使用すると、ラウンド トリップを何度も繰り返したり、サーバー側にデータを処理するための特殊なロジックを組み込んだりすることなく、複数行のデータをクライアント アプリケーションから SQL Server へと簡単にマーシャリングできます。</span><span class="sxs-lookup"><span data-stu-id="10aef-104">Table-valued parameters provide an easy way to marshal multiple rows of data from a client application to SQL Server without requiring multiple round trips or special server-side logic for processing the data.</span></span> <span data-ttu-id="10aef-105">テーブル値パラメーターを使用すると、クライアント アプリケーションのデータ行をカプセル化して単一のパラメーター化コマンドでサーバーに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="10aef-105">You can use table-valued parameters to encapsulate rows of data in a client application and send the data to the server in a single parameterized command.</span></span> <span data-ttu-id="10aef-106">受信データ行はテーブル変数に格納され、Transact-SQL によって操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="10aef-106">The incoming data rows are stored in a table variable that can then be operated on by using Transact-SQL.</span></span>  
  
 <span data-ttu-id="10aef-107">テーブル値パラメーターの列値には、Transact-SQL の標準的な SELECT ステートメントを使ってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="10aef-107">Column values in table-valued parameters can be accessed using standard Transact-SQL SELECT statements.</span></span> <span data-ttu-id="10aef-108">テーブル値パラメーターは厳密に型指定されており、その構造は自動的に検証されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-108">Table-valued parameters are strongly typed and their structure is automatically validated.</span></span> <span data-ttu-id="10aef-109">テーブル値パラメーターのサイズは、サーバーのメモリによってのみ制限されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-109">The size of table-valued parameters is limited only by server memory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10aef-110">テーブル値パラメーターでデータを返すことはできません。</span><span class="sxs-lookup"><span data-stu-id="10aef-110">You cannot return data in a table-valued parameter.</span></span> <span data-ttu-id="10aef-111">テーブル値パラメーターは入力専用です。OUTPUT キーワードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10aef-111">Table-valued parameters are input-only; the OUTPUT keyword is not supported.</span></span>  
  
 <span data-ttu-id="10aef-112">テーブル値パラメーターの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10aef-112">For more information about table-valued parameters, see the following resources.</span></span>  
  
|<span data-ttu-id="10aef-113">リソース</span><span class="sxs-lookup"><span data-stu-id="10aef-113">Resource</span></span>|<span data-ttu-id="10aef-114">説明</span><span class="sxs-lookup"><span data-stu-id="10aef-114">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="10aef-115">テーブル値パラメーターの使用 (データベース エンジン)</span><span class="sxs-lookup"><span data-stu-id="10aef-115">Use Table-Valued Parameters (Database Engine)</span></span>](/sql/relational-databases/tables/use-table-valued-parameters-database-engine)|<span data-ttu-id="10aef-116">テーブル値パラメーターの作成方法および使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10aef-116">Describes how to create and use table-valued parameters.</span></span>|  
|<span data-ttu-id="10aef-117">[ユーザー定義テーブル型](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="10aef-117">[User-Defined Table Types](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))</span></span>|<span data-ttu-id="10aef-118">テーブル値パラメーターを宣言する際に使用するユーザー定義テーブル型について説明します。</span><span class="sxs-lookup"><span data-stu-id="10aef-118">Describes user-defined table types that are used to declare table-valued parameters.</span></span>|  
  
## <a name="passing-multiple-rows-in-previous-versions-of-sql-server"></a><span data-ttu-id="10aef-119">旧バージョンの SQL Server での複数行の受け渡し</span><span class="sxs-lookup"><span data-stu-id="10aef-119">Passing Multiple Rows in Previous Versions of SQL Server</span></span>  

 <span data-ttu-id="10aef-120">SQL Server 2008 にテーブル値パラメーターが導入されるまでは、複数行データをストアド プロシージャまたはパラメーター化 SQL コマンドに渡す方法は限られていました。</span><span class="sxs-lookup"><span data-stu-id="10aef-120">Before table-valued parameters were introduced to SQL Server 2008, the options for passing multiple rows of data to a stored procedure or a parameterized SQL command were limited.</span></span> <span data-ttu-id="10aef-121">開発者が選択できる複数の行をサーバーに渡すためのオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="10aef-121">A developer could choose from the following options for passing multiple rows to the server:</span></span>  
  
- <span data-ttu-id="10aef-122">複数のデータ列とデータ行の値を表すには、一連の個別のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="10aef-122">Use a series of individual parameters to represent the values in multiple columns and rows of data.</span></span> <span data-ttu-id="10aef-123">このメソッドを使用して渡すことができるデータの量は、許可されているパラメーター数によって制限されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-123">The amount of data that can be passed by using this method is limited by the number of parameters allowed.</span></span> <span data-ttu-id="10aef-124">SQL Server プロシージャが持つことのできるパラメーター数は最大 2,100 です。</span><span class="sxs-lookup"><span data-stu-id="10aef-124">SQL Server procedures can have, at most, 2100 parameters.</span></span> <span data-ttu-id="10aef-125">これらの個々の値をテーブル変数または一時テーブルにまとめて処理するには、サーバー側ロジックが必要です。</span><span class="sxs-lookup"><span data-stu-id="10aef-125">Server-side logic is required to assemble these individual values into a table variable or a temporary table for processing.</span></span>  
  
- <span data-ttu-id="10aef-126">複数のデータ値を区切り文字列または XML ドキュメントにバンドルし、それらのテキスト値をプロシージャまたはステートメントに渡します。</span><span class="sxs-lookup"><span data-stu-id="10aef-126">Bundle multiple data values into delimited strings or XML documents and then pass those text values to a procedure or statement.</span></span> <span data-ttu-id="10aef-127">これを行うには、そのプロシージャまたはステートメントに、データ構造の検証と値のバンドルの解除に必要なロジックが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-127">This requires the procedure or statement to include the logic necessary for validating the data structures and unbundling the values.</span></span>  
  
- <span data-ttu-id="10aef-128">複数の行 (<xref:System.Data.SqlClient.SqlDataAdapter> の `Update` メソッドを呼び出すことによって作成された行など) に影響を及ぼす、データを変更するための一連の個別 SQL ステートメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="10aef-128">Create a series of individual SQL statements for data modifications that affect multiple rows, such as those created by calling the `Update` method of a <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="10aef-129">サーバーへの変更の送信は個別に行うことも、グループにまとめることもできます。</span><span class="sxs-lookup"><span data-stu-id="10aef-129">Changes can be submitted to the server individually or batched into groups.</span></span> <span data-ttu-id="10aef-130">ただし、複数のステートメントをまとめてバッチ送信しても、サーバーで実行されるときはそれぞれ個別に処理されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-130">However, even when submitted in batches that contain multiple statements, each statement is executed separately on the server.</span></span>  
  
- <span data-ttu-id="10aef-131">`bcp` ユーティリティ プログラムまたは <xref:System.Data.SqlClient.SqlBulkCopy> オブジェクトを使用して、多数のデータ行をテーブルに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="10aef-131">Use the `bcp` utility program or the <xref:System.Data.SqlClient.SqlBulkCopy> object to load many rows of data into a table.</span></span> <span data-ttu-id="10aef-132">この方法は効率的ですが、データが一時テーブルまたはテーブル変数に読み込まれなければ、サーバー側での処理がサポートされません。</span><span class="sxs-lookup"><span data-stu-id="10aef-132">Although this technique is very efficient, it does not support server-side processing unless the data is loaded into a temporary table or table variable.</span></span>  
  
## <a name="creating-table-valued-parameter-types"></a><span data-ttu-id="10aef-133">テーブル値パラメーター型の作成</span><span class="sxs-lookup"><span data-stu-id="10aef-133">Creating Table-Valued Parameter Types</span></span>  

 <span data-ttu-id="10aef-134">テーブル値パラメーターは、Transact-SQL の CREATE TYPE ステートメントを使用して定義された厳密に型指定されたテーブルの構造に基づいています。</span><span class="sxs-lookup"><span data-stu-id="10aef-134">Table-valued parameters are based on strongly typed table structures that are defined by using Transact-SQL CREATE TYPE statements.</span></span> <span data-ttu-id="10aef-135">クライアント アプリケーションでテーブル値パラメーターを使用するには、まず SQL Server でテーブル型を作成し、その構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-135">You have to create a table type and define the structure in SQL Server before you can use table-valued parameters in your client applications.</span></span> <span data-ttu-id="10aef-136">テーブル型の作成の詳細については、「[ユーザー定義テーブル型](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10aef-136">For more information about creating table types, see [User-Defined Table Types](/previous-versions/sql/sql-server-2008/bb522526(v=sql.100)).</span></span>  
  
 <span data-ttu-id="10aef-137">次のステートメントは、CategoryID と CategoryName 列から成る CategoryTableType というテーブル型を作成します。</span><span class="sxs-lookup"><span data-stu-id="10aef-137">The following statement creates a table type named CategoryTableType that consists of CategoryID and CategoryName columns:</span></span>  
  
```sql
CREATE TYPE dbo.CategoryTableType AS TABLE  
    ( CategoryID int, CategoryName nvarchar(50) )  
```  
  
 <span data-ttu-id="10aef-138">テーブル型を作成したら、その型に基づいてテーブル値パラメーターを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="10aef-138">After you create a table type, you can declare table-valued parameters based on that type.</span></span> <span data-ttu-id="10aef-139">次の Transact-SQL フラグメントは、ストアド プロシージャ定義の中でテーブル値パラメーターを宣言する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-139">The following Transact-SQL fragment demonstrates how to declare a table-valued parameter in a stored procedure definition.</span></span> <span data-ttu-id="10aef-140">テーブル値パラメーターの宣言には READONLY キーワードが必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="10aef-140">Note that the READONLY keyword is required for declaring a table-valued parameter.</span></span>  
  
```sql
CREATE PROCEDURE usp_UpdateCategories
    (@tvpNewCategories dbo.CategoryTableType READONLY)  
```  
  
## <a name="modifying-data-with-table-valued-parameters-transact-sql"></a><span data-ttu-id="10aef-141">テーブル値パラメーターによるデータの変更 (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="10aef-141">Modifying Data with Table-Valued Parameters (Transact-SQL)</span></span>  

 <span data-ttu-id="10aef-142">テーブル値パラメーターは、単一のステートメントを実行して複数行を操作する、セット ベースのデータ変更の中で使用できます。</span><span class="sxs-lookup"><span data-stu-id="10aef-142">Table-valued parameters can be used in set-based data modifications that affect multiple rows by executing a single statement.</span></span> <span data-ttu-id="10aef-143">たとえば、テーブル値パラメーター内のすべての行を選択して、データベース テーブルに挿入できます。また、テーブル値パラメーターを更新対象テーブルに結合して、更新ステートメントを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="10aef-143">For example, you can select all the rows in a table-valued parameter and insert them into a database table, or you can create an update statement by joining a table-valued parameter to the table you want to update.</span></span>  
  
 <span data-ttu-id="10aef-144">次の Transact-SQL UPDATE ステートメントは、テーブル値パラメーターを Categories テーブルに結合して使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-144">The following Transact-SQL UPDATE statement demonstrates how to use a table-valued parameter by joining it to the Categories table.</span></span> <span data-ttu-id="10aef-145">FROM 句の中でテーブル値パラメーターを JOIN と共に使用する場合は、次に示すように、別名も使用する必要があります。ここでは、テーブル値パラメーターは "ec" という別名になっています。</span><span class="sxs-lookup"><span data-stu-id="10aef-145">When you use a table-valued parameter with a JOIN in a FROM clause, you must also alias it, as shown here, where the table-valued parameter is aliased as "ec":</span></span>  
  
```sql
UPDATE dbo.Categories  
    SET Categories.CategoryName = ec.CategoryName  
    FROM dbo.Categories INNER JOIN @tvpEditedCategories AS ec  
    ON dbo.Categories.CategoryID = ec.CategoryID;  
```  
  
 <span data-ttu-id="10aef-146">この Transact-SQL の例は、単一のセット ベース操作で INSERT を実行するためにテーブル値パラメーターから行を選択する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-146">This Transact-SQL example demonstrates how to select rows from a table-valued parameter to perform an INSERT in a single set-based operation.</span></span>  
  
```sql
INSERT INTO dbo.Categories (CategoryID, CategoryName)  
    SELECT nc.CategoryID, nc.CategoryName FROM @tvpNewCategories AS nc;  
```  
  
## <a name="limitations-of-table-valued-parameters"></a><span data-ttu-id="10aef-147">テーブル値パラメーターの制限</span><span class="sxs-lookup"><span data-stu-id="10aef-147">Limitations of Table-Valued Parameters</span></span>  

 <span data-ttu-id="10aef-148">テーブル値パラメーターにはいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-148">There are several limitations to table-valued parameters:</span></span>  
  
- <span data-ttu-id="10aef-149">テーブル値パラメーターを [CLR ユーザー定義の関数](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions)に渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="10aef-149">You cannot pass table-valued parameters to [CLR user-defined functions](/sql/relational-databases/clr-integration-database-objects-user-defined-functions/clr-user-defined-functions).</span></span>  
  
- <span data-ttu-id="10aef-150">テーブル値パラメーターには、UNIQUE 制約または PRIMARY KEY 制約に対応する目的でのみインデックスを設定できます。</span><span class="sxs-lookup"><span data-stu-id="10aef-150">Table-valued parameters can only be indexed to support UNIQUE or PRIMARY KEY constraints.</span></span> <span data-ttu-id="10aef-151">SQL Server はテーブル値パラメーターの統計を保持しません。</span><span class="sxs-lookup"><span data-stu-id="10aef-151">SQL Server does not maintain statistics on table-valued parameters.</span></span>  
  
- <span data-ttu-id="10aef-152">テーブル値パラメーターは Transact-SQL コードの中では読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="10aef-152">Table-valued parameters are read-only in Transact-SQL code.</span></span> <span data-ttu-id="10aef-153">テーブル値パラメーターの行の列値は更新できません。また、行の挿入や削除もできません。</span><span class="sxs-lookup"><span data-stu-id="10aef-153">You cannot update the column values in the rows of a table-valued parameter and you cannot insert or delete rows.</span></span> <span data-ttu-id="10aef-154">テーブル値パラメーターのストアド プロシージャまたはパラメーター化されたステートメントに渡すデータを変更するには、そのデータを一時テーブルまたはテーブル変数に挿入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-154">To modify the data that is passed to a stored procedure or parameterized statement in table-valued parameter, you must insert the data into a temporary table or into a table variable.</span></span>  
  
- <span data-ttu-id="10aef-155">ALTER TABLE ステートメントをテーブル値パラメーターの設計変更に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="10aef-155">You cannot use ALTER TABLE statements to modify the design of table-valued parameters.</span></span>  
  
## <a name="configuring-a-sqlparameter-example"></a><span data-ttu-id="10aef-156">SqlParameter の構成例</span><span class="sxs-lookup"><span data-stu-id="10aef-156">Configuring a SqlParameter Example</span></span>  

 <span data-ttu-id="10aef-157"><xref:System.Data.SqlClient> では、テーブル値パラメーターのデータを <xref:System.Data.DataTable>、<xref:System.Data.Common.DbDataReader>、または <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> オブジェクトから読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="10aef-157"><xref:System.Data.SqlClient> supports populating table-valued parameters from <xref:System.Data.DataTable>, <xref:System.Data.Common.DbDataReader> or <xref:System.Collections.Generic.IEnumerable%601> \ <xref:Microsoft.SqlServer.Server.SqlDataRecord> objects.</span></span> <span data-ttu-id="10aef-158"><xref:System.Data.SqlClient.SqlParameter.TypeName%2A> の <xref:System.Data.SqlClient.SqlParameter> プロパティを使用して、テーブル値パラメーターの型名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-158">You must specify a type name for the table-valued parameter by using the <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="10aef-159">`TypeName` は、サーバーで以前に作成した互換性のある型の名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-159">The `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="10aef-160">次のコード フラグメントは、データを挿入するために <xref:System.Data.SqlClient.SqlParameter> を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-160">The following code fragment demonstrates how to configure <xref:System.Data.SqlClient.SqlParameter> to insert data.</span></span>  

<span data-ttu-id="10aef-161">次の例では、`addedCategories` 変数に <xref:System.Data.DataTable> が含まれています。</span><span class="sxs-lookup"><span data-stu-id="10aef-161">In the following example, the `addedCategories` variable contains a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="10aef-162">変数がどのように設定されているかを確認するには、次の「[ストアド プロシージャへのテーブル値パラメーターの受け渡し](#passing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10aef-162">To see how the variable is populated, see the examples in the next section, [Passing a Table-Valued Parameter to a Stored Procedure](#passing).</span></span>

```csharp  
// Configure the command and parameter.  
SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
tvpParam.SqlDbType = SqlDbType.Structured;  
tvpParam.TypeName = "dbo.CategoryTableType";  
```  
  
```vb  
' Configure the command and parameter.  
Dim insertCommand As New SqlCommand(sqlInsert, connection)  
Dim tvpParam As SqlParameter = _  
   insertCommand.Parameters.AddWithValue( _  
  "@tvpNewCategories", addedCategories)  
tvpParam.SqlDbType = SqlDbType.Structured  
tvpParam.TypeName = "dbo.CategoryTableType"  
```  
  
 <span data-ttu-id="10aef-163"><xref:System.Data.Common.DbDataReader> から派生した任意のオブジェクトを使用して、一連の行データをテーブル値パラメーターに挿入することもできます。その方法を次のフラグメントに示します。</span><span class="sxs-lookup"><span data-stu-id="10aef-163">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter, as shown in this fragment:</span></span>  
  
```csharp  
// Configure the SqlCommand and table-valued parameter.  
SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
insertCommand.CommandType = CommandType.StoredProcedure;  
SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", dataReader);  
tvpParam.SqlDbType = SqlDbType.Structured;  
```  
  
```vb  
' Configure the SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  dataReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
```  
  
## <a name="passing-a-table-valued-parameter-to-a-stored-procedure"></a><a name="passing"></a> <span data-ttu-id="10aef-164">ストアド プロシージャへのテーブル値パラメーターの受け渡し</span><span class="sxs-lookup"><span data-stu-id="10aef-164">Passing a Table-Valued Parameter to a Stored Procedure</span></span>  

 <span data-ttu-id="10aef-165">この例は、テーブル値パラメーターのデータをストアド プロシージャに渡す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-165">This example demonstrates how to pass table-valued parameter data to a stored procedure.</span></span> <span data-ttu-id="10aef-166">追加された行が、<xref:System.Data.DataTable.GetChanges%2A> メソッドを使って新しい <xref:System.Data.DataTable> に抽出された後、</span><span class="sxs-lookup"><span data-stu-id="10aef-166">The code extracts added rows into a new <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.GetChanges%2A> method.</span></span> <span data-ttu-id="10aef-167"><xref:System.Data.SqlClient.SqlCommand> が定義され、<xref:System.Data.SqlClient.SqlCommand.CommandType%2A> プロパティが <xref:System.Data.CommandType.StoredProcedure> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-167">The code then defines a <xref:System.Data.SqlClient.SqlCommand>, setting the <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> property to <xref:System.Data.CommandType.StoredProcedure>.</span></span> <span data-ttu-id="10aef-168"><xref:System.Data.SqlClient.SqlParameter> は <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> メソッドを使って設定され、<xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> は `Structured` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-168">The <xref:System.Data.SqlClient.SqlParameter> is populated by using the <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> method and the <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> is set to `Structured`.</span></span> <span data-ttu-id="10aef-169">次に <xref:System.Data.SqlClient.SqlCommand> メソッドを使用して <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> が実行されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-169">The <xref:System.Data.SqlClient.SqlCommand> is then executed by using the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection object.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Configure the SqlCommand and SqlParameter.  
  SqlCommand insertCommand = new SqlCommand("usp_InsertCategories", connection);  
  insertCommand.CommandType = CommandType.StoredProcedure;  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection object.  
Using connection  
   '  Create a DataTable with the modified rows.  
   Dim addedCategories As DataTable = _  
     CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Configure the SqlCommand and SqlParameter.  
   Dim insertCommand As New SqlCommand( _  
     "usp_InsertCategories", connection)  
   insertCommand.CommandType = CommandType.StoredProcedure  
   Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
     "@tvpNewCategories", addedCategories)  
   tvpParam.SqlDbType = SqlDbType.Structured  
  
   '  Execute the command.  
   insertCommand.ExecuteNonQuery()  
End Using  
```  
  
### <a name="passing-a-table-valued-parameter-to-a-parameterized-sql-statement"></a><span data-ttu-id="10aef-170">パラメーター化 SQL ステートメントへのテーブル値パラメーターの受け渡し</span><span class="sxs-lookup"><span data-stu-id="10aef-170">Passing a Table-Valued Parameter to a Parameterized SQL Statement</span></span>  

 <span data-ttu-id="10aef-171">次の例は、データ ソースとしてテーブル値パラメーターを持つ SELECT サブクエリ付きの INSERT ステートメントを使用して、dbo.Categories テーブルにデータを挿入する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-171">The following example demonstrates how to insert data into the dbo.Categories table by using an INSERT statement with a SELECT subquery that has a table-valued parameter as the data source.</span></span> <span data-ttu-id="10aef-172">テーブル値パラメーターをパラメーター化 SQL ステートメントに渡すときは、<xref:System.Data.SqlClient.SqlParameter> の新しい <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> プロパティを使用して、テーブル値パラメーターの型名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-172">When passing a table-valued parameter to a parameterized SQL statement, you must specify a type name for the table-valued parameter by using the new <xref:System.Data.SqlClient.SqlParameter.TypeName%2A> property of a <xref:System.Data.SqlClient.SqlParameter>.</span></span> <span data-ttu-id="10aef-173">この `TypeName` は、サーバーで以前に作成した互換性のある型の名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-173">This `TypeName` must match the name of a compatible type previously created on the server.</span></span> <span data-ttu-id="10aef-174">この例のコードは、`TypeName` プロパティを使用して、dbo.CategoryTableType で定義されている型構造体を参照しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-174">The code in this example uses the `TypeName` property to reference the type structure defined in dbo.CategoryTableType.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10aef-175">テーブル値パラメーターで ID 列の値を指定する場合は、そのセッションの SET IDENTITY_INSERT ステートメントを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10aef-175">If you supply a value for an identity column in a table-valued parameter, you must issue the SET IDENTITY_INSERT statement for the session.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
using (connection)  
{  
  // Create a DataTable with the modified rows.  
  DataTable addedCategories = CategoriesDataTable.GetChanges(DataRowState.Added);  

  // Define the INSERT-SELECT statement.  
  string sqlInsert =
      "INSERT INTO dbo.Categories (CategoryID, CategoryName)"  
      + " SELECT nc.CategoryID, nc.CategoryName"  
      + " FROM @tvpNewCategories AS nc;"  

  // Configure the command and parameter.  
  SqlCommand insertCommand = new SqlCommand(sqlInsert, connection);  
  SqlParameter tvpParam = insertCommand.Parameters.AddWithValue("@tvpNewCategories", addedCategories);  
  tvpParam.SqlDbType = SqlDbType.Structured;  
  tvpParam.TypeName = "dbo.CategoryTableType";  

  // Execute the command.  
  insertCommand.ExecuteNonQuery();  
}  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
Using connection  
  ' Create a DataTable with the modified rows.  
  Dim addedCategories As DataTable = _  
    CategoriesDataTable.GetChanges(DataRowState.Added)  
  
  ' Define the INSERT-SELECT statement.  
  Dim sqlInsert As String = _  
  "INSERT INTO dbo.Categories (CategoryID, CategoryName)" _  
  & " SELECT nc.CategoryID, nc.CategoryName" _  
  & " FROM @tvpNewCategories AS nc;"  
  
  ' Configure the command and parameter.  
  Dim insertCommand As New SqlCommand(sqlInsert, connection)  
  Dim tvpParam As SqlParameter = _  
     insertCommand.Parameters.AddWithValue( _  
    "@tvpNewCategories", addedCategories)  
  tvpParam.SqlDbType = SqlDbType.Structured  
  tvpParam.TypeName = "dbo.CategoryTableType"  
  
  ' Execute the query  
  insertCommand.ExecuteNonQuery()  
End Using  
```  
  
## <a name="streaming-rows-with-a-datareader"></a><span data-ttu-id="10aef-176">DataReader による行のストリーミング</span><span class="sxs-lookup"><span data-stu-id="10aef-176">Streaming Rows with a DataReader</span></span>  

 <span data-ttu-id="10aef-177">テーブル値パラメーターにデータ行をストリーム出力するには、<xref:System.Data.Common.DbDataReader> から派生したオブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="10aef-177">You can also use any object derived from <xref:System.Data.Common.DbDataReader> to stream rows of data to a table-valued parameter.</span></span> <span data-ttu-id="10aef-178">次のコード フラグメントは、<xref:System.Data.OracleClient.OracleCommand> と <xref:System.Data.OracleClient.OracleDataReader> を使用して、Oracle データベースからデータを取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="10aef-178">The following code fragment demonstrates retrieving data from an Oracle database by using an <xref:System.Data.OracleClient.OracleCommand> and an <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="10aef-179">その後、<xref:System.Data.SqlClient.SqlCommand> を、1 つの入力パラメーターを使用してストアド プロシージャを呼び出すように構成します。</span><span class="sxs-lookup"><span data-stu-id="10aef-179">The code then configures a <xref:System.Data.SqlClient.SqlCommand> to invoke a stored procedure with a single input parameter.</span></span> <span data-ttu-id="10aef-180"><xref:System.Data.SqlClient.SqlParameter> の <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> プロパティは `Structured` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="10aef-180">The <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> property of the <xref:System.Data.SqlClient.SqlParameter> is set to `Structured`.</span></span> <span data-ttu-id="10aef-181"><xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> は `OracleDataReader` の結果セットをテーブル値パラメーターとしてストアド プロシージャに渡します。</span><span class="sxs-lookup"><span data-stu-id="10aef-181">The <xref:System.Data.SqlClient.SqlParameterCollection.AddWithValue%2A> passes the `OracleDataReader` result set to the stored procedure as a table-valued parameter.</span></span>  
  
```csharp  
// Assumes connection is an open SqlConnection.  
// Retrieve data from Oracle.  
OracleCommand selectCommand = new OracleCommand(  
   "Select CategoryID, CategoryName FROM Categories;",  
   oracleConnection);  
OracleDataReader oracleReader = selectCommand.ExecuteReader(  
   CommandBehavior.CloseConnection);  
  
 // Configure the SqlCommand and table-valued parameter.  
 SqlCommand insertCommand = new SqlCommand(  
   "usp_InsertCategories", connection);  
 insertCommand.CommandType = CommandType.StoredProcedure;  
 SqlParameter tvpParam =  
    insertCommand.Parameters.AddWithValue(  
    "@tvpNewCategories", oracleReader);  
 tvpParam.SqlDbType = SqlDbType.Structured;  
  
 // Execute the command.  
 insertCommand.ExecuteNonQuery();  
```  
  
```vb  
' Assumes connection is an open SqlConnection.  
' Retrieve data from Oracle.  
Dim selectCommand As New OracleCommand( _  
  "Select CategoryID, CategoryName FROM Categories;", _  
  oracleConnection)  
Dim oracleReader As OracleDataReader = _  
  selectCommand.ExecuteReader(CommandBehavior.CloseConnection)  
  
' Configure SqlCommand and table-valued parameter.  
Dim insertCommand As New SqlCommand("usp_InsertCategories", connection)  
insertCommand.CommandType = CommandType.StoredProcedure  
Dim tvpParam As SqlParameter = _  
  insertCommand.Parameters.AddWithValue("@tvpNewCategories", _  
  oracleReader)  
tvpParam.SqlDbType = SqlDbType.Structured  
  
' Execute the command.  
insertCommand.ExecuteNonQuery()  
```  
  
## <a name="see-also"></a><span data-ttu-id="10aef-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="10aef-182">See also</span></span>

- [<span data-ttu-id="10aef-183">パラメーターおよびパラメーター データ型の構成</span><span class="sxs-lookup"><span data-stu-id="10aef-183">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="10aef-184">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="10aef-184">Commands and Parameters</span></span>](../commands-and-parameters.md)
- [<span data-ttu-id="10aef-185">DataAdapter パラメーター</span><span class="sxs-lookup"><span data-stu-id="10aef-185">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- [<span data-ttu-id="10aef-186">ADO.NET における SQL Server データ操作</span><span class="sxs-lookup"><span data-stu-id="10aef-186">SQL Server Data Operations in ADO.NET</span></span>](sql-server-data-operations.md)
- [<span data-ttu-id="10aef-187">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="10aef-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
