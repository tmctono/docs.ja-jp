---
title: DataRow および DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 8a98dc44eda9ebda09235193c58bd831fc52d04d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205091"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="a648b-102">DataRow および DataRowView</span><span class="sxs-lookup"><span data-stu-id="a648b-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="a648b-103"><xref:System.Data.DataView> は、<xref:System.Data.DataRowView> オブジェクトの列挙可能なコレクションを公開します。</span><span class="sxs-lookup"><span data-stu-id="a648b-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="a648b-104">**DataRowView**オブジェクトは、基になるテーブル内の列の名前または序数参照によってインデックスが作成されたオブジェクト配列として値を公開します。</span><span class="sxs-lookup"><span data-stu-id="a648b-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="a648b-105">DataRowView によって<xref:System.Data.DataRow>公開されているには、 <xref:System.Data.DataRowView.Row%2A> **DataRowView**のプロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a648b-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="a648b-106">**DataRowView**を使用して値を表示すると<xref:System.Data.DataView.RowStateFilter%2A> 、 **DataView**のプロパティによって、基になる**DataRow**の行バージョンが決まります。</span><span class="sxs-lookup"><span data-stu-id="a648b-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="a648b-107">**DataRow**を使用して異なる行バージョンにアクセスする方法の詳細については、「[行の状態と行のバージョン](row-states-and-row-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a648b-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="a648b-108">テーブルの現在の値と元の値をすべて表示するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="a648b-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a648b-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="a648b-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="a648b-110">DataViews</span><span class="sxs-lookup"><span data-stu-id="a648b-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="a648b-111">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="a648b-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
