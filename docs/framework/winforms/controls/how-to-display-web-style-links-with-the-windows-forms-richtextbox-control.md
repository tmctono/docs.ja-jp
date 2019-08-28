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
ms.openlocfilehash: ce71981f7b233d3e168689c766128646eed3e981
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046186"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="2a4f0-102">方法: Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する</span><span class="sxs-lookup"><span data-stu-id="2a4f0-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="2a4f0-103">Windows フォーム<xref:System.Windows.Forms.RichTextBox>コントロールでは、Web リンクを色分けおよび下線付きで表示できます。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="2a4f0-104">リンクがクリックされたときに、リンクテキストで指定された Web サイトを表示するブラウザーウィンドウを開くコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="2a4f0-105">RichTextBox コントロールを使用して Web ページにリンクするには</span><span class="sxs-lookup"><span data-stu-id="2a4f0-105">To link to a Web page with the RichTextBox control</span></span>

1. <span data-ttu-id="2a4f0-106">プロパティを、有効な URL (たとえば "http://www.microsoft.com/") を含む文字列に設定します。 <xref:System.Windows.Forms.RichTextBox.Text%2A></span><span class="sxs-lookup"><span data-stu-id="2a4f0-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>

2. <span data-ttu-id="2a4f0-107"><xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>プロパティが (既定値) に設定されていることを`true`確認します。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>

3. <span data-ttu-id="2a4f0-108"><xref:System.Diagnostics.Process>オブジェクトの新しいグローバルインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>

4. <span data-ttu-id="2a4f0-109">目的のテキストをブラウザーに<xref:System.Windows.Forms.RichTextBox.LinkClicked>送信するイベントのイベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>

    <span data-ttu-id="2a4f0-110">次の例では、 <xref:System.Windows.Forms.RichTextBox.LinkClicked>イベントによって、Internet Explorer のインスタンスが、 <xref:System.Windows.Forms.RichTextBox>コントロールの<xref:System.Windows.Forms.RichTextBox.Text%2A>プロパティで指定された URL に開かれます。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="2a4f0-111">この例では、フォームに<xref:System.Windows.Forms.RichTextBox>コントロールがあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2a4f0-112">権限が不十分<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>であるために部分信頼<xref:System.Security.SecurityException>コンテキストでコードを実行している場合、メソッドを呼び出すと例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="2a4f0-113">詳しくは、「[コード アクセス セキュリティの基礎](../../misc/code-access-security-basics.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

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

    <span data-ttu-id="2a4f0-114">(ビジュアルC++)プロセス`p`を初期化する必要があります。これを行うには、次のステートメントをフォームのコンストラクターに含めます。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    <span data-ttu-id="2a4f0-115">(ビジュアルC#、ビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

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

    <span data-ttu-id="2a4f0-116">作業が終了したら、作成したプロセスをすぐに停止することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="2a4f0-117">上記のコードを参照すると、プロセスを停止するためのコードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2a4f0-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2a4f0-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a4f0-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="2a4f0-119">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="2a4f0-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="2a4f0-120">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="2a4f0-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
