---
title: RichTextBox コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 2b1a6604df3979e83e4a815cdb4a9397ab4e67ad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012465"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="f2aed-102">RichTextBox コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="f2aed-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="f2aed-103">Windows フォーム`RichTextBox`を表示する、入力、およびテキストの書式形式のコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="f2aed-104">`RichTextBox`コントロールはすべて、<xref:System.Windows.Forms.TextBox>コントロールを使用して、できますが、できますフォント、色、およびリンクの表示; ファイルは元に戻すおよびやり直し操作の編集からテキストと埋め込み画像を読み込み、指定した文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="f2aed-105">`RichTextBox`コントロールを通常使用するテキストの操作を行い、Microsoft Word などのワード プロセッシング アプリケーションに似た機能を表示します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="f2aed-106">ように、<xref:System.Windows.Forms.TextBox>コントロール、`RichTextBox`コントロールがスクロール バーを表示できますとは異なり、<xref:System.Windows.Forms.TextBox>コントロール、既定では水平および垂直の両方向のスクロール バーを表示し、スクロール バーの追加の設定があります。</span><span class="sxs-lookup"><span data-stu-id="f2aed-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2aed-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f2aed-107">In This Section</span></span>  
 [<span data-ttu-id="f2aed-108">RichTextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="f2aed-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="f2aed-109">一般的な概念が導入されています、`RichTextBox`コントロールで、ユーザー入力を許可するには、表示、および書式設定オプションのテキストを操作します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="f2aed-110">方法: Windows フォームの RichTextBox コントロールにおける属性の変更を書式設定するかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="f2aed-111">フォントと段落の書式設定の変更を追跡する方法について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="f2aed-112">方法: スクロール バーを表示で、Windows フォームの RichTextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="f2aed-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="f2aed-113">内のスクロール バーの使用可能な多くの選択肢について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="f2aed-114">方法: Windows フォームの RichTextBox コントロールで Web スタイル リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="f2aed-115">Web サイトにリンクする方法について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="f2aed-116">方法: Windows フォームの RichTextBox コントロールでドラッグ アンド ドロップ操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f2aed-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="f2aed-117">データにドラッグする方法について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="f2aed-118">方法: Windows フォームの RichTextBox コントロールにファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="f2aed-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="f2aed-119">既存のファイルを読み込む方法について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="f2aed-120">方法: Windows フォームの RichTextBox コントロールでのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="f2aed-121">内容を保存する方法について説明、`RichTextBox`ファイルを制御します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="f2aed-122">方法: Windows フォームの RichTextBox コントロールのフォント属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="f2aed-123">フォント ファミリ、サイズ、スタイル、およびテキストの色を設定する方法について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="f2aed-124">方法: インデント、ぶら下げインデント、および箇条書き段落を Windows フォームの RichTextBox コントロールでを設定します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="f2aed-125">内の段落を書式設定する方法について説明します、`RichTextBox`コントロール。</span><span class="sxs-lookup"><span data-stu-id="f2aed-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f2aed-126">参照</span><span class="sxs-lookup"><span data-stu-id="f2aed-126">Reference</span></span>  
 <span data-ttu-id="f2aed-127"><xref:System.Windows.Forms.RichTextBox> クラス</span><span class="sxs-lookup"><span data-stu-id="f2aed-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="f2aed-128">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f2aed-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2aed-129">Related Sections</span></span>  
 [<span data-ttu-id="f2aed-130">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="f2aed-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="f2aed-131">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="f2aed-132">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="f2aed-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="f2aed-133">一般的な概念が導入されています、<xref:System.Windows.Forms.TextBox>コントロールで、ユーザーからの編集可能で、複数行の入力を許可します。</span><span class="sxs-lookup"><span data-stu-id="f2aed-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
