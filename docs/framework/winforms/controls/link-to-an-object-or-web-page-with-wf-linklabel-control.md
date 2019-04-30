---
title: '方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: edebfaee6f0da6826f4b757568408662f3208d41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012863"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="dbd5d-102">方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする</span><span class="sxs-lookup"><span data-stu-id="dbd5d-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="dbd5d-103">Windows フォーム<xref:System.Windows.Forms.LinkLabel>コントロールをフォーム上で Web スタイルのリンクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="dbd5d-104">リンクがクリックされたときに、リンクにアクセスしたかを示す色を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="dbd5d-105">色の変更の詳細については、次を参照してください。[方法。Windows フォーム LinkLabel コントロールの外観を変更する](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>  
  
## <a name="linking-to-another-form"></a><span data-ttu-id="dbd5d-106">別のフォームへのリンク</span><span class="sxs-lookup"><span data-stu-id="dbd5d-106">Linking to Another Form</span></span>  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="dbd5d-107">LinkLabel コントロールで別のフォームにリンクするには</span><span class="sxs-lookup"><span data-stu-id="dbd5d-107">To link to another form with a LinkLabel control</span></span>  
  
1. <span data-ttu-id="dbd5d-108">設定、<xref:System.Windows.Forms.LinkLabel.Text%2A>プロパティに適切なキャプション。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2. <span data-ttu-id="dbd5d-109">設定、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティのキャプションのどの部分がリンクとして示されます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="dbd5d-110">示される方法は、リンク ラベルの外観に関連するプロパティに依存します。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="dbd5d-111"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>によって表される値、 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 2 つの数値、文字の開始位置および文字の数を含むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="dbd5d-112"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティ ウィンドウで、または、次のような方法でのコードでプロパティを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3. <span data-ttu-id="dbd5d-113"><xref:System.Windows.Forms.LinkLabel.LinkClicked>イベント ハンドラーを呼び出す、<xref:System.Windows.Forms.Form.Show%2A>プロジェクトで、別のフォームを開き、設定する方法、<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dbd5d-114">インスタンス、<xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs>クラスへの参照を実行する、<xref:System.Windows.Forms.LinkLabel>にキャストする必要はありませんが、クリックしてされたコントロール、`sender`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a><span data-ttu-id="dbd5d-115">Web ページへのリンク</span><span class="sxs-lookup"><span data-stu-id="dbd5d-115">Linking to a Web Page</span></span>  
 <span data-ttu-id="dbd5d-116"><xref:System.Windows.Forms.LinkLabel>コントロールが既定のブラウザーで Web ページを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="dbd5d-117">LinkLabel コントロールで Internet Explorer と Web ページへのリンクを開始するには</span><span class="sxs-lookup"><span data-stu-id="dbd5d-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>  
  
1. <span data-ttu-id="dbd5d-118">設定、<xref:System.Windows.Forms.LinkLabel.Text%2A>プロパティに適切なキャプション。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2. <span data-ttu-id="dbd5d-119">設定、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティのキャプションのどの部分がリンクとして示されます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
3. <span data-ttu-id="dbd5d-120"><xref:System.Windows.Forms.LinkLabel.LinkClicked>例外処理ブロックでは、途中のイベント ハンドラーを設定する 2 番目のプロシージャを呼び出す、<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>プロパティを`true`を使用して、 <xref:System.Diagnostics.Process.Start%2A> URL を使用して、既定のブラウザーを開始する方法。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="dbd5d-121">使用する、<xref:System.Diagnostics.Process.Start%2A>メソッドへの参照を追加する必要がある、<xref:System.Diagnostics?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="dbd5d-122">部分信頼環境で次のコードを実行するかどうか (など、共有ドライブ上)、JIT コンパイラが失敗したときに、`VisitLink`メソッドが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="dbd5d-123">`System.Diagnostics.Process.Start`ステートメントが失敗した、リンク確認要求があるとします。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="dbd5d-124">例外をキャッチするときに、`VisitLink`メソッドが呼び出されると、次のコードにより、JIT コンパイラに失敗した場合、エラー適切に処理されます。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dbd5d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbd5d-125">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="dbd5d-126">LinkLabel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="dbd5d-126">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="dbd5d-127">方法: Windows フォーム LinkLabel コントロールの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="dbd5d-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="dbd5d-128">LinkLabel コントロール</span><span class="sxs-lookup"><span data-stu-id="dbd5d-128">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
