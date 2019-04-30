---
title: AutoIncrement 列の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034373"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="32f12-102">AutoIncrement 列の作成</span><span class="sxs-lookup"><span data-stu-id="32f12-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="32f12-103">列値を一意にするために、新しい行がテーブルに追加されたときに列値が自動的にインクリメントされるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="32f12-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="32f12-104">自動インクリメントを作成する<xref:System.Data.DataColumn>、設定、<xref:System.Data.DataColumn.AutoIncrement%2A>プロパティには、列の**true**します。</span><span class="sxs-lookup"><span data-stu-id="32f12-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="32f12-105"><xref:System.Data.DataColumn>で定義されている値から開始し、<xref:System.Data.DataColumn.AutoIncrementSeed%2A>プロパティ、各行の値を追加し、 **AutoIncrement**列で定義されている値が、<xref:System.Data.DataColumn.AutoIncrementStep%2A>列のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="32f12-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="32f12-106">**AutoIncrement**列、お勧め、<xref:System.Data.DataColumn.ReadOnly%2A>のプロパティ、 **DataColumn**に設定する**true**します。</span><span class="sxs-lookup"><span data-stu-id="32f12-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="32f12-107">値 200 から開始して 3 ずつインクリメントする列を作成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="32f12-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="32f12-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="32f12-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="32f12-109">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="32f12-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="32f12-110">DataTables</span><span class="sxs-lookup"><span data-stu-id="32f12-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="32f12-111">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="32f12-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
