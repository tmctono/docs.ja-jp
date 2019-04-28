---
title: TextBox コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932549"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="c3ba8-102">TextBox コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="c3ba8-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="c3ba8-103">Windows フォームのテキスト ボックスは、ユーザーからの入力を取得する、またはテキストを表示するに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="c3ba8-104"><xref:System.Windows.Forms.TextBox>コントロールもできる読み取り専用ですが、通常、編集可能なテキストに使用します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="c3ba8-105">テキスト ボックスでは、複数の行を表示、テキスト、コントロールのサイズをラップ、および基本的な書式設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="c3ba8-106"><xref:System.Windows.Forms.TextBox>コントロールは、コントロールに表示または入力テキストを単一の書式スタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="c3ba8-107">複数の種類の書式設定されたテキストを表示するには、使用、<xref:System.Windows.Forms.RichTextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="c3ba8-108">詳細については、次を参照してください。 [RichTextBox コントロールの概要](richtextbox-control-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="c3ba8-109">TextBox コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="c3ba8-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="c3ba8-110">コントロールによって表示されるテキストが含まれている、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="c3ba8-111">既定では、テキスト ボックス内の 2048 文字まで入力できます。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="c3ba8-112">設定した場合、<xref:System.Windows.Forms.TextBox.Multiline%2A>プロパティを`true`、最大 32 KB のテキストを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="c3ba8-113"><xref:System.Windows.Forms.TextBox.Text%2A>実行時またはユーザー入力によってコードでは、実行時に [プロパティ] ウィンドウで、デザイン時にプロパティを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="c3ba8-114">テキスト ボックスの現在の内容は、読み取ることによって実行時に取得できます、<xref:System.Windows.Forms.TextBox.Text%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="c3ba8-115">次のコード例では、実行時にコントロールのテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="c3ba8-116">`InitializeMyControl`プロシージャが自動的に実行されません。 呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3ba8-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3ba8-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="c3ba8-118">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="c3ba8-119">方法: Windows フォーム TextBox コントロールでパスワード テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c3ba8-120">方法: 読み取り専用テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="c3ba8-121">方法: 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="c3ba8-122">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c3ba8-123">方法: Windows フォームの TextBox コントロールで複数の行を表示します。</span><span class="sxs-lookup"><span data-stu-id="c3ba8-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="c3ba8-124">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="c3ba8-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
