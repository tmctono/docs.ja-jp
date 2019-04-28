---
title: DataTable 内のデータの表示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: fa8749550e10256ee0623714cc95e03a838655c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607031"
---
# <a name="viewing-data-in-a-datatable"></a><span data-ttu-id="20482-102">DataTable 内のデータの表示</span><span class="sxs-lookup"><span data-stu-id="20482-102">Viewing Data in a DataTable</span></span>

<span data-ttu-id="20482-103">内容にアクセスすることができます、<xref:System.Data.DataTable>を使用して、**行**と**列**のコレクション、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="20482-103">You can access the contents of a <xref:System.Data.DataTable> by using the **Rows** and **Columns** collections of the **DataTable**.</span></span> <span data-ttu-id="20482-104">使用することも、<xref:System.Data.DataTable.Select%2A>内のデータのサブセットを返すメソッドを**DataTable**検索基準などの基準に従って並べ替え順序、および行の状態。</span><span class="sxs-lookup"><span data-stu-id="20482-104">You can also use the <xref:System.Data.DataTable.Select%2A> method to return subsets of the data in a **DataTable** according to criteria including search criteria, sort order, and row state.</span></span> <span data-ttu-id="20482-105">また、使用することができます、<xref:System.Data.DataRowCollection.Find%2A>のメソッド、 **DataRowCollection**主キーの値を使用して特定の行を検索するとき。</span><span class="sxs-lookup"><span data-stu-id="20482-105">Additionally, you can use the <xref:System.Data.DataRowCollection.Find%2A> method of the **DataRowCollection** when searching for a particular row using a primary key value.</span></span>

<span data-ttu-id="20482-106">**選択**のメソッド、 **DataTable**オブジェクトのセットを返します<xref:System.Data.DataRow>指定した条件に一致するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="20482-106">The **Select** method of the **DataTable** object returns a set of <xref:System.Data.DataRow> objects that match the specified criteria.</span></span> <span data-ttu-id="20482-107">**選択**のフィルター式、並べ替え式では、省略可能な引数を受け取ると**DataViewRowState**します。</span><span class="sxs-lookup"><span data-stu-id="20482-107">**Select** takes optional arguments of a filter expression, sort expression, and **DataViewRowState**.</span></span> <span data-ttu-id="20482-108">フィルター式に基づいて返される行を識別する**DataColumn**などの値`LastName = 'Smith'`します。</span><span class="sxs-lookup"><span data-stu-id="20482-108">The filter expression identifies which rows to return based on **DataColumn** values, such as `LastName = 'Smith'`.</span></span> <span data-ttu-id="20482-109">並べ替え式は、列の並べ替えについての標準 SQL 規則に基づく `LastName ASC, FirstName ASC` などの式です。</span><span class="sxs-lookup"><span data-stu-id="20482-109">The sort expression follows standard SQL conventions for ordering columns, for example `LastName ASC, FirstName ASC`.</span></span> <span data-ttu-id="20482-110">式の作成に関する規則は、次を参照してください。、<xref:System.Data.DataColumn.Expression%2A>のプロパティ、 **DataColumn**クラス。</span><span class="sxs-lookup"><span data-stu-id="20482-110">For rules about writing expressions, see the <xref:System.Data.DataColumn.Expression%2A> property of the **DataColumn** class.</span></span>

