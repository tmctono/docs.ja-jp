---
title: DataSet の内容のコピー
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: f60ef817773b6234b19856bfc0727eedb67e113e
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205178"
---
# <a name="copying-dataset-contents"></a><span data-ttu-id="c45ba-102">DataSet の内容のコピー</span><span class="sxs-lookup"><span data-stu-id="c45ba-102">Copying DataSet Contents</span></span>
<span data-ttu-id="c45ba-103">の<xref:System.Data.DataSet>コピーを作成して、元のデータに影響を与えずにデータを操作したり、データ**セット**のデータのサブセットを操作したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-103">You can create a copy of a <xref:System.Data.DataSet> so that you can work with data without affecting the original data, or work with a subset of the data from a **DataSet**.</span></span> <span data-ttu-id="c45ba-104">**データセット**をコピーするときは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-104">When copying a **DataSet**, you can:</span></span>  
  
- <span data-ttu-id="c45ba-105">スキーマ、データ、行状態情報、および行バージョンを含む、**データセット**の正確なコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c45ba-105">Create an exact copy of the **DataSet**, including the schema, data, row state information, and row versions.</span></span>  
  
- <span data-ttu-id="c45ba-106">既存の**データセット**のスキーマを含み、変更された行のみを含む**データセット**を作成します。</span><span class="sxs-lookup"><span data-stu-id="c45ba-106">Create a **DataSet** that contains the schema of an existing **DataSet**, but only rows that have been modified.</span></span> <span data-ttu-id="c45ba-107">変更されたすべての行を返すことも、特定の**DataRowState**を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-107">You can return all rows that have been modified, or specify a specific **DataRowState**.</span></span> <span data-ttu-id="c45ba-108">行の状態の詳細については、「[行の状態と行のバージョン](row-states-and-row-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c45ba-108">For more information about row states, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
- <span data-ttu-id="c45ba-109">行をコピーせずに、**データセット**のスキーマ (リレーショナル構造) のみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c45ba-109">Copy the schema, or relational structure, of the **DataSet** only, without copying any rows.</span></span> <span data-ttu-id="c45ba-110">行は、<xref:System.Data.DataTable> を使用して、既存の <xref:System.Data.DataTable.ImportRow%2A> にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-110">Rows can be imported into an existing <xref:System.Data.DataTable> using <xref:System.Data.DataTable.ImportRow%2A>.</span></span>  
  
 <span data-ttu-id="c45ba-111">スキーマとデータの両方を含む**データセット**の正確なコピーを作成するに<xref:System.Data.DataSet.Copy%2A>は、**データセット**のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c45ba-111">To create an exact copy of the **DataSet** that includes both schema and data, use the <xref:System.Data.DataSet.Copy%2A> method of the **DataSet**.</span></span> <span data-ttu-id="c45ba-112">次のコード例は、**データセット**の正確なコピーを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c45ba-112">The following code example shows how to create an exact copy of the **DataSet**.</span></span>  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 <span data-ttu-id="c45ba-113">スキーマと、**追加**、**変更**、または**削除**された行を表すデータだけを含むデータ**セット**のコピーを<xref:System.Data.DataSet.GetChanges%2A>作成するには、データ**セット**のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c45ba-113">To create a copy of a **DataSet** that includes schema and only the data representing **Added**, **Modified**, or **Deleted** rows, use the <xref:System.Data.DataSet.GetChanges%2A> method of the **DataSet**.</span></span> <span data-ttu-id="c45ba-114">**GetChanges**を呼び出すときに**DataRowState**値を渡すことで、 **GetChanges**を使用して、指定した行の状態の行のみを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-114">You can also use **GetChanges** to return only rows with a specified row state by passing a **DataRowState** value when calling **GetChanges**.</span></span> <span data-ttu-id="c45ba-115">次のコード例は、 **GetChanges**を呼び出すときに**DataRowState**を渡す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c45ba-115">The following code example shows how to pass a **DataRowState** when calling **GetChanges**.</span></span>  
  
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
  
 <span data-ttu-id="c45ba-116">スキーマのみを含む**データセット**のコピーを作成するには、 <xref:System.Data.DataSet.Clone%2A> **データセット**のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c45ba-116">To create a copy of a **DataSet** that only includes schema, use the <xref:System.Data.DataSet.Clone%2A> method of the **DataSet**.</span></span> <span data-ttu-id="c45ba-117">また、 **DataTable**の**importrow**メソッドを使用して、複製された**データセット**に既存の行を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-117">You can also add existing rows to the cloned **DataSet** using the **ImportRow** method of the **DataTable**.</span></span> <span data-ttu-id="c45ba-118">**Importrow**は、指定されたテーブルにデータ、行の状態、および行のバージョン情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="c45ba-118">**ImportRow** adds data, row state, and row version information to the specified table.</span></span> <span data-ttu-id="c45ba-119">列名が一致し、データ型が互換性のある型の場合には、列の値だけが追加されます。</span><span class="sxs-lookup"><span data-stu-id="c45ba-119">Column values are added only where the column name matches and the data type is compatible.</span></span>  
  
 <span data-ttu-id="c45ba-120">次のコード例では、**データセット**の複製を作成し、元の**データ**セットの行を、**国**の列の値が "ドイツ" になっている顧客の**データセット**の複製の**customers**テーブルに追加します。".</span><span class="sxs-lookup"><span data-stu-id="c45ba-120">The following code example creates a clone of a **DataSet** and then adds the rows from the original **DataSet** to the **Customers** table in the **DataSet** clone for customers where the **CountryRegion** column has the value "Germany".</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c45ba-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="c45ba-121">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="c45ba-122">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="c45ba-122">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c45ba-123">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="c45ba-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
