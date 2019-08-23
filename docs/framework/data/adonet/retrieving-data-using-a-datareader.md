---
title: DataReader によるデータの取得
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 561ebd7ac6948fa42f73ebb4f1eb97c574e6d7e7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963184"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="4f461-102">DataReader を使用してデータを取得する</span><span class="sxs-lookup"><span data-stu-id="4f461-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="4f461-103">**Datareader**を使用してデータを取得するには、 **command**オブジェクトのインスタンスを作成した後、 **ExecuteReader**を呼び出してデータソースから行を取得し、 **datareader**を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f461-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="4f461-104">**DataReader**は、バッファリングされていないデータストリームを提供します。これにより、手続き型のロジックによって、データソースからの結果を順番に効率的に処理できます。</span><span class="sxs-lookup"><span data-stu-id="4f461-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="4f461-105">データがメモリにキャッシュされないため、大量のデータを取得する場合は、 **DataReader**を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f461-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="4f461-106">`command` Datareader`reader`を使用する例を次に示します。は有効な datareader を表し、は有効な Command オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="4f461-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="4f461-107">クエリ結果から行を取得するには、 **DataReader. Read**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f461-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="4f461-108">返された行の各列には、列の名前または序数を**DataReader**に渡すことによってアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f461-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="4f461-109">ただし、最適なパフォーマンスを得るために、 **DataReader**には、ネイティブデータ型 (**getdatetime**、 **getdatetime**、 **getdatetime**、 **GetInt32**など) の列値にアクセスできる一連のメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f461-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="4f461-110">データプロバイダー固有の**datareader**の型指定されたアクセサーメソッドの一覧<xref:System.Data.OleDb.OleDbDataReader>については、「」および<xref:System.Data.SqlClient.SqlDataReader>「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f461-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="4f461-111">基になるデータ型がわかっている場合は、型指定されたアクセサーメソッドを使用して、列の値を取得するときに必要な型変換の量を減らします。</span><span class="sxs-lookup"><span data-stu-id="4f461-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="4f461-112">次の例では、 **DataReader**オブジェクトを反復処理し、各行から2つの列を返します。</span><span class="sxs-lookup"><span data-stu-id="4f461-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="4f461-113">DataReader の終了</span><span class="sxs-lookup"><span data-stu-id="4f461-113">Closing the DataReader</span></span>  
 <span data-ttu-id="4f461-114">**DataReader**オブジェクトの使用が終了したら、常に**Close**メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f461-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="4f461-115">**コマンド**に出力パラメーターまたは戻り値が含まれている場合、これらの値は**DataReader**が閉じられるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="4f461-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="4f461-116">**Datareader**が開いている間は、その**datareader**によって**接続**が排他的に使用されています。</span><span class="sxs-lookup"><span data-stu-id="4f461-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="4f461-117">元の**datareader**が閉じられるまで、**接続**のコマンド (別の**datareader**の作成を含む) を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f461-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f461-118">クラスの**Finalize**メソッドで、**接続**、 **DataReader**、またはその他のマネージオブジェクトに対して**Close**または**Dispose**を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="4f461-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="4f461-119">終了処理では、クラスに直接所有されているアンマネージ リソースだけを解放してください。</span><span class="sxs-lookup"><span data-stu-id="4f461-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="4f461-120">クラスがアンマネージリソースを所有していない場合は、クラス定義に**Finalize**メソッドを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="4f461-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="4f461-121">詳細については、「[ガベージコレクション](../../../standard/garbage-collection/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f461-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="4f461-122">NextResult を使用して複数の結果セットを取得する</span><span class="sxs-lookup"><span data-stu-id="4f461-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="4f461-123">**DataReader**から複数の結果セットが返された場合は、 **nextresult**メソッドを呼び出して、結果セットを順番に反復処理します。</span><span class="sxs-lookup"><span data-stu-id="4f461-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="4f461-124"><xref:System.Data.SqlClient.SqlDataReader> メソッドを使用して、2 つの SELECT ステートメントの結果を処理する <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f461-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="4f461-125">DataReader からのスキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="4f461-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="4f461-126">**DataReader**が開いている間は、 **getschematable**メソッドを使用して、現在の結果セットに関するスキーマ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4f461-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="4f461-127">**Getschematable**は、 <xref:System.Data.DataTable>現在の結果セットのスキーマ情報を含む行と列を含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4f461-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="4f461-128">DataTable には、結果セットの列ごとに1行の**データ**が格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f461-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="4f461-129">スキーマテーブルの各列は、結果セットの行で返される列のプロパティにマップされます。ここで、 **ColumnName**はプロパティの名前、列の値はプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="4f461-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="4f461-130">次の例では、 **DataReader**のスキーマ情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="4f461-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="4f461-131">OLE DB の章を操作する</span><span class="sxs-lookup"><span data-stu-id="4f461-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="4f461-132">階層型の行セット、つまりチャプター (OLE DB type **DBTYPE_HCHAPTER**、ADO 型**adchapter**) は、 <xref:System.Data.OleDb.OleDbDataReader>を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="4f461-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="4f461-133">チャプターを含むクエリが**datareader**として返された場合、チャプターはその**datareader**の列として返され、 **datareader**オブジェクトとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="4f461-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="4f461-134">ADO.NET**データセット**を使用すると、テーブル間の親子リレーションシップを使用して、階層的な行セットを表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4f461-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="4f461-135">詳細については、「[データセット、datatable、および DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f461-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="4f461-136">MSDataShape プロバイダーを使用して、顧客リストの顧客別オーダーのチャプター列を生成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f461-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
```vb  
Using connection As OleDbConnection = New OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" &
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind")

    Using custCMD As OleDbCommand = New OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " &
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " &
        "RELATE CustomerID TO CustomerID)", connection)

        connection.Open()

        Using custReader As OleDbDataReader = custCMD.ExecuteReader()

            Do While custReader.Read()
                Console.WriteLine("Orders for " & custReader.GetString(1))
                ' custReader.GetString(1) = CompanyName  

                Using orderReader As OleDbDataReader = custReader.GetValue(2)
                    ' custReader.GetValue(2) = Orders chapter as DataReader  

                    Do While orderReader.Read()
                        Console.WriteLine(vbTab & orderReader.GetInt32(1))
                        ' orderReader.GetInt32(1) = OrderID  
                    Loop
                    orderReader.Close()
                End Using
            Loop
            ' Make sure to always close readers and connections.  
            custReader.Close()
        End Using
    End Using
End Using
```  
  
```csharp  
using (OleDbConnection connection = new OleDbConnection(
    "Provider=MSDataShape;Data Provider=SQLOLEDB;" +
    "Data Source=localhost;Integrated Security=SSPI;Initial Catalog=northwind"))
{
    using (OleDbCommand custCMD = new OleDbCommand(
        "SHAPE {SELECT CustomerID, CompanyName FROM Customers} " +
        "APPEND ({SELECT CustomerID, OrderID FROM Orders} AS CustomerOrders " +
        "RELATE CustomerID TO CustomerID)", connection))
    {
        connection.Open();

        using (OleDbDataReader custReader = custCMD.ExecuteReader())
        {

            while (custReader.Read())
            {
                Console.WriteLine("Orders for " + custReader.GetString(1));
                // custReader.GetString(1) = CompanyName  

                using (OleDbDataReader orderReader = (OleDbDataReader)custReader.GetValue(2))
                {
                    // custReader.GetValue(2) = Orders chapter as DataReader  

                    while (orderReader.Read())
                        Console.WriteLine("\t" + orderReader.GetInt32(1));
                    // orderReader.GetInt32(1) = OrderID  
                    orderReader.Close();
                }
            }
            // Make sure to always close readers and connections.  
            custReader.Close();
        }
    }
}
```  
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="4f461-137">Oracle REF cursor を使用して結果を返す</span><span class="sxs-lookup"><span data-stu-id="4f461-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="4f461-138">.NET Framework Data Provider for Oracle は、クエリ結果を返すために、Oracle REF CURSOR の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f461-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="4f461-139">Oracle REF CURSOR は <xref:System.Data.OracleClient.OracleDataReader> として返されます。</span><span class="sxs-lookup"><span data-stu-id="4f461-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="4f461-140">Oracle REF カーソルを<xref:System.Data.OracleClient.OracleDataReader>表すオブジェクトを取得するには、 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f461-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="4f461-141">にデータを格納<xref:System.Data.OracleClient.OracleCommand> するため<xref:System.Data.OracleClient.OracleDataAdapter>に使用されるの**SelectCommand**として1つ以上の Oracle REF cursor を返すを指定することもできます。<xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="4f461-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="4f461-142">Oracle データソースから返された ref カーソルにアクセスするには<xref:System.Data.OracleClient.OracleCommand> 、クエリのを作成し、ref カーソル<xref:System.Data.OracleClient.OracleCommand.Parameters>を参照する出力パラメーターをの<xref:System.Data.OracleClient.OracleCommand>コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4f461-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="4f461-143">パラメーターの名前は、クエリの REF CURSOR パラメーターの名前と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f461-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="4f461-144">パラメーターの型をに<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>設定します。</span><span class="sxs-lookup"><span data-stu-id="4f461-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4f461-145">のメソッドは<xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> 、REF カーソル<xref:System.Data.OracleClient.OracleDataReader>のを返します。<xref:System.Data.OracleClient.OracleCommand></span><span class="sxs-lookup"><span data-stu-id="4f461-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="4f461-146">が複数の REF cursorを返す場合は、複数の出力パラメーターを追加します。<xref:System.Data.OracleClient.OracleCommand></span><span class="sxs-lookup"><span data-stu-id="4f461-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="4f461-147">異なる REF カーソルにアクセスするには、 <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f461-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4f461-148">の呼び出し<xref:System.Data.OracleClient.OracleCommand.ExecuteReader>は、最初<xref:System.Data.OracleClient.OracleDataReader>の REF カーソルを参照するを返します。</span><span class="sxs-lookup"><span data-stu-id="4f461-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="4f461-149">その後、メソッドを<xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType>呼び出して、後続の REF カーソルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4f461-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="4f461-150"><xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>コレクション内のパラメーターは、REF CURSOR 出力パラメーターと名前で一致します<xref:System.Data.OracleClient.OracleDataReader>が、は<xref:System.Data.OracleClient.OracleCommand.Parameters>コレクションに追加された順序でこれらのパラメーターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="4f461-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="4f461-151">たとえば、次のような Oracle パッケージとパッケージ本体があるとします。</span><span class="sxs-lookup"><span data-stu-id="4f461-151">For example, consider the following Oracle package and package body.</span></span>  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS   
  TYPE T_CURSOR IS REF CURSOR;   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR);   
END CURSPKG;  
  
CREATE OR REPLACE PACKAGE BODY CURSPKG AS   
  PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
    DEPTCURSOR OUT T_CURSOR)   
  IS   
  BEGIN   
    OPEN EMPCURSOR FOR SELECT * FROM DEMO.EMPLOYEE;   
    OPEN DEPTCURSOR FOR SELECT * FROM DEMO.DEPARTMENT;   
  END OPEN_TWO_CURSORS;   
