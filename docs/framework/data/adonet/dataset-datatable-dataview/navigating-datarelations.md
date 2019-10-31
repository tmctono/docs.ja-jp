---
title: DataRelation の移動
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 73523297454be37716acedad13498954ef9a89a0
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040344"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="34760-102">DataRelation の移動</span><span class="sxs-lookup"><span data-stu-id="34760-102">Navigating DataRelations</span></span>
<span data-ttu-id="34760-103"><xref:System.Data.DataRelation> の主な機能の 1 つは、<xref:System.Data.DataTable> の 1 つの <xref:System.Data.DataSet> から別の  を移動できることです。</span><span class="sxs-lookup"><span data-stu-id="34760-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="34760-104">これにより、関連する**datatable**から1つの**DataRow**が渡されたときに、1つの**datatable**内の関連するすべての <xref:System.Data.DataRow> オブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="34760-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="34760-105">たとえば、customers テーブルと orders テーブルの間に**DataRelation**を確立した後、 **GetChildRows**を使用して特定の顧客行のすべての注文行を取得できます。</span><span class="sxs-lookup"><span data-stu-id="34760-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="34760-106">次のコード例では、 **Customers**テーブルと**データセット**の**Orders**テーブルの間に**DataRelation**を作成し、各顧客のすべての注文を返します。</span><span class="sxs-lookup"><span data-stu-id="34760-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="34760-107">上記の例に基づいて、4 つのテーブルを相互に関連付け、そのテーブルのリレーションシップ間を移動する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="34760-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="34760-108">前の例と同様に、 **CustomerID**は**Customers**テーブルを**Orders**テーブルに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="34760-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="34760-109">**Customers**テーブルの顧客ごとに、 **orders**テーブル内のすべての子行が決定され、特定の顧客が持つ注文の数とその**OrderID**値が返されます。</span><span class="sxs-lookup"><span data-stu-id="34760-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="34760-110">展開された例では、 **OrderDetails**テーブルと**Products**テーブルからも値が返されます。</span><span class="sxs-lookup"><span data-stu-id="34760-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="34760-111">**Orders**テーブルは、 **OrderID**を使用して**OrderDetails**テーブルに関連付けられており、顧客の注文ごとに、どの製品と数量が注文されたかを判断します。</span><span class="sxs-lookup"><span data-stu-id="34760-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="34760-112">**OrderDetails**テーブルに含まれるのは注文済み製品の**productid**のみであるため、 **OrderDetails**は ProductName**を使用する** **製品**に関連付けられ、 **ProductName**が返されます。</span><span class="sxs-lookup"><span data-stu-id="34760-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="34760-113">このリレーションシップでは、 **Products**テーブルが親であり、 **Order Details**テーブルが子です。</span><span class="sxs-lookup"><span data-stu-id="34760-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="34760-114">その結果、 **OrderDetails**テーブルを反復処理するときに、 **GetParentRow**が呼び出され、関連する**ProductName**の値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="34760-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="34760-115">**Customers**テーブルと**Orders**テーブルに対して**DataRelation**が作成された場合、 **createConstraints**フラグに値が指定されていないことに注意してください (既定値は**true**です)。</span><span class="sxs-lookup"><span data-stu-id="34760-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="34760-116">これは、 **Orders**テーブルのすべての行に、親**Customers**テーブルに存在する**CustomerID**値があることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="34760-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="34760-117">**Customers**テーブルに存在しない**Orders**テーブルに**CustomerID**が存在する場合、<xref:System.Data.ForeignKeyConstraint> によって例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="34760-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="34760-118">子列に親列に含まれていない値が含まれている可能性がある場合は、 **DataRelation**を追加するときに**createConstraints**フラグを**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="34760-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="34760-119">この例では、 **Orders**テーブルと**OrderDetails**テーブルの間の**DataRelation**に対して**createConstraints**フラグが**false**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="34760-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="34760-120">これにより、アプリケーションは**OrderDetails**テーブルからすべてのレコードを返すことができ、実行時の例外を生成することなく**Orders**テーブルのレコードのサブセットのみを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="34760-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="34760-121">展開された例では、次の形式で出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="34760-121">The expanded sample generates output in the following format.</span></span>  
  
```output  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="34760-122">次のコード例は、返される**Orders**テーブル内のレコードのサブセットだけを使用して、 **OrderDetails**テーブルと**Products**テーブルの値が返される、拡張されたサンプルです。</span><span class="sxs-lookup"><span data-stu-id="34760-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="34760-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="34760-123">See also</span></span>

- [<span data-ttu-id="34760-124">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="34760-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="34760-125">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="34760-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
