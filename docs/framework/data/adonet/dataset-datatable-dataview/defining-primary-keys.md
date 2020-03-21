---
title: 主キーの定義
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 159b23eb4ef5ca38ebce6e488080d315ec3be081
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151183"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="f387a-102">主キーの定義</span><span class="sxs-lookup"><span data-stu-id="f387a-102">Defining Primary Keys</span></span>
<span data-ttu-id="f387a-103">通常、データベース テーブルには、テーブル内の各行を一意に識別する単一の列または複数の列があります。</span><span class="sxs-lookup"><span data-stu-id="f387a-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="f387a-104">行を識別するこのような列を、主キーと呼びます。</span><span class="sxs-lookup"><span data-stu-id="f387a-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="f387a-105">として単<xref:System.Data.DataColumn>一<xref:System.Data.DataTable.PrimaryKey%2A><xref:System.Data.DataTable>のを指定すると、テーブルは自動的に false<xref:System.Data.DataColumn.AllowDBNull%2A>**に、**<xref:System.Data.DataColumn.Unique%2A>プロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f387a-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="f387a-106">複数列の主キーの場合 **、AllowDBNull**プロパティのみが自動的に**false**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f387a-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="f387a-107">次の例に示すように<xref:System.Data.DataTable>**、PrimaryKey**プロパティは、その値として 1 つ以上の**DataColumn**オブジェクトの配列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f387a-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="f387a-108">最初の例は、1 つの列を主キーとして定義しています。</span><span class="sxs-lookup"><span data-stu-id="f387a-108">The first example defines a single column as the primary key.</span></span>  
  
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
  
 <span data-ttu-id="f387a-109">2 つの列を主キーとして定義する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f387a-109">The following example defines two columns as a primary key.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f387a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="f387a-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="f387a-111">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="f387a-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="f387a-112">DataTables</span><span class="sxs-lookup"><span data-stu-id="f387a-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="f387a-113">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f387a-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
