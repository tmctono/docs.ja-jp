---
title: 主キーの定義
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 84c84cb8fc0ee484b09c69c72571a19c335b58f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607312"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="69302-102">主キーの定義</span><span class="sxs-lookup"><span data-stu-id="69302-102">Defining Primary Keys</span></span>
<span data-ttu-id="69302-103">通常、データベース テーブルには、テーブル内の各行を一意に識別する単一の列または複数の列があります。</span><span class="sxs-lookup"><span data-stu-id="69302-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="69302-104">行を識別するこのような列を、主キーと呼びます。</span><span class="sxs-lookup"><span data-stu-id="69302-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="69302-105">1 つを指定すると<xref:System.Data.DataColumn>として、<xref:System.Data.DataTable.PrimaryKey%2A>の<xref:System.Data.DataTable>、テーブルが自動的に設定、<xref:System.Data.DataColumn.AllowDBNull%2A>プロパティには、列の**false**と<xref:System.Data.DataColumn.Unique%2A>プロパティを**true**します。</span><span class="sxs-lookup"><span data-stu-id="69302-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="69302-106">複数列プライマリ キーの場合のみ、 **AllowDBNull**プロパティが自動的に設定**false**します。</span><span class="sxs-lookup"><span data-stu-id="69302-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="69302-107">**PrimaryKey**のプロパティを<xref:System.Data.DataTable>値として 1 つまたは複数の配列を受け取る**DataColumn**オブジェクトの場合、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="69302-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="69302-108">最初の例は、1 つの列を主キーとして定義しています。</span><span class="sxs-lookup"><span data-stu-id="69302-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="69302-109">2 つの列を主キーとして定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="69302-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="69302-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="69302-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="69302-111">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="69302-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="69302-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="69302-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="69302-113">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="69302-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
