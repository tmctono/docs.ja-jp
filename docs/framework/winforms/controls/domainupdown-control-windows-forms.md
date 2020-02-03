---
title: DomainUpDown コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745829"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="a60c5-102">DomainUpDown コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="a60c5-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="a60c5-103">Windows フォームの <xref:System.Windows.Forms.DomainUpDown> コントロールは、テキストボックスと、リストを上または下に移動するためのボタンのペアの組み合わせに似ています。</span><span class="sxs-lookup"><span data-stu-id="a60c5-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="a60c5-104">コントロールは、選択肢の一覧からテキスト文字列を表示して設定します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="a60c5-105">ユーザーは上下のボタンをクリックして一覧内を移動し、上下の方向キーを押すか、リスト内の項目に一致する文字列を入力することで、文字列を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a60c5-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="a60c5-106">このコントロールの1つの使用方法は、アルファベット順に並べ替えられた名前のリストから項目を選択することです。</span><span class="sxs-lookup"><span data-stu-id="a60c5-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="a60c5-107">(一覧を並べ替えるには、[<xref:System.Windows.Forms.DomainUpDown.Sorted%2A>] プロパティを `true`に設定します)。このコントロールの機能は、リストボックスまたはコンボボックスとよく似ていますが、スペースが非常に小さくなります。</span><span class="sxs-lookup"><span data-stu-id="a60c5-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="a60c5-108">コントロールのキープロパティは、<xref:System.Windows.Forms.DomainUpDown.Items%2A>、<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>、および <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>です。</span><span class="sxs-lookup"><span data-stu-id="a60c5-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="a60c5-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A> プロパティには、コントロールにテキスト値が表示されるオブジェクトの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a60c5-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="a60c5-110"><xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> が `false`に設定されている場合、コントロールは、ユーザーが入力してリスト内の値と照合するテキストを自動的に完了します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="a60c5-111"><xref:System.Windows.Forms.DomainUpDown.Wrap%2A> が `true`に設定されている場合、最後の項目を超えてスクロールすると、リストの最初の項目に移動します (その逆も同様)。</span><span class="sxs-lookup"><span data-stu-id="a60c5-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="a60c5-112">コントロールの主要なメソッドは <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> と <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>です。</span><span class="sxs-lookup"><span data-stu-id="a60c5-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="a60c5-113">このコントロールは、テキスト文字列のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-113">This control displays only text strings.</span></span> <span data-ttu-id="a60c5-114">数値を表示するコントロールが必要な場合は、<xref:System.Windows.Forms.NumericUpDown> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="a60c5-115">詳細については、「 [NumericUpDown Control](numericupdown-control-windows-forms.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a60c5-115">For more information, see [NumericUpDown Control](numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a60c5-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a60c5-116">In This Section</span></span>  
 [<span data-ttu-id="a60c5-117">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="a60c5-117">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="a60c5-118"><xref:System.Windows.Forms.DomainUpDown> コントロールの一般的な概念について説明します。これにより、ユーザーがテキスト文字列の一覧から参照したり選択したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a60c5-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="a60c5-119">方法: Windows フォーム DomainUpDown コントロールにプログラムで項目を追加する</span><span class="sxs-lookup"><span data-stu-id="a60c5-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="a60c5-120"><xref:System.Windows.Forms.DomainUpDown> コントロールに表示するテキスト文字列を指定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="a60c5-121">方法: Windows フォームの DomainUpDown コントロールから項目を削除する</span><span class="sxs-lookup"><span data-stu-id="a60c5-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="a60c5-122">コード内の <xref:System.Windows.Forms.DomainUpDown> コントロールから項目を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a60c5-123">リファレンス</span><span class="sxs-lookup"><span data-stu-id="a60c5-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="a60c5-124">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="a60c5-125">このクラスについて説明し、すべてのメンバーへのリンクを示します。「」をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a60c5-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="a60c5-126">Related Sections</span></span>  
 [<span data-ttu-id="a60c5-127">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="a60c5-127">Controls You Can Use On Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="a60c5-128">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="a60c5-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
