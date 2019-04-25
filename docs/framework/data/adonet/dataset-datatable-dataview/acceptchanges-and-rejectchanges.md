---
title: AcceptChange と RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: bbcc666b99c2bade479e5ee51750b043c820845d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879906"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="75fd3-102">AcceptChange と RejectChange</span><span class="sxs-lookup"><span data-stu-id="75fd3-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="75fd3-103">内のデータに加えられた変更の精度を確認した後、<xref:System.Data.DataTable>を使用して変更を受け入れることができます、<xref:System.Data.DataRow.AcceptChanges%2A>のメソッド、 <xref:System.Data.DataRow>、 <xref:System.Data.DataTable>、または<xref:System.Data.DataSet>、これは、設定、**現在**行値を**元**値し、設定は、 **RowState**プロパティを**Unchanged**します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="75fd3-104">いずれかをクリアして承認または変更を拒否する**RowError**情報と設定、 **HasErrors**プロパティを**false**します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="75fd3-105">変更を受け入れるかまたは拒否した場合、データ ソース内で実行中の更新操作にも影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="75fd3-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="75fd3-106">詳細については、次を参照してください。 [Dataadapter によるデータ ソースを更新](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="75fd3-107">外部キー制約が存在しない場合、 **DataTable**、変更が承認されるかを使用して拒否された**AcceptChanges**と**RejectChanges** の子の行に反映されます**DataRow**に従い、 **ForeignKeyConstraint.AcceptRejectRule**します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="75fd3-108">詳細については、次を参照してください。 [DataTable の制約](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="75fd3-109">行にエラーがあるかどうかをチェックし、必要に応じてエラーを解決し、エラーを解決できない場合にはその行を拒否する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="75fd3-110">解決、エラーのことに注意してください、 **RowError**値は空の文字列にリセット原因、 **HasErrors**プロパティを設定する**false**します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="75fd3-111">エラーのあるすべての行が解決または拒否されたときに**AcceptChanges**全体のすべての変更を受け入れるために呼び出される**DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="75fd3-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a><span data-ttu-id="75fd3-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="75fd3-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="75fd3-113">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="75fd3-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="75fd3-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="75fd3-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
