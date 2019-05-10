---
title: '方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
ms.openlocfilehash: a9d8c02a05723814d074ff91c847471287588618
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642969"
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a><span data-ttu-id="8dca4-102">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御する</span><span class="sxs-lookup"><span data-stu-id="8dca4-102">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>
<span data-ttu-id="8dca4-103">Windows フォームと<xref:System.Windows.Forms.TextBox>コントロールがフォーカスを受け取る最初に、テキスト ボックス内の既定のカーソルが既存のテキストの左側にします。</span><span class="sxs-lookup"><span data-stu-id="8dca4-103">When a Windows Forms <xref:System.Windows.Forms.TextBox> control first receives the focus, the default insertion within the text box is to the left of any existing text.</span></span> <span data-ttu-id="8dca4-104">ユーザーは、キーボードまたはマウス カーソルを移動できます。</span><span class="sxs-lookup"><span data-stu-id="8dca4-104">The user can move the insertion point with the keyboard or the mouse.</span></span> <span data-ttu-id="8dca4-105">テキスト ボックスは、フォーカスを得たを失い場合、カーソルが任意の場所、ユーザー置かれたことになります。</span><span class="sxs-lookup"><span data-stu-id="8dca4-105">If the text box loses and then regains the focus, the insertion point will be wherever the user last placed it.</span></span>  
  
 <span data-ttu-id="8dca4-106">場合によっては、この動作は、ユーザーの混乱を招くにできます。</span><span class="sxs-lookup"><span data-stu-id="8dca4-106">In some cases, this behavior can be disconcerting to the user.</span></span> <span data-ttu-id="8dca4-107">アプリケーションをワード プロセッシング、ユーザーは既存のテキストの後に表示される新しい文字を予想どおりです。</span><span class="sxs-lookup"><span data-stu-id="8dca4-107">In a word processing application, the user might expect new characters to appear after any existing text.</span></span> <span data-ttu-id="8dca4-108">データ エントリのアプリケーションで、ユーザーが任意の既存のエントリを置換する新しい文字予想します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-108">In a data entry application, the user might expect new characters to replace any existing entry.</span></span> <span data-ttu-id="8dca4-109"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>と<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>プロパティを有効にすることを目的に合わせて動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> and <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> properties enable you to modify the behavior to suit your purpose.</span></span>  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a><span data-ttu-id="8dca4-110">TextBox コントロールでのカーソル位置を制御するには</span><span class="sxs-lookup"><span data-stu-id="8dca4-110">To control the insertion point in a TextBox control</span></span>  
  
1. <span data-ttu-id="8dca4-111"><xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to an appropriate value.</span></span> <span data-ttu-id="8dca4-112">0 は、最初の文字の左側にすぐにカーソルを配置します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-112">Zero places the insertion point immediately to the left of the first character.</span></span>  
  
2. <span data-ttu-id="8dca4-113">(省略可能)設定、<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>プロパティを選択するテキストの長さにします。</span><span class="sxs-lookup"><span data-stu-id="8dca4-113">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="8dca4-114">次のコードは、常に 0 に挿入ポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-114">The code below always returns the insertion point to 0.</span></span> <span data-ttu-id="8dca4-115">`TextBox1_Enter`イベント ハンドラーの詳細については、コントロールにバインドする必要がありますを参照してください[Windows フォームでのイベント ハンドラーの作成](../creating-event-handlers-in-windows-forms.md)です。</span><span class="sxs-lookup"><span data-stu-id="8dca4-115">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [Creating Event Handlers in Windows Forms](../creating-event-handlers-in-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a><span data-ttu-id="8dca4-116">挿入ポイントを既定で表示します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-116">Making the Insertion Point Visible by Default</span></span>  
 <span data-ttu-id="8dca4-117"><xref:System.Windows.Forms.TextBox>挿入ポイントが新しいフォームのみ場合に既定で表示される、<xref:System.Windows.Forms.TextBox>コントロールがタブ オーダーの先頭にします。</span><span class="sxs-lookup"><span data-stu-id="8dca4-117">The <xref:System.Windows.Forms.TextBox> insertion point is visible by default in a new form only if the <xref:System.Windows.Forms.TextBox> control is first in the tab order.</span></span> <span data-ttu-id="8dca4-118">提供する場合にのみ、カーソルがそれ以外の場合、表示、<xref:System.Windows.Forms.TextBox>キーボードまたはマウスのいずれかにフォーカスします。</span><span class="sxs-lookup"><span data-stu-id="8dca4-118">Otherwise, the insertion point appears only if you give the <xref:System.Windows.Forms.TextBox> the focus with either the keyboard or the mouse.</span></span>  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a><span data-ttu-id="8dca4-119">既定では新しいフォームにテキスト ボックスのカーソル位置を表示する</span><span class="sxs-lookup"><span data-stu-id="8dca4-119">To make the text box insertion point visible by default on a new form</span></span>  
  
- <span data-ttu-id="8dca4-120">設定、<xref:System.Windows.Forms.TextBox>コントロールの<xref:System.Windows.Forms.Control.TabIndex%2A>プロパティを`0`します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-120">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.Control.TabIndex%2A> property to `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dca4-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8dca4-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="8dca4-122">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="8dca4-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="8dca4-123">方法: Windows フォーム TextBox コントロールでパスワード テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="8dca4-124">方法: 読み取り専用テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="8dca4-125">方法: 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-125">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="8dca4-126">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-126">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="8dca4-127">方法: Windows フォームの TextBox コントロールで複数の行を表示します。</span><span class="sxs-lookup"><span data-stu-id="8dca4-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="8dca4-128">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="8dca4-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
