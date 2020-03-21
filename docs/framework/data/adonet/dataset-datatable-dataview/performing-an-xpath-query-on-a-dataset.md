---
title: DataSet に対する XPath クエリの実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 5e9a00ab78a57c3c1686d7c87ed8b45d9b2649af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150832"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="c02fc-102">DataSet に対する XPath クエリの実行</span><span class="sxs-lookup"><span data-stu-id="c02fc-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="c02fc-103">同期された<xref:System.Data.DataSet>XML<xref:System.Xml.XmlDataDocument>との間のリレーションシップを使用すると、XML パス言語 (XPath) クエリなど **、XmlDataDocument**にアクセスし、**データセット**に直接アクセスするよりも便利な特定の機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c02fc-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="c02fc-104">たとえば<xref:System.Data.DataTable>、 の**Select**メソッドを使用して**DataSet**内の他のテーブルとのリレーションシップを移動するのではなく、 **DataSet**と同期された**XmlDataDocument**に対して XPath クエリを実行して、 の形式で<xref:System.Xml.XmlNodeList>XML 要素の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c02fc-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="c02fc-105"><xref:System.Xml.XmlElement>ノードとしてキャストされた**XmlNodeList**のノードは、 **XmlDataDocument**の**GetRowFromElement**メソッドに渡され、同期された<xref:System.Data.DataRow>**データセット**内のテーブルの行への一致する参照を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="c02fc-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="c02fc-106">たとえば、次に示すコード サンプルでは孫 XPath クエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="c02fc-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="c02fc-107">**データセット**には **、"得意先"** テーブル **、"受注"**、および "**受注明細**" という 3 つのテーブルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c02fc-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="c02fc-108">サンプルでは、最初に **[得意先]** テーブルと [**受注]** テーブルの間、および **[受注]** テーブルと [**受注明細**] テーブルの間に親子関係が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c02fc-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="c02fc-109">次に、XPath クエリを実行して、孫**の OrderDetails**ノードに値が 43 の**ProductID**ノードがある**顧客**ノードの**XmlNodeList**を返します。</span><span class="sxs-lookup"><span data-stu-id="c02fc-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="c02fc-110">基本的に、サンプルでは XPath クエリを使用して、**製品 ID**が 43 の製品を注文した顧客を特定しています。</span><span class="sxs-lookup"><span data-stu-id="c02fc-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c02fc-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="c02fc-111">See also</span></span>

- [<span data-ttu-id="c02fc-112">DataSet と XmlDataDocument の同期</span><span class="sxs-lookup"><span data-stu-id="c02fc-112">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)
- [<span data-ttu-id="c02fc-113">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="c02fc-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
