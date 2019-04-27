---
title: DataTable の編集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 0300ceab16d9a94bd04468f7acd105e69d13e643
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879841"
---
# <a name="datatable-edits"></a><span data-ttu-id="836a1-102">DataTable の編集</span><span class="sxs-lookup"><span data-stu-id="836a1-102">DataTable Edits</span></span>
<span data-ttu-id="836a1-103"><xref:System.Data.DataRow> 内の列値を変更すると、その変更はすぐに行の現在の状態に反映されます。</span><span class="sxs-lookup"><span data-stu-id="836a1-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="836a1-104"><xref:System.Data.DataRowState>に設定されている、 **Modified**、され、変更が受け入れられますまたは拒否を使用して、<xref:System.Data.DataRow.AcceptChanges%2A>または<xref:System.Data.DataRow.RejectChanges%2A>のメソッド、 **DataRow**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="836a1-105">**DataRow**を編集しているときに、行の状態を中断するのに使用できる 3 つのメソッドも提供されます。</span><span class="sxs-lookup"><span data-stu-id="836a1-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="836a1-106">これらのメソッドとは、<xref:System.Data.DataRow.BeginEdit%2A>、<xref:System.Data.DataRow.EndEdit%2A> および <xref:System.Data.DataRow.CancelEdit%2A> です。</span><span class="sxs-lookup"><span data-stu-id="836a1-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="836a1-107">列の値を変更する場合、 **DataRow**を直接、 **DataRow**を使用して列の値を管理、**現在**、**既定**と**元**行のバージョン。</span><span class="sxs-lookup"><span data-stu-id="836a1-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="836a1-108">これらの行のバージョンだけでなく、 **BeginEdit**、 **EndEdit**、および**CancelEdit**メソッドを使用して、4 番目の行のバージョン。**提案された**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="836a1-109">行のバージョンの詳細については、次を参照してください。[行の状態と行バージョン](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)します。</span><span class="sxs-lookup"><span data-stu-id="836a1-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="836a1-110">**提案済み**呼び出しによって開始編集操作中に行バージョンが存在する**BeginEdit**を使用するか終了して**EndEdit**または**CancelEdit**または呼び出すことによって**AcceptChanges**または**RejectChanges**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="836a1-111">編集操作中に適用できます検証ロジックの個々 の列を評価することによって、 **ProposedValue**で、 **ColumnChanged**のイベント、 **DataTable**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="836a1-112">**ColumnChanged**イベントを保持**DataColumnChangeEventArgs**変更されている列をする参照を保持する、 **ProposedValue**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="836a1-113">提示された値を評価した後で、値を変更するか、または編集をキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="836a1-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="836a1-114">うち、行が移動、編集が終了したとき、**提案済み**状態。</span><span class="sxs-lookup"><span data-stu-id="836a1-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="836a1-115">編集内容を確認するには呼び出すことによって**EndEdit**、呼び出すことによって、それらをキャンセルできます**CancelEdit**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="836a1-116">注意してください**EndEdit**が編集内容を確認して、**データセット**まで変更を実際には受け入れません**AcceptChanges**が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="836a1-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="836a1-117">なおを呼び出す場合**AcceptChanges**で編集を終了する前に**EndEdit**または**CancelEdit**、編集を終了し、 **提案済み**両方の行の値を受け入れる、**現在**と**元**行のバージョン。</span><span class="sxs-lookup"><span data-stu-id="836a1-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="836a1-118">同様に、呼び出す**RejectChanges**編集を終了し、破棄、**現在**と**提案済み**行のバージョン。</span><span class="sxs-lookup"><span data-stu-id="836a1-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="836a1-119">呼び出す**EndEdit**または**CancelEdit**呼び出した後**AcceptChanges**または**RejectChanges**編集が既にあるため、影響を与えません終了しました。</span><span class="sxs-lookup"><span data-stu-id="836a1-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="836a1-120">次の例を使用する方法を示します**BeginEdit**で**EndEdit**と**CancelEdit**します。</span><span class="sxs-lookup"><span data-stu-id="836a1-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="836a1-121">例もチェック、 **ProposedValue**で、 **ColumnChanged**イベントされ、編集をキャンセルするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="836a1-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="836a1-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="836a1-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="836a1-123">DataTable 内のデータの操作</span><span class="sxs-lookup"><span data-stu-id="836a1-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="836a1-124">DataTable イベントの処理</span><span class="sxs-lookup"><span data-stu-id="836a1-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)
- [<span data-ttu-id="836a1-125">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="836a1-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
