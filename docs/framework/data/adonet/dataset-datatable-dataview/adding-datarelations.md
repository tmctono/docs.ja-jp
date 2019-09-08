---
title: DataRelation の追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 8157d296636d0f8661a35af35de561f5cc49c30b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784811"
---
# <a name="adding-datarelations"></a><span data-ttu-id="23448-102">DataRelation の追加</span><span class="sxs-lookup"><span data-stu-id="23448-102">Adding DataRelations</span></span>
<span data-ttu-id="23448-103">複数の <xref:System.Data.DataSet> オブジェクトを含む <xref:System.Data.DataTable> では、<xref:System.Data.DataRelation> オブジェクトを使用して 1 つのテーブルを別のテーブルに関連付けたり、テーブル間を移動したり、関連付けたテーブルから子または親の行を戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="23448-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="23448-104">**Datarelation**を作成するために必要な引数は、作成する**datarelation**の名前と、リレーションシップの親列および<xref:System.Data.DataColumn>子列として機能する列への1つ以上の参照の配列です。</span><span class="sxs-lookup"><span data-stu-id="23448-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="23448-105">**DataRelation**を作成したら、それを使用してテーブル間を移動したり、値を取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="23448-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="23448-106"><xref:System.Data.UniqueConstraint> <xref:System.Data.ForeignKeyConstraint>に<xref:System.Data.DataSet> **DataRelation**を追加すると、既定では、親テーブルへの、および子テーブルへのが追加されます。</span><span class="sxs-lookup"><span data-stu-id="23448-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="23448-107">これらの既定の制約の詳細については、「 [DataTable の制約](datatable-constraints.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23448-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="23448-108">次のコード例では、 <xref:System.Data.DataSet>で 2 <xref:System.Data.DataTable>つのオブジェクトを使用して**DataRelation**を作成します。</span><span class="sxs-lookup"><span data-stu-id="23448-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="23448-109">各<xref:System.Data.DataTable>には、2つ<xref:System.Data.DataTable>のオブジェクト間のリンクとして機能する CustID という名前の列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="23448-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="23448-110">この例では、 <xref:System.Data.DataSet>の**リレーション**コレクションに単一の**DataRelation**を追加します。</span><span class="sxs-lookup"><span data-stu-id="23448-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="23448-111">この例の最初の引数では、作成する**DataRelation**の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="23448-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="23448-112">2番目の引数は親**datacolumn**を設定し、3番目の引数は子**datacolumn**を設定します。</span><span class="sxs-lookup"><span data-stu-id="23448-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="23448-113">**DataRelation**には、**入れ子になっ**たプロパティもあります。 **true**に設定すると、を使用<xref:System.Data.DataSet.WriteXml%2A>して XML 要素として書き込まれるときに、子テーブルの行が親テーブルの関連付けられた行に入れ子になります。</span><span class="sxs-lookup"><span data-stu-id="23448-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="23448-114">詳しくは、「[DataSet での XML の使用](using-xml-in-a-dataset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23448-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23448-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="23448-115">See also</span></span>

- [<span data-ttu-id="23448-116">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="23448-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="23448-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="23448-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
