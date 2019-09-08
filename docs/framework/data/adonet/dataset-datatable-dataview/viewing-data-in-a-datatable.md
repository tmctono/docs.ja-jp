---
title: DataTable 内のデータの表示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: c13f0b802b2714a17ea4014625a65ebd1b0011f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785852"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="71cf0-102">DataTable 内のデータの表示</span><span class="sxs-lookup"><span data-stu-id="71cf0-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="71cf0-103">の<xref:System.Data.DataTable>内容にアクセスするには、 **DataTable**の**Rows**コレクションと**Columns**コレクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="71cf0-104">また、 <xref:System.Data.DataTable.Select%2A>メソッドを使用して、検索条件、並べ替え順序、および行の状態などの条件に基づいて、 **DataTable**内のデータのサブセットを返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="71cf0-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="71cf0-105">また、主キーの値<xref:System.Data.DataRowCollection.Find%2A>を使用して特定の行を検索するときに、 **DataRowCollection**のメソッドを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="71cf0-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="71cf0-106">**DataTable**オブジェクトの**Select**メソッドは、指定された<xref:System.Data.DataRow>条件に一致するオブジェクトのセットを返します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="71cf0-107">**Select**は、フィルター式、並べ替え式、および**DataViewRowState**の省略可能な引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="71cf0-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="71cf0-108">フィルター式は、 **DataColumn**値 (など) に基づいて`LastName = 'Smith'`返される行を識別します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="71cf0-109">並べ替え式は、列の並べ替えについての標準 SQL 規則に基づく `LastName ASC, FirstName ASC` などの式です。</span><span class="sxs-lookup"><span data-stu-id="71cf0-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="71cf0-110">式の記述に関する規則につい<xref:System.Data.DataColumn.Expression%2A>ては、 **DataColumn**クラスのプロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71cf0-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="71cf0-111">Datatable の**Select**メソッドに対して多数の呼び出しを実行している場合は、最初に<xref:System.Data.DataView> **datatable**のを作成することによってパフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="71cf0-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="71cf0-112">**DataView**を作成すると、テーブルの行にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="71cf0-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="71cf0-113">次に、 **Select**メソッドはそのインデックスを使用して、クエリ結果の生成にかかる時間を大幅に短縮します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="71cf0-114">**DataTable**の**DataView**の作成の詳細については、「 [dataviews](dataviews.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71cf0-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](dataviews.md).</span></span>

<span data-ttu-id="71cf0-115">**Select**メソッドは、 <xref:System.Data.DataViewRowState>に基づいて表示または操作する行のバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="71cf0-116">次の表では、使用可能な**DataViewRowState**列挙値について説明します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="71cf0-117">DataViewRowState の値</span><span class="sxs-lookup"><span data-stu-id="71cf0-117">DataViewRowState value</span></span>|<span data-ttu-id="71cf0-118">説明</span><span class="sxs-lookup"><span data-stu-id="71cf0-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="71cf0-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="71cf0-119">**CurrentRows**</span></span>|<span data-ttu-id="71cf0-120">変更されていない行、追加された行、および変更された行を含む現在の行。</span><span class="sxs-lookup"><span data-stu-id="71cf0-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="71cf0-121">**削除**</span><span class="sxs-lookup"><span data-stu-id="71cf0-121">**Deleted**</span></span>|<span data-ttu-id="71cf0-122">削除された行。</span><span class="sxs-lookup"><span data-stu-id="71cf0-122">A deleted row.</span></span>|
|<span data-ttu-id="71cf0-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="71cf0-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="71cf0-124">元のデータを変更した後のバージョンである、現在のバージョン。</span><span class="sxs-lookup"><span data-stu-id="71cf0-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="71cf0-125">(「 **ModifiedOriginal**」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="71cf0-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="71cf0-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="71cf0-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="71cf0-127">変更されたすべての行の元のバージョン。</span><span class="sxs-lookup"><span data-stu-id="71cf0-127">The original version of all modified rows.</span></span> <span data-ttu-id="71cf0-128">現在のバージョンは、 **ModifiedCurrent**を使用して入手できます。</span><span class="sxs-lookup"><span data-stu-id="71cf0-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="71cf0-129">**れ**</span><span class="sxs-lookup"><span data-stu-id="71cf0-129">**Added**</span></span>|<span data-ttu-id="71cf0-130">新しい行。</span><span class="sxs-lookup"><span data-stu-id="71cf0-130">A new row.</span></span>|
|<span data-ttu-id="71cf0-131">**None**</span><span class="sxs-lookup"><span data-stu-id="71cf0-131">**None**</span></span>|<span data-ttu-id="71cf0-132">なし。</span><span class="sxs-lookup"><span data-stu-id="71cf0-132">None.</span></span>|
|<span data-ttu-id="71cf0-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="71cf0-133">**OriginalRows**</span></span>|<span data-ttu-id="71cf0-134">変更されていない行および削除された行を含む元の行。</span><span class="sxs-lookup"><span data-stu-id="71cf0-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="71cf0-135">**Unchanged**</span><span class="sxs-lookup"><span data-stu-id="71cf0-135">**Unchanged**</span></span>|<span data-ttu-id="71cf0-136">変更されていない行。</span><span class="sxs-lookup"><span data-stu-id="71cf0-136">An unchanged row.</span></span>|

<span data-ttu-id="71cf0-137">次の例では、**データセット**オブジェクトをフィルター処理して、 **DataViewRowState**が**currentrows**に設定されている行のみを処理するようにしています。</span><span class="sxs-lookup"><span data-stu-id="71cf0-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

<span data-ttu-id="71cf0-138">**Select**メソッドを使用して、異なる**RowState**値またはフィールド値を持つ行を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="71cf0-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="71cf0-139">次の例では、削除されたすべての行を参照する**datarow**配列を返し、 **custlname**によって並べ替えられた、 **CustID**列が5より大きいすべての行を参照する別の**datarow**配列を返します。</span><span class="sxs-lookup"><span data-stu-id="71cf0-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="71cf0-140">**削除さ**れた行の情報を表示する方法の詳細については、「[行の状態と行のバージョン](row-states-and-row-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71cf0-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a><span data-ttu-id="71cf0-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="71cf0-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="71cf0-142">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="71cf0-142">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="71cf0-143">行の状態とバージョン</span><span class="sxs-lookup"><span data-stu-id="71cf0-143">Row States and Row Versions</span></span>](row-states-and-row-versions.md)
- [<span data-ttu-id="71cf0-144">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="71cf0-144">ADO.NET Overview</span></span>](../ado-net-overview.md)
