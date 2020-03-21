---
title: DataReader によるデータの取得
ms.date: 10/29/2018
dev_langs:
- csharp
- vb
ms.assetid: 97afc121-fb8b-465b-bab3-6d844420badb
ms.openlocfilehash: 88cd85ce343aaab08b944f81c9659918014da0a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149025"
---
# <a name="retrieve-data-using-a-datareader"></a><span data-ttu-id="f556c-102">データ リーダーを使用してデータを取得する</span><span class="sxs-lookup"><span data-stu-id="f556c-102">Retrieve data using a DataReader</span></span>
<span data-ttu-id="f556c-103">**DataReader**を使用してデータを取得するには、**コマンド**オブジェクトのインスタンスを作成し **、Command.ExecuteReader**を呼び出してデータ ソースから行を取得して**DataReader**を作成します。</span><span class="sxs-lookup"><span data-stu-id="f556c-103">To retrieve data using a **DataReader**, create an instance of the **Command** object, and then create a **DataReader** by calling **Command.ExecuteReader** to retrieve rows from a data source.</span></span> <span data-ttu-id="f556c-104">**DataReader**は、データ ソースからの結果を効率的に処理する手続きロジックを可能にするデータのバッファリングされていないストリームを提供します。</span><span class="sxs-lookup"><span data-stu-id="f556c-104">The **DataReader** provides an unbuffered stream of data that allows procedural logic to efficiently process results from a data source sequentially.</span></span> <span data-ttu-id="f556c-105">**データリーダー**は、大量のデータがメモリにキャッシュされないために、大量のデータを取得する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="f556c-105">The **DataReader** is a good choice when you're retrieving large amounts of data because the data is not cached in memory.</span></span>

<span data-ttu-id="f556c-106">次の例では、有効な**DataReader**`reader`を表し、`command`有効なコマンド オブジェクトを表す DataReader を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f556c-106">The following example illustrates using a **DataReader**, where `reader` represents a valid DataReader and `command` represents a valid Command object.</span></span>  

```csharp
reader = command.ExecuteReader();  
```

```vb
reader = command.ExecuteReader()
```  

<span data-ttu-id="f556c-107">クエリ結果から行を取得するには **、DataReader.Read**メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f556c-107">Use the **DataReader.Read** method to obtain a row from the query results.</span></span> <span data-ttu-id="f556c-108">返された行の各列にアクセスするには、列の名前または序数を**DataReader**に渡します。</span><span class="sxs-lookup"><span data-stu-id="f556c-108">You can access each column of the returned row by passing the name or ordinal number of the column to the **DataReader**.</span></span> <span data-ttu-id="f556c-109">ただし、最高のパフォーマンスを得るために **、DataReader**には、ネイティブ データ型 **(GetDateTime** **、GetDouble、GetGuid** **、GetInt32**など) の列値にアクセスできる一連のメソッドが用意されています。 **GetGuid**</span><span class="sxs-lookup"><span data-stu-id="f556c-109">However, for best performance, the **DataReader** provides a series of methods that allow you to access column values in their native data types (**GetDateTime**, **GetDouble**, **GetGuid**, **GetInt32**, and so on).</span></span> <span data-ttu-id="f556c-110">データ プロバイダ固有の**DataReader**の型指定されたアクセサー<xref:System.Data.OleDb.OleDbDataReader>メソッド<xref:System.Data.SqlClient.SqlDataReader>の一覧については、および を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-110">For a list of typed accessor methods for data provider-specific **DataReaders**, see <xref:System.Data.OleDb.OleDbDataReader> and <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="f556c-111">基になるデータ型がわかっている場合に型指定されたアクセサー メソッドを使用すると、列値を取得するときに必要な型変換の量が減少します。</span><span class="sxs-lookup"><span data-stu-id="f556c-111">Using the typed accessor methods when you know the underlying data type reduces the amount of type conversion required when retrieving the column value.</span></span>  
  
 <span data-ttu-id="f556c-112">次の例では **、DataReader**オブジェクトを反復処理し、各行から 2 つの列を返します。</span><span class="sxs-lookup"><span data-stu-id="f556c-112">The following example iterates through a **DataReader** object and returns two columns from each row.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.HasRows#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.HasRows/VB/source.vb#1)]  
  
