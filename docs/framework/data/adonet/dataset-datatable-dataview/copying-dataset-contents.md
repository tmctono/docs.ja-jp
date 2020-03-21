---
title: DataSet の内容のコピー
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151365"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="ad7e6-102">DataSet の内容のコピー</span><span class="sxs-lookup"><span data-stu-id="ad7e6-102">Copying DataSet Contents</span></span>
<span data-ttu-id="ad7e6-103">の<xref:System.Data.DataSet>コピーを作成して、元のデータに影響を与えずにデータを操作したり **、DataSet**からデータのサブセットを操作したりできます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="ad7e6-104">データセットをコピーする場合 **、** 次のことができます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="ad7e6-105">スキーマ、データ、行の状態情報、および行のバージョンを含む**DataSet**の正確なコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="ad7e6-106">既存の**DataSet**のスキーマを含む**DataSet**を作成しますが、変更された行のみを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="ad7e6-107">変更されたすべての行を返すか、特定の**DataRowState**を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="ad7e6-108">行の状態の詳細については、「[行の状態」および「行バージョン](row-states-and-row-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="ad7e6-109">行をコピーせずに、**データセット**のスキーマまたはリレーショナル構造のみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="ad7e6-110">行は、<xref:System.Data.DataTable> を使用して、既存の <xref:System.Data.DataTable.ImportRow%2A> にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="ad7e6-111">スキーマとデータの両方を含む**DataSet**の正確なコピーを作成<xref:System.Data.DataSet.Copy%2A>するには、 **DataSet**のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="ad7e6-112">次のコード例は、 **DataSet**の正確なコピーを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="ad7e6-113">スキーマを含む DataSet のコピーを作成し、**追加済み**、**変更済**み、または**削除された**行を表<xref:System.Data.DataSet.GetChanges%2A>すデータのみを含む**DataSet**のコピーを作成するには、 **DataSet**のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="ad7e6-114">また **、GetChanges**を使用して **、GetChanges**を呼び出すときに**DataRowState**値を渡すことで、指定した行の状態の行だけを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="ad7e6-115">次のコード例は **、GetChanges**を呼び出すときに**DataRowState**を渡す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 <span data-ttu-id="ad7e6-116">スキーマのみを含む**DataSet**のコピーを作成するには、 <xref:System.Data.DataSet.Clone%2A> **DataSet**のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="ad7e6-117">DataTable の**ImportRow**メソッドを使用して、複製された**データセット**に既存の**DataTable**行を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="ad7e6-118">**ImportRow は**、指定されたテーブルにデータ、行の状態、および行バージョン情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="ad7e6-119">列名が一致し、データ型が互換性のある型の場合には、列の値だけが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="ad7e6-120">次のコード例では、**データセット**の複製を作成し、元の**データセット**の行を **、"国の地域**" 列の値が "ドイツ" の顧客の**データセット**の複製物の **[得意先**] テーブルに追加します。</span><span class="sxs-lookup"><span data-stu-id="ad7e6-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad7e6-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad7e6-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="ad7e6-122">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="ad7e6-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="ad7e6-123">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ad7e6-123">ADO.NET Overview</span></span>](../ado-net-overview.md)
