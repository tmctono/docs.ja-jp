---
title: '方法: Windows フォームの RichTextBox コントロールにスクロール バーを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 152706cee511e4bca1dd324a652e8077b1f8548a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312658"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="a272c-102">方法: Windows フォームの RichTextBox コントロールにスクロール バーを表示する</span><span class="sxs-lookup"><span data-stu-id="a272c-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="a272c-103">既定では、Windows フォームで<xref:System.Windows.Forms.RichTextBox>コントロールは、必要に応じて、垂直および水平スクロール バーを表示します。</span><span class="sxs-lookup"><span data-stu-id="a272c-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="a272c-104">7 つの可能な値がある、<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>のプロパティ、<xref:System.Windows.Forms.RichTextBox>コントロールは、次の表で説明されています。</span><span class="sxs-lookup"><span data-stu-id="a272c-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="a272c-105">RichTextBox コントロールにスクロール バーを表示するには</span><span class="sxs-lookup"><span data-stu-id="a272c-105">To display scroll bars in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="a272c-106"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a272c-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="a272c-107">場合、水平スクロール バーなどの型は表示されません、<xref:System.Windows.Forms.RichTextBox.Multiline%2A>プロパティに設定されて`false`します。</span><span class="sxs-lookup"><span data-stu-id="a272c-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2. <span data-ttu-id="a272c-108">設定、<xref:System.Windows.Forms.RichTextBox.ScrollBars%2A>プロパティの適切な値を<xref:System.Windows.Forms.RichTextBoxScrollBars>列挙体。</span><span class="sxs-lookup"><span data-stu-id="a272c-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="a272c-109">[値]</span><span class="sxs-lookup"><span data-stu-id="a272c-109">Value</span></span>|<span data-ttu-id="a272c-110">説明</span><span class="sxs-lookup"><span data-stu-id="a272c-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="a272c-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (既定値)</span><span class="sxs-lookup"><span data-stu-id="a272c-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="a272c-112">テキストがコントロールの高さや幅を超えた場合にのみ、水平または垂直スクロール バー、またはその両方を表示します。</span><span class="sxs-lookup"><span data-stu-id="a272c-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="a272c-113">任意の種類のスクロール バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a272c-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="a272c-114">水平方向のスクロール バーのテキストがコントロールの幅を超えた場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a272c-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="a272c-115">(この場合、<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>にプロパティを設定する必要があります`false`)。</span><span class="sxs-lookup"><span data-stu-id="a272c-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="a272c-116">垂直方向のスクロール バーのテキストがコントロールの高さを超えた場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a272c-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="a272c-117">水平スクロール バーの場合に表示されます、<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>プロパティに設定されて`false`します。</span><span class="sxs-lookup"><span data-stu-id="a272c-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="a272c-118">テキストがコントロールの幅を超えていない場合は、スクロール バーを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a272c-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="a272c-119">常に垂直スクロール バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a272c-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="a272c-120">テキストがコントロールの長さを超えていない場合は、スクロール バーを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="a272c-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="a272c-121">常に垂直スクロール バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a272c-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="a272c-122">水平スクロール バーの場合に表示されます、<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>プロパティに設定されて`false`します。</span><span class="sxs-lookup"><span data-stu-id="a272c-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="a272c-123">テキストがコントロールの高さや幅を超えていない場合、スクロール バーは淡色表示になります。</span><span class="sxs-lookup"><span data-stu-id="a272c-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3. <span data-ttu-id="a272c-124"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="a272c-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="a272c-125">[値]</span><span class="sxs-lookup"><span data-stu-id="a272c-125">Value</span></span>|<span data-ttu-id="a272c-126">説明</span><span class="sxs-lookup"><span data-stu-id="a272c-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="a272c-127">コントロール内のテキスト行の区切りに達するまで右にスクロールされますので、コントロールの幅に合わせて自動的に調整されません。</span><span class="sxs-lookup"><span data-stu-id="a272c-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="a272c-128">または、両方の水平スクロール バーの上に選択した場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a272c-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="a272c-129">`true` (既定値)</span><span class="sxs-lookup"><span data-stu-id="a272c-129">`true` (default)</span></span>|<span data-ttu-id="a272c-130">コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="a272c-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="a272c-131">水平スクロール バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a272c-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="a272c-132">1 つまたは複数の段落を表示する、上記の垂直スクロール バーまたは [なし] を選択した場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a272c-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a272c-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="a272c-133">See also</span></span>

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="a272c-134">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="a272c-134">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="a272c-135">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="a272c-135">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
