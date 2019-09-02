---
title: DataSet に対する XPath クエリの実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 56d1d11240934036994a14e454cf1a1d8b95226a
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204538"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="e2dbb-102">DataSet に対する XPath クエリの実行</span><span class="sxs-lookup"><span data-stu-id="e2dbb-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="e2dbb-103">同期<xref:System.Data.DataSet>されたと<xref:System.Xml.XmlDataDocument>の間のリレーションシップにより、 **XmlDataDocument**にアクセスする xml パス言語 (XPath) クエリなどの xml サービスを使用できるようになり、特定の機能をより簡単に実行できるようになります。**データセット**への直接アクセス。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="e2dbb-104">たとえば<xref:System.Data.DataTable> 、の**Select**メソッドを使用して**データセット**内の他のテーブルとの間でリレーションシップを移動するのではなく、**データセット**と同期されている**XmlDataDocument**に対して XPath クエリを実行することで、の形式の XML 要素のリスト<xref:System.Xml.XmlNodeList>。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="e2dbb-105">ノードとして <xref:System.Xml.XmlElement>キャストされた xmlnodelist のノードを**XmlDataDocument**の<xref:System.Data.DataRow> **getrowfromelement**メソッドに渡して、同期**された内のテーブルの行に一致する参照を返すことができます。データセット**。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="e2dbb-106">たとえば、次に示すコード サンプルでは孫 XPath クエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="e2dbb-107">**データセット**には、次の3つのテーブルが格納されます。**顧客**、**注文**、および**OrderDetails**。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="e2dbb-108">このサンプルでは、 **Customers**テーブルと**orders**テーブルの間、および**orders**テーブルと**OrderDetails**テーブルの間に親子関係が最初に作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="e2dbb-109">次に、XPath クエリが実行されて、孫**OrderDetails**ノードに43という値の**ProductID**ノードがある**Customers**ノードの**xmlnodelist**が返されます。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="e2dbb-110">基本的に、このサンプルでは、XPath クエリを使用して、 **ProductID**が43の製品を発注した顧客を特定します。</span><span class="sxs-lookup"><span data-stu-id="e2dbb-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2dbb-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="e2dbb-111">See also</span></span>

- [<span data-ttu-id="e2dbb-112">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="e2dbb-112">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="e2dbb-113">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e2dbb-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
