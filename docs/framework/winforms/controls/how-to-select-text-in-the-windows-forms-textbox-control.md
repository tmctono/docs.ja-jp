---
title: TextBox コントロール内のテキストを選択する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: 8a32e40f14ddae6f8ddcaa6d62337329df6fde26
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745308"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="a82ff-102">方法 : Windows フォーム TextBox コントロールでテキストを選択する</span><span class="sxs-lookup"><span data-stu-id="a82ff-102">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="a82ff-103">Windows フォーム <xref:System.Windows.Forms.TextBox> コントロールでプログラムによってテキストを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a82ff-103">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="a82ff-104">たとえば、特定の文字列を検索する関数を作成する場合、テキストを選択して、検出された文字列の位置のリーダーを視覚的に警告することができます。</span><span class="sxs-lookup"><span data-stu-id="a82ff-104">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="a82ff-105">プログラムによってテキストを選択するには</span><span class="sxs-lookup"><span data-stu-id="a82ff-105">To select text programmatically</span></span>  
  
1. <span data-ttu-id="a82ff-106"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> プロパティを、選択するテキストの先頭に設定します。</span><span class="sxs-lookup"><span data-stu-id="a82ff-106">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="a82ff-107"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> プロパティは、テキストの文字列内の挿入ポイントを示す数値です。0は左端の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="a82ff-107">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="a82ff-108"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> プロパティがテキストボックス内の文字数以上に設定されている場合、挿入ポイントは最後の文字の後に配置されます。</span><span class="sxs-lookup"><span data-stu-id="a82ff-108">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="a82ff-109"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> プロパティを、選択するテキストの長さに設定します。</span><span class="sxs-lookup"><span data-stu-id="a82ff-109">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="a82ff-110"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> プロパティは、挿入ポイントの幅を設定する数値です。</span><span class="sxs-lookup"><span data-stu-id="a82ff-110">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="a82ff-111"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> を0より大きい数値に設定すると、現在の挿入ポイントから始まる文字数が選択されます。</span><span class="sxs-lookup"><span data-stu-id="a82ff-111">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="a82ff-112">Optional<xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> プロパティを使用して、選択したテキストにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a82ff-112">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="a82ff-113">次のコードでは、コントロールの <xref:System.Windows.Forms.Control.Enter> イベントが発生したときにテキストボックスの内容を選択します。</span><span class="sxs-lookup"><span data-stu-id="a82ff-113">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="a82ff-114">この例では、テキストボックスに `null` または空の文字列ではない <xref:System.Windows.Forms.TextBox.Text%2A> プロパティの値があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a82ff-114">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="a82ff-115">テキストボックスがフォーカスを受け取ると、テキストボックス内の現在のテキストが選択されます。</span><span class="sxs-lookup"><span data-stu-id="a82ff-115">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="a82ff-116">`TextBox1_Enter` イベントハンドラーはコントロールにバインドされている必要があります。詳細については、「[方法: Windows フォームの実行時にイベントハンドラーを作成](../how-to-create-event-handlers-at-run-time-for-windows-forms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a82ff-116">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="a82ff-117">この例をテストするには、テキストボックスにフォーカスが移動するまで Tab キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a82ff-117">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="a82ff-118">テキストボックス内をクリックすると、テキストは選択されません。</span><span class="sxs-lookup"><span data-stu-id="a82ff-118">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a82ff-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a82ff-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a82ff-120">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a82ff-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a82ff-121">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="a82ff-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="a82ff-122">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="a82ff-122">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a82ff-123">方法: 読み取り専用テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="a82ff-123">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="a82ff-124">方法: 文字列に引用符を挿入する</span><span class="sxs-lookup"><span data-stu-id="a82ff-124">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a82ff-125">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="a82ff-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a82ff-126">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="a82ff-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
