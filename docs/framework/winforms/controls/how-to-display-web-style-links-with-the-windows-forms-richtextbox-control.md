---
title: '方法: Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 05d9ad4766584b59cca7c31f49b737d4696a9921
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053539"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="302cb-102">方法: Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する</span><span class="sxs-lookup"><span data-stu-id="302cb-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="302cb-103">Windows フォーム<xref:System.Windows.Forms.RichTextBox>コントロールは、カラーや下線が引かれたとしての Web リンクを表示できます。</span><span class="sxs-lookup"><span data-stu-id="302cb-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="302cb-104">リンクがクリックされたときに、リンク テキストに指定された Web サイトを表示するブラウザー ウィンドウを開いてコードを記述することができます。</span><span class="sxs-lookup"><span data-stu-id="302cb-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="302cb-105">RichTextBox コントロールでの Web ページにリンクするには</span><span class="sxs-lookup"><span data-stu-id="302cb-105">To link to a Web page with the RichTextBox control</span></span>  
  
1. <span data-ttu-id="302cb-106">設定、<xref:System.Windows.Forms.RichTextBox.Text%2A>プロパティを有効な URL を含む文字列に (たとえば、"http://www.microsoft.com/")。</span><span class="sxs-lookup"><span data-stu-id="302cb-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2. <span data-ttu-id="302cb-107">必ず、<xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>プロパティに設定されて`true`(既定)。</span><span class="sxs-lookup"><span data-stu-id="302cb-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3. <span data-ttu-id="302cb-108">場合は、新しいグローバル インスタンスを作成、<xref:System.Diagnostics.Process>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="302cb-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4. <span data-ttu-id="302cb-109">イベント ハンドラーを記述、<xref:System.Windows.Forms.RichTextBox.LinkClicked>目的のテキストをブラウザーに送信するイベントです。</span><span class="sxs-lookup"><span data-stu-id="302cb-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="302cb-110">次の例で、<xref:System.Windows.Forms.RichTextBox.LinkClicked>イベントで指定された URL を Internet Explorer のインスタンスを開き、<xref:System.Windows.Forms.RichTextBox.Text%2A>のプロパティ、<xref:System.Windows.Forms.RichTextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="302cb-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="302cb-111">この例では使用して、フォーム、<xref:System.Windows.Forms.RichTextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="302cb-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="302cb-112">呼び出し元に、<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>が発生、メソッド、<xref:System.Security.SecurityException>特権がないため、部分的に信頼されたコンテキストでコードを実行している場合は例外です。</span><span class="sxs-lookup"><span data-stu-id="302cb-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="302cb-113">詳しくは、「[コード アクセス セキュリティの基礎](../../misc/code-access-security-basics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="302cb-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>  
  
    ```vb  
    Public p As New System.Diagnostics.Process  
    Private Sub RichTextBox1_LinkClicked _  
       (ByVal sender As Object, ByVal e As _  
       System.Windows.Forms.LinkClickedEventArgs) _  
       Handles RichTextBox1.LinkClicked  
          ' Call Process.Start method to open a browser  
          ' with link text as URL.  
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)  
    End Sub  
    ```  
  
    ```csharp  
    public System.Diagnostics.Process p = new System.Diagnostics.Process();  
  
    private void richTextBox1_LinkClicked(object sender,   
    System.Windows.Forms.LinkClickedEventArgs e)  
    {  
       // Call Process.Start method to open a browser  
       // with link text as URL.  
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);  
    }  
    ```  
  
    ```cpp  
    public:  
       System::Diagnostics::Process ^ p;  
  
    private:  
       void richTextBox1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkClickedEventArgs ^  e)  
       {  
          // Call Process.Start method to open a browser  
          // with link text as URL.  
          p = System::Diagnostics::Process::Start("IExplore.exe",  
             e->LinkText);  
       }  
    ```  
  
     <span data-ttu-id="302cb-114">(Visual C++)プロセスを初期化する必要があります`p`フォームのコンス トラクターに次のステートメントを含めることで実行できます。</span><span class="sxs-lookup"><span data-stu-id="302cb-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="302cb-115">(Visual C#、Visual C)イベント ハンドラーを登録するフォームのコンス トラクターでは、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="302cb-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.LinkClicked += new   
       System.Windows.Forms.LinkClickedEventHandler  
       (this.richTextBox1_LinkClicked);  
    ```  
  
    ```cpp  
    this->richTextBox1->LinkClicked += gcnew  
       System::Windows::Forms::LinkClickedEventHandler  
       (this, &Form1::richTextBox1_LinkClicked);  
    ```  
  
     <span data-ttu-id="302cb-116">作業が完了したら作成したプロセスをすぐに停止するのには重要です。</span><span class="sxs-lookup"><span data-stu-id="302cb-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="302cb-117">上に示したコードを指すようこのプロセスを停止するコードになります。</span><span class="sxs-lookup"><span data-stu-id="302cb-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
    ```vb  
    Public Sub StopWebProcess()  
       p.Kill()  
    End Sub  
    ```  
  
    ```csharp  
    public void StopWebProcess()  
    {  
       p.Kill();  
    }  
    ```  
  
    ```cpp  
    public: void StopWebProcess()  
    {  
       p->Kill();  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="302cb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="302cb-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="302cb-119">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="302cb-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="302cb-120">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="302cb-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
