---
title: '方法: (Windows フォーム) 文字列に引用符を挿入します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 0148f9fde9d69bb1605776f1ab617079be96b59e
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053466"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="d9e97-102">方法: (Windows フォーム) 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="d9e97-103">テキストの文字列に引用符 (" ") を挿入することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9e97-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="d9e97-104">例:</span><span class="sxs-lookup"><span data-stu-id="d9e97-104">For example:</span></span>  
  
 <span data-ttu-id="d9e97-105">わかりました、「を扱う優れた!」</span><span class="sxs-lookup"><span data-stu-id="d9e97-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="d9e97-106">代わりに、使用することも、<xref:Microsoft.VisualBasic.ControlChars.Quote>定数としてフィールド。</span><span class="sxs-lookup"><span data-stu-id="d9e97-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="d9e97-107">コードの文字列に引用符を挿入するには</span><span class="sxs-lookup"><span data-stu-id="d9e97-107">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="d9e97-108">Visual basic を埋め込み引用符として行の 2 つの引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="d9e97-109">ビジュアルでC#とビジュアルC++、エスケープ シーケンスを挿入\\"を埋め込み引用符として。</span><span class="sxs-lookup"><span data-stu-id="d9e97-109">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="d9e97-110">たとえば、上記の文字列を作成するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-110">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="d9e97-111">- または -</span><span class="sxs-lookup"><span data-stu-id="d9e97-111">-or-</span></span>  
  
2. <span data-ttu-id="d9e97-112">引用符を表す ASCII 文字または Unicode 文字を挿入します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="d9e97-113">Visual basic では、ASCII 文字 (34) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="d9e97-114">ビジュアルでC#、Unicode 文字 (\u0022) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="d9e97-115">この例では、基本文字セットの文字を指定するユニバーサル文字名を使用できないため、\u0022 を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9e97-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="d9e97-116">使用した場合、C3851 が発生します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="d9e97-117">詳細については、「[コンパイラ エラー C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9e97-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="d9e97-118">- または -</span><span class="sxs-lookup"><span data-stu-id="d9e97-118">-or-</span></span>  
  
3. <span data-ttu-id="d9e97-119">文字の定数を定義し、必要に応じてその定数を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9e97-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d9e97-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9e97-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="d9e97-121">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="d9e97-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="d9e97-122">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="d9e97-123">方法: Windows フォーム TextBox コントロールでパスワード テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d9e97-124">方法: 読み取り専用テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="d9e97-125">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d9e97-126">方法: Windows フォームの TextBox コントロールで複数の行を表示します。</span><span class="sxs-lookup"><span data-stu-id="d9e97-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="d9e97-127">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="d9e97-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
