---
title: '方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: ab5df1233c16a7ce076efa817fb14808b588ebcd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300984"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="a9930-102">方法: Windows フォームの TextBox コントロールを使用してパスワード テキスト ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="a9930-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="a9930-103">パスワード ボックスは、ユーザーが入力文字列中に、プレース ホルダー文字を表示する Windows フォーム テキスト ボックスです。</span><span class="sxs-lookup"><span data-stu-id="a9930-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="a9930-104">パスワード テキスト ボックスを作成するには</span><span class="sxs-lookup"><span data-stu-id="a9930-104">To create a password text box</span></span>  
  
1. <span data-ttu-id="a9930-105">設定、<xref:System.Windows.Forms.TextBox.PasswordChar%2A>のプロパティ、<xref:System.Windows.Forms.TextBox>特定の文字をコントロールします。</span><span class="sxs-lookup"><span data-stu-id="a9930-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="a9930-106"><xref:System.Windows.Forms.TextBox.PasswordChar%2A>プロパティは、テキスト ボックスに表示される文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9930-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="a9930-107">たとえば、アスタリスクをパスワード ボックスに表示する場合は、指定 \* の<xref:System.Windows.Forms.TextBox.PasswordChar%2A>プロパティ ウィンドウでプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9930-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="a9930-108">次に、どのような文字は、ユーザーがテキスト ボックスに関係なく、アスタリスクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9930-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2. <span data-ttu-id="a9930-109">(省略可能)設定、<xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9930-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="a9930-110">プロパティは、テキスト ボックスに入力できる文字数を決定します。</span><span class="sxs-lookup"><span data-stu-id="a9930-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="a9930-111">最大長を超過した場合は、ビープ音が鳴ります、テキスト ボックスは、多くの文字を受け付けません。</span><span class="sxs-lookup"><span data-stu-id="a9930-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="a9930-112">使用すると、パスワードを推測しようとしているハッカーのパスワードの最大長としてしない可能性がありますので注意があります。</span><span class="sxs-lookup"><span data-stu-id="a9930-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="a9930-113">次のコード例では、最大で 14 文字の文字列をそのまま使用され、文字列の代わりにアスタリスクが表示されるテキスト ボックスを初期化する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a9930-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="a9930-114">`InitializeMyControl`プロシージャが自動的に実行されません。 呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9930-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a9930-115">使用して、<xref:System.Windows.Forms.TextBox.PasswordChar%2A>プロパティ テキスト ボックスには、その他のユーザーは、入力ユーザーを確認する場合は、ユーザーのパスワードを決定できませんを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a9930-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="a9930-116">このセキュリティ対策では、あらゆる種類のストレージや、アプリケーション ロジックが原因で発生する可能性があるパスワードの送信は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a9930-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="a9930-117">入力したテキストが何らかの方法で暗号化されていないので、他の機密データを同じように扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9930-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="a9930-118">として表示されない場合でも、パスワードはされているとして扱われますプレーン テキスト文字列 (いくつか追加のセキュリティ対策を実装している) 場合を除き、します。</span><span class="sxs-lookup"><span data-stu-id="a9930-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a9930-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9930-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="a9930-120">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a9930-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="a9930-121">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御します。</span><span class="sxs-lookup"><span data-stu-id="a9930-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="a9930-122">方法: 読み取り専用テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9930-122">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="a9930-123">方法: 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="a9930-123">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="a9930-124">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="a9930-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a9930-125">方法: Windows フォームの TextBox コントロールで複数の行を表示します。</span><span class="sxs-lookup"><span data-stu-id="a9930-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="a9930-126">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="a9930-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
