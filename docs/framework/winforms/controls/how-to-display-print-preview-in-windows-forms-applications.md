---
title: '方法: Windows フォーム アプリケーションに印刷プレビューを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929007"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="b58d1-102">方法: Windows フォーム アプリケーションに印刷プレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="b58d1-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="b58d1-103"><xref:System.Windows.Forms.PrintPreviewDialog>コントロールを使用すると、ユーザーがドキュメントを印刷する前に頻繁に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b58d1-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="b58d1-104">これを行うには、 <xref:System.Drawing.Printing.PrintDocument>クラスのインスタンスを指定する必要があります。これは、印刷するドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="b58d1-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="b58d1-105"><xref:System.Drawing.Printing.PrintDocument>コンポーネントで印刷プレビューを使用する方法の詳細につい[ては、「」を参照してください。印刷プレビュー](../advanced/how-to-print-in-windows-forms-using-print-preview.md)を使用して Windows フォームに印刷します。</span><span class="sxs-lookup"><span data-stu-id="b58d1-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b58d1-106">実行時に<xref:System.Windows.Forms.PrintPreviewDialog>コントロールを使用するには、ローカルまたはネットワーク経由でコンピューターにプリンターがインストールされている必要があります。これ<xref:System.Windows.Forms.PrintPreviewDialog>は、印刷時のドキュメントの外観をコンポーネントが決定する方法の一部であるためです。</span><span class="sxs-lookup"><span data-stu-id="b58d1-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="b58d1-107">コントロール<xref:System.Windows.Forms.PrintPreviewDialog>はクラスを<xref:System.Drawing.Printing.PrinterSettings>使用します。</span><span class="sxs-lookup"><span data-stu-id="b58d1-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="b58d1-108">さらに、 <xref:System.Windows.Forms.PrintPreviewDialog> <xref:System.Windows.Forms.PrintPreviewDialog>コンポーネントと同じ<xref:System.Drawing.Printing.PageSettings>ように、コントロールはクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="b58d1-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="b58d1-109"><xref:System.Windows.Forms.PrintPreviewDialog>コントロールの<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>プロパティで指定された印刷ドキュメントは、クラス<xref:System.Drawing.Printing.PrinterSettings>と<xref:System.Drawing.Printing.PageSettings>クラスの両方のインスタンスを参照します。これらは、ドキュメントをプレビューウィンドウに表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b58d1-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="b58d1-110">Printプレビューダイアログコントロールを使用してページを表示するには</span><span class="sxs-lookup"><span data-stu-id="b58d1-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="b58d1-111"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用してダイアログ ボックスを表示し、使用する <xref:System.Drawing.Printing.PrintDocument> を指定します。</span><span class="sxs-lookup"><span data-stu-id="b58d1-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="b58d1-112">次のコード例では、 <xref:System.Windows.Forms.Button> <xref:System.Windows.Forms.Control.Click>コントロールのイベントハンドラーが<xref:System.Windows.Forms.PrintPreviewDialog>コントロールのインスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="b58d1-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="b58d1-113">印刷ドキュメントは<xref:System.Windows.Forms.PrintDialog.Document%2A>プロパティで指定されます。</span><span class="sxs-lookup"><span data-stu-id="b58d1-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="b58d1-114">次の例では、印刷ドキュメントが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="b58d1-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="b58d1-115">この例では、フォーム<xref:System.Windows.Forms.Button>にコントロール<xref:System.Drawing.Printing.PrintDocument> 、という名前`myDocument`の<xref:System.Windows.Forms.PrintPreviewDialog>コンポーネント、およびコントロールが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b58d1-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="b58d1-116">(ビジュアルC#、ビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="b58d1-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b58d1-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b58d1-117">See also</span></span>

- [<span data-ttu-id="b58d1-118">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b58d1-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="b58d1-119">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="b58d1-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="b58d1-120">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="b58d1-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="b58d1-121">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="b58d1-121">Windows Forms</span></span>](../index.md)
