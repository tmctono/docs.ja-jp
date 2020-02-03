---
title: '方法: ユーザーのコンピューターに接続されているプリンターを選択する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 7fc2427468540ac0a1480f6140cbb34c3a0f1ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746511"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a><span data-ttu-id="d754a-102">方法 : Windows フォームでユーザーのコンピューターに接続されたプリンターを選択する</span><span class="sxs-lookup"><span data-stu-id="d754a-102">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>
<span data-ttu-id="d754a-103">既定のプリンター以外のプリンターに印刷することがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d754a-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="d754a-104"><xref:System.Windows.Forms.PrintDialog> コンポーネントを使用すると、現在インストールされているプリンターからユーザーに選択させることができます。</span><span class="sxs-lookup"><span data-stu-id="d754a-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="d754a-105"><xref:System.Windows.Forms.PrintDialog> コンポーネントでは、 <xref:System.Windows.Forms.DialogResult> コンポーネントの <xref:System.Windows.Forms.PrintDialog> がキャプチャされ、プリンターの選択に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d754a-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="d754a-106">次の手順では、既定のプリンターに印刷するテキスト ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d754a-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="d754a-107"><xref:System.Windows.Forms.PrintDialog> クラスがインスタンス化されます。</span><span class="sxs-lookup"><span data-stu-id="d754a-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="d754a-108">プリンターを選択してファイルを印刷するには</span><span class="sxs-lookup"><span data-stu-id="d754a-108">To choose a printer and then print a file</span></span>  
  
1. <span data-ttu-id="d754a-109"><xref:System.Windows.Forms.PrintDialog> コンポーネントを使用して、使用するプリンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="d754a-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="d754a-110">次のコード例では、2 つのイベントを処理しています。</span><span class="sxs-lookup"><span data-stu-id="d754a-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="d754a-111">最初の <xref:System.Windows.Forms.Button> コントロールの <xref:System.Windows.Forms.Control.Click> イベントでは、<xref:System.Windows.Forms.PrintDialog> クラスがインスタンス化され、ユーザーが選択したプリンターが <xref:System.Windows.Forms.DialogResult> プロパティにキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="d754a-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="d754a-112">2番目のイベントでは、<xref:System.Drawing.Printing.PrintDocument> コンポーネントの <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントで、指定されたプリンターにサンプルドキュメントが出力されます。</span><span class="sxs-lookup"><span data-stu-id="d754a-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="d754a-113">(ビジュアルC#とビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="d754a-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d754a-114">参照</span><span class="sxs-lookup"><span data-stu-id="d754a-114">See also</span></span>

- [<span data-ttu-id="d754a-115">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="d754a-115">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
