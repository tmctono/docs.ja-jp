---
title: AutoIncrement 列の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 2548ad9382b406978dac0a3d366207626278f501
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205134"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="8c176-102">AutoIncrement 列の作成</span><span class="sxs-lookup"><span data-stu-id="8c176-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="8c176-103">列値を一意にするために、新しい行がテーブルに追加されたときに列値が自動的にインクリメントされるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="8c176-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="8c176-104">自動インクリメント<xref:System.Data.DataColumn>を作成するには、列<xref:System.Data.DataColumn.AutoIncrement%2A>のプロパティを**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="8c176-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="8c176-105">次<xref:System.Data.DataColumn>に、は、 <xref:System.Data.DataColumn.AutoIncrementSeed%2A>プロパティで定義されている値で始まり、各行が追加されると、列の<xref:System.Data.DataColumn.AutoIncrementStep%2A>プロパティで定義されている値によって AutoIncrement 列の値が増加します。</span><span class="sxs-lookup"><span data-stu-id="8c176-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="8c176-106">**Autoincrement**列の場合は、 **DataColumn**の<xref:System.Data.DataColumn.ReadOnly%2A>プロパティを**true**に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8c176-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="8c176-107">値 200 から開始して 3 ずつインクリメントする列を作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="8c176-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8c176-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c176-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="8c176-109">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="8c176-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="8c176-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="8c176-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="8c176-111">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="8c176-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
