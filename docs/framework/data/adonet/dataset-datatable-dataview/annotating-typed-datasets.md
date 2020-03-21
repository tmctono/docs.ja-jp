---
title: 型指定された DataSet の注釈
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151521"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="571b8-102">型指定された DataSet の注釈</span><span class="sxs-lookup"><span data-stu-id="571b8-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="571b8-103">注釈を使用すると、基になるスキーマを変更せずに型指定された <xref:System.Data.DataSet> の要素の名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="571b8-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="571b8-104">基になるスキーマの要素の名前を変更すると、型指定された**DataSet**がデータ ソースに存在しないオブジェクトを参照し、データ ソースに存在するオブジェクトへの参照が失われます。</span><span class="sxs-lookup"><span data-stu-id="571b8-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="571b8-105">注釈を使用すると、より意味のある名前で型指定された**DataSet**内のオブジェクトの名前をカスタマイズできるため、基になるスキーマをそのまま使用しながら、コードを読みやすくし、型指定された**DataSet**をクライアントが使いやすくすることができます。</span><span class="sxs-lookup"><span data-stu-id="571b8-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="571b8-106">たとえば、**ノースウィンド**データベースの**Customers**テーブルに対する次のスキーマ要素は **、DataRow**オブジェクト名として **[得意先] と**[<xref:System.Data.DataRowCollection>**得意先]** という名前になります。</span><span class="sxs-lookup"><span data-stu-id="571b8-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="571b8-107">**顧客**の**データ行の名前**は、クライアント コードで意味がありますが、1 つのオブジェクトであるため **、CustomersRow**の**データ行**名は誤解を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="571b8-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="571b8-108">また、一般的なシナリオでは、オブジェクトは**Row**識別子なしで参照され、代わりに単に**Customer**オブジェクトと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="571b8-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="571b8-109">解決策は、スキーマにア名を付け **、DataRow**オブジェクトと**DataRowCollection**オブジェクトの新しい名前を識別することです。</span><span class="sxs-lookup"><span data-stu-id="571b8-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="571b8-110">上記のスキーマに注釈を付けたスキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="571b8-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="571b8-111">**型指定された名前**の値を**Customer**に指定すると **、DataRow**オブジェクト名が**Customer**になります。</span><span class="sxs-lookup"><span data-stu-id="571b8-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="571b8-112">**型指定された複数の**値を**指定して顧客**の**データRowコレクション**名**を保持します**。</span><span class="sxs-lookup"><span data-stu-id="571b8-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="571b8-113">使用できる注釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="571b8-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="571b8-114">Annotation</span><span class="sxs-lookup"><span data-stu-id="571b8-114">Annotation</span></span>|<span data-ttu-id="571b8-115">説明</span><span class="sxs-lookup"><span data-stu-id="571b8-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="571b8-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="571b8-116">**typedName**</span></span>|<span data-ttu-id="571b8-117">オブジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="571b8-117">Name of the object.</span></span>|  
|<span data-ttu-id="571b8-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="571b8-118">**typedPlural**</span></span>|<span data-ttu-id="571b8-119">オブジェクトのコレクション名。</span><span class="sxs-lookup"><span data-stu-id="571b8-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="571b8-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="571b8-120">**typedParent**</span></span>|<span data-ttu-id="571b8-121">親のリレーションシップで参照される場合のオブジェクト名。</span><span class="sxs-lookup"><span data-stu-id="571b8-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="571b8-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="571b8-122">**typedChildren**</span></span>|<span data-ttu-id="571b8-123">子のリレーションシップからオブジェクトを返すメソッド名。</span><span class="sxs-lookup"><span data-stu-id="571b8-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="571b8-124">**null値**</span><span class="sxs-lookup"><span data-stu-id="571b8-124">**nullValue**</span></span>|<span data-ttu-id="571b8-125">基になる値が**DBNull**の場合の値。</span><span class="sxs-lookup"><span data-stu-id="571b8-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="571b8-126">**null 値**の注釈については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="571b8-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="571b8-127">デフォルトは **_throw**です。</span><span class="sxs-lookup"><span data-stu-id="571b8-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="571b8-128">次の表は **、nullValue**アノテーションに指定できる値を示しています。</span><span class="sxs-lookup"><span data-stu-id="571b8-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="571b8-129">nullValue の値</span><span class="sxs-lookup"><span data-stu-id="571b8-129">nullValue Value</span></span>|<span data-ttu-id="571b8-130">説明</span><span class="sxs-lookup"><span data-stu-id="571b8-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="571b8-131">*置換値*</span><span class="sxs-lookup"><span data-stu-id="571b8-131">*Replacement Value*</span></span>|<span data-ttu-id="571b8-132">返される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="571b8-132">Specify a value to be returned.</span></span> <span data-ttu-id="571b8-133">返された値は要素の型と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="571b8-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="571b8-134">たとえば、整数型フィールドが null の場合に 0 を返すために `nullValue="0"` を使用します。</span><span class="sxs-lookup"><span data-stu-id="571b8-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="571b8-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="571b8-135">**_throw**</span></span>|<span data-ttu-id="571b8-136">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="571b8-136">Throw an exception.</span></span> <span data-ttu-id="571b8-137">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="571b8-137">This is the default.</span></span>|  
|<span data-ttu-id="571b8-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="571b8-138">**_null**</span></span>|<span data-ttu-id="571b8-139">プリミティブ型が見つかった場合は、null 参照を返すか、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="571b8-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="571b8-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="571b8-140">**_empty**</span></span>|<span data-ttu-id="571b8-141">文字列の場合は**String.Empty**を返します。</span><span class="sxs-lookup"><span data-stu-id="571b8-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="571b8-142">プリミティブ型が見つかった場合、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="571b8-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="571b8-143">次の表は、型指定された**DataSet**内のオブジェクトの既定値と使用可能な注釈を示しています。</span><span class="sxs-lookup"><span data-stu-id="571b8-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="571b8-144">オブジェクト/メソッド/イベント</span><span class="sxs-lookup"><span data-stu-id="571b8-144">Object/Method/Event</span></span>|<span data-ttu-id="571b8-145">Default</span><span class="sxs-lookup"><span data-stu-id="571b8-145">Default</span></span>|<span data-ttu-id="571b8-146">Annotation</span><span class="sxs-lookup"><span data-stu-id="571b8-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="571b8-147">**Datatable**</span><span class="sxs-lookup"><span data-stu-id="571b8-147">**DataTable**</span></span>|<span data-ttu-id="571b8-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="571b8-148">TableNameDataTable</span></span>|<span data-ttu-id="571b8-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="571b8-149">typedPlural</span></span>|  
|<span data-ttu-id="571b8-150">**データテーブル**メソッド</span><span class="sxs-lookup"><span data-stu-id="571b8-150">**DataTable** Methods</span></span>|<span data-ttu-id="571b8-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="571b8-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="571b8-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="571b8-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="571b8-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="571b8-153">DeleteTableNameRow</span></span>|<span data-ttu-id="571b8-154">typedName</span><span class="sxs-lookup"><span data-stu-id="571b8-154">typedName</span></span>|  
|<span data-ttu-id="571b8-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="571b8-155">**DataRowCollection**</span></span>|<span data-ttu-id="571b8-156">TableName</span><span class="sxs-lookup"><span data-stu-id="571b8-156">TableName</span></span>|<span data-ttu-id="571b8-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="571b8-157">typedPlural</span></span>|  
|<span data-ttu-id="571b8-158">**Datarow**</span><span class="sxs-lookup"><span data-stu-id="571b8-158">**DataRow**</span></span>|<span data-ttu-id="571b8-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="571b8-159">TableNameRow</span></span>|<span data-ttu-id="571b8-160">typedName</span><span class="sxs-lookup"><span data-stu-id="571b8-160">typedName</span></span>|  
|<span data-ttu-id="571b8-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="571b8-161">**DataColumn**</span></span>|<span data-ttu-id="571b8-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="571b8-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="571b8-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="571b8-163">DataRow.ColumnName</span></span>|<span data-ttu-id="571b8-164">typedName</span><span class="sxs-lookup"><span data-stu-id="571b8-164">typedName</span></span>|  
|<span data-ttu-id="571b8-165">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="571b8-165">**Property**</span></span>|<span data-ttu-id="571b8-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="571b8-166">PropertyName</span></span>|<span data-ttu-id="571b8-167">typedName</span><span class="sxs-lookup"><span data-stu-id="571b8-167">typedName</span></span>|  
|<span data-ttu-id="571b8-168">**子供**アクセサー</span><span class="sxs-lookup"><span data-stu-id="571b8-168">**Child** Accessor</span></span>|<span data-ttu-id="571b8-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="571b8-169">GetChildTableNameRows</span></span>|<span data-ttu-id="571b8-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="571b8-170">typedChildren</span></span>|  
|<span data-ttu-id="571b8-171">**親**アクセサー</span><span class="sxs-lookup"><span data-stu-id="571b8-171">**Parent** Accessor</span></span>|<span data-ttu-id="571b8-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="571b8-172">TableNameRow</span></span>|<span data-ttu-id="571b8-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="571b8-173">typedParent</span></span>|  
|<span data-ttu-id="571b8-174">**データセット**イベント</span><span class="sxs-lookup"><span data-stu-id="571b8-174">**DataSet** Events</span></span>|<span data-ttu-id="571b8-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="571b8-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="571b8-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="571b8-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="571b8-177">typedName</span><span class="sxs-lookup"><span data-stu-id="571b8-177">typedName</span></span>|  
  
 <span data-ttu-id="571b8-178">型指定された**データセット**の注釈を使用するには、XML スキーマ定義言語 (XSD) スキーマに次の**xmlns**参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="571b8-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="571b8-179">データベース テーブルから xsd を作成<xref:System.Data.DataSet.WriteXmlSchema%2A>するには、「 Visual [Studio でデータセットを操作する](/visualstudio/data-tools/dataset-tools-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="571b8-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="571b8-180">次に示す **、"受注"** テーブルに関係のある**Northwind**データベースの**Customers**テーブルを公開する、サンプルのアノーセット スキーマを示します。</span><span class="sxs-lookup"><span data-stu-id="571b8-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""
      xmlns:xs="http://www.w3.org/2001/XMLSchema"
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="571b8-181">サンプル スキーマから作成された厳密に型指定された**データセット**を使用するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="571b8-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="571b8-182">このテーブルでは<xref:System.Data.SqlClient.SqlDataAdapter>、1 つを使用して<xref:System.Data.SqlClient.SqlDataAdapter>**[得意先]** テーブルにデータを入力し、もう 1 つを使用して **[受注]** テーブルにデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="571b8-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="571b8-183">厳密に型指定された**データセットは**、**データリレーションシップ**を定義します。</span><span class="sxs-lookup"><span data-stu-id="571b8-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="571b8-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="571b8-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="571b8-185">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="571b8-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="571b8-186">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="571b8-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="571b8-187">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="571b8-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
