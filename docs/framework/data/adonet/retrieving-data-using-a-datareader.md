---
title: DataReader によるデータの取得
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149025"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="d11f6-102">DataReader を使用してデータを取得する</span><span class="sxs-lookup"><span data-stu-id="d11f6-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="d11f6-103">**DataReader** を使用してデータを取得するには、**Command** オブジェクトのインスタンスを作成した後、**Command.ExecuteReader** を呼び出して **DataReader** を作成し、データ ソースから行を取得します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="d11f6-104">**DataReader** では、手続きロジックがデータ ソースからの結果を順番に効率的に処理できるようにするバッファリングされないデータ ストリームが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="d11f6-105">**DataReader** はデータをメモリにキャッシュしないため、大量のデータを取得する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="d11f6-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="d11f6-106">**DataReader** を使用する例を次に示します。ここで、`reader` は有効な DataReader を、`command` は有効な Command オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="d11f6-107">クエリ結果から行を取得するには、**DataReader.Read** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="d11f6-108">返された行の各列にアクセスするには、その列の名前または序数を **DataReader** に渡します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="d11f6-109">ただし、**DataReader** では、最適のパフォーマンスが得られるように、ネイティブのデータ型を使用して列の値にアクセスできる一連のメソッド (**GetDateTime**、**GetDouble**、**GetGuid**、**GetInt32** など) が提供されています。</span><span class="sxs-lookup"><span data-stu-id="d11f6-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="d11f6-110">データ プロバイダー固有の **DataReader** に対する型指定されたアクセサー メソッドの一覧については、<xref:System.Data.OleDb.OleDbDataReader> および <xref:System.Data.SqlClient.SqlDataReader> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="d11f6-111">基になるデータ型がわかっているときは、型指定されたアクセサー メソッドを使用すると、列の値を取得するときに必要な型変換の量が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="d11f6-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="d11f6-112">次に、**DataReader** オブジェクトを反復処理して各行から 2 つの列を返す例を示します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="d11f6-113">DataReader の終了</span><span class="sxs-lookup"><span data-stu-id="d11f6-113">Closing the DataReader</span></span>  
 <span data-ttu-id="d11f6-114">**DataReader** オブジェクトを使い終えたら、**Close** メソッドを必ず呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="d11f6-115">**Command** に出力パラメーターまたは戻り値が含まれている場合、**DataReader** が閉じられるまで、それらの値を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d11f6-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="d11f6-116">**DataReader** が開かれている間、**Connection** はその **DataReader** によって排他的に使用されています。</span><span class="sxs-lookup"><span data-stu-id="d11f6-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="d11f6-117">元の **DataReader** が閉じられるまでは、別の **DataReader** の作成など、どのようなコマンドもその **Connection** に対して実行できません。</span><span class="sxs-lookup"><span data-stu-id="d11f6-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d11f6-118">クラスの **Finalize** メソッド内では、**Connection**、**DataReader**、またはその他のマネージド オブジェクトに対して、**Close** または **Dispose** を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="d11f6-119">終了処理では、クラスに直接所有されているアンマネージ リソースだけを解放してください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="d11f6-120">クラスがアンマネージド リソースを所有していない場合は、クラス定義に **Finalize** メソッドを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="d11f6-121">詳しくは、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="d11f6-122">NextResult による複数の結果セットの取得</span><span class="sxs-lookup"><span data-stu-id="d11f6-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="d11f6-123">**DataReader** から複数の結果セットが返される場合は、**NextResult** メソッドを呼び出して、結果セットを順番に反復処理します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="d11f6-124"><xref:System.Data.SqlClient.SqlDataReader> メソッドを使用して、2 つの SELECT ステートメントの結果を処理する <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="d11f6-125">DataReader からのスキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="d11f6-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="d11f6-126">**DataReader** が開かれている間に **GetSchemaTable** メソッドを使用して、現在の結果セットについてのスキーマ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="d11f6-127">**GetSchemaTable** は、現在の結果セットのスキーマ情報を含む行と列が設定されている <xref:System.Data.DataTable> オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="d11f6-128">**DataTable** には結果セットの列ごとに 1 行が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="d11f6-129">スキーマ テーブルの各列は、結果セットの行で返される列の 1 つのプロパティにマップされます。**ColumnName** はそのプロパティの名前であり、列の値はプロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="d11f6-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="d11f6-130">**DataReader** のスキーマ情報を出力する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="d11f6-131">OLE DB のチャプターの使用</span><span class="sxs-lookup"><span data-stu-id="d11f6-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="d11f6-132">階層構造の行セット、つまりチャプター (OLE DB では **DBTYPE_HCHAPTER** 型、ADO では **adChapter** 型) は、<xref:System.Data.OleDb.OleDbDataReader> を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="d11f6-133">チャプターを含むクエリが **DataReader** として返されるとき、チャプターはその **DataReader** の列として返され、**DataReader** オブジェクトとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="d11f6-134">ADO.NET の **DataSet** を使用することで、テーブル間の親子のリレーションシップを使用して階層構造の行セットを表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="d11f6-135">詳しくは、「[DataSet、DataTable、および DataView](./dataset-datatable-dataview/index.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-135">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="d11f6-136">MSDataShape プロバイダーを使用して、顧客リストの顧客別オーダーのチャプター列を生成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="d11f6-137">Oracle REF CURSOR による結果の取得</span><span class="sxs-lookup"><span data-stu-id="d11f6-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="d11f6-138">.NET Framework Data Provider for Oracle は、クエリ結果を返すために、Oracle REF CURSOR の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d11f6-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="d11f6-139">Oracle REF CURSOR は <xref:System.Data.OracleClient.OracleDataReader> として返されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="d11f6-140"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> メソッドを使用して、Oracle の REF CURSOR を表す <xref:System.Data.OracleClient.OracleDataReader> オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="d11f6-141"><xref:System.Data.DataSet> を設定するために使用される <xref:System.Data.OracleClient.OracleDataAdapter> に対する **SelectCommand** として 1 つまたは複数の Oracle の REF CURSOR を返す <xref:System.Data.OracleClient.OracleCommand> を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="d11f6-142">Oracle データ ソースから返された REF CURSOR にアクセスするには、クエリ用の <xref:System.Data.OracleClient.OracleCommand> を作成し、<xref:System.Data.OracleClient.OracleCommand> の <xref:System.Data.OracleClient.OracleCommand.Parameters> コレクションに、REF CURSOR を参照する出力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="d11f6-143">パラメーターの名前は、クエリの REF CURSOR パラメーターの名前と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d11f6-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="d11f6-144">パラメーターの型を <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> に設定します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d11f6-145"><xref:System.Data.OracleClient.OracleCommand> の <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> メソッドでは、REF CURSOR に対する <xref:System.Data.OracleClient.OracleDataReader> が返されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="d11f6-146"><xref:System.Data.OracleClient.OracleCommand> で複数の REF CURSOR が返される場合は、複数の出力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="d11f6-147"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> メソッドを呼び出すことにより、異なる REF CURSOR にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d11f6-148"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader> を呼び出すと、最初の REF CURSOR を参照している <xref:System.Data.OracleClient.OracleDataReader> が返されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="d11f6-149">次に <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> メソッドを呼び出すと、後続の REF CURSOR にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="d11f6-150"><xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> コレクションのパラメーターが REF CURSOR 出力パラメーターの名前と一致していても、<xref:System.Data.OracleClient.OracleDataReader> は、<xref:System.Data.OracleClient.OracleCommand.Parameters> コレクションに追加された順に出力パラメーターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d11f6-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="d11f6-151">たとえば、次のような Oracle パッケージとパッケージ本体があるとします。</span><span class="sxs-lookup"><span data-stu-id="d11f6-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="d11f6-152">次のコードで作成する <xref:System.Data.OracleClient.OracleCommand> では、<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> 型の 2 つのパラメーターを <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> コレクションに追加することで、上の Oracle パッケージから REF CURSOR を返します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="d11f6-153"><xref:System.Data.OracleClient.OracleDataReader> の <xref:System.Data.OracleClient.OracleDataReader.Read> メソッドと <xref:System.Data.OracleClient.OracleDataReader.NextResult> メソッドを使用して、上のコマンドの結果を返すコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="d11f6-154">REF CURSOR パラメーターは順番に返されます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="d11f6-155">上のコマンドを使用して、Oracle パッケージの結果を <xref:System.Data.DataSet> に設定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d11f6-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="d11f6-156">**OverflowException** が発生しないようにするため、<xref:System.Data.DataRow> に値を格納する前に、Oracle の NUMBER 型を有効な .NET Framework のデータ型に変換することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d11f6-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="d11f6-157"><xref:System.Data.Common.DataAdapter.FillError> イベントを使用して、**OverflowException** が発生したかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d11f6-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="d11f6-158"><xref:System.Data.Common.DataAdapter.FillError> イベントについて詳しくは、「[DataAdapter のイベント処理](handling-dataadapter-events.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d11f6-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11f6-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="d11f6-159">See also</span></span>

- [<span data-ttu-id="d11f6-160">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="d11f6-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="d11f6-161">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="d11f6-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="d11f6-162">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="d11f6-162">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="d11f6-163">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="d11f6-163">ADO.NET Overview</span></span>](ado-net-overview.md)
