---
title: DataView の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 05122f7c980c4b7dfdb27eec73464a4f0556ba99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034386"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="296d7-102">DataView の作成</span><span class="sxs-lookup"><span data-stu-id="296d7-102">Creating a DataView</span></span>
<span data-ttu-id="296d7-103"><xref:System.Data.DataView> は 2 とおりの方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="296d7-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="296d7-104">使用することができます、 **DataView**への参照を作成できますコンス トラクター、または、<xref:System.Data.DataTable.DefaultView%2A>のプロパティ、<xref:System.Data.DataTable>します。</span><span class="sxs-lookup"><span data-stu-id="296d7-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="296d7-105">**DataView**コンス トラクターは空、またはいずれかがかかることができます、 **DataTable**引数を 1 つとして、または**DataTable**フィルター条件、並べ替え条件、および行と共に状態フィルター。</span><span class="sxs-lookup"><span data-stu-id="296d7-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="296d7-106">使用する追加の引数の詳細については、 **DataView**を参照してください[並べ替えとフィルター データ](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="296d7-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="296d7-107">のインデックス、 **DataView**ときにも、構築、 **DataView**が作成されるときのいずれかと、**並べ替え**、 **RowFilter**、または**RowStateFilter**プロパティが変更されると、任意の最初の並べ替え順序を指定するか、作成するときに、コンス トラクター引数としてフィルタ リング条件によって最適なパフォーマンスを実現し、 **DataView**します。</span><span class="sxs-lookup"><span data-stu-id="296d7-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="296d7-108">作成、 **DataView**並べ替えまたはフィルター条件を指定しを設定せず、**並べ替え**、 **RowFilter**、または**RowStateFilter**プロパティが、その後、インデックスの構築には少なくとも 2 回: したらときに、 **DataView**が作成し、もう一度、並べ替えまたはフィルターのプロパティのいずれかが変更された日時。</span><span class="sxs-lookup"><span data-stu-id="296d7-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="296d7-109">作成する場合、 **DataView**を任意の引数を受け取らないコンス トラクターを使用することができなくを使用する、 **DataView**を設定するまで、**テーブル**プロパティ.</span><span class="sxs-lookup"><span data-stu-id="296d7-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="296d7-110">次のコード例は、作成する方法を示します、 **DataView**を使用して、 **DataView**コンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="296d7-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="296d7-111">A **RowFilter**、**並べ替え**列、および**DataViewRowState**に沿ってで提供されている、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="296d7-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="296d7-112">次のコード例は、既定値への参照を取得する方法を示します**DataView**の**DataTable**を使用して、 **DefaultView**テーブルのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="296d7-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="296d7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="296d7-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="296d7-114">DataViews</span><span class="sxs-lookup"><span data-stu-id="296d7-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="296d7-115">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="296d7-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [<span data-ttu-id="296d7-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="296d7-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="296d7-117">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="296d7-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
