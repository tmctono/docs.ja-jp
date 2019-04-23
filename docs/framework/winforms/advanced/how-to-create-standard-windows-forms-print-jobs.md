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
ms.openlocfilehash: 816da93218e20f73f16c14769ed1a549dd3d8eb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335408"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="1fbd9-102">方法: 標準の Windows フォーム印刷ジョブを作成する</span><span class="sxs-lookup"><span data-stu-id="1fbd9-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="1fbd9-103">Windows フォームにおける印刷の基盤は、<xref:System.Drawing.Printing.PrintDocument>コンポーネント、具体的には、<xref:System.Drawing.Printing.PrintDocument.PrintPage>イベント。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="1fbd9-104">処理するコードを記述することで、<xref:System.Drawing.Printing.PrintDocument.PrintPage>イベント、印刷と印刷方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="1fbd9-105">印刷ジョブを作成するには</span><span class="sxs-lookup"><span data-stu-id="1fbd9-105">To create a print job</span></span>  
  
1. <span data-ttu-id="1fbd9-106">追加、<xref:System.Drawing.Printing.PrintDocument>コンポーネントをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="1fbd9-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="1fbd9-108">独自の印刷ロジックをコーディングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="1fbd9-109">さらに、印刷する対象を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="1fbd9-110">次のコード例で赤い四角形内にサンプル グラフィックを作成、<xref:System.Drawing.Printing.PrintDocument.PrintPage>印刷対象として機能するイベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="1fbd9-111">(Visual C# と[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、イベント ハンドラーを登録するフォームのコンス トラクターで、次のコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="1fbd9-112">コードを記述することも、<xref:System.Drawing.Printing.PrintDocument.BeginPrint>と<xref:System.Drawing.Printing.PrintDocument.EndPrint>などページの総数を表す印刷を整数デクリメントされる各ページの印刷イベント。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1fbd9-113">追加することができます、<xref:System.Windows.Forms.PrintDialog>コンポーネントをフォームをユーザーに、クリーンで効率的なユーザー インターフェイス (UI) を提供します。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="1fbd9-114">設定、<xref:System.Windows.Forms.PrintDialog.Document%2A>のプロパティ、<xref:System.Windows.Forms.PrintDialog>コンポーネント有効にするドキュメントの印刷に関連するプロパティを設定することがフォーム上で使用します。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="1fbd9-115">詳細については、<xref:System.Windows.Forms.PrintDialog>コンポーネントを参照してください[PrintDialog コンポーネント](../controls/printdialog-component-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="1fbd9-116">Windows フォームの詳細詳細については、プログラムで印刷ジョブを作成する方法など、印刷ジョブを参照してください<xref:System.Drawing.Printing.PrintPageEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="1fbd9-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbd9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fbd9-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="1fbd9-118">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="1fbd9-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
