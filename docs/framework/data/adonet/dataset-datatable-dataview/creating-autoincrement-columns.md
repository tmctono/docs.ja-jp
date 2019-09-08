---
title: AutoIncrement 列の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786453"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="04c4d-102">AutoIncrement 列の作成</span><span class="sxs-lookup"><span data-stu-id="04c4d-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="04c4d-103">列値を一意にするために、新しい行がテーブルに追加されたときに列値が自動的にインクリメントされるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="04c4d-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="04c4d-104">自動インクリメント<xref:System.Data.DataColumn>を作成するには、列<xref:System.Data.DataColumn.AutoIncrement%2A>のプロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="04c4d-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="04c4d-105">次<xref:System.Data.DataColumn>に、は、 <xref:System.Data.DataColumn.AutoIncrementSeed%2A>プロパティで定義されている値で始まり、各行が追加されると、列の<xref:System.Data.DataColumn.AutoIncrementStep%2A>プロパティで定義されている値によって AutoIncrement 列の値が増加します。</span><span class="sxs-lookup"><span data-stu-id="04c4d-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="04c4d-106">**Autoincrement**列の場合は、 **DataColumn**の<xref:System.Data.DataColumn.ReadOnly%2A>プロパティを**true**に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04c4d-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="04c4d-107">値 200 から開始して 3 ずつインクリメントする列を作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="04c4d-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="04c4d-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="04c4d-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="04c4d-109">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="04c4d-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="04c4d-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="04c4d-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="04c4d-111">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="04c4d-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
