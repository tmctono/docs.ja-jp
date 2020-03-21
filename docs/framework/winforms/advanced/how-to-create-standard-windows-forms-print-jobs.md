---
title: 標準印刷ジョブの作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182568"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="f7f38-102">方法 : 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="f7f38-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="f7f38-103">Windows フォームでの印刷の基礎は<xref:System.Drawing.Printing.PrintDocument>、コンポーネント、つまり、イベント<xref:System.Drawing.Printing.PrintDocument.PrintPage>です。</span><span class="sxs-lookup"><span data-stu-id="f7f38-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="f7f38-104">イベントを処理するコードを<xref:System.Drawing.Printing.PrintDocument.PrintPage>記述することにより、印刷する内容と印刷方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7f38-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="f7f38-105">印刷ジョブを作成するには</span><span class="sxs-lookup"><span data-stu-id="f7f38-105">To create a print job</span></span>  
  
1. <span data-ttu-id="f7f38-106">フォームに<xref:System.Drawing.Printing.PrintDocument>コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f7f38-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="f7f38-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="f7f38-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="f7f38-108">独自の印刷ロジックをコーディングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f38-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="f7f38-109">また、印刷する品目を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f38-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="f7f38-110">次のコード例では、赤い四角形の形をしたサンプル グラフィックが<xref:System.Drawing.Printing.PrintDocument.PrintPage>、印刷するマテリアルとして機能するイベント ハンドラーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="f7f38-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="f7f38-111">(ビジュアル C# およびビジュアル C++)フォームのコンストラクターに次のコードを配置して、イベント ハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="f7f38-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="f7f38-112">また、<xref:System.Drawing.Printing.PrintDocument.BeginPrint>イベントと<xref:System.Drawing.Printing.PrintDocument.EndPrint>イベントのコードを記述することもできます 。</span><span class="sxs-lookup"><span data-stu-id="f7f38-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f7f38-113">フォームにコンポーネントを<xref:System.Windows.Forms.PrintDialog>追加すると、ユーザーにクリーンで効率的なユーザー インターフェイス (UI) を提供できます。</span><span class="sxs-lookup"><span data-stu-id="f7f38-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="f7f38-114">コンポーネントの<xref:System.Windows.Forms.PrintDialog.Document%2A>プロパティを<xref:System.Windows.Forms.PrintDialog>設定すると、フォームで作業している印刷ドキュメントに関連するプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f7f38-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="f7f38-115">コンポーネントの<xref:System.Windows.Forms.PrintDialog>詳細については、「 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f38-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="f7f38-116">Windows フォーム印刷ジョブの詳細 (プログラムによる印刷ジョブの作成方法など) の詳細については、「 <xref:System.Drawing.Printing.PrintPageEventArgs>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7f38-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f38-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7f38-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="f7f38-118">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="f7f38-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
