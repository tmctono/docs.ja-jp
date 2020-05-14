---
title: 型指定された DataSet の注釈
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151521"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="b177d-102">型指定された DataSet の注釈</span><span class="sxs-lookup"><span data-stu-id="b177d-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="b177d-103">注釈を使用すると、基になるスキーマを変更せずに型指定された <xref:System.Data.DataSet> の要素の名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b177d-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="b177d-104">基になるスキーマの要素の名前を変更すると、データ ソースにあるオブジェクトへの参照が失われるだけでなく、型指定された **DataSet** がデータ ソースにないオブジェクトを参照することになります。</span><span class="sxs-lookup"><span data-stu-id="b177d-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="b177d-105">注釈を使用すると、基になるスキーマを変更せずに、型指定された **DataSet** のオブジェクトをわかりやすい名前にカスタマイズできるため、コードが読みやすくなり、型指定された **DataSet** がクライアントで使用しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b177d-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="b177d-106">たとえば、次の **Northwind** データベースの **Customers** テーブルのスキーマ要素は、**CustomersRow** という名前の **DataRow** オブジェクト名および **Customers** という名前の <xref:System.Data.DataRowCollection> となります。</span><span class="sxs-lookup"><span data-stu-id="b177d-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="b177d-107">**Customers** という **DataRowCollection** 名は、クライアント コードでは意味がありますが、**CustomersRow** という **DataRow** 名は単一のオブジェクトであるため、誤解が生じます。</span><span class="sxs-lookup"><span data-stu-id="b177d-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="b177d-108">また、一般的なシナリオでは、オブジェクトは **Row** ID を指定せずに参照されるため、単に **Customer** オブジェクトとして参照されます。</span><span class="sxs-lookup"><span data-stu-id="b177d-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="b177d-109">この問題を解決するには、スキーマに注釈を付け、**DataRow** オブジェクトと **DataRowCollection** オブジェクトに新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b177d-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="b177d-110">上記のスキーマに注釈を付けたスキーマを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b177d-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="b177d-111">**Customer** という **typedName** 値を指定すると、**Customer** という **DataRow** オブジェクト名になります。</span><span class="sxs-lookup"><span data-stu-id="b177d-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="b177d-112">**Customers** という **typedPlural** 値を指定すると、**Customers** という **DataRowCollection** 名が保存されます。</span><span class="sxs-lookup"><span data-stu-id="b177d-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="b177d-113">使用できる注釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="b177d-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="b177d-114">注釈</span><span class="sxs-lookup"><span data-stu-id="b177d-114">Annotation</span></span>|<span data-ttu-id="b177d-115">説明</span><span class="sxs-lookup"><span data-stu-id="b177d-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b177d-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="b177d-116">**typedName**</span></span>|<span data-ttu-id="b177d-117">オブジェクト名。</span><span class="sxs-lookup"><span data-stu-id="b177d-117">Name of the object.</span></span>|  
|<span data-ttu-id="b177d-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="b177d-118">**typedPlural**</span></span>|<span data-ttu-id="b177d-119">オブジェクトのコレクション名。</span><span class="sxs-lookup"><span data-stu-id="b177d-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="b177d-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="b177d-120">**typedParent**</span></span>|<span data-ttu-id="b177d-121">親のリレーションシップで参照される場合のオブジェクト名。</span><span class="sxs-lookup"><span data-stu-id="b177d-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="b177d-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="b177d-122">**typedChildren**</span></span>|<span data-ttu-id="b177d-123">子のリレーションシップからオブジェクトを返すメソッド名。</span><span class="sxs-lookup"><span data-stu-id="b177d-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="b177d-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="b177d-124">**nullValue**</span></span>|<span data-ttu-id="b177d-125">基になる値が **DBNull** の場合の値。</span><span class="sxs-lookup"><span data-stu-id="b177d-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="b177d-126">**nullValue** の注釈については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b177d-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="b177d-127">既定値は **_throw** です。</span><span class="sxs-lookup"><span data-stu-id="b177d-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="b177d-128">**nullValue** 注釈に指定できる値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="b177d-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="b177d-129">nullValue の値</span><span class="sxs-lookup"><span data-stu-id="b177d-129">nullValue Value</span></span>|<span data-ttu-id="b177d-130">説明</span><span class="sxs-lookup"><span data-stu-id="b177d-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="b177d-131">*置換値*</span><span class="sxs-lookup"><span data-stu-id="b177d-131">*Replacement Value*</span></span>|<span data-ttu-id="b177d-132">返される値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b177d-132">Specify a value to be returned.</span></span> <span data-ttu-id="b177d-133">返された値は要素の型と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b177d-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="b177d-134">たとえば、整数型フィールドが null の場合に 0 を返すために `nullValue="0"` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b177d-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="b177d-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="b177d-135">**_throw**</span></span>|<span data-ttu-id="b177d-136">例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b177d-136">Throw an exception.</span></span> <span data-ttu-id="b177d-137">既定値です。</span><span class="sxs-lookup"><span data-stu-id="b177d-137">This is the default.</span></span>|  
|<span data-ttu-id="b177d-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="b177d-138">**_null**</span></span>|<span data-ttu-id="b177d-139">プリミティブ型が見つかった場合は、null 参照を返すか、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b177d-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="b177d-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="b177d-140">**_empty**</span></span>|<span data-ttu-id="b177d-141">文字列の場合は **String.Empty** を、それ以外の場合は空のコンストラクターから作成されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b177d-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="b177d-142">プリミティブ型が見つかった場合、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="b177d-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="b177d-143">型指定された **DataSet** のオブジェクトの既定値と使用できる注釈を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="b177d-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="b177d-144">オブジェクト/メソッド/イベント</span><span class="sxs-lookup"><span data-stu-id="b177d-144">Object/Method/Event</span></span>|<span data-ttu-id="b177d-145">Default</span><span class="sxs-lookup"><span data-stu-id="b177d-145">Default</span></span>|<span data-ttu-id="b177d-146">注釈</span><span class="sxs-lookup"><span data-stu-id="b177d-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="b177d-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="b177d-147">**DataTable**</span></span>|<span data-ttu-id="b177d-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="b177d-148">TableNameDataTable</span></span>|<span data-ttu-id="b177d-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="b177d-149">typedPlural</span></span>|  
|<span data-ttu-id="b177d-150">**DataTable** のメソッド</span><span class="sxs-lookup"><span data-stu-id="b177d-150">**DataTable** Methods</span></span>|<span data-ttu-id="b177d-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="b177d-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="b177d-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="b177d-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="b177d-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="b177d-153">DeleteTableNameRow</span></span>|<span data-ttu-id="b177d-154">typedName</span><span class="sxs-lookup"><span data-stu-id="b177d-154">typedName</span></span>|  
|<span data-ttu-id="b177d-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="b177d-155">**DataRowCollection**</span></span>|<span data-ttu-id="b177d-156">TableName</span><span class="sxs-lookup"><span data-stu-id="b177d-156">TableName</span></span>|<span data-ttu-id="b177d-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="b177d-157">typedPlural</span></span>|  
|<span data-ttu-id="b177d-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="b177d-158">**DataRow**</span></span>|<span data-ttu-id="b177d-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="b177d-159">TableNameRow</span></span>|<span data-ttu-id="b177d-160">typedName</span><span class="sxs-lookup"><span data-stu-id="b177d-160">typedName</span></span>|  
|<span data-ttu-id="b177d-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="b177d-161">**DataColumn**</span></span>|<span data-ttu-id="b177d-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="b177d-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="b177d-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="b177d-163">DataRow.ColumnName</span></span>|<span data-ttu-id="b177d-164">typedName</span><span class="sxs-lookup"><span data-stu-id="b177d-164">typedName</span></span>|  
|<span data-ttu-id="b177d-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="b177d-165">**Property**</span></span>|<span data-ttu-id="b177d-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="b177d-166">PropertyName</span></span>|<span data-ttu-id="b177d-167">typedName</span><span class="sxs-lookup"><span data-stu-id="b177d-167">typedName</span></span>|  
|<span data-ttu-id="b177d-168">**Child** アクセサー</span><span class="sxs-lookup"><span data-stu-id="b177d-168">**Child** Accessor</span></span>|<span data-ttu-id="b177d-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="b177d-169">GetChildTableNameRows</span></span>|<span data-ttu-id="b177d-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="b177d-170">typedChildren</span></span>|  
|<span data-ttu-id="b177d-171">**Parent** アクセサー</span><span class="sxs-lookup"><span data-stu-id="b177d-171">**Parent** Accessor</span></span>|<span data-ttu-id="b177d-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="b177d-172">TableNameRow</span></span>|<span data-ttu-id="b177d-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="b177d-173">typedParent</span></span>|  
|<span data-ttu-id="b177d-174">**DataSet** イベント</span><span class="sxs-lookup"><span data-stu-id="b177d-174">**DataSet** Events</span></span>|<span data-ttu-id="b177d-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="b177d-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="b177d-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="b177d-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="b177d-177">typedName</span><span class="sxs-lookup"><span data-stu-id="b177d-177">typedName</span></span>|  
  
 <span data-ttu-id="b177d-178">型指定された **DataSet** の注釈を使用するには、XML スキーマ定義言語 (XSD) スキーマに次の **xmlns** 参照をインクルードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b177d-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="b177d-179">データベース テーブルから xsd を作成するには、<xref:System.Data.DataSet.WriteXmlSchema%2A> に関するトピック、または「[Visual Studio でのデータセットの操作](/visualstudio/data-tools/dataset-tools-in-visual-studio)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b177d-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="b177d-180">**Orders** テーブルとのリレーションを持つ **Northwind** データベースの **Customers** テーブルを公開する、注釈の付いたスキーマのサンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="b177d-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="b177d-181">サンプル スキーマから作成された厳密に型指定された **DataSet** を次のコード サンプルで使用します。</span><span class="sxs-lookup"><span data-stu-id="b177d-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="b177d-182">また、一方の <xref:System.Data.SqlClient.SqlDataAdapter> を使用して **Customers** テーブルを、他方の <xref:System.Data.SqlClient.SqlDataAdapter> を使用して **Orders** テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="b177d-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="b177d-183">厳密に型指定された **DataSet** により、**DataRelations** が定義されます。</span><span class="sxs-lookup"><span data-stu-id="b177d-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b177d-184">関連項目</span><span class="sxs-lookup"><span data-stu-id="b177d-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="b177d-185">型指定されたデータセット</span><span class="sxs-lookup"><span data-stu-id="b177d-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="b177d-186">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="b177d-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b177d-187">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="b177d-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
