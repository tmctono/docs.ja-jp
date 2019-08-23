---
title: '方法: 標準の Windows フォーム印刷ジョブを作成する'
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
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938242"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="78637-102">方法: 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="78637-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="78637-103">Windows フォームでの印刷の基礎は、 <xref:System.Drawing.Printing.PrintDocument>特<xref:System.Drawing.Printing.PrintDocument.PrintPage>にイベントであるコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="78637-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="78637-104"><xref:System.Drawing.Printing.PrintDocument.PrintPage>イベントを処理するコードを記述することによって、印刷する内容と印刷方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="78637-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="78637-105">印刷ジョブを作成するには</span><span class="sxs-lookup"><span data-stu-id="78637-105">To create a print job</span></span>  
  
1. <span data-ttu-id="78637-106">コンポーネントを<xref:System.Drawing.Printing.PrintDocument>フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="78637-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="78637-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="78637-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="78637-108">独自の印刷ロジックをコーディングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78637-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="78637-109">また、印刷する素材を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78637-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="78637-110">次のコード例では、赤い四角形の形状のサンプルグラフィックが<xref:System.Drawing.Printing.PrintDocument.PrintPage>イベントハンドラーに作成され、印刷される素材として機能します。</span><span class="sxs-lookup"><span data-stu-id="78637-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="78637-111">(ビジュアルC#とビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="78637-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="78637-112">また、イベント<xref:System.Drawing.Printing.PrintDocument.BeginPrint>および<xref:System.Drawing.Printing.PrintDocument.EndPrint>イベントのコードを記述することもできます。たとえば、印刷するページの総数を表す整数を含め、各ページが印刷するたびにデクリメントします。</span><span class="sxs-lookup"><span data-stu-id="78637-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="78637-113">フォームにコンポーネントを<xref:System.Windows.Forms.PrintDialog>追加して、ユーザーに対してクリーンで効率的なユーザーインターフェイス (UI) を提供できます。</span><span class="sxs-lookup"><span data-stu-id="78637-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="78637-114">コンポーネントのプロパティを設定すると、フォーム上で作業している印刷ドキュメントに関連するプロパティを設定できます。 <xref:System.Windows.Forms.PrintDialog.Document%2A> <xref:System.Windows.Forms.PrintDialog></span><span class="sxs-lookup"><span data-stu-id="78637-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="78637-115">コンポーネントの<xref:System.Windows.Forms.PrintDialog>詳細については、「 [PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78637-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="78637-116">プログラムで印刷ジョブを作成する方法など、Windows フォーム印刷ジョブの詳細については、「 <xref:System.Drawing.Printing.PrintPageEventArgs>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78637-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78637-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="78637-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="78637-118">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="78637-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
