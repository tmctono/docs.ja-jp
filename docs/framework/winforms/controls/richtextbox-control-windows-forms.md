---
title: RichTextBox コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- RichTextBox control [Windows Forms]
- rich edit controls
ms.assetid: 3225f2ef-c6d9-4bd4-9d3e-2219e58edbf2
ms.openlocfilehash: 9d26ec7bfc4d75b304bbc9dc98dbbeaed64effe7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743124"
---
# <a name="richtextbox-control-windows-forms"></a><span data-ttu-id="8bbf7-102">RichTextBox コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="8bbf7-102">RichTextBox Control (Windows Forms)</span></span>
<span data-ttu-id="8bbf7-103">Windows フォーム `RichTextBox` コントロールは、書式設定を使用してテキストを表示、入力、および操作するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-103">The Windows Forms `RichTextBox` control is used for displaying, entering, and manipulating text with formatting.</span></span> <span data-ttu-id="8bbf7-104">`RichTextBox` コントロールは、<xref:System.Windows.Forms.TextBox> コントロールが行うすべての操作を実行しますが、フォント、色、およびリンクを表示することもできます。ファイルからテキストと埋め込み画像を読み込みます。元に戻す操作とやり直し編集操作指定された文字を検索します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-104">The `RichTextBox` control does everything the <xref:System.Windows.Forms.TextBox> control does, but it can also display fonts, colors, and links; load text and embedded images from a file; undo and redo editing operations; and find specified characters.</span></span> <span data-ttu-id="8bbf7-105">`RichTextBox` コントロールは、通常、Microsoft Word などのワードプロセッシングアプリケーションに似たテキスト操作と表示機能を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-105">The `RichTextBox` control is typically used to provide text manipulation and display features similar to word processing applications such as Microsoft Word.</span></span> <span data-ttu-id="8bbf7-106"><xref:System.Windows.Forms.TextBox> コントロールと同様に、`RichTextBox` コントロールはスクロールバーを表示できます。ただし、<xref:System.Windows.Forms.TextBox> コントロールとは異なり、水平スクロールバーと垂直スクロールバーの両方が既定で表示され、追加のスクロールバーの設定があります。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-106">Like the <xref:System.Windows.Forms.TextBox> control, the `RichTextBox` control can display scroll bars; but unlike the <xref:System.Windows.Forms.TextBox> control, it displays both horizontal and vertical scrollbars by default and has additional scrollbar settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8bbf7-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8bbf7-107">In This Section</span></span>  
 [<span data-ttu-id="8bbf7-108">RichTextBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="8bbf7-108">RichTextBox Control Overview</span></span>](richtextbox-control-overview-windows-forms.md)  
 <span data-ttu-id="8bbf7-109">ユーザーが書式設定オプションを使用してテキストを入力、表示、操作できるようにする `RichTextBox` コントロールの一般的な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-109">Introduces the general concepts of the `RichTextBox` control, which allows users to enter, display, and manipulate text with formatting options.</span></span>  
  
 [<span data-ttu-id="8bbf7-110">方法: Windows フォームの RichTextBox コントロールにおける書式属性の変更を確認する</span><span class="sxs-lookup"><span data-stu-id="8bbf7-110">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>](determine-when-formatting-attributes-change-wf-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-111">`RichTextBox` コントロールでフォントおよび段落書式の変更を追跡する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-111">Explains how to keep track of changes in font and paragraph formatting in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="8bbf7-112">方法: Windows フォームの RichTextBox コントロールにスクロール バーを表示する</span><span class="sxs-lookup"><span data-stu-id="8bbf7-112">How to: Display Scroll Bars in the Windows Forms RichTextBox Control</span></span>](how-to-display-scroll-bars-in-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-113">`RichTextBox` コントロールのスクロールバーで使用できる多くの選択肢について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-113">Describes the many choices available for scroll bars in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="8bbf7-114">方法: Windows フォームの RichTextBox コントロールを使用して Web スタイルのリンクを表示する</span><span class="sxs-lookup"><span data-stu-id="8bbf7-114">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>](how-to-display-web-style-links-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-115">`RichTextBox` コントロールから Web サイトにリンクする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-115">Explains how to link to Web sites from the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="8bbf7-116">方法: Windows フォームの RichTextBox コントロールにおけるドラッグ アンド ドロップ操作を有効にする</span><span class="sxs-lookup"><span data-stu-id="8bbf7-116">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>](enable-drag-and-drop-operations-with-wf-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-117">`RichTextBox` コントロールにデータをドラッグする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-117">Provides instructions for dragging data into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="8bbf7-118">方法: Windows フォームの RichTextBox コントロールにファイルを読み込む</span><span class="sxs-lookup"><span data-stu-id="8bbf7-118">How to: Load Files into the Windows Forms RichTextBox Control</span></span>](how-to-load-files-into-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-119">既存のファイルを `RichTextBox` コントロールに読み込む手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-119">Provides instructions for loading an existing file into the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="8bbf7-120">方法: Windows フォームの RichTextBox コントロールを使用してファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="8bbf7-120">How to: Save Files with the Windows Forms RichTextBox Control</span></span>](how-to-save-files-with-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-121">`RichTextBox` コントロールの内容をファイルに保存する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-121">Provides instructions for saving the contents of the `RichTextBox` control to a file.</span></span>  
  
 [<span data-ttu-id="8bbf7-122">方法: Windows フォームの RichTextBox コントロールのフォント属性を設定する</span><span class="sxs-lookup"><span data-stu-id="8bbf7-122">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>](how-to-set-font-attributes-for-the-windows-forms-richtextbox-control.md)  
 <span data-ttu-id="8bbf7-123">`RichTextBox` コントロールのテキストのフォントファミリ、サイズ、スタイル、および色を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-123">Describes how to set the font family, size, style, and color of text in the `RichTextBox` control.</span></span>  
  
 [<span data-ttu-id="8bbf7-124">方法: Windows フォームの RichTextBox コントロールを使用してインデント、ぶら下げインデント、および箇条書き段落を設定する</span><span class="sxs-lookup"><span data-stu-id="8bbf7-124">How to: Set Indents, Hanging Indents, and Bulleted Paragraphs with the Windows Forms RichTextBox Control</span></span>](set-indents-hanging-indents-bulleted-paragraphs-with-wf-richtextbox.md)  
 <span data-ttu-id="8bbf7-125">`RichTextBox` コントロールの段落の書式を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-125">Describes how to format paragraphs in the `RichTextBox` control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8bbf7-126">リファレンス</span><span class="sxs-lookup"><span data-stu-id="8bbf7-126">Reference</span></span>  
 <span data-ttu-id="8bbf7-127"><xref:System.Windows.Forms.RichTextBox> クラス</span><span class="sxs-lookup"><span data-stu-id="8bbf7-127"><xref:System.Windows.Forms.RichTextBox> class</span></span>  
 <span data-ttu-id="8bbf7-128">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8bbf7-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bbf7-129">Related Sections</span></span>  
 [<span data-ttu-id="8bbf7-130">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="8bbf7-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="8bbf7-131">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="8bbf7-132">TextBox コントロール</span><span class="sxs-lookup"><span data-stu-id="8bbf7-132">TextBox Control</span></span>](textbox-control-windows-forms.md)  
 <span data-ttu-id="8bbf7-133"><xref:System.Windows.Forms.TextBox> コントロールの一般的な概念について説明します。これにより、ユーザーが編集可能な複数行の入力を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8bbf7-133">Introduces the general concepts of the <xref:System.Windows.Forms.TextBox> control, which allows editable, multiline input from the user.</span></span>
