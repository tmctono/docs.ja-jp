---
title: DataTable へのデータの追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151534"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="815d1-102">DataTable へのデータの追加</span><span class="sxs-lookup"><span data-stu-id="815d1-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="815d1-103"><xref:System.Data.DataTable> を作成し、列と制約を使用してそのテーブルの構造を定義した後で、テーブルに新しいデータ行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="815d1-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="815d1-104">新しい行を追加するには、新しい変数を <xref:System.Data.DataRow> 型として宣言します。</span><span class="sxs-lookup"><span data-stu-id="815d1-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="815d1-105">メソッドを呼び出すと、新しい**DataRow**オブジェクトが<xref:System.Data.DataTable.NewRow%2A>返されます。</span><span class="sxs-lookup"><span data-stu-id="815d1-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="815d1-106">**次に、DataTable**によって定義されたテーブルの構造に基づいて**DataRow**オブジェクトが<xref:System.Data.DataColumnCollection>作成されます。</span><span class="sxs-lookup"><span data-stu-id="815d1-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="815d1-107">NewRow メソッドを呼び出して新しい行を作成**NewRow**する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="815d1-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="815d1-108">その後でインデックスまたは列名を使用して、新しく追加した行を操作する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="815d1-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="815d1-109">新しい行にデータを挿入した後 **、Add**メソッドを使用して、次の<xref:System.Data.DataRowCollection>コードに示す行を に追加します。</span><span class="sxs-lookup"><span data-stu-id="815d1-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="815d1-110">Add**メソッドを**呼び出して、次の例に示すように、値<xref:System.Object>の配列を渡して新しい行を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="815d1-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="815d1-111">**Object**として型指定された値の配列を**Add**メソッドに渡すと、テーブル内に新しい行が作成され、その列値がオブジェクト配列の値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="815d1-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="815d1-112">配列内の値は、テーブル内での列の順序に基づいて、列に順次的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="815d1-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="815d1-113">次の使用例は、新しく作成した **[得意先]** テーブルに 10 行を追加します。</span><span class="sxs-lookup"><span data-stu-id="815d1-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="815d1-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="815d1-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="815d1-115">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="815d1-115">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="815d1-116">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="815d1-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
