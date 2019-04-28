---
title: DataReader によるデータの取得
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 8063f239123ec1a2f2650adf9d76f7ceaaa50673
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664261"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="c1a48-102">DataReader によるデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="c1a48-103">使用してデータを取得する、 **DataReader**のインスタンスを作成、**コマンド**オブジェクト、し、作成、 **DataReader**呼び出して**Command.ExecuteReader**データ ソースから行を取得します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="c1a48-104">**DataReader**は手続き型のロジックを効率的にデータ ソースからの結果を順番に処理を可能にするデータのバッファリングされていないストリームを提供します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="c1a48-105">**DataReader**データがメモリにキャッシュされていないために、大量のデータを取得しているときをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c1a48-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="c1a48-106">次の例を使用して、 **DataReader**ここで、`reader`は有効な datareader と`command`有効な Command オブジェクトを表します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="c1a48-107">使用して、 **DataReader.Read**クエリ結果から行を取得します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="c1a48-108">返された行の各列をアクセスするには、名前または列の序数を渡すことによって、 **DataReader**します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="c1a48-109">ただし、最高のパフォーマンスについて、 **DataReader**一連のネイティブ データ型の列の値にアクセスできるようにするメソッドを提供します (**GetDateTime**、 **GetDouble**、 **GetGuid**、 **GetInt32**など)。</span><span class="sxs-lookup"><span data-stu-id="c1a48-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="c1a48-110">データ プロバイダーに固有の型指定されたアクセサー メソッドの一覧については**DataReaders**を参照してください<xref:System.Data.OleDb.OleDbDataReader>と<xref:System.Data.SqlClient.SqlDataReader>します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="c1a48-111">型は、基になるデータがわかっている場合は、型指定されたアクセサー メソッドを使用して、列の値を取得するときに必要な型変換の量を減らします。</span><span class="sxs-lookup"><span data-stu-id="c1a48-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="c1a48-112">次の例を反復処理を**DataReader**オブジェクトを各行から 2 つの列を返します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="c1a48-113">DataReader の終了</span><span class="sxs-lookup"><span data-stu-id="c1a48-113">Closing the DataReader</span></span>  
 <span data-ttu-id="c1a48-114">常に呼び出し、**閉じる**メソッドを使用してが完了したら、 **DataReader**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1a48-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="c1a48-115">場合、**コマンド**の出力を含むパラメーターまたは戻り値の場合は、これらの値をまでご利用いただけません、 **DataReader**が閉じられました。</span><span class="sxs-lookup"><span data-stu-id="c1a48-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="c1a48-116">中に、 **DataReader**が開いて、**接続**によって排他的に使用されて**DataReader**します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="c1a48-117">任意のコマンドを実行することはできません、**接続**、もう 1 つ作成を含む**DataReader**、まで、元の**DataReader**が閉じられました。</span><span class="sxs-lookup"><span data-stu-id="c1a48-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1a48-118">呼び出さないでください**閉じる**または**Dispose**上、**接続**、 **DataReader**、またはその他のマネージ オブジェクトで、 **Finalize**クラスのメソッド。</span><span class="sxs-lookup"><span data-stu-id="c1a48-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="c1a48-119">終了処理では、クラスに直接所有されているアンマネージ リソースだけを解放してください。</span><span class="sxs-lookup"><span data-stu-id="c1a48-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="c1a48-120">クラスがアンマネージ リソースを所有していない場合は含まれません、 **Finalize**メソッド、クラス定義にします。</span><span class="sxs-lookup"><span data-stu-id="c1a48-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="c1a48-121">詳細については、次を参照してください。[ガベージ コレクション](../../../../docs/standard/garbage-collection/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-121">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="c1a48-122">NextResult による複数の結果を取得する設定します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="c1a48-123">場合、 **DataReader**呼び出し、複数の結果セットを返す、 **NextResult**結果を反復処理するメソッドが順番に設定します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="c1a48-124"><xref:System.Data.SqlClient.SqlDataReader> メソッドを使用して、2 つの SELECT ステートメントの結果を処理する <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="c1a48-125">DataReader からスキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="c1a48-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="c1a48-126">中に、 **DataReader**は開くことができますを取得する設定を使用して現在の結果に関するスキーマ情報、 **GetSchemaTable**メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1a48-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="c1a48-127">**GetSchemaTable**を返します、<xref:System.Data.DataTable>行と、現在の結果セットのスキーマ情報を含む列を含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1a48-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="c1a48-128">**DataTable**結果セットの列ごとに 1 つの行が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1a48-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="c1a48-129">スキーマ テーブルの各列に返される列のプロパティにマップ、結果の行セットを**ColumnName**プロパティの名前であり、列の値は、プロパティの値。</span><span class="sxs-lookup"><span data-stu-id="c1a48-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="c1a48-130">次の例のスキーマ情報を書き込みます**DataReader**します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="c1a48-131">OLE DB のチャプターの使用</span><span class="sxs-lookup"><span data-stu-id="c1a48-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="c1a48-132">階層的な行セット、つまりチャプター (OLE DB 型**DBTYPE_HCHAPTER**、ADO 型**adChapter**) を使用して取得できます、<xref:System.Data.OleDb.OleDbDataReader>します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="c1a48-133">チャプターを含むクエリとして返される場合、 **DataReader**、章を内の列として返されます**DataReader**として公開されると、 **DataReader**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c1a48-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="c1a48-134">ADO.NET**データセット**テーブル間の親子リレーションシップを使用して階層的な行セットを表すためも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c1a48-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="c1a48-135">詳細については、次を参照してください。 [Dataset、Datatable、および Dataview](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-135">For more information, see [DataSets, DataTables, and DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="c1a48-136">MSDataShape プロバイダーを使用して、顧客リストの顧客別オーダーのチャプター列を生成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="c1a48-137">Oracle REF Cursor による結果の取得</span><span class="sxs-lookup"><span data-stu-id="c1a48-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="c1a48-138">.NET Framework Data Provider for Oracle は、クエリ結果を返すために、Oracle REF CURSOR の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c1a48-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="c1a48-139">Oracle REF CURSOR は <xref:System.Data.OracleClient.OracleDataReader> として返されます。</span><span class="sxs-lookup"><span data-stu-id="c1a48-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="c1a48-140">取得することができます、<xref:System.Data.OracleClient.OracleDataReader>を使用して Oracle REF CURSOR を表すオブジェクトを<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1a48-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="c1a48-141">指定することも、<xref:System.Data.OracleClient.OracleCommand>として 1 つまたは複数の Oracle REF Cursor を返す、 **SelectCommand**の<xref:System.Data.OracleClient.OracleDataAdapter>塗りつぶしに使用される、 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="c1a48-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="c1a48-142">Oracle データ ソースから返された REF CURSOR にアクセスするには、作成、 <xref:System.Data.OracleClient.OracleCommand> 、クエリの REF CURSOR を参照する出力パラメーターを追加し、<xref:System.Data.OracleClient.OracleCommand.Parameters>のコレクション、<xref:System.Data.OracleClient.OracleCommand>します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="c1a48-143">パラメーターの名前は、クエリの REF CURSOR パラメーターの名前と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1a48-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="c1a48-144">設定するパラメーターの型<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c1a48-145"><xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>のメソッド、<xref:System.Data.OracleClient.OracleCommand>を返します、 <xref:System.Data.OracleClient.OracleDataReader> REF CURSOR の。</span><span class="sxs-lookup"><span data-stu-id="c1a48-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="c1a48-146">場合、<xref:System.Data.OracleClient.OracleCommand>複数の REF CURSOR を返す複数の出力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="c1a48-147">それぞれの REF Cursor を呼び出すことによってアクセスできる、<xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="c1a48-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c1a48-148">呼び出し<xref:System.Data.OracleClient.OracleCommand.ExecuteReader>を返します、<xref:System.Data.OracleClient.OracleDataReader>最初の REF CURSOR を参照します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="c1a48-149">呼び出して、<xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType>後続の REF Cursor にアクセスするメソッド。</span><span class="sxs-lookup"><span data-stu-id="c1a48-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="c1a48-150">では、パラメーター、<xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>コレクションの一致、REF CURSOR 出力パラメーターを名前で、<xref:System.Data.OracleClient.OracleDataReader>に追加された順番にアクセスして、<xref:System.Data.OracleClient.OracleCommand.Parameters>コレクション。</span><span class="sxs-lookup"><span data-stu-id="c1a48-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="c1a48-151">たとえば、次のような Oracle パッケージとパッケージ本体があるとします。</span><span class="sxs-lookup"><span data-stu-id="c1a48-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="c1a48-152">次のコード作成、<xref:System.Data.OracleClient.OracleCommand>型の 2 つのパラメーターを追加することで、前のバージョンの Oracle パッケージから REF Cursor を返す<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>を<xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>コレクション。</span><span class="sxs-lookup"><span data-stu-id="c1a48-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="c1a48-153">次のコードを使用して前のコマンドの結果を返します、<xref:System.Data.OracleClient.OracleDataReader.Read>と<xref:System.Data.OracleClient.OracleDataReader.NextResult>のメソッド、<xref:System.Data.OracleClient.OracleDataReader>します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="c1a48-154">REF CURSOR パラメーターは順番に返されます。</span><span class="sxs-lookup"><span data-stu-id="c1a48-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="c1a48-155">次の例では、前のコマンドを使用して、事前設定、 <xref:System.Data.DataSet> Oracle パッケージの結果。</span><span class="sxs-lookup"><span data-stu-id="c1a48-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
>  <span data-ttu-id="c1a48-156">回避するために、 **OverflowException**、有効な .NET Framework 型に値を格納する前に、Oracle の NUMBER 型から変換を処理することをお勧め、 <xref:System.Data.DataRow>。</span><span class="sxs-lookup"><span data-stu-id="c1a48-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="c1a48-157">使用することができます、<xref:System.Data.Common.DataAdapter.FillError>イベントかどうかを**OverflowException**が発生しました。</span><span class="sxs-lookup"><span data-stu-id="c1a48-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="c1a48-158">詳細については、<xref:System.Data.Common.DataAdapter.FillError>イベントを参照してください[DataAdapter イベントの処理](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)します。</span><span class="sxs-lookup"><span data-stu-id="c1a48-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a48-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1a48-159">See also</span></span>

- [<span data-ttu-id="c1a48-160">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="c1a48-160">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="c1a48-161">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="c1a48-161">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="c1a48-162">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="c1a48-162">Retrieving Database Schema Information</span></span>](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="c1a48-163">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="c1a48-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
