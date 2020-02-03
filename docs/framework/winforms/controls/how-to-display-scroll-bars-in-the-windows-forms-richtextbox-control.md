---
title: RichTextBox コントロールにスクロールバーを表示する
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes [Windows Forms], displaying scroll bars
- scroll bars [Windows Forms], displaying in controls
- RichTextBox control [Windows Forms], displaying scroll bars
ms.assetid: cdeb42e1-86e8-410c-ba46-18aec264ef5f
ms.openlocfilehash: 2185b572ef20765043d3df3dbfd8bf5b21cfac28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745557"
---
# <a name="how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="fd4f0-102">方法 : Windows フォームの RichTextBox コントロールにスクロール バーを表示する</span><span class="sxs-lookup"><span data-stu-id="fd4f0-102">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="fd4f0-103">既定では、必要に応じて、Windows フォーム <xref:System.Windows.Forms.RichTextBox> コントロールに水平スクロールバーと垂直スクロールバーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-103">By default, the Windows Forms <xref:System.Windows.Forms.RichTextBox> control displays horizontal and vertical scroll bars as necessary.</span></span> <span data-ttu-id="fd4f0-104">次の表に示すように、<xref:System.Windows.Forms.RichTextBox> コントロールの <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> プロパティに使用できる値は7つあります。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-104">There are seven possible values for the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property of the <xref:System.Windows.Forms.RichTextBox> control, which are described in the table below.</span></span>  
  
### <a name="to-display-scroll-bars-in-a-richtextbox-control"></a><span data-ttu-id="fd4f0-105">RichTextBox コントロールにスクロールバーを表示するには</span><span class="sxs-lookup"><span data-stu-id="fd4f0-105">To display scroll bars in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="fd4f0-106"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-106">Set the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="fd4f0-107"><xref:System.Windows.Forms.RichTextBox.Multiline%2A> プロパティが `false`に設定されている場合、水平を含むスクロールバーの種類は表示されません。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-107">No type of scroll bar, including horizontal, will display if the <xref:System.Windows.Forms.RichTextBox.Multiline%2A> property is set to `false`.</span></span>  
  
2. <span data-ttu-id="fd4f0-108"><xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> プロパティを <xref:System.Windows.Forms.RichTextBoxScrollBars> 列挙の適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-108">Set the <xref:System.Windows.Forms.RichTextBox.ScrollBars%2A> property to an appropriate value of the <xref:System.Windows.Forms.RichTextBoxScrollBars> enumeration.</span></span>  
  
    |<span data-ttu-id="fd4f0-109">値</span><span class="sxs-lookup"><span data-stu-id="fd4f0-109">Value</span></span>|<span data-ttu-id="fd4f0-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="fd4f0-110">Description</span></span>|  
    |-----------|-----------------|  
    |<span data-ttu-id="fd4f0-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (規定値)</span><span class="sxs-lookup"><span data-stu-id="fd4f0-111"><xref:System.Windows.Forms.RichTextBoxScrollBars.Both> (default)</span></span>|<span data-ttu-id="fd4f0-112">テキストがコントロールの幅または長さを超えた場合にのみ、水平または垂直のスクロールバー、またはその両方を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-112">Displays horizontal or vertical scroll bars, or both, only when text exceeds the width or length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.None>|<span data-ttu-id="fd4f0-113">どの種類のスクロールバーも表示されません。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-113">Never displays any type of scroll bar.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Horizontal>|<span data-ttu-id="fd4f0-114">テキストがコントロールの幅を超えた場合にのみ、水平スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-114">Displays a horizontal scroll bar only when the text exceeds the width of the control.</span></span> <span data-ttu-id="fd4f0-115">(これを行うには、<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティを `false`に設定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-115">(For this to occur, the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property must be set to `false`.)</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.Vertical>|<span data-ttu-id="fd4f0-116">テキストがコントロールの高さを超えた場合にのみ、垂直スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-116">Displays a vertical scroll bar only when the text exceeds the height of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedHorizontal>|<span data-ttu-id="fd4f0-117"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティが `false`に設定されている場合、水平スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-117">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="fd4f0-118">テキストがコントロールの幅を超えていない場合、スクロールバーは淡色表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-118">The scroll bar appears dimmed when text does not exceed the width of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedVertical>|<span data-ttu-id="fd4f0-119">常に垂直スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-119">Always displays a vertical scroll bar.</span></span> <span data-ttu-id="fd4f0-120">テキストがコントロールの長さを超えていない場合、スクロールバーは淡色表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-120">The scroll bar appears dimmed when text does not exceed the length of the control.</span></span>|  
    |<xref:System.Windows.Forms.RichTextBoxScrollBars.ForcedBoth>|<span data-ttu-id="fd4f0-121">常に垂直スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-121">Always displays a vertical scrollbar.</span></span> <span data-ttu-id="fd4f0-122"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティが `false`に設定されている場合、水平スクロールバーを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-122">Displays a horizontal scroll bar when the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property is set to `false`.</span></span> <span data-ttu-id="fd4f0-123">テキストがコントロールの幅または長さを超えていない場合、スクロールバーはグレー表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-123">The scroll bars appear grayed when text does not exceed the width or length of the control.</span></span>|  
  
3. <span data-ttu-id="fd4f0-124"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-124">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="fd4f0-125">値</span><span class="sxs-lookup"><span data-stu-id="fd4f0-125">Value</span></span>|<span data-ttu-id="fd4f0-126">[説明]</span><span class="sxs-lookup"><span data-stu-id="fd4f0-126">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="fd4f0-127">コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されないので、改行に達するまで右にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-127">Text in the control is not automatically adjusted to fit the width of the control, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="fd4f0-128">上にある水平スクロールバーまたは両方を選択した場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-128">Use this value if you chose horizontal scroll bars or both, above.</span></span>|  
    |<span data-ttu-id="fd4f0-129">`true` (規定値)</span><span class="sxs-lookup"><span data-stu-id="fd4f0-129">`true` (default)</span></span>|<span data-ttu-id="fd4f0-130">コントロール内のテキストは、コントロールの幅に合わせて自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-130">Text in the control is automatically adjusted to fit the width of the control.</span></span> <span data-ttu-id="fd4f0-131">水平スクロールバーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-131">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="fd4f0-132">1つ以上の段落を表示する場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd4f0-132">Use this value if you chose vertical scroll bars or none, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fd4f0-133">参照</span><span class="sxs-lookup"><span data-stu-id="fd4f0-133">See also</span></span>

- <xref:System.Windows.Forms.RichTextBoxScrollBars>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="fd4f0-134">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="fd4f0-134">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="fd4f0-135">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="fd4f0-135">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
