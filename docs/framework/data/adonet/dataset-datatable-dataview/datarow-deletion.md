---
title: DataRow の削除
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 7c80294c4bc879e6a1df4c9d1170eef14b8b83de
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915815"
---
# <a name="datarow-deletion"></a><span data-ttu-id="5a298-102">DataRow の削除</span><span class="sxs-lookup"><span data-stu-id="5a298-102">DataRow Deletion</span></span>
<span data-ttu-id="5a298-103"><xref:System.Data.DataRow>オブジェクト<xref:System.Data.DataRowCollection> <xref:System.Data.DataRow.Delete%2A>からオブジェクトを削除するには、オブジェクトの Remove メソッドと DataRow オブジェクトのメソッドの2つのメソッドを使用できます。 <xref:System.Data.DataTable></span><span class="sxs-lookup"><span data-stu-id="5a298-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="5a298-104">メソッドは**DataRowCollection**から DataRow を削除しますが、 <xref:System.Data.DataRow.Delete%2A>メソッドは行を削除対象としてマークするだけです。 <xref:System.Data.DataRowCollection.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="5a298-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="5a298-105">実際の削除は、アプリケーションが**AcceptChanges**メソッドを呼び出したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="5a298-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="5a298-106"><xref:System.Data.DataRow.Delete%2A> を使用すると、行を実際に削除する前に、削除対象としてどの行がマークされているかをプログラムによってチェックできます。</span><span class="sxs-lookup"><span data-stu-id="5a298-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="5a298-107">削除対象としてマークされている行の <xref:System.Data.DataRow.RowState%2A> プロパティは、<xref:System.Data.DataRow.Delete%2A> に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5a298-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="5a298-108"><xref:System.Data.DataRow.Delete%2A> オブジェクトを反復処理している間は、foreach ループで <xref:System.Data.DataRowCollection.Remove%2A> も <xref:System.Data.DataRowCollection> も呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5a298-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="5a298-109"><xref:System.Data.DataRow.Delete%2A> または <xref:System.Data.DataRowCollection.Remove%2A> はコレクションの状態を変更します。</span><span class="sxs-lookup"><span data-stu-id="5a298-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="5a298-110">DataAdapter およびリレーショナル<xref:System.Data.DataSet>データソースと共にまたは**DataTable**を使用する場合は、 **DataRow**の**Delete**メソッドを使用して行を削除します。</span><span class="sxs-lookup"><span data-stu-id="5a298-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="5a298-111">**Delete**メソッドは、行を**DataSet**または**DataTable**で**削除済み**としてマークしますが、削除はしません。</span><span class="sxs-lookup"><span data-stu-id="5a298-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="5a298-112">代わりに、 **DataAdapter**が**削除済み**としてマークされた行を検出すると、 **DeleteCommand**メソッドを実行してデータソースの行を削除します。</span><span class="sxs-lookup"><span data-stu-id="5a298-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="5a298-113">この行は、 **AcceptChanges**メソッドを使用して完全に削除できます。</span><span class="sxs-lookup"><span data-stu-id="5a298-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="5a298-114">**Remove**を使用して行を削除すると、その行はテーブルから完全に削除されますが、 **DataAdapter**はデータソースの行を削除しません。</span><span class="sxs-lookup"><span data-stu-id="5a298-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="5a298-115">**DataRowCollection**の**Remove**メソッドは、次の例に示すように、 **DataRow**を引数として受け取り、コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="5a298-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="5a298-116">これに対して、次の例では、 **DataRow**の**Delete**メソッドを呼び出して、その**RowState**を**Deleted**に変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5a298-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="5a298-117">行が削除対象としてマークされていて、 **datatable**オブジェクトの**AcceptChanges**メソッドを呼び出すと、その行が**datatable**から削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a298-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="5a298-118">これに対し、 **RejectChanges**を呼び出すと、行の**RowState**は、**削除済み**としてマークされる前の行に戻ります。</span><span class="sxs-lookup"><span data-stu-id="5a298-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a298-119">**DataRow**の**RowState**が**追加**された場合、これはテーブルに追加されたばかりであることを意味し、**削除済み**としてマークされ、テーブルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a298-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a298-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a298-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="5a298-121">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="5a298-121">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="5a298-122">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="5a298-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
