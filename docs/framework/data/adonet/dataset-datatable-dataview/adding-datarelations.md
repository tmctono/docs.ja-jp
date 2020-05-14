---
title: DataRelation の追加
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 8157d296636d0f8661a35af35de561f5cc49c30b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784811"
---
# <a name="adding-datarelations"></a><span data-ttu-id="bd283-102">DataRelation の追加</span><span class="sxs-lookup"><span data-stu-id="bd283-102">Adding DataRelations</span></span>
<span data-ttu-id="bd283-103">複数の <xref:System.Data.DataSet> オブジェクトを含む <xref:System.Data.DataTable> では、<xref:System.Data.DataRelation> オブジェクトを使用して 1 つのテーブルを別のテーブルに関連付けたり、テーブル間を移動したり、関連付けたテーブルから子または親の行を戻したりできます。</span><span class="sxs-lookup"><span data-stu-id="bd283-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="bd283-104">**DataRelation** の作成に必要な引数は、作成する **DataRelation** の名前、およびそのリレーションシップで親子の列となる列への 1 つ以上の <xref:System.Data.DataColumn> 参照の配列です。</span><span class="sxs-lookup"><span data-stu-id="bd283-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="bd283-105">**DataRelation** を作成した後は、それを使用して、テーブル間の移動や値の取得を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd283-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="bd283-106"><xref:System.Data.DataSet> に **DataRelation** を追加すると、既定では、<xref:System.Data.UniqueConstraint> が親テーブルに、<xref:System.Data.ForeignKeyConstraint> が子テーブルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bd283-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="bd283-107">これらの既定の制約について詳しくは、「[DataTable の制約](datatable-constraints.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd283-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="bd283-108">次のコード例では、<xref:System.Data.DataSet> の 2 つの <xref:System.Data.DataTable> オブジェクトを使用して、**DataRelation** を作成します。</span><span class="sxs-lookup"><span data-stu-id="bd283-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bd283-109">各 <xref:System.Data.DataTable> にある **CustID** という名前の列は、2 つの <xref:System.Data.DataTable> オブジェクト間のリンクとして機能します。</span><span class="sxs-lookup"><span data-stu-id="bd283-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="bd283-110">例では、単一の **DataRelation** が <xref:System.Data.DataSet> の **Relations** コレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="bd283-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="bd283-111">例の最初の引数では、作成する **DataRelation** の名前が指定されています。</span><span class="sxs-lookup"><span data-stu-id="bd283-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="bd283-112">2 番目の引数では親の **DataColumn** が設定され、3 番目の引数では子の **DataColumn** が設定されます。</span><span class="sxs-lookup"><span data-stu-id="bd283-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="bd283-113">**DataRelation** には、**Nested** プロパティもあります。それを **true** に設定すると、<xref:System.Data.DataSet.WriteXml%2A> を使用して XML 要素として書き込んだときに、子テーブルの行が、親テーブルの関連付けられた行の中に入れ子になります。</span><span class="sxs-lookup"><span data-stu-id="bd283-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="bd283-114">詳しくは、「[DataSet での XML の使用](using-xml-in-a-dataset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd283-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd283-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd283-115">See also</span></span>

- [<span data-ttu-id="bd283-116">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="bd283-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bd283-117">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="bd283-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
