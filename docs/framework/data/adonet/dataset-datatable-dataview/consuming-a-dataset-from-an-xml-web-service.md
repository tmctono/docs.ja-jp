---
title: XML Web サービスからの DataSet の使用
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: 962163b51507647fd975815c214891a6d692e66c
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203952"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="03ba5-102">XML Web サービスからの DataSet の使用</span><span class="sxs-lookup"><span data-stu-id="03ba5-102">Consuming a DataSet from an XML Web Service</span></span>
<span data-ttu-id="03ba5-103"><xref:System.Data.DataSet> は、非接続型デザインで設計されています。インターネットで簡単にデータを転送するのが目的の一部です。</span><span class="sxs-lookup"><span data-stu-id="03ba5-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="03ba5-104">**データセット**は xml web サービスからの入力または出力として指定できることを示す "serializable" です。 xml web サービスからクライアントおよびクライアントに**データセット**の内容をストリームするために必要な追加のコーディングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="03ba5-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="03ba5-105">**データセット**は、DiffGram 形式を使用して xml ストリームに暗黙的に変換され、ネットワーク経由で送信された後、受信側の**データセット**として xml ストリームから再構築されます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="03ba5-106">これにより、XML Web サービスを使用してリレーショナル データを送信および返送する、たいへん簡単で柔軟性のある方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="03ba5-107">DiffGram 形式の詳細については、「diffgram[グラム](diffgrams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03ba5-107">For more information about the DiffGram format, see [DiffGrams](diffgrams.md).</span></span>  
  
 <span data-ttu-id="03ba5-108">次の例では、データ**セット**を使用してリレーショナルデータ (変更されたデータを含む) を転送し、更新内容を元のデータソースに解決する XML Web サービスとクライアントを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03ba5-109">XML Web サービスを作成する場合は、常にセキュリティへの影響を考慮することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="03ba5-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="03ba5-110">XML Web サービスのセキュリティ保護の詳細については、「 [ASP.NET を使用して作成された Xml Web サービスのセキュリティ保護](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03ba5-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a><span data-ttu-id="03ba5-111">DataSet を返し、処理する XML Web サービスを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="03ba5-111">To create an XML Web service that returns and consumes a DataSet</span></span>  
  
1. <span data-ttu-id="03ba5-112">XML Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="03ba5-113">この例では、データを返す XML Web サービスが作成されます。この例では、 **Northwind**データベースから顧客の一覧を取得し、データの更新を含むデータ**セット**を受け取ります。このデータは、xml web サービスによって元のデータソースに解決されます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="03ba5-114">XML Web サービスは、次の2つのメソッドを公開します。データソースへの更新を解決するために、顧客の一覧と**UpdateCustomers**を返す**getcustomers**。</span><span class="sxs-lookup"><span data-stu-id="03ba5-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="03ba5-115">この XML Web サービスは、Web サーバー上の DataSetSample.asmx というファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="03ba5-116">次のコードは、DataSetSample.asmx の内容の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="03ba5-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     <span data-ttu-id="03ba5-117">一般的なシナリオでは、オプティミスティック同時実行制御違反をキャッチするために**UpdateCustomers**メソッドが記述されます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="03ba5-118">説明を簡単にするために、この例では UpdateCustmoers メソッドを省略しています。</span><span class="sxs-lookup"><span data-stu-id="03ba5-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="03ba5-119">オプティミスティック同時実行制御の詳細については、「[オプティミスティック同時実行制御](../optimistic-concurrency.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03ba5-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="03ba5-120">XML Web サービス プロキシを作成します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="03ba5-121">XML Web サービスのクライアントは、公開されたメソッドを使用するために SOAP プロキシを必要とします。</span><span class="sxs-lookup"><span data-stu-id="03ba5-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="03ba5-122">このプロキシは、Visual Studio を使用して生成することができます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="03ba5-123">Visual Studio から既存の Web サービスへの Web 参照を設定することにより、この手順で説明されているすべての動作が自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="03ba5-124">プロキシ クラスを手動で作成する場合は、後述の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03ba5-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="03ba5-125">ほとんどの場合、Visual Studio による、クライアント アプリケーションのプロキシ クラスの作成で十分です。</span><span class="sxs-lookup"><span data-stu-id="03ba5-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="03ba5-126">プロキシは、Web サービス記述言語ツールを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="03ba5-127">たとえば、XML Web サービスが URL `http://myserver/data/DataSetSample.asmx`で公開されている場合は、次のようなコマンドを発行して、 **WebData**の名前空間を持つ Visual Basic .net プロキシを作成し、ファイルサンプルに格納します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-127">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="03ba5-128">ファイル sample.cs に C# プロキシを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="03ba5-129">その後、プロキシをライブラリとしてコンパイルし、XML Web サービスのクライアントにインポートします。</span><span class="sxs-lookup"><span data-stu-id="03ba5-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="03ba5-130">sample.vb に格納されている Visual Basic .NET プロキシ コードを sample.dll としてコンパイルするには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="03ba5-131">sample.cs に格納されている C# プロキシ コードを sample.dll としてコンパイルするには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="03ba5-132">XML Web サービスのクライアントを作成します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="03ba5-133">Visual Studio で Web サービスプロキシクラスを生成する場合は、単にクライアントプロジェクトを作成し、ソリューションエクスプローラー ウィンドウでプロジェクトを右クリックし、 **Web 参照の追加** をクリックして、使用可能な web の一覧から web サービスを選択します。サービス (web サービスが現在のソリューション内または現在のコンピューターで使用できない場合、Web サービスエンドポイントのアドレスの指定が必要になることがあります)。上記の手順に従って、XML Web サービス プロキシを作成した場合は、それをクライアント コードにインポートし、XML Web サービスのメソッドを処理できます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, click **Add Web Reference**, and select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint, if the Web service isn't available within the current solution, or on the current computer.) If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span> <span data-ttu-id="03ba5-134">次のサンプルコードは、プロキシライブラリをインポートし、 **Getcustomers**を呼び出して顧客の一覧を取得し、新しい顧客を追加して、更新された**データセット**を**UpdateCustomers**に返します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-134">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="03ba5-135">この例では、GetChanges によって返される**データセット**を**UpdateCustomers**に渡しています **。** これは、変更された行のみが**UpdateCustomers**に渡される必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="03ba5-135">Notice that the example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="03ba5-136">**UpdateCustomers**は解決された**データセット**を返します。このデータセットを既存の**データセット**に**マージ**して、解決された変更と行のエラー情報を更新に組み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="03ba5-136">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="03ba5-137">次のコードは、Visual Studio を使用して Web 参照を作成し、 **[Web 参照の追加]** ダイアログボックスで dssample への web 参照の名前を変更したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="03ba5-137">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =   
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     <span data-ttu-id="03ba5-138">プロキシ クラスを手動で作成する場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="03ba5-138">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="03ba5-139">このサンプルをコンパイルするには、作成したプロキシ ライブラリ (sample.dll) および関連する .NET ライブラリを指定します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-139">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="03ba5-140">ファイル client.vb に格納されている Visual Basic .NET バージョンのサンプルをコンパイルするには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-140">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="03ba5-141">ファイル client.cs に格納されている C# バージョンのサンプルをコンパイルするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="03ba5-141">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="03ba5-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="03ba5-142">See also</span></span>

- [<span data-ttu-id="03ba5-143">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="03ba5-143">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="03ba5-144">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="03ba5-144">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="03ba5-145">DataTables</span><span class="sxs-lookup"><span data-stu-id="03ba5-145">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="03ba5-146">DataAdapter からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="03ba5-146">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="03ba5-147">DataAdapter によるデータ ソースの更新</span><span class="sxs-lookup"><span data-stu-id="03ba5-147">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="03ba5-148">DataAdapter パラメーター</span><span class="sxs-lookup"><span data-stu-id="03ba5-148">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- <span data-ttu-id="03ba5-149">[Web サービス記述言語ツール (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="03ba5-149">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="03ba5-150">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="03ba5-150">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
