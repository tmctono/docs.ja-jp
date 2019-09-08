---
title: DataRelation の入れ子化
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 971a1bddc40521dc7381ecb2e39709c0fed282ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785987"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="0a593-102">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="0a593-102">Nesting DataRelations</span></span>
<span data-ttu-id="0a593-103">データのリレーショナル表現では、各テーブルに含まれている行が、列または列セットを使用して相互に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="0a593-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="0a593-104">ADO.NET の <xref:System.Data.DataSet> では、テーブル間のリレーションシップは <xref:System.Data.DataRelation> を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="0a593-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="0a593-105">**DataRelation**を作成する場合、列の親子リレーションシップは、リレーションシップを通じてのみ管理されます。</span><span class="sxs-lookup"><span data-stu-id="0a593-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="0a593-106">テーブルと列はそれぞれ別個のエンティティです。</span><span class="sxs-lookup"><span data-stu-id="0a593-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="0a593-107">XML のデータ階層表現では、子要素が入れ子の状態で含まれている親要素によって親子のリレーションシップが表現されます。</span><span class="sxs-lookup"><span data-stu-id="0a593-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="0a593-108">**データセット**が<xref:System.Xml.XmlDataDocument>と同期されるとき、または**WriteXml**を使用して XML データとして書き込まれるときに、子オブジェクトの入れ子を容易にするために、 **DataRelation**は**入れ子になっ**たプロパティを公開します。</span><span class="sxs-lookup"><span data-stu-id="0a593-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="0a593-109">**DataRelation**の**nested**プロパティを**true**に設定すると、XML データとして書き込まれるとき、または**XmlDataDocument**と同期されるときに、リレーションシップの子行が親列内に入れ子になります。</span><span class="sxs-lookup"><span data-stu-id="0a593-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="0a593-110">既定では、 **DataRelation**の**Nested**プロパティは**false**です。</span><span class="sxs-lookup"><span data-stu-id="0a593-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="0a593-111">たとえば、次の**データセット**について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="0a593-111">For example, consider the following **DataSet**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 <span data-ttu-id="0a593-112">このデータセットでは、 **DataRelation**オブジェクトの**nested**プロパティは**true**に設定されていない**ため、この** **データセット**が XML データとして表される場合、子オブジェクトは親要素内に入れ子にされません。</span><span class="sxs-lookup"><span data-stu-id="0a593-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="0a593-113">入れ子になっていないデータリレーションを含む**データ** **セット**の XML 表現を変換すると、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a593-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="0a593-114">データ リレーションシップは入れ子にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a593-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="0a593-115">これを行うには、 **Nested**プロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0a593-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="0a593-116">次に、トップダウン階層形式の XPath クエリ式を使用してデータを検索、変換するコードを XSLT スタイル シートに記述します。</span><span class="sxs-lookup"><span data-stu-id="0a593-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="0a593-117">次のコード例は、**データセット**で**WriteXml**を呼び出した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="0a593-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 <span data-ttu-id="0a593-118">**Customers**要素と**Orders**要素は兄弟要素として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0a593-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="0a593-119">**Orders**要素をそれぞれの親要素の子として表示する場合は、 **DataRelation**の**Nested**プロパティを**true**に設定し、次の値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a593-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="0a593-120">次のコードは、結果として得られる出力を示しています。 **Orders**要素はそれぞれの親要素の中に入れ子になっています。</span><span class="sxs-lookup"><span data-stu-id="0a593-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a593-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0a593-121">See also</span></span>

- [<span data-ttu-id="0a593-122">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="0a593-122">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="0a593-123">DataRelation の追加</span><span class="sxs-lookup"><span data-stu-id="0a593-123">Adding DataRelations</span></span>](adding-datarelations.md)
- [<span data-ttu-id="0a593-124">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="0a593-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="0a593-125">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="0a593-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
