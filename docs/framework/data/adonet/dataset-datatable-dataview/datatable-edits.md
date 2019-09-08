---
title: DataTable の編集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 689a297eb5368d35c2e7dd034426edbe665e7ed2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785386"
---
# <a name="datatable-edits"></a><span data-ttu-id="46689-102">DataTable の編集</span><span class="sxs-lookup"><span data-stu-id="46689-102">DataTable Edits</span></span>
<span data-ttu-id="46689-103"><xref:System.Data.DataRow> 内の列値を変更すると、その変更はすぐに行の現在の状態に反映されます。</span><span class="sxs-lookup"><span data-stu-id="46689-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="46689-104">次<xref:System.Data.DataRowState>に、が**Modified**に設定され、 <xref:System.Data.DataRow.AcceptChanges%2A> **DataRow**のメソッドまたは<xref:System.Data.DataRow.RejectChanges%2A>メソッドを使用して変更が受け入れられるか拒否されます。</span><span class="sxs-lookup"><span data-stu-id="46689-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="46689-105">**DataRow**には、編集中に行の状態を中断するために使用できる3つのメソッドも用意されています。</span><span class="sxs-lookup"><span data-stu-id="46689-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="46689-106">これらのメソッドとは、<xref:System.Data.DataRow.BeginEdit%2A>、<xref:System.Data.DataRow.EndEdit%2A> および <xref:System.Data.DataRow.CancelEdit%2A> です。</span><span class="sxs-lookup"><span data-stu-id="46689-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="46689-107">**Datarow**内の列の値を直接変更すると、 **Datarow**は、**現在**、**既定**、および**元**の行バージョンを使用して列の値を管理します。</span><span class="sxs-lookup"><span data-stu-id="46689-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="46689-108">これらの行バージョンに加えて、 **BeginEdit**、 **EndEdit**、および**CancelEdit**メソッドでは、4番目の行バージョンが使用されます。**提案済み**。</span><span class="sxs-lookup"><span data-stu-id="46689-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="46689-109">行バージョンの詳細については、「[行の状態と行のバージョン](row-states-and-row-versions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46689-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="46689-110">**提案**された行バージョンは、編集操作中に存在します。これは、 **EndEdit**または**CancelEdit**を使用するか、または**AcceptChanges**または**RejectChanges**を呼び出して、 **BeginEdit**を呼び出して開始します。</span><span class="sxs-lookup"><span data-stu-id="46689-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="46689-111">編集操作中に、 **DataTable**の**Columnchanged**イベントの**ProposedValue**を評価することによって、個々の列に検証ロジックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="46689-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="46689-112">**Columnchanged**イベントは、変更されている列と**ProposedValue**に参照を保持する**DataColumnChangeEventArgs**を保持します。</span><span class="sxs-lookup"><span data-stu-id="46689-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="46689-113">提示された値を評価した後で、値を変更するか、または編集をキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="46689-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="46689-114">編集が終了すると、行は**提案**された状態から移動します。</span><span class="sxs-lookup"><span data-stu-id="46689-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="46689-115">**EndEdit**を呼び出すことで編集を確認できます。または、 **CancelEdit**を呼び出して、編集を取り消すこともできます。</span><span class="sxs-lookup"><span data-stu-id="46689-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="46689-116">**EndEdit**が編集内容を確認しても、 **AcceptChanges**が呼び出されるまで、**データセット**は実際には変更を受け入れないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="46689-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="46689-117">また、 **EndEdit**または**CancelEdit**で編集を終了する前に**AcceptChanges**を呼び出すと、編集が終了し、**現在**の行バージョンと**元**の行バージョンの両方に対して、**提案**された行の値が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="46689-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="46689-118">同様に、 **RejectChanges**を呼び出すと、編集が終了し、**現在**の行バージョンと**提案**された行バージョンが破棄されます。</span><span class="sxs-lookup"><span data-stu-id="46689-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="46689-119">**AcceptChanges**または**RejectChanges**を呼び出した後に**EndEdit**または**CancelEdit**を呼び出すと、編集が既に終了しているため、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="46689-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="46689-120">次の例は、 **EndEdit**と**CancelEdit**での**BeginEdit**の使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="46689-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="46689-121">また、この例では、 **Columnchanged**イベントの**ProposedValue**を確認し、編集を取り消すかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="46689-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="46689-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="46689-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="46689-123">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="46689-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="46689-124">DataTable イベントの処理</span><span class="sxs-lookup"><span data-stu-id="46689-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="46689-125">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="46689-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
