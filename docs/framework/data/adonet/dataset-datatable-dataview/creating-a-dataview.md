---
title: DataView の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151339"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="54c83-102">DataView の作成</span><span class="sxs-lookup"><span data-stu-id="54c83-102">Creating a DataView</span></span>
<span data-ttu-id="54c83-103"><xref:System.Data.DataView> は 2 とおりの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="54c83-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="54c83-104">**DataView**コンストラクタを使用するか、プロパティへの参照を<xref:System.Data.DataTable.DefaultView%2A>作成することができます。 <xref:System.Data.DataTable></span><span class="sxs-lookup"><span data-stu-id="54c83-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="54c83-105">**DataView**コンストラクターは空にすることも **、DataTable**を単一の引数として使用することも、フィルター条件、並べ替え条件、および行状態フィルターとともに**DataTable**を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="54c83-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="54c83-106">**DataView**で使用できる追加の引数の詳細については、「[データの並べ替えとフィルター](sorting-and-filtering-data.md)処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54c83-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="54c83-107">**DataView**のインデックスは **、DataView**が作成されるときに、並**べ替え\*\*\*\*、RowFilter**、または**RowStateFilter**のいずれかのプロパティが変更されたときに、最もパフォーマンスが高いため **、DataView**を作成するときに、最初の並べ替え順序またはフィルタ条件をコンストラクターの引数として指定することで、最適なパフォーマンスを実現します。</span><span class="sxs-lookup"><span data-stu-id="54c83-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="54c83-108">並べ替え条件またはフィルター条件を指定せずに**DataView**を作成し、後で**並べ替え\*\*\*\*、RowFilter**、または**RowStateFilter**プロパティを設定すると **、DataView**が作成されたときと、並べ替えまたはフィルターのプロパティのいずれかが変更されたときに、少なくとも 2 回インデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="54c83-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="54c83-109">引数を取らないコンストラクタを使用して**DataView**を作成する場合 **、Table**プロパティを設定するまで**DataView**を使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54c83-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="54c83-110">次のコード例は **、DataView**コンストラクターを使用して**DataView**を作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54c83-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="54c83-111">**行フィルター**、**並べ替え**列、および**データビュー行状態**は、**データ テーブル**と共に提供されます。</span><span class="sxs-lookup"><span data-stu-id="54c83-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],
    "Country = 'USA'",
    "ContactName",
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="54c83-112">次のコード例は、テーブルの**DefaultView**プロパティを使用して **、データ テーブル**の既定の**データ ビュー**への参照を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="54c83-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="54c83-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="54c83-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="54c83-114">DataViews</span><span class="sxs-lookup"><span data-stu-id="54c83-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="54c83-115">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="54c83-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="54c83-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="54c83-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="54c83-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="54c83-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
