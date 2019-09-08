---
title: DataView の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 3e1c31dac458594eee70ddd99469aca7cf63b848
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785478"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="924d9-102">DataView の作成</span><span class="sxs-lookup"><span data-stu-id="924d9-102">Creating a DataView</span></span>
<span data-ttu-id="924d9-103"><xref:System.Data.DataView> は 2 とおりの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="924d9-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="924d9-104">**DataView**コンストラクターを使用することも、 <xref:System.Data.DataTable.DefaultView%2A> <xref:System.Data.DataTable>のプロパティへの参照を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="924d9-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="924d9-105">**DataView**コンストラクターは空にすることも、 **datatable**を単一の引数として使用することも **、datatable を**フィルター条件、並べ替え条件、および行の状態フィルターと共に取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="924d9-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="924d9-106">**DataView**で使用できるその他の引数の詳細については、「[データの並べ替えとフィルター処理](sorting-and-filtering-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="924d9-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="924d9-107">**Dataview の**インデックスは、 **dataview**が作成されたときと、 **Sort**、 **RowFilter**、または**rowstatefilter**の各プロパティが変更されたときに、最適なパフォーマンスを実現するために、最初の**DataView**を作成するときに、コンストラクター引数として並べ替え順序またはフィルター条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="924d9-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="924d9-108">並べ替えまたはフィルター条件を指定せずに**dataview**を作成した後、 **sort**、 **RowFilter**、または**rowstatefilter**の各プロパティを後で設定すると、インデックスが少なくとも2回作成されます。 **dataview**が並べ替えまたはフィルターのプロパティが変更されたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="924d9-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="924d9-109">引数を受け取らないコンストラクターを使用して**dataview**を作成した場合、**テーブル**プロパティを設定するまで**dataview**を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="924d9-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="924d9-110">**Dataview**コンストラクターを使用して**dataview**を作成する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="924d9-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="924d9-111">**DataTable**と共に**RowFilter**、 **Sort**列、および**DataViewRowState**が指定されています。</span><span class="sxs-lookup"><span data-stu-id="924d9-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="924d9-112">次のコード例は、テーブルの**DefaultView**プロパティを使用して、 **DataTable**の既定の**DataView**への参照を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="924d9-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="924d9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="924d9-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="924d9-114">DataViews</span><span class="sxs-lookup"><span data-stu-id="924d9-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="924d9-115">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="924d9-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="924d9-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="924d9-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="924d9-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="924d9-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
