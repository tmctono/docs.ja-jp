---
title: DataView イベントの処理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: 6c2e554b7e6bde3e82190f70723f272b0d39a18a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61880036"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="a04d4-102">DataView イベントの処理</span><span class="sxs-lookup"><span data-stu-id="a04d4-102">Handling DataView Events</span></span>
<span data-ttu-id="a04d4-103"><xref:System.Data.DataView.ListChanged> の <xref:System.Data.DataView> イベントを使用して、ビューが更新されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a04d4-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="a04d4-104">基になるテーブルの行の追加、削除、または変更や、このスキーマの列の追加または削除、親子のリレーションシップの変更など、これらの更新を行うとこのイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="a04d4-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="a04d4-105">**ListChanged**イベントも通知を表示している行のリストが新しい並べ替え順序またはフィルターの適用により大幅に変更された場合。</span><span class="sxs-lookup"><span data-stu-id="a04d4-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="a04d4-106">**ListChanged**イベントを実装して、 **ListChangedEventHandler**の委任、<xref:System.ComponentModel>入力の名前空間ととして受け取り、<xref:System.ComponentModel.ListChangedEventArgs>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a04d4-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="a04d4-107">使用してどのような種類の変更が発生したかを判断できます、<xref:System.ComponentModel.ListChangedType>列挙値、 **ListChangedType**のプロパティ、 **ListChangedEventArgs**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a04d4-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="a04d4-108">ための追加に関連する変更、削除、または行を移動の追加または削除された行の新しいインデックスと削除された行の前のインデックスにアクセスできますを使用して、 **NewIndex**のプロパティ、 **ListChangedEventArgs**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a04d4-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="a04d4-109">移動された行の場合、移動された行の古いインデックス アクセスできるを使用して、 **OldIndex**のプロパティ、 **ListChangedEventArgs**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a04d4-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="a04d4-110">**DataViewManager**も公開、 **ListChanged**テーブルが追加または削除された場合、またはに変更が行われている場合に通知するイベント、**リレーション**のコレクション、基になる**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="a04d4-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="a04d4-111">次のコード例は、追加する方法を示します、 **ListChanged**イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a04d4-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a04d4-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="a04d4-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="a04d4-113">DataViews</span><span class="sxs-lookup"><span data-stu-id="a04d4-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="a04d4-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="a04d4-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
