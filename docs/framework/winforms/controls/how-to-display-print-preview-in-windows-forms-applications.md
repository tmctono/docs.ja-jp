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
ms.openlocfilehash: cfdc8d21b3ddad19fd38eef9cb1c506920da9de6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609883"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="d8e97-102">方法: Windows フォーム アプリケーションに印刷プレビューを表示する</span><span class="sxs-lookup"><span data-stu-id="d8e97-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="d8e97-103">使用することができます、<xref:System.Windows.Forms.PrintPreviewDialog>印刷する前に多くの場合、ドキュメントを表示するユーザーを有効にするコントロール。</span><span class="sxs-lookup"><span data-stu-id="d8e97-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="d8e97-104">これを行うには、インスタンスを指定する必要があります、<xref:System.Drawing.Printing.PrintDocument>クラスです。 これは、印刷するドキュメント。</span><span class="sxs-lookup"><span data-stu-id="d8e97-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="d8e97-105">印刷プレビューでの使用の詳細については、<xref:System.Drawing.Printing.PrintDocument>コンポーネントを参照してください[方法。印刷プレビューを使用して Windows フォームにおける印刷](../advanced/how-to-print-in-windows-forms-using-print-preview.md)します。</span><span class="sxs-lookup"><span data-stu-id="d8e97-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8e97-106">使用する、<xref:System.Windows.Forms.PrintPreviewDialog>コントロール、実行時にユーザーが必要ローカルまたはネットワークを介してコンピューターにインストールされているプリンターは部分的方法、<xref:System.Windows.Forms.PrintPreviewDialog>コンポーネントは、印刷時にドキュメントがどのように表示されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d8e97-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="d8e97-107"><xref:System.Windows.Forms.PrintPreviewDialog>コントロール、<xref:System.Drawing.Printing.PrinterSettings>クラス。</span><span class="sxs-lookup"><span data-stu-id="d8e97-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="d8e97-108">さらに、<xref:System.Windows.Forms.PrintPreviewDialog>コントロール、<xref:System.Drawing.Printing.PageSettings>クラスと同様、<xref:System.Windows.Forms.PrintPreviewDialog>はコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="d8e97-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="d8e97-109">指定された印刷ドキュメント、<xref:System.Windows.Forms.PrintPreviewDialog>コントロールの<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>プロパティが両方のインスタンスを指す、<xref:System.Drawing.Printing.PrinterSettings>と<xref:System.Drawing.Printing.PageSettings>クラス、およびこれらがプレビュー ウィンドウにドキュメントを表示するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d8e97-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="d8e97-110">PrintPreviewDialog コントロールを使用してページを表示するには</span><span class="sxs-lookup"><span data-stu-id="d8e97-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="d8e97-111"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用してダイアログ ボックスを表示し、使用する <xref:System.Drawing.Printing.PrintDocument> を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8e97-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="d8e97-112">次のコード例で、<xref:System.Windows.Forms.Button>コントロールの<xref:System.Windows.Forms.Control.Click>イベント ハンドラーのインスタンスを開き、<xref:System.Windows.Forms.PrintPreviewDialog>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d8e97-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="d8e97-113">印刷ドキュメントがで指定された、<xref:System.Windows.Forms.PrintDialog.Document%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d8e97-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="d8e97-114">次の例では、印刷ドキュメントは指定されません。</span><span class="sxs-lookup"><span data-stu-id="d8e97-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="d8e97-115">この例で、フォームに、<xref:System.Windows.Forms.Button>コントロール、<xref:System.Drawing.Printing.PrintDocument>という名前のコンポーネント`myDocument`と<xref:System.Windows.Forms.PrintPreviewDialog>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d8e97-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="d8e97-116">(Visual c#、 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="d8e97-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8e97-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8e97-117">See also</span></span>

- [<span data-ttu-id="d8e97-118">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8e97-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="d8e97-119">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="d8e97-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="d8e97-120">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="d8e97-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="d8e97-121">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="d8e97-121">Windows Forms</span></span>](../index.md)
