---
title: CheckedListBox コントロールでチェックされている項目を確認する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5854f7e6be759daeb604458ea8554d3c98ed39c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743241"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="f0e73-102">方法 : Windows フォーム CheckedListBox コントロールでオンになっている項目を判断する</span><span class="sxs-lookup"><span data-stu-id="f0e73-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="f0e73-103">Windows フォーム <xref:System.Windows.Forms.CheckedListBox> コントロールにデータを表示する場合は、<xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> プロパティに格納されているコレクションを反復処理するか、<xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> メソッドを使用してリストをステップ実行し、どの項目がチェックされるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f0e73-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="f0e73-104"><xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> メソッドは、項目のインデックス番号を引数として受け取り、`true` または `false`を返します。</span><span class="sxs-lookup"><span data-stu-id="f0e73-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="f0e73-105">期待しているものとは異なり、<xref:System.Windows.Forms.ListBox.SelectedItems%2A> と <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> のプロパティでは、どの項目がチェックされるかは決定されません。どの項目が強調表示されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f0e73-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="f0e73-106">CheckedListBox コントロールでチェックされている項目を確認するには</span><span class="sxs-lookup"><span data-stu-id="f0e73-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="f0e73-107">コレクションが0から始まるため、<xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> コレクションを反復処理して0から開始します。</span><span class="sxs-lookup"><span data-stu-id="f0e73-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="f0e73-108">このメソッドは、リスト全体ではなく、チェックされた項目の一覧に項目番号を提供します。</span><span class="sxs-lookup"><span data-stu-id="f0e73-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="f0e73-109">このため、リストの最初の項目がチェックされず、2番目の項目がオンになっている場合は、次のコードに "Checked Item 1 = MyListItem2" のようなテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0e73-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - <span data-ttu-id="f0e73-110">または</span><span class="sxs-lookup"><span data-stu-id="f0e73-110">or -</span></span>  
  
2. <span data-ttu-id="f0e73-111">コレクションが0から始まるため、<xref:System.Windows.Forms.CheckedListBox.Items%2A> コレクションをステップ実行し、各項目に対して <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0e73-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="f0e73-112">この方法では、一覧の項目番号が表示されるので、リスト内の最初の項目がチェックされず、2番目の項目がオンになっている場合は、"Item 2 = MyListItem2" のような内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0e73-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;   
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f0e73-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0e73-113">See also</span></span>

- [<span data-ttu-id="f0e73-114">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="f0e73-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