> [!TIP]
> <span data-ttu-id="20482-111">に対する呼び出しの数を実行している場合、**選択**のメソッド、 **DataTable**、最初に作成してパフォーマンスを向上させることができます、<xref:System.Data.DataView>の**DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="20482-111">If you are performing a number of calls to the **Select** method of a **DataTable**, you can increase performance by first creating a <xref:System.Data.DataView> for the **DataTable**.</span></span> <span data-ttu-id="20482-112">作成、 **DataView**テーブルの行のインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="20482-112">Creating the **DataView** indexes the rows of the table.</span></span> <span data-ttu-id="20482-113">**選択**メソッドを使用し、そのインデックス、クエリの結果を生成する時間を大幅に削減します。</span><span class="sxs-lookup"><span data-stu-id="20482-113">The **Select** method then uses that index, significantly reducing the time to generate the query result.</span></span> <span data-ttu-id="20482-114">作成する方法については、 **DataView**の**DataTable**を参照してください[Dataview](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)します。</span><span class="sxs-lookup"><span data-stu-id="20482-114">For information about creating a **DataView** for a **DataTable**, see [DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>

<span data-ttu-id="20482-115">**選択**メソッドを表示または操作する行のバージョンに基づいて判断します、<xref:System.Data.DataViewRowState>します。</span><span class="sxs-lookup"><span data-stu-id="20482-115">The **Select** method determines which version of the rows to view or manipulate based on a <xref:System.Data.DataViewRowState>.</span></span> <span data-ttu-id="20482-116">次の表に、考えられる**DataViewRowState**列挙値。</span><span class="sxs-lookup"><span data-stu-id="20482-116">The following table describes the possible **DataViewRowState** enumeration values.</span></span>

|<span data-ttu-id="20482-117">DataViewRowState の値</span><span class="sxs-lookup"><span data-stu-id="20482-117">DataViewRowState value</span></span>|<span data-ttu-id="20482-118">説明</span><span class="sxs-lookup"><span data-stu-id="20482-118">Description</span></span>|
|----------------------------|-----------------|
|<span data-ttu-id="20482-119">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="20482-119">**CurrentRows**</span></span>|<span data-ttu-id="20482-120">変更されていない行、追加された行、および変更された行を含む現在の行。</span><span class="sxs-lookup"><span data-stu-id="20482-120">Current rows including unchanged, added, and modified rows.</span></span>|
|<span data-ttu-id="20482-121">**削除**</span><span class="sxs-lookup"><span data-stu-id="20482-121">**Deleted**</span></span>|<span data-ttu-id="20482-122">削除された行。</span><span class="sxs-lookup"><span data-stu-id="20482-122">A deleted row.</span></span>|
|<span data-ttu-id="20482-123">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="20482-123">**ModifiedCurrent**</span></span>|<span data-ttu-id="20482-124">元のデータを変更した後のバージョンである、現在のバージョン。</span><span class="sxs-lookup"><span data-stu-id="20482-124">A current version, which is a modified version of original data.</span></span> <span data-ttu-id="20482-125">(を参照してください**ModifiedOriginal**)。</span><span class="sxs-lookup"><span data-stu-id="20482-125">(See **ModifiedOriginal**.)</span></span>|
|<span data-ttu-id="20482-126">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="20482-126">**ModifiedOriginal**</span></span>|<span data-ttu-id="20482-127">変更されたすべての行の元のバージョン。</span><span class="sxs-lookup"><span data-stu-id="20482-127">The original version of all modified rows.</span></span> <span data-ttu-id="20482-128">現在のバージョンが利用可能なを使用して**ModifiedCurrent**します。</span><span class="sxs-lookup"><span data-stu-id="20482-128">The current version is available using **ModifiedCurrent**.</span></span>|
|<span data-ttu-id="20482-129">**追加**</span><span class="sxs-lookup"><span data-stu-id="20482-129">**Added**</span></span>|<span data-ttu-id="20482-130">新しい行。</span><span class="sxs-lookup"><span data-stu-id="20482-130">A new row.</span></span>|
|<span data-ttu-id="20482-131">**None**</span><span class="sxs-lookup"><span data-stu-id="20482-131">**None**</span></span>|<span data-ttu-id="20482-132">なし。</span><span class="sxs-lookup"><span data-stu-id="20482-132">None.</span></span>|
|<span data-ttu-id="20482-133">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="20482-133">**OriginalRows**</span></span>|<span data-ttu-id="20482-134">変更されていない行および削除された行を含む元の行。</span><span class="sxs-lookup"><span data-stu-id="20482-134">Original rows, including unchanged and deleted rows.</span></span>|
|<span data-ttu-id="20482-135">**変更なし**</span><span class="sxs-lookup"><span data-stu-id="20482-135">**Unchanged**</span></span>|<span data-ttu-id="20482-136">変更されていない行。</span><span class="sxs-lookup"><span data-stu-id="20482-136">An unchanged row.</span></span>|

<span data-ttu-id="20482-137">次の例では、**データセット**だけを操作できる行を持つようにオブジェクトをフィルター処理**DataViewRowState**に設定されている**CurrentRows**します。</span><span class="sxs-lookup"><span data-stu-id="20482-137">In the following example, the **DataSet** object is filtered so that you are only working with rows whose **DataViewRowState** is set to **CurrentRows**.</span></span>

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

<span data-ttu-id="20482-138">**選択**メソッドを使用して、異なる行を返す**RowState**値またはフィールド値。</span><span class="sxs-lookup"><span data-stu-id="20482-138">The **Select** method can be used to return rows with differing **RowState** values or field values.</span></span> <span data-ttu-id="20482-139">次の例を返します、 **DataRow**が削除されてを返す他のすべての行を参照する配列**DataRow**によって順序付けられた、すべての行を参照する配列**CustLName**、場所、 **CustID**列が 5 より大きい。</span><span class="sxs-lookup"><span data-stu-id="20482-139">The following example returns a **DataRow** array that references all rows that have been deleted, and returns another **DataRow** array that references all rows, ordered by **CustLName**, where the **CustID** column is greater than 5.</span></span> <span data-ttu-id="20482-140">内の情報を表示する方法については、 **Deleted**行を参照してください[行の状態と行バージョン](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)します。</span><span class="sxs-lookup"><span data-stu-id="20482-140">For information about how to view the information in the **Deleted** row, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="20482-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="20482-141">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [<span data-ttu-id="20482-142">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="20482-142">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="20482-143">行の状態とバージョン</span><span class="sxs-lookup"><span data-stu-id="20482-143">Row States and Row Versions</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)
- [<span data-ttu-id="20482-144">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="20482-144">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
