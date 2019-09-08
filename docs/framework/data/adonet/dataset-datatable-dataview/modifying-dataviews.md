---
title: DataView の変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3e811410ea9fdd4be0cbd84b895483f69f58b0d0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786046"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="5925b-102">DataView の変更</span><span class="sxs-lookup"><span data-stu-id="5925b-102">Modifying DataViews</span></span>
<span data-ttu-id="5925b-103"><xref:System.Data.DataView> を使用して、データ行を基になるテーブルに追加、削除、または変更できます。</span><span class="sxs-lookup"><span data-stu-id="5925b-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="5925b-104">**Dataview**を使用して基になるテーブルのデータを変更する機能は、 **dataview**の3つのブール型プロパティのいずれかを設定することによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="5925b-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="5925b-105">この 3 つのプロパティとは、<xref:System.Data.DataView.AllowNew%2A>、<xref:System.Data.DataView.AllowEdit%2A> および <xref:System.Data.DataView.AllowDelete%2A> です。</span><span class="sxs-lookup"><span data-stu-id="5925b-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="5925b-106">既定では、これらは**true**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5925b-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="5925b-107">**AllowNew**が**true**の場合、 **DataView**のメソッド<xref:System.Data.DataView.AddNew%2A>を使用して新しい<xref:System.Data.DataRowView>を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5925b-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="5925b-108"><xref:System.Data.DataTable> **DataRowView**の<xref:System.Data.DataRowView.EndEdit%2A>メソッドが呼び出されるまで、新しい行が基になるに実際に追加されるわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5925b-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="5925b-109"><xref:System.Data.DataRowView.CancelEdit%2A> **DataRowView**のメソッドが呼び出されると、新しい行は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="5925b-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="5925b-110">同時に編集できる**DataRowView**は1つだけであることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="5925b-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="5925b-111">保留中の行が存在するときに**DataRowView**の**AddNew**メソッドまたは**BeginEdit**メソッドを呼び出すと、保留中の行に対して**EndEdit**が暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5925b-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="5925b-112">**EndEdit**を呼び出すと、変更は基になる**datatable**に適用され、後で**datatable**、DataSet、または**データセット**の**AcceptChanges**メソッドまたは **RejectChanges メソッドを使用してコミットまたは拒否できます。DataRow**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5925b-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="5925b-113">**AllowNew**が**false**の場合、 **DataRowView**の**AddNew**メソッドを呼び出すと例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5925b-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="5925b-114">**AllowEdit**が**true**の場合、 **DataRowView**を使用して**DataRow**の内容を変更できます。</span><span class="sxs-lookup"><span data-stu-id="5925b-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="5925b-115">**DataRowView**を使用して基になる行に対する変更を確認するか、 **DataRowView**を使用して変更を拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="5925b-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="5925b-116">一度に編集できるのは 1 行だけです。</span><span class="sxs-lookup"><span data-stu-id="5925b-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="5925b-117">保留中の行が存在するときに**DataRowView**の**AddNew**メソッドまたは**BeginEdit**メソッドを呼び出すと、保留中の行に対して**EndEdit**が暗黙的に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5925b-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="5925b-118">**EndEdit**が呼び出されると、指定された変更は基になる**DataRow**の**現在**の行バージョンに配置され、後でコミット**または**拒否することができます。そのため**には、** **DataTable**、 **DataSet**、または**DataRow**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5925b-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="5925b-119">**AllowEdit**が**false**の場合、 **DataView**の値を変更しようとすると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5925b-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="5925b-120">既存の**DataRowView**が編集されている場合でも、基になる**DataTable**のイベントは、提案された変更で発生します。</span><span class="sxs-lookup"><span data-stu-id="5925b-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="5925b-121">基になる**DataRow**で**EndEdit**また**は CancelEdit**を呼び出すと、 **DataRowView**で**EndEdit**または**CancelEdit**が呼び出されているかどうかにかかわらず、保留中の変更が適用または取り消されます。</span><span class="sxs-lookup"><span data-stu-id="5925b-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="5925b-122">**Allowdelete**が**true**の場合、 **dataview**または**DataRowView**オブジェクトの**delete**メソッドを使用して**Dataview**から行を削除すると、基になる**DataTable**から行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="5925b-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="5925b-123">後で、 **AcceptChanges**または**RejectChanges**を使用して、削除をコミットまたは拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="5925b-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="5925b-124">**Allowdelete**が**false**の場合、 **DataView**または**DataRowView**の**Delete**メソッドを呼び出すと例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5925b-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="5925b-125">次のコード例では、 **dataview**を使用して行を削除し、 **dataview**を使用して基になるテーブルに新しい行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5925b-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a><span data-ttu-id="5925b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5925b-126">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="5925b-127">DataViews</span><span class="sxs-lookup"><span data-stu-id="5925b-127">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="5925b-128">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="5925b-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