END CURSPKG;   
```  
  
 <span data-ttu-id="4f461-152">次のコードは、 <xref:System.Data.OracleClient.OracleCommand>型<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>の2つのパラメーターを<xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>コレクションに追加することによって、以前の Oracle パッケージから参照カーソルを返すを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f461-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
```vb  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
```  
  
```csharp  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
```  
  
 <span data-ttu-id="4f461-153">次のコードは、 <xref:System.Data.OracleClient.OracleDataReader.Read> <xref:System.Data.OracleClient.OracleDataReader>のメソッドと<xref:System.Data.OracleClient.OracleDataReader.NextResult>メソッドを使用して、前のコマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4f461-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="4f461-154">REF CURSOR パラメーターは順番に返されます。</span><span class="sxs-lookup"><span data-stu-id="4f461-154">The REF CURSOR parameters are returned in order.</span></span>  
  
```vb  
oraConn.Open()  
  
Dim cursCmd As OracleCommand = New OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn)  
cursCmd.CommandType = CommandType.StoredProcedure  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output  
  
Dim reader As OracleDataReader = cursCmd.ExecuteReader()  
  
Console.WriteLine(vbCrLf & "Emp ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2))  
Loop  
  
reader.NextResult()  
  
Console.WriteLine(vbCrLf & "Dept ID" & vbTab & "Name")  
  
Do While reader.Read()  
  Console.WriteLine("{0}" & vbTab & "{1}", reader.GetOracleNumber(0), reader.GetString(1))  
Loop  
' Make sure to always close readers and connections.  
reader.Close()  
oraConn.Close()  
```  
  
```csharp  
oraConn.Open();  
  
OracleCommand cursCmd = new OracleCommand("CURSPKG.OPEN_TWO_CURSORS", oraConn);  
cursCmd.CommandType = CommandType.StoredProcedure;  
cursCmd.Parameters.Add("EMPCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
cursCmd.Parameters.Add("DEPTCURSOR", OracleType.Cursor).Direction = ParameterDirection.Output;  
  
OracleDataReader reader = cursCmd.ExecuteReader();  
  
Console.WriteLine("\nEmp ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}, {2}", reader.GetOracleNumber(0), reader.GetString(1), reader.GetString(2));  
  
reader.NextResult();  
  
Console.WriteLine("\nDept ID\tName");  
  
while (reader.Read())  
  Console.WriteLine("{0}\t{1}", reader.GetOracleNumber(0), reader.GetString(1));  
// Make sure to always close readers and connections.  
reader.Close();  
oraConn.Close();  
```  
  
 <span data-ttu-id="4f461-155">次の例では、前のコマンドを<xref:System.Data.DataSet>使用して、Oracle パッケージの結果をに設定します。</span><span class="sxs-lookup"><span data-stu-id="4f461-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
```vb  
Dim ds As DataSet = New DataSet()  
  
Dim adapter As OracleDataAdapter = New OracleDataAdapter(cursCmd)  
adapter.TableMappings.Add("Table", "Employees")  
adapter.TableMappings.Add("Table1", "Departments")  
  
adapter.Fill(ds)  
```  
  
```csharp  
DataSet ds = new DataSet();  
  
OracleDataAdapter adapter = new OracleDataAdapter(cursCmd);  
adapter.TableMappings.Add("Table", "Employees");  
adapter.TableMappings.Add("Table1", "Departments");  
  
adapter.Fill(ds);  
```

> [!NOTE]
> <span data-ttu-id="4f461-156">**OverflowException**を回避するには、に値<xref:System.Data.DataRow>を格納する前に、Oracle の数値型から有効な .NET Framework 型への変換も処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f461-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="4f461-157">イベントを使用し<xref:System.Data.Common.DataAdapter.FillError>て、 **OverflowException**が発生したかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="4f461-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="4f461-158"><xref:System.Data.Common.DataAdapter.FillError>イベントの詳細については、「 [DataAdapter イベントの処理](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f461-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f461-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f461-159">See also</span></span>

- [<span data-ttu-id="4f461-160">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="4f461-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="4f461-161">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="4f461-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="4f461-162">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="4f461-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="4f461-163">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="4f461-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
