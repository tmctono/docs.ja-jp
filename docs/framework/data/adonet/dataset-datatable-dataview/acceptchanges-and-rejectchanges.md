---
title: AcceptChange と RejectChange
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: a8589b157bc2579a03d856b73802abc9a4b42855
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204077"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="28bbf-102">AcceptChange と RejectChange</span><span class="sxs-lookup"><span data-stu-id="28bbf-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="28bbf-103">で<xref:System.Data.DataTable> <xref:System.Data.DataRow.AcceptChanges%2A>データに対して行われた変更の精度を確認した後、 <xref:System.Data.DataRow>、 <xref:System.Data.DataTable>、または<xref:System.Data.DataSet>のメソッドを使用して変更を受け入れることができます。これにより、**現在**の**行の値がに設定されます。元**の値は、 **RowState**プロパティを**Unchanged**に設定します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="28bbf-104">変更の受け入れまたは拒否を行うと、 **RowError**情報がクリアされ、 **haserrors**プロパティが**false**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="28bbf-105">変更を受け入れるかまたは拒否した場合、データ ソース内で実行中の更新操作にも影響することがあります。</span><span class="sxs-lookup"><span data-stu-id="28bbf-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="28bbf-106">詳細については、「 [dataadapter を使用したデータソースの更新](../updating-data-sources-with-dataadapters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28bbf-106">For more information, see [Updating Data Sources with DataAdapters](../updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="28bbf-107">**DataTable**に foreign key 制約が存在する場合、 **AcceptChanges**と**RejectChanges**を使用して許可または拒否された変更は、 **DataRow**の子行に反映されます **。ForeignKeyConstraint AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="28bbf-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="28bbf-108">詳細については、「 [DataTable の制約](datatable-constraints.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28bbf-108">For more information, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="28bbf-109">行にエラーがあるかどうかをチェックし、必要に応じてエラーを解決し、エラーを解決できない場合にはその行を拒否する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="28bbf-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="28bbf-110">解決されたエラーについては、 **RowError**の値が空の文字列にリセットされ、 **haserrors**プロパティが**false**に設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28bbf-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="28bbf-111">エラーのあるすべての行が解決または拒否された場合、**データテーブル**全体のすべての変更を受け入れるために**AcceptChanges**が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="28bbf-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28bbf-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="28bbf-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="28bbf-113">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="28bbf-113">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="28bbf-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="28bbf-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
