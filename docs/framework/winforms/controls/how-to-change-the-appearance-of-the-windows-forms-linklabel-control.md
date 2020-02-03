---
title: LinkLabel コントロールの外観を変更する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746619"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="590b1-102">方法 : Windows フォーム LinkLabel コントロールの表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="590b1-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="590b1-103">さまざまな目的に合わせて、<xref:System.Windows.Forms.LinkLabel> コントロールによって表示されるテキストを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="590b1-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="590b1-104">たとえば、テキストを特定の色に下線付きで表示するように設定することによって、テキストをクリックできることをユーザーに示すのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="590b1-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="590b1-105">ユーザーがテキストをクリックすると、色が別の色に変わります。</span><span class="sxs-lookup"><span data-stu-id="590b1-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="590b1-106">この動作を制御するには、<xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>、<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>、および <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> の各プロパティの5つのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="590b1-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="590b1-107">LinkLabel コントロールの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="590b1-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="590b1-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A> と <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> のプロパティを、必要な色に設定します。</span><span class="sxs-lookup"><span data-stu-id="590b1-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="590b1-109">これは、プログラムによって、または **[プロパティ]** ウィンドウでデザイン時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="590b1-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="590b1-110"><xref:System.Windows.Forms.LinkLabel.Text%2A> プロパティを適切なキャプションに設定します。</span><span class="sxs-lookup"><span data-stu-id="590b1-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="590b1-111">これは、プログラムによって、または **[プロパティ]** ウィンドウでデザイン時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="590b1-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="590b1-112">キャプションのどの部分をリンクとして示すかを決定するには、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="590b1-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="590b1-113"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 値は、2つの数値、開始文字の位置、および文字数を含む <xref:System.Windows.Forms.LinkArea> で表されます。</span><span class="sxs-lookup"><span data-stu-id="590b1-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="590b1-114">これは、プログラムによって、または **[プロパティ]** ウィンドウでデザイン時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="590b1-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="590b1-115"><xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> プロパティを <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>、<xref:System.Windows.Forms.LinkBehavior.HoverUnderline>、または <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>に設定します。</span><span class="sxs-lookup"><span data-stu-id="590b1-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="590b1-116"><xref:System.Windows.Forms.LinkBehavior.HoverUnderline>に設定されている場合、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A> によって決定されるキャプションの部分には、ポインターがその上にあるときにのみ下線が引かれます。</span><span class="sxs-lookup"><span data-stu-id="590b1-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="590b1-117"><xref:System.Windows.Forms.LinkLabel.LinkClicked> イベントハンドラーで、<xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="590b1-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="590b1-118">リンクが参照されている場合は、通常は色によって、何らかの形で表示を変更します。</span><span class="sxs-lookup"><span data-stu-id="590b1-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="590b1-119">テキストは、<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> プロパティによって指定された色に変更されます。</span><span class="sxs-lookup"><span data-stu-id="590b1-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="590b1-120">参照</span><span class="sxs-lookup"><span data-stu-id="590b1-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="590b1-121">LinkLabel コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="590b1-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="590b1-122">方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする</span><span class="sxs-lookup"><span data-stu-id="590b1-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="590b1-123">LinkLabel コントロール</span><span class="sxs-lookup"><span data-stu-id="590b1-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
