---
title: DataView の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 539e9763c8aa4affdb6f3bd219a99dbca50cee01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202344"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="d692c-102">DataView の作成</span><span class="sxs-lookup"><span data-stu-id="d692c-102">Creating a DataView</span></span>

<span data-ttu-id="d692c-103"><xref:System.Data.DataView> は 2 とおりの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="d692c-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="d692c-104">**DataView** コンストラクターを使用するか、または <xref:System.Data.DataTable> の <xref:System.Data.DataTable.DefaultView%2A> プロパティへの参照を作成します。</span><span class="sxs-lookup"><span data-stu-id="d692c-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="d692c-105">空の **DataView** コンストラクターを使用できます。また、DataView コンストラクターでは、**DataTable** を 1 つの引数としてとるか、またはフィルター条件、並べ替え条件、および行状態フィルターと共に **DataTable** を使用します。</span><span class="sxs-lookup"><span data-stu-id="d692c-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="d692c-106">**DataView** で使用できるその他の引数については、「[データの並べ替えとフィルター処理](sorting-and-filtering-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d692c-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="d692c-107">**DataView** のインデックスが作成されるのは、**DataView** が作成される時点と、**Sort**、**RowFilter**、または **RowStateFilter** の各プロパティが変更される時点であるため、**DataView** の作成時に初期の並べ替え順序または初期フィルター条件をコンストラクター引数として指定すると、パフォーマンスを最大限に引き出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d692c-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="d692c-108">並べ替え条件やフィルター条件を指定せずに **DataView** を作成してから、**Sort**、**RowFilter**、または **RowStateFilter** の各プロパティを設定すると、インデックスが少なくとも 2 回作成されます。これは、**DataView** の作成時点と、並べ替えプロパティまたはフィルター プロパティの変更時です。</span><span class="sxs-lookup"><span data-stu-id="d692c-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="d692c-109">引数のないコンストラクターを使用して **DataView** を作成すると、**Table** プロパティを設定するまで、**DataView** を使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d692c-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="d692c-110">次のコード例では、**DataView** コンストラクターを使用して **DataView** を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d692c-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="d692c-111">**DataTable** と共に **RowFilter**、**Sort** 列、および **DataViewRowState** が指定されています。</span><span class="sxs-lookup"><span data-stu-id="d692c-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="d692c-112">テーブルの **DefaultView** プロパティを使用して **DataTable** の既定の **DataView** への参照を取得するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d692c-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d692c-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d692c-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="d692c-114">DataViews</span><span class="sxs-lookup"><span data-stu-id="d692c-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="d692c-115">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="d692c-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="d692c-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="d692c-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="d692c-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="d692c-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