## <a name="closing-the-datareader"></a><span data-ttu-id="f556c-113">DataReader の終了</span><span class="sxs-lookup"><span data-stu-id="f556c-113">Closing the DataReader</span></span>  
 <span data-ttu-id="f556c-114">**DataReader**オブジェクトの使用が完了したら、必ず**Close**メソッドを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-114">Always call the **Close** method when you have finished using the **DataReader** object.</span></span>  
  
 <span data-ttu-id="f556c-115">**コマンド**に出力パラメータまたは戻り値が含まれている場合 **、DataReader**を閉じるまでこれらの値は使用できません。</span><span class="sxs-lookup"><span data-stu-id="f556c-115">If your **Command** contains output parameters or return values, those values are not available until the **DataReader** is closed.</span></span>  
  
 <span data-ttu-id="f556c-116">データ**リーダー**が開いている間、**接続**はその**DataReader**によって排他的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-116">While a **DataReader** is open, the **Connection** is in use exclusively by that **DataReader**.</span></span> <span data-ttu-id="f556c-117">元の**DataReader**を閉じるまでは、別の**DataReader**を作成するなど、**接続**に対してコマンドを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="f556c-117">You cannot execute any commands for the **Connection**, including creating another **DataReader**, until the original **DataReader** is closed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f556c-118">クラスの**Finalize**メソッドで、**接続** **、DataReader、** またはその他のマネージ オブジェクトで**Close**または**Dispose**を呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f556c-118">Do not call **Close** or **Dispose** on a **Connection**, a **DataReader**, or any other managed object in the **Finalize** method of your class.</span></span> <span data-ttu-id="f556c-119">終了処理では、クラスに直接所有されているアンマネージ リソースだけを解放してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-119">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="f556c-120">クラスがアンマネージ リソースを所有していない場合は、クラス定義に**Finalize**メソッドを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="f556c-120">If your class does not own any unmanaged resources, do not include a **Finalize** method in your class definition.</span></span> <span data-ttu-id="f556c-121">詳細については、「[ガベージ コレクション](../../../standard/garbage-collection/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-121">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
## <a name="retrieving-multiple-result-sets-using-nextresult"></a><span data-ttu-id="f556c-122">NextResult を使用して複数の結果セットを取得する</span><span class="sxs-lookup"><span data-stu-id="f556c-122">Retrieving multiple result sets using NextResult</span></span>  
 <span data-ttu-id="f556c-123">**DataReader**が複数の結果セットを返す場合は **、NextResult**メソッドを呼び出して結果セットを順番に反復処理します。</span><span class="sxs-lookup"><span data-stu-id="f556c-123">If the **DataReader** returns multiple result sets, call the **NextResult** method to iterate through the result sets sequentially.</span></span> <span data-ttu-id="f556c-124"><xref:System.Data.SqlClient.SqlDataReader> メソッドを使用して、2 つの SELECT ステートメントの結果を処理する <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f556c-124">The following example shows the <xref:System.Data.SqlClient.SqlDataReader> processing the results of two SELECT statements using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.NextResult#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.NextResult/VB/source.vb#1)]  
  
## <a name="getting-schema-information-from-the-datareader"></a><span data-ttu-id="f556c-125">データ リーダーからのスキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="f556c-125">Getting schema information from the DataReader</span></span>  
 <span data-ttu-id="f556c-126">データ**リーダー**が開いている間は **、GetSchemaTable**メソッドを使用して、現在の結果セットに関するスキーマ情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-126">While a **DataReader** is open, you can retrieve schema information about the current result set using the **GetSchemaTable** method.</span></span> <span data-ttu-id="f556c-127">**GetSchemaTable**は<xref:System.Data.DataTable>、現在の結果セットのスキーマ情報を含む行と列が設定されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f556c-127">**GetSchemaTable** returns a <xref:System.Data.DataTable> object populated with rows and columns that contain the schema information for the current result set.</span></span> <span data-ttu-id="f556c-128">**DataTable には**、結果セットの各列に対して 1 行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f556c-128">The **DataTable** contains one row for each column of the result set.</span></span> <span data-ttu-id="f556c-129">スキーマ テーブルの各列は、結果セットの行に返される列のプロパティにマップされます。 **ColumnName**</span><span class="sxs-lookup"><span data-stu-id="f556c-129">Each column of the schema table maps to a property of the columns returned in the rows of the result set, where the **ColumnName** is the name of the property and the value of the column is the value of the property.</span></span> <span data-ttu-id="f556c-130">次の例では **、DataReader**のスキーマ情報を書き出します。</span><span class="sxs-lookup"><span data-stu-id="f556c-130">The following example writes out the schema information for **DataReader**.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetSchemaTable#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetSchemaTable/VB/source.vb#1)]  
  
## <a name="working-with-ole-db-chapters"></a><span data-ttu-id="f556c-131">OLE DB の章の使用</span><span class="sxs-lookup"><span data-stu-id="f556c-131">Working with OLE DB chapters</span></span>  
 <span data-ttu-id="f556c-132">階層行セットまたは章 ( OLE DB の種類**DBTYPE_HCHAPTER**、 ADO の種類<xref:System.Data.OleDb.OleDbDataReader>**adChapter**) は、 を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-132">Hierarchical rowsets, or chapters (OLE DB type **DBTYPE_HCHAPTER**, ADO type **adChapter**), can be retrieved using the <xref:System.Data.OleDb.OleDbDataReader>.</span></span> <span data-ttu-id="f556c-133">章を含むクエリが**DataReader**として返されると、そのチャプターはその**DataReader**の列として返され **、DataReader**オブジェクトとして公開されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-133">When a query that includes a chapter is returned as a **DataReader**, the chapter is returned as a column in that **DataReader** and is exposed as a **DataReader** object.</span></span>  
  
 <span data-ttu-id="f556c-134">ADO.NET **DataSet**は、テーブル間の親子リレーションシップを使用して階層行セットを表すためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-134">The ADO.NET **DataSet** can also be used to represent hierarchical rowsets by using parent-child relationships between tables.</span></span> <span data-ttu-id="f556c-135">詳細については、「[データセット、データ テーブル、およびデータ ビュー](./dataset-datatable-dataview/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-135">For more information, see [DataSets, DataTables, and DataViews](./dataset-datatable-dataview/index.md).</span></span>  
  
 <span data-ttu-id="f556c-136">MSDataShape プロバイダーを使用して、顧客リストの顧客別オーダーのチャプター列を生成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f556c-136">The following code example uses the MSDataShape Provider to generate a chapter column of orders for each customer in a list of customers.</span></span>  
  
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
  
## <a name="returning-results-with-oracle-ref-cursors"></a><span data-ttu-id="f556c-137">オラクル REF の CURSORS で結果を返す</span><span class="sxs-lookup"><span data-stu-id="f556c-137">Returning results with Oracle REF CURSORs</span></span>  
 <span data-ttu-id="f556c-138">.NET Framework Data Provider for Oracle は、クエリ結果を返すために、Oracle REF CURSOR の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f556c-138">The .NET Framework Data Provider for Oracle supports the use of Oracle REF CURSORs to return a query result.</span></span> <span data-ttu-id="f556c-139">Oracle REF CURSOR は <xref:System.Data.OracleClient.OracleDataReader> として返されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-139">An Oracle REF CURSOR is returned as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 <span data-ttu-id="f556c-140">メソッドを使用して<xref:System.Data.OracleClient.OracleDataReader>、Oracle REF CURSOR を表す<xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-140">You can retrieve an <xref:System.Data.OracleClient.OracleDataReader> object that represents an Oracle REF CURSOR by using the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> method.</span></span> <span data-ttu-id="f556c-141">また、 を<xref:System.Data.OracleClient.OracleCommand>埋めるために<xref:System.Data.OracleClient.OracleDataAdapter>使用されるコマンドの**選択コマンド**として 1 つ以上の Oracle REF の<xref:System.Data.DataSet>CUROR を返す を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f556c-141">You can also specify an <xref:System.Data.OracleClient.OracleCommand> that returns one or more Oracle REF CURSORs as the **SelectCommand** for an <xref:System.Data.OracleClient.OracleDataAdapter> used to fill a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="f556c-142">Oracle データ ソースから返された REF CURSOR に<xref:System.Data.OracleClient.OracleCommand>アクセスするには、クエリ用の を作成し、REF CURSOR<xref:System.Data.OracleClient.OracleCommand.Parameters>を参照する<xref:System.Data.OracleClient.OracleCommand>出力パラメータを.</span><span class="sxs-lookup"><span data-stu-id="f556c-142">To access a REF CURSOR returned from an Oracle data source, create an <xref:System.Data.OracleClient.OracleCommand> for your query and add an output parameter that references the REF CURSOR to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection of your <xref:System.Data.OracleClient.OracleCommand>.</span></span> <span data-ttu-id="f556c-143">パラメーターの名前は、クエリの REF CURSOR パラメーターの名前と一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f556c-143">The name of the parameter must match the name of the REF CURSOR parameter in your query.</span></span> <span data-ttu-id="f556c-144">パラメータの型を<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>に設定します。</span><span class="sxs-lookup"><span data-stu-id="f556c-144">Set the type of the parameter to <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f556c-145">REF<xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType><xref:System.Data.OracleClient.OracleCommand>カーソルのメソッドは<xref:System.Data.OracleClient.OracleDataReader>、を返します。</span><span class="sxs-lookup"><span data-stu-id="f556c-145">The <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method of your <xref:System.Data.OracleClient.OracleCommand> returns an <xref:System.Data.OracleClient.OracleDataReader> for the REF CURSOR.</span></span>  
  
 <span data-ttu-id="f556c-146">複数の<xref:System.Data.OracleClient.OracleCommand>REF CURSORS を返す場合は、複数の出力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="f556c-146">If your <xref:System.Data.OracleClient.OracleCommand> returns multiple REF CURSORS, add multiple output parameters.</span></span> <span data-ttu-id="f556c-147">メソッドを呼び出すことによって、異なる REF <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> CURSORs にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f556c-147">You can access the different REF CURSORs by calling the <xref:System.Data.OracleClient.OracleCommand.ExecuteReader?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f556c-148">呼び出<xref:System.Data.OracleClient.OracleCommand.ExecuteReader>しは<xref:System.Data.OracleClient.OracleDataReader>、参照元の最初の REF カーソルを返します。</span><span class="sxs-lookup"><span data-stu-id="f556c-148">The call to <xref:System.Data.OracleClient.OracleCommand.ExecuteReader> returns an <xref:System.Data.OracleClient.OracleDataReader> referencing the first REF CURSOR.</span></span> <span data-ttu-id="f556c-149">その後、このメソッド<xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType>を呼び出して、後続の REF CURSOR にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f556c-149">You can then call the <xref:System.Data.OracleClient.OracleDataReader.NextResult?displayProperty=nameWithType> method to access subsequent REF CURSORs.</span></span> <span data-ttu-id="f556c-150"><xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>コレクション内のパラメーターは REF CURSOR 出力パラメーターを名前で一<xref:System.Data.OracleClient.OracleDataReader>致させますが、パラメーターはコレクションに追加された順序でアクセス<xref:System.Data.OracleClient.OracleCommand.Parameters>します。</span><span class="sxs-lookup"><span data-stu-id="f556c-150">Although the parameters in your <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection match the REF CURSOR output parameters by name, the <xref:System.Data.OracleClient.OracleDataReader> accesses them in the order in which they were added to the <xref:System.Data.OracleClient.OracleCommand.Parameters> collection.</span></span>  
  
 <span data-ttu-id="f556c-151">たとえば、次のような Oracle パッケージとパッケージ本体があるとします。</span><span class="sxs-lookup"><span data-stu-id="f556c-151">For example, consider the following Oracle package and package body.</span></span>  
  
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
  
 <span data-ttu-id="f556c-152">次のコードでは、<xref:System.Data.OracleClient.OracleCommand><xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType>前の Oracle パッケージから REF CURSORs を返すを<xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType>作成します。</span><span class="sxs-lookup"><span data-stu-id="f556c-152">The following code creates an <xref:System.Data.OracleClient.OracleCommand> that returns the REF CURSORs from the previous Oracle package by adding two parameters of type <xref:System.Data.OracleClient.OracleType.Cursor?displayProperty=nameWithType> to the <xref:System.Data.OracleClient.OracleCommand.Parameters?displayProperty=nameWithType> collection.</span></span>  
  
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
  
 <span data-ttu-id="f556c-153">次のコードは、 の<xref:System.Data.OracleClient.OracleDataReader.Read>メソッドと<xref:System.Data.OracleClient.OracleDataReader.NextResult>メソッドを使用して、<xref:System.Data.OracleClient.OracleDataReader>前のコマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f556c-153">The following code returns the results of the previous command using the <xref:System.Data.OracleClient.OracleDataReader.Read> and <xref:System.Data.OracleClient.OracleDataReader.NextResult> methods of the <xref:System.Data.OracleClient.OracleDataReader>.</span></span> <span data-ttu-id="f556c-154">REF CURSOR パラメーターは順番に返されます。</span><span class="sxs-lookup"><span data-stu-id="f556c-154">The REF CURSOR parameters are returned in order.</span></span>  
  
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
  
 <span data-ttu-id="f556c-155">次の例では、前のコマンドを使用<xref:System.Data.DataSet>して、Oracle パッケージの結果を a に入力します。</span><span class="sxs-lookup"><span data-stu-id="f556c-155">The following example uses the previous command to populate a <xref:System.Data.DataSet> with the results of the Oracle package.</span></span>  
  
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
> <span data-ttu-id="f556c-156">**OverflowException**を避けるには、値を に格納する前に、Oracle NUMBER 型から有効な .NET Framework 型<xref:System.Data.DataRow>への変換も処理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f556c-156">To avoid an **OverflowException**, we recommend that you also handle any conversion from the Oracle NUMBER type to a valid .NET Framework type before storing the value in a <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="f556c-157">イベントを<xref:System.Data.Common.DataAdapter.FillError>使用して **、OverflowException**が発生したかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f556c-157">You can use the <xref:System.Data.Common.DataAdapter.FillError> event to determine if an **OverflowException** has occurred.</span></span> <span data-ttu-id="f556c-158">イベントの<xref:System.Data.Common.DataAdapter.FillError>詳細については、「 [DataAdapter イベントの処理](handling-dataadapter-events.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f556c-158">For more information on the <xref:System.Data.Common.DataAdapter.FillError> event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f556c-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="f556c-159">See also</span></span>

- [<span data-ttu-id="f556c-160">DataAdapter と DataReader</span><span class="sxs-lookup"><span data-stu-id="f556c-160">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="f556c-161">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="f556c-161">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="f556c-162">データベース スキーマ情報の取得</span><span class="sxs-lookup"><span data-stu-id="f556c-162">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="f556c-163">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f556c-163">ADO.NET Overview</span></span>](ado-net-overview.md)
