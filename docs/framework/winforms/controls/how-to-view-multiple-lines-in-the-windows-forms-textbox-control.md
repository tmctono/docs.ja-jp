---
title: '方法: Windows フォーム TextBox コントロールで複数行を表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: 47404f02a753fe143dd573bdf73143416872af9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012920"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="2c91a-102">方法: Windows フォーム TextBox コントロールで複数行を表示する</span><span class="sxs-lookup"><span data-stu-id="2c91a-102">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="2c91a-103">既定では、Windows フォームで<xref:System.Windows.Forms.TextBox>コントロールが 1 行のテキストを表示し、スクロール バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2c91a-103">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="2c91a-104">テキストが使用可能な領域よりも長い場合は、テキストの一部のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c91a-104">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="2c91a-105">この既定の動作を設定して変更することができます、 <xref:System.Windows.Forms.TextBox.Multiline%2A>、 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>、および<xref:System.Windows.Forms.TextBox.ScrollBars%2A>プロパティを適切な値にします。</span><span class="sxs-lookup"><span data-stu-id="2c91a-105">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="2c91a-106">テキスト ボックス コントロール内の復帰を表示するには</span><span class="sxs-lookup"><span data-stu-id="2c91a-106">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="2c91a-107">複数の行に改行を表示する<xref:System.Windows.Forms.TextBox>を使用して、<xref:System.Environment.NewLine%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2c91a-107">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="2c91a-108">注意してくださいをエスケープ文字の解釈 (\\) 言語に固有です。</span><span class="sxs-lookup"><span data-stu-id="2c91a-108">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="2c91a-109">Visual Basic で`Chr$(13) & Chr$(10)`のキャリッジ リターンとライン フィード文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="2c91a-109">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="2c91a-110">TextBox コントロールで複数の行を表示するには</span><span class="sxs-lookup"><span data-stu-id="2c91a-110">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="2c91a-111"><xref:System.Windows.Forms.TextBox.Multiline%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-111">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="2c91a-112">場合<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>は`true`(既定)、コントロール内のテキストは、1 つまたは複数の段落を感じるかもしれません。 それ以外の場合、一部の行が、コントロールの端にあるクリップが一覧として表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c91a-112">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="2c91a-113"><xref:System.Windows.Forms.TextBox.ScrollBars%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-113">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="2c91a-114">[値]</span><span class="sxs-lookup"><span data-stu-id="2c91a-114">Value</span></span>|<span data-ttu-id="2c91a-115">説明</span><span class="sxs-lookup"><span data-stu-id="2c91a-115">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="2c91a-116">テキストが段落の場合は、この値を使用するほとんどの場合にコントロールに適合します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-116">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="2c91a-117">ユーザーは、マウス ポインターを使用して、一度にすべてを表示するには、テキストが長すぎる場合、コントロール内を移動します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-117">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="2c91a-118">幅を超える可能性がありますうちいくつかの行の一覧を表示する場合、この値を使用して、<xref:System.Windows.Forms.TextBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="2c91a-118">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="2c91a-119">一覧は、コントロールの高さを超える可能性がある場合は、この値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-119">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="2c91a-120"><xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-120">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="2c91a-121">[値]</span><span class="sxs-lookup"><span data-stu-id="2c91a-121">Value</span></span>|<span data-ttu-id="2c91a-122">説明</span><span class="sxs-lookup"><span data-stu-id="2c91a-122">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="2c91a-123">コントロール内のテキストが自動的に折り返さ、ため、行の区切りに達するまで右にスクロールされます。</span><span class="sxs-lookup"><span data-stu-id="2c91a-123">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="2c91a-124">選択した場合、この値を使用して<xref:System.Windows.Forms.ScrollBars.Horizontal>スクロール バーまたは<xref:System.Windows.Forms.ScrollBars.Both>上、します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-124">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="2c91a-125">`true` (既定値)</span><span class="sxs-lookup"><span data-stu-id="2c91a-125">`true` (default)</span></span>|<span data-ttu-id="2c91a-126">水平スクロール バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2c91a-126">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="2c91a-127">選択した場合、この値を使用して<xref:System.Windows.Forms.ScrollBars.Vertical>スクロール バーまたは<xref:System.Windows.Forms.ScrollBars.None>、上記の 1 つまたは複数の段落を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-127">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c91a-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c91a-128">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="2c91a-129">TextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="2c91a-129">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="2c91a-130">方法: Windows フォーム TextBox コントロールでのカーソル位置を制御します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-130">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="2c91a-131">方法: Windows フォーム TextBox コントロールでパスワード テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-131">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="2c91a-132">方法: 読み取り専用テキスト ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-132">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="2c91a-133">方法: 文字列に引用符を挿入します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-133">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="2c91a-134">方法: Windows フォームの TextBox コントロールでテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="2c91a-134">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="2c91a-135">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="2c91a-135">TextBox Control</span></span>](textbox-control-windows-forms.md)
