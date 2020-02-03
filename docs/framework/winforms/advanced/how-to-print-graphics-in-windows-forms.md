---
title: '方法: グラフィックスを印刷する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740648"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="9bd34-102">方法 : Windows フォームでグラフィックスを印刷する</span><span class="sxs-lookup"><span data-stu-id="9bd34-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="9bd34-103">多くの場合、Windows ベースのアプリケーションでグラフィックスを印刷する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bd34-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="9bd34-104"><xref:System.Drawing.Graphics> クラスには、画面やプリンターなどのデバイスにオブジェクトを描画するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9bd34-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="9bd34-105">グラフィックスを印刷するには</span><span class="sxs-lookup"><span data-stu-id="9bd34-105">To print graphics</span></span>  
  
1. <span data-ttu-id="9bd34-106">フォームに <xref:System.Drawing.Printing.PrintDocument> コンポーネントを追加します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="9bd34-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> イベントハンドラーで、<xref:System.Drawing.Printing.PrintPageEventArgs> クラスの <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> プロパティを使用して、印刷するグラフィックスの種類をプリンターに指示します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="9bd34-108">次のコード例は、外接する四角形内に青い楕円を作成するために使用されるイベントハンドラーを示しています。</span><span class="sxs-lookup"><span data-stu-id="9bd34-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="9bd34-109">四角形の位置と次元は次のとおりです: 100, 150 から、幅250と高さ250。</span><span class="sxs-lookup"><span data-stu-id="9bd34-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="9bd34-110">(ビジュアルC#とビジュアルC++)フォームのコンストラクターに次のコードを配置して、イベントハンドラーを登録します。</span><span class="sxs-lookup"><span data-stu-id="9bd34-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9bd34-111">参照</span><span class="sxs-lookup"><span data-stu-id="9bd34-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="9bd34-112">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="9bd34-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
