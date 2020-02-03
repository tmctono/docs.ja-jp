---
title: 標準の印刷ジョブを作成する
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741521"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="d6514-102">方法 : 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="d6514-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="d6514-103">Windows フォームでの印刷の基礎は、<xref:System.Drawing.Printing.PrintDocument> コンポーネント (具体的には <xref:System.Drawing.Printing.PrintDocument.PrintPage> イベント) です。</span><span class="sxs-lookup"><span data-stu-id="d6514-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="d6514-104"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントを処理するコードを記述することによって、印刷する内容と印刷方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d6514-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="d6514-105">印刷ジョブを作成するには</span><span class="sxs-lookup"><span data-stu-id="d6514-105">To create a print job</span></span>  
  
1. <span data-ttu-id="d6514-106">フォームに <xref:System.Drawing.Printing.PrintDocument> コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6514-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="d6514-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="d6514-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="d6514-108">独自の印刷ロジックをコーディングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6514-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="d6514-109">また、印刷する素材を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6514-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="d6514-110">次のコード例では、<xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントハンドラーに赤い四角形の形状のサンプルグラフィックが作成され、印刷する素材として機能します。</span><span class="sxs-lookup"><span data-stu-id="d6514-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="d6514-111">(ビジュアルC#とビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="d6514-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="d6514-112">また、<xref:System.Drawing.Printing.PrintDocument.BeginPrint> イベントと <xref:System.Drawing.Printing.PrintDocument.EndPrint> イベントのコードを記述することもできます。たとえば、印刷するページの合計数を表す整数を含めて、各ページが印刷するたびにデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="d6514-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d6514-113"><xref:System.Windows.Forms.PrintDialog> コンポーネントをフォームに追加して、ユーザーに対してクリーンで効率的なユーザーインターフェイス (UI) を提供できます。</span><span class="sxs-lookup"><span data-stu-id="d6514-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="d6514-114"><xref:System.Windows.Forms.PrintDialog> コンポーネントの [<xref:System.Windows.Forms.PrintDialog.Document%2A>] プロパティを設定すると、フォーム上で作業している印刷ドキュメントに関連するプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d6514-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="d6514-115"><xref:System.Windows.Forms.PrintDialog> コンポーネントの詳細については、「 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6514-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="d6514-116">プログラムで印刷ジョブを作成する方法など、Windows フォームの印刷ジョブの詳細については、「<xref:System.Drawing.Printing.PrintPageEventArgs>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6514-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6514-117">参照</span><span class="sxs-lookup"><span data-stu-id="d6514-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="d6514-118">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="d6514-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
