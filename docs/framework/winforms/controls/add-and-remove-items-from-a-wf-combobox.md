---
title: ComboBox、ListBox、または CheckedListBox コントロールの項目を追加および削除する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: 3a83d98af42386b566b4af7bc11ff383dea8fd6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746296"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="1da52-102">方法 : Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="1da52-102">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="1da52-103">項目は、さまざまな方法で Windows フォームコンボボックス、リストボックス、またはチェックリストボックスに追加できます。これらのコントロールはさまざまなデータソースにバインドできるためです。</span><span class="sxs-lookup"><span data-stu-id="1da52-103">Items can be added to a Windows Forms combo box, list box, or checked list box in a variety of ways, because these controls can be bound to a variety of data sources.</span></span> <span data-ttu-id="1da52-104">ただし、このトピックでは、最も簡単な方法について説明し、データバインディングは不要です。</span><span class="sxs-lookup"><span data-stu-id="1da52-104">However, this topic demonstrates the simplest method and requires no data binding.</span></span> <span data-ttu-id="1da52-105">通常、表示される項目は文字列です。ただし、任意のオブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1da52-105">The items displayed are usually strings; however, any object can be used.</span></span> <span data-ttu-id="1da52-106">コントロールに表示されるテキストは、オブジェクトの `ToString` メソッドによって返される値です。</span><span class="sxs-lookup"><span data-stu-id="1da52-106">The text that is displayed in the control is the value returned by the object's `ToString` method.</span></span>  
  
### <a name="to-add-items"></a><span data-ttu-id="1da52-107">項目を追加するには</span><span class="sxs-lookup"><span data-stu-id="1da52-107">To add items</span></span>  
  
1. <span data-ttu-id="1da52-108">`ObjectCollection` クラスの `Add` メソッドを使用して、文字列またはオブジェクトをリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1da52-108">Add the string or object to the list by using the `Add` method of the `ObjectCollection` class.</span></span> <span data-ttu-id="1da52-109">コレクションは、`Items` プロパティを使用して参照されます。</span><span class="sxs-lookup"><span data-stu-id="1da52-109">The collection is referenced using the `Items` property:</span></span>  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - <span data-ttu-id="1da52-110">または</span><span class="sxs-lookup"><span data-stu-id="1da52-110">or -</span></span>  
  
2. <span data-ttu-id="1da52-111">`Insert` メソッドを使用して、リスト内の目的の位置に文字列またはオブジェクトを挿入します。</span><span class="sxs-lookup"><span data-stu-id="1da52-111">Insert the string or object at the desired point in the list with the `Insert` method:</span></span>  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - <span data-ttu-id="1da52-112">または</span><span class="sxs-lookup"><span data-stu-id="1da52-112">or -</span></span>  
  
3. <span data-ttu-id="1da52-113">配列全体を `Items` コレクションに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1da52-113">Assign an entire array to the `Items` collection:</span></span>  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="1da52-114">アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="1da52-114">To remove an item</span></span>  
  
1. <span data-ttu-id="1da52-115">`Remove` または `RemoveAt` メソッドを呼び出して、項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="1da52-115">Call the `Remove` or `RemoveAt` method to delete items.</span></span>  
  
     <span data-ttu-id="1da52-116">`Remove` には、削除する項目を指定する引数が1つあります。`RemoveAt`</span><span class="sxs-lookup"><span data-stu-id="1da52-116">`Remove` has one argument that specifies the item to remove.`RemoveAt`</span></span> <span data-ttu-id="1da52-117">指定したインデックス番号の項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="1da52-117">removes the item with the specified index number.</span></span>  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a><span data-ttu-id="1da52-118">すべての項目を削除するには</span><span class="sxs-lookup"><span data-stu-id="1da52-118">To remove all items</span></span>  
  
1. <span data-ttu-id="1da52-119">`Clear` メソッドを呼び出して、コレクションからすべての項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="1da52-119">Call the `Clear` method to remove all items from the collection:</span></span>  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1da52-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="1da52-120">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="1da52-121">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える</span><span class="sxs-lookup"><span data-stu-id="1da52-121">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="1da52-122">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="1da52-122">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="1da52-123">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="1da52-123">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
