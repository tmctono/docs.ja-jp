---
title: DataView イベントの処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b625fad846c4c6cf008843bff1f6b0eabe0e1de4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151105"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="97e99-102">DataView イベントの処理</span><span class="sxs-lookup"><span data-stu-id="97e99-102">Handling DataView Events</span></span>
<span data-ttu-id="97e99-103"><xref:System.Data.DataView.ListChanged> の <xref:System.Data.DataView> イベントを使用して、ビューが更新されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="97e99-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="97e99-104">基になるテーブルの行の追加、削除、または変更や、このスキーマの列の追加または削除、親子のリレーションシップの変更など、これらの更新を行うとこのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="97e99-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="97e99-105">**ListChanged**イベントは、新しい並べ替え順序またはフィルタの適用により、表示している行のリストが大幅に変更されたかどうかを通知します。</span><span class="sxs-lookup"><span data-stu-id="97e99-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="97e99-106">イベント**は**、名前空間の**ListChangedEventHandler**デリゲートを<xref:System.ComponentModel>実装し、オブジェクトの<xref:System.ComponentModel.ListChangedEventArgs>入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="97e99-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="97e99-107">**オブジェクトの** **ListChangedType**プロパティの列挙値を<xref:System.ComponentModel.ListChangedType>使用して、どのような変更が発生したかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="97e99-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="97e99-108">行の追加、削除、または移動を含む変更の場合、追加または移動された行の新しいインデックスと、削除された行の前のインデックスに **、ListChangedEventArgs**オブジェクトの**NewIndex**プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="97e99-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="97e99-109">移動された行の場合は、**オブジェクト**の**OldIndex**プロパティを使用して、移動された行の前のインデックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="97e99-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="97e99-110">**また、テーブル**が追加または削除された場合、または基になる**DataSet**の**Relations**コレクションに変更が加えられた場合に通知する**ListChanged**イベントも公開されます。</span><span class="sxs-lookup"><span data-stu-id="97e99-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="97e99-111">次のコード例は **、ListChanged**イベント ハンドラーを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="97e99-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="97e99-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="97e99-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="97e99-113">DataViews</span><span class="sxs-lookup"><span data-stu-id="97e99-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="97e99-114">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="97e99-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
