---
title: DataView イベントの処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b3a1077bff9bf457b4aef0b05357d4a9260f8973
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204821"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="3258d-102">DataView イベントの処理</span><span class="sxs-lookup"><span data-stu-id="3258d-102">Handling DataView Events</span></span>
<span data-ttu-id="3258d-103"><xref:System.Data.DataView.ListChanged> の <xref:System.Data.DataView> イベントを使用して、ビューが更新されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3258d-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="3258d-104">基になるテーブルの行の追加、削除、または変更や、このスキーマの列の追加または削除、親子のリレーションシップの変更など、これらの更新を行うとこのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3258d-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="3258d-105">また、 **ListChanged**イベントは、表示している行の一覧が新しい並べ替え順序またはフィルターの適用によって大幅に変更された場合にも通知します。</span><span class="sxs-lookup"><span data-stu-id="3258d-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="3258d-106">**ListChanged**イベントは、 <xref:System.ComponentModel>名前空間の**listchangedeventhandler**デリゲートを実装し、オブジェクトを<xref:System.ComponentModel.ListChangedEventArgs>入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3258d-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="3258d-107">**ListChangedEventArgs**オブジェクトの**list type**プロパティの列挙値を<xref:System.ComponentModel.ListChangedType>使用して、発生した変更の種類を確認できます。</span><span class="sxs-lookup"><span data-stu-id="3258d-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="3258d-108">行の追加、削除、または移動を含む変更の場合、追加または移動された行の新しいインデックス、および削除された行の前のインデックスは、 **ListChangedEventArgs**オブジェクトの**NewIndex**プロパティを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3258d-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="3258d-109">移動された行の場合は、 **ListChangedEventArgs**オブジェクトの**oldindex**プロパティを使用して、移動された行の前のインデックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3258d-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="3258d-110">また、 **DataViewManager**は、テーブルが追加または削除されたかどうか、または基になる**データセット**の**リレーション**コレクションに変更が加えられたかどうかを通知する**ListChanged**イベントも公開します。</span><span class="sxs-lookup"><span data-stu-id="3258d-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="3258d-111">次のコード例は、 **ListChanged**イベントハンドラーを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3258d-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3258d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3258d-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="3258d-113">DataViews</span><span class="sxs-lookup"><span data-stu-id="3258d-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="3258d-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="3258d-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
