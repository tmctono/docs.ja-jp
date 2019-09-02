---
title: データの並べ替えとフィルター処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 0907aa2a66e1bf51fefc7bed8ea2612cc0c830fa
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203219"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="6ca6d-102">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="6ca6d-102">Sorting and Filtering Data</span></span>
<span data-ttu-id="6ca6d-103"><xref:System.Data.DataView> には、<xref:System.Data.DataTable> のデータの並べ替えとフィルター処理を行うさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="6ca6d-104"><xref:System.Data.DataView.Sort%2A> プロパティを使用すれば、1 列または複数列の並べ替え順序を指定し、ASC (昇順) パラメーターと DESC (降順) パラメーターを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="6ca6d-105"><xref:System.Data.DataView.ApplyDefaultSort%2A> プロパティを使用すると、テーブルの主キー列 (1 列または複数列) に基づいて、昇順の並べ替え順序を自動的に作成できます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="6ca6d-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>**Sort**プロパティが null 参照または空の文字列の場合、およびテーブルに主キーが定義されている場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="6ca6d-107"><xref:System.Data.DataView.RowFilter%2A> プロパティを使用すると、列の値に基づいて行のサブセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="6ca6d-108">**RowFilter**プロパティの有効な式の詳細については、 <xref:System.Data.DataColumn.Expression%2A> <xref:System.Data.DataColumn>クラスのプロパティの参照情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="6ca6d-109">データのサブセットの動的ビューを提供するのではなく、データに対する特定のクエリの結果を返す場合は、 **DataView**のメソッド<xref:System.Data.DataView.Find%2A>また<xref:System.Data.DataView.FindRows%2A>はメソッドを使用して、 **RowFilter**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="6ca6d-110">**RowFilter**プロパティを設定すると、データのインデックスが再構築され、アプリケーションにオーバーヘッドが追加され、パフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="6ca6d-111">**RowFilter**プロパティは、バインドされたコントロールがフィルター処理された結果を表示するデータバインドアプリケーションで最適に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="6ca6d-112">**Find**メソッドと**FindRows**メソッドは、インデックスの再構築を必要とせずに、現在のインデックスを利用します。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="6ca6d-113">**Find**メソッドと**FindRows**メソッドの詳細については、「[行の検索](finding-rows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="6ca6d-114"><xref:System.Data.DataView.RowStateFilter%2A> プロパティを使用して、表示する行バージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="6ca6d-115">**DataView**は、基になる行の**RowState**に応じて、公開する行バージョンを暗黙的に管理します。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="6ca6d-116">たとえば、 **Rowstatefilter**が DataViewRowState に設定されている場合、 **DataView**は、**現在**の行バージョンがないため、**削除さ**れたすべての行の**元**の行バージョンを公開し**ます**。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="6ca6d-117">**DataRowView**の**RowVersion**プロパティを使用して、公開されている行バージョンを特定できます。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="6ca6d-118">次の表は、 **DataViewRowState**のオプションを示しています。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="6ca6d-119">DataViewRowState のオプション</span><span class="sxs-lookup"><span data-stu-id="6ca6d-119">DataViewRowState options</span></span>|<span data-ttu-id="6ca6d-120">説明</span><span class="sxs-lookup"><span data-stu-id="6ca6d-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="6ca6d-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-121">**CurrentRows**</span></span>|<span data-ttu-id="6ca6d-122">**変更** **され**ていない、追加、および**変更**されたすべての行の**現在**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="6ca6d-123">既定値です。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-123">This is the default.</span></span>|  
    |<span data-ttu-id="6ca6d-124">**れ**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-124">**Added**</span></span>|<span data-ttu-id="6ca6d-125">**追加された**すべての行の**現在**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="6ca6d-126">**削除**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-126">**Deleted**</span></span>|<span data-ttu-id="6ca6d-127">**削除された**すべての行の**元**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="6ca6d-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="6ca6d-129">すべての**変更**された行の**現在**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="6ca6d-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="6ca6d-131">**変更**されたすべての行の**元**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="6ca6d-132">**None**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-132">**None**</span></span>|<span data-ttu-id="6ca6d-133">行がありません。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-133">No rows.</span></span>|  
    |<span data-ttu-id="6ca6d-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-134">**OriginalRows**</span></span>|<span data-ttu-id="6ca6d-135">**変更**されていない、**変更** **された、および削除された**すべての行の**元**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="6ca6d-136">**Unchanged**</span><span class="sxs-lookup"><span data-stu-id="6ca6d-136">**Unchanged**</span></span>|<span data-ttu-id="6ca6d-137">**変更**されていないすべての行の**現在**の行バージョン。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="6ca6d-138">行の状態と行のバージョンの詳細については、「[行の状態と](row-states-and-row-versions.md)行のバージョン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="6ca6d-139">在庫数が標準在庫数以下である製品を、仕入先 ID (supplier ID) で並べ替え、さらに製品名 (product name) で並べ替えたビューを作成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6ca6d-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ca6d-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ca6d-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="6ca6d-141">DataViews</span><span class="sxs-lookup"><span data-stu-id="6ca6d-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="6ca6d-142">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="6ca6d-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
