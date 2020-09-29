---
title: DataRow および DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: bce90c1d310178e66da7c758c6df2cd357199c8b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153288"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="92417-102">DataRow および DataRowView</span><span class="sxs-lookup"><span data-stu-id="92417-102">DataRows and DataRowViews</span></span>

<span data-ttu-id="92417-103"><xref:System.Data.DataView> は、<xref:System.Data.DataRowView> オブジェクトの列挙可能なコレクションを公開します。</span><span class="sxs-lookup"><span data-stu-id="92417-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="92417-104">**DataRowView** オブジェクトは、基になるテーブルの列の名前または列の序数参照によってインデックスが設定されているオブジェクトの配列として値を公開します。</span><span class="sxs-lookup"><span data-stu-id="92417-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="92417-105">**DataRowView** の <xref:System.Data.DataRowView.Row%2A> プロパティを使用することによって、**DataRowView** で公開されている <xref:System.Data.DataRow> にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="92417-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="92417-106">**DataRowView** を使用して値を表示している場合は、**DataView** の <xref:System.Data.DataView.RowStateFilter%2A> プロパティによって、基になる **DataRow** から公開される行バージョンが決まります。</span><span class="sxs-lookup"><span data-stu-id="92417-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="92417-107">**DataRow** を使用してさまざまな行バージョンにアクセスする方法については、「[行の状態とバージョン](row-states-and-row-versions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="92417-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="92417-108">テーブルの現在の値と元の値をすべて表示するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="92417-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92417-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="92417-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="92417-110">DataViews</span><span class="sxs-lookup"><span data-stu-id="92417-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="92417-111">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="92417-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
