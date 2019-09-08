---
title: DataRow および DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 7c76435b8a0f7a874504813d91d5eda929d08f67
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786422"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="99397-102">DataRow および DataRowView</span><span class="sxs-lookup"><span data-stu-id="99397-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="99397-103"><xref:System.Data.DataView> は、<xref:System.Data.DataRowView> オブジェクトの列挙可能なコレクションを公開します。</span><span class="sxs-lookup"><span data-stu-id="99397-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="99397-104">**DataRowView**オブジェクトは、基になるテーブル内の列の名前または序数参照によってインデックスが作成されたオブジェクト配列として値を公開します。</span><span class="sxs-lookup"><span data-stu-id="99397-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="99397-105">DataRowView によって<xref:System.Data.DataRow>公開されているには、 <xref:System.Data.DataRowView.Row%2A> **DataRowView**のプロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99397-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="99397-106">**DataRowView**を使用して値を表示すると<xref:System.Data.DataView.RowStateFilter%2A> 、 **DataView**のプロパティによって、基になる**DataRow**の行バージョンが決まります。</span><span class="sxs-lookup"><span data-stu-id="99397-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="99397-107">**DataRow**を使用して異なる行バージョンにアクセスする方法の詳細については、「[行の状態と行のバージョン](row-states-and-row-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99397-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="99397-108">テーブルの現在の値と元の値をすべて表示するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="99397-108">The following code example displays all the current and original values in a table.</span></span>  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="99397-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="99397-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="99397-110">DataViews</span><span class="sxs-lookup"><span data-stu-id="99397-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="99397-111">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="99397-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
