---
title: データの並べ替えとフィルター処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 8d8bd85f65adfde5f239e1e2dd79d65517b745a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607428"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="4ac14-102">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="4ac14-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="4ac14-103"><xref:System.Data.DataView> には、<xref:System.Data.DataTable> のデータの並べ替えとフィルター処理を行うさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4ac14-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="4ac14-104"><xref:System.Data.DataView.Sort%2A> プロパティを使用すれば、1 列または複数列の並べ替え順序を指定し、ASC (昇順) パラメーターと DESC (降順) パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4ac14-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="4ac14-105"><xref:System.Data.DataView.ApplyDefaultSort%2A> プロパティを使用すると、テーブルの主キー列 (1 列または複数列) に基づいて、昇順の並べ替え順序を自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="4ac14-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="4ac14-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> 場合にのみ適用されます、**並べ替え**プロパティが null 参照または空の文字列と、テーブルが定義されている主キーを持っている場合。</span><span class="sxs-lookup"><span data-stu-id="4ac14-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="4ac14-107"><xref:System.Data.DataView.RowFilter%2A> プロパティを使用すると、列の値に基づいて行のサブセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4ac14-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="4ac14-108">詳細については、有効な式の**RowFilter**プロパティに関するリファレンス情報を参照してください、<xref:System.Data.DataColumn.Expression%2A>のプロパティ、<xref:System.Data.DataColumn>クラス。</span><span class="sxs-lookup"><span data-stu-id="4ac14-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="4ac14-109">取得、データのサブセットの動的なビューを提供することではなく、データの特定のクエリの結果を使用する場合、<xref:System.Data.DataView.Find%2A>または<xref:System.Data.DataView.FindRows%2A>のメソッド、 **DataView**最高のパフォーマンスを実現するためには設定、 **RowFilter**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="4ac14-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="4ac14-110">設定、 **RowFilter**プロパティは、アプリケーションにオーバーヘッドを追加し、パフォーマンスが低下は、データのインデックスを再構築します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="4ac14-111">**RowFilter**プロパティは、最適な使用データ バインド アプリケーションでバインドされたコントロールがフィルター処理された結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ac14-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="4ac14-112">**検索**と**FindRows**メソッドは、再構築するインデックスを必要とせず、現在のインデックスを活用します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="4ac14-113">詳細については、**検索**と**FindRows**メソッドを参照してください[行の検索](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md).</span></span>  
  
- <span data-ttu-id="4ac14-114"><xref:System.Data.DataView.RowStateFilter%2A> プロパティを使用して、表示する行バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4ac14-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="4ac14-115">**DataView**に応じてを公開する行バージョンを暗黙的に管理、 **RowState**の基になる行のできます。</span><span class="sxs-lookup"><span data-stu-id="4ac14-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="4ac14-116">たとえば場合、 **RowStateFilter**に設定されている**DataViewRowState.Deleted**、 **DataView**公開、**元**の行のバージョンすべて**Deleted**行があるためありません**現在**行バージョン。</span><span class="sxs-lookup"><span data-stu-id="4ac14-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="4ac14-117">使用して、公開される行の行バージョンを指定できます、 **RowVersion**のプロパティ、 **DataRowView**します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="4ac14-118">次の表は、オプションの**DataViewRowState**します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="4ac14-119">DataViewRowState のオプション</span><span class="sxs-lookup"><span data-stu-id="4ac14-119">DataViewRowState options</span></span>|<span data-ttu-id="4ac14-120">説明</span><span class="sxs-lookup"><span data-stu-id="4ac14-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="4ac14-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="4ac14-121">**CurrentRows**</span></span>|<span data-ttu-id="4ac14-122">**現在**行バージョンのすべて**Unchanged**、 **Added**、および**Modified**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="4ac14-123">既定値です。</span><span class="sxs-lookup"><span data-stu-id="4ac14-123">This is the default.</span></span>|  
    |<span data-ttu-id="4ac14-124">**追加**</span><span class="sxs-lookup"><span data-stu-id="4ac14-124">**Added**</span></span>|<span data-ttu-id="4ac14-125">**現在**行バージョンのすべて**Added**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="4ac14-126">**削除**</span><span class="sxs-lookup"><span data-stu-id="4ac14-126">**Deleted**</span></span>|<span data-ttu-id="4ac14-127">**元**行バージョンのすべて**Deleted**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="4ac14-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="4ac14-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="4ac14-129">**現在**行バージョンのすべて**Modified**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="4ac14-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="4ac14-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="4ac14-131">**元**行バージョンのすべて**Modified**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="4ac14-132">**None**</span><span class="sxs-lookup"><span data-stu-id="4ac14-132">**None**</span></span>|<span data-ttu-id="4ac14-133">行がありません。</span><span class="sxs-lookup"><span data-stu-id="4ac14-133">No rows.</span></span>|  
    |<span data-ttu-id="4ac14-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="4ac14-134">**OriginalRows**</span></span>|<span data-ttu-id="4ac14-135">**元**行バージョンのすべて**Unchanged**、 **Modified**、および**Deleted**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="4ac14-136">**変更なし**</span><span class="sxs-lookup"><span data-stu-id="4ac14-136">**Unchanged**</span></span>|<span data-ttu-id="4ac14-137">**現在**行バージョンのすべて**Unchanged**行。</span><span class="sxs-lookup"><span data-stu-id="4ac14-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="4ac14-138">行の状態と行のバージョンの詳細については、次を参照してください。[行の状態と行バージョン](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-138">For more information about row states and row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="4ac14-139">在庫数が標準在庫数以下である製品を、仕入先 ID (supplier ID) で並べ替え、さらに製品名 (product name) で並べ替えたビューを作成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4ac14-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ac14-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ac14-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="4ac14-141">DataViews</span><span class="sxs-lookup"><span data-stu-id="4ac14-141">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="4ac14-142">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="4ac14-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
