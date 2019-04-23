---
title: '方法: Windows フォームの RichTextBox コントロールを使用してインデント、ぶら下げインデント、箇条書き段落を設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: ef579923ac2b9ea9905a60000d93f6bfc90ed5b8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342675"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="15e8f-102">方法: Windows フォームの RichTextBox コントロールを使用してインデント、ぶら下げインデント、箇条書き段落を設定する</span><span class="sxs-lookup"><span data-stu-id="15e8f-102">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="15e8f-103">Windows フォーム<xref:System.Windows.Forms.RichTextBox>コントロールが、表示するテキストを書式設定するためのさまざまなオプションです。</span><span class="sxs-lookup"><span data-stu-id="15e8f-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="15e8f-104">設定して箇条書きとして選択した段落を書式設定することができます、<xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="15e8f-104">You can format selected paragraphs as bulleted lists by setting the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="15e8f-105">使用することも、 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>、 <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>、および<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>左側と、コントロールの右端と左端の他の行のテキストの段落のインデントを設定するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="15e8f-105">You can also use the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>, <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>, and <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> properties to set the indentation of paragraphs relative to the left and right edges of the control, and the left edge of other lines of text.</span></span>  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a><span data-ttu-id="15e8f-106">段落を箇条書きとして書式設定するには</span><span class="sxs-lookup"><span data-stu-id="15e8f-106">To format a paragraph as a bulleted list</span></span>  
  
1. <span data-ttu-id="15e8f-107"><xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="15e8f-107">Set the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property to `true`.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a><span data-ttu-id="15e8f-108">段落にインデントを設定するには</span><span class="sxs-lookup"><span data-stu-id="15e8f-108">To indent a paragraph</span></span>  
  
1. <span data-ttu-id="15e8f-109">設定、<xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>プロパティにコントロールの左端とテキストの左端のピクセル単位で距離を表す整数。</span><span class="sxs-lookup"><span data-stu-id="15e8f-109">Set the <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> property to an integer representing the distance in pixels between the left edge of the control and the left edge of the text.</span></span>  
  
2. <span data-ttu-id="15e8f-110">設定、<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>プロパティに同じ段落の後続行の左端と段落のテキストの最初の行の左端のピクセル単位で距離を表す整数。</span><span class="sxs-lookup"><span data-stu-id="15e8f-110">Set the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property to an integer representing the distance in pixels between the left edge of the first line of text in the paragraph and the left edge of subsequent lines in the same paragraph.</span></span> <span data-ttu-id="15e8f-111">値、<xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A>プロパティは、最初の行の下で折り返されて段落内の行にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="15e8f-111">The value of the <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> property only applies to lines in a paragraph that have wrapped below the first line.</span></span>  
  
3. <span data-ttu-id="15e8f-112">設定、<xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>プロパティに、コントロールの右端とテキストの右端の間のピクセル単位で距離を表す整数。</span><span class="sxs-lookup"><span data-stu-id="15e8f-112">Set the <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> property to an integer representing the distance in pixels between the right edge of the control and the right edge of the text.</span></span>  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="15e8f-113">これらすべてのプロパティは、選択したテキストを含む段落に影響し、現在の挿入ポイントの後に入力されるテキストにも影響します。</span><span class="sxs-lookup"><span data-stu-id="15e8f-113">All these properties affect any paragraphs that contain selected text, and also the text that is typed after the current insertion point.</span></span> <span data-ttu-id="15e8f-114">たとえば、ユーザーが段落内の単語を選択して、インデントを調整すると、新しい設定はその単語を含む段落全体に適用され、選択した段落の後に入力される段落にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="15e8f-114">For example, when a user selects a word within a paragraph and then adjusts the indentation, the new settings will apply to the entire paragraph that contains that word, and also to any paragraphs subsequently entered after the selected paragraph.</span></span> <span data-ttu-id="15e8f-115">プログラムでテキストを選択する方法の詳細については、次を参照してください。<xref:System.Windows.Forms.TextBoxBase.Select%2A>します。</span><span class="sxs-lookup"><span data-stu-id="15e8f-115">For information about selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e8f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="15e8f-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="15e8f-117">RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="15e8f-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="15e8f-118">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="15e8f-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
