---
title: DomainUpDown コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: 83d674e3fb7ff7e715b75c635b891cd4e9703a21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972056"
---
# <a name="domainupdown-control-windows-forms"></a><span data-ttu-id="e1b8b-102">DomainUpDown コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="e1b8b-102">DomainUpDown Control (Windows Forms)</span></span>
<span data-ttu-id="e1b8b-103">Windows フォーム<xref:System.Windows.Forms.DomainUpDown>コントロールのようを組み合わせたテキスト ボックスとボタンのペアのリストを上下に移動します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control looks like a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="e1b8b-104">コントロールは、表示し、選択肢の一覧からテキスト文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="e1b8b-105">ユーザーは、一覧内を移動するボタンと下矢印をクリックすると、上下の矢印キーを押して、または、リスト内の項目に一致する文字列を入力して、文字列を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="e1b8b-106">このコントロールの用途の 1 つは、名のアルファベット順に並べ替えられたリストから項目を選択するためです。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span> <span data-ttu-id="e1b8b-107">(一覧を並べ替えるには、設定、<xref:System.Windows.Forms.DomainUpDown.Sorted%2A>プロパティを`true`)。このコントロールの機能は、リスト ボックスまたはコンボ ボックスによく似ていますが、非常に小さい領域を占めます。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-107">(To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.) The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
 <span data-ttu-id="e1b8b-108">コントロールのプロパティは<xref:System.Windows.Forms.DomainUpDown.Items%2A>、 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>、および<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-108">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="e1b8b-109"><xref:System.Windows.Forms.DomainUpDown.Items%2A>プロパティに文字列値を持つが、コントロールに表示されるオブジェクトの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-109">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="e1b8b-110">場合<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>に設定されている`false`コントロールは、ユーザーが型し、リスト内の値に一致するテキストを自動的に完了します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-110">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="e1b8b-111">場合<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>に設定されている`true`、過去の最後の項目スクロールをクリックすると、最初の項目の一覧で、またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-111">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="e1b8b-112">コントロールの主要なメソッドは<xref:System.Windows.Forms.DomainUpDown.UpButton%2A>と<xref:System.Windows.Forms.DomainUpDown.DownButton%2A>します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-112">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="e1b8b-113">このコントロールには、テキスト文字列のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-113">This control displays only text strings.</span></span> <span data-ttu-id="e1b8b-114">数値の値を表示するコントロールを実行する場合に、使用、<xref:System.Windows.Forms.NumericUpDown>コントロール。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-114">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="e1b8b-115">詳細については、次を参照してください。 [NumericUpDown コントロール](numericupdown-control-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-115">For more information, see [NumericUpDown Control](numericupdown-control-windows-forms.md) .</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1b8b-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e1b8b-116">In This Section</span></span>  
 [<span data-ttu-id="e1b8b-117">DomainUpDown コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="e1b8b-117">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)  
 <span data-ttu-id="e1b8b-118">一般的な概念が導入されています、<xref:System.Windows.Forms.DomainUpDown>コントロールを参照し、テキスト文字列の一覧から選択することができます。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-118">Introduces the general concepts of the <xref:System.Windows.Forms.DomainUpDown> control, which allows users to browse through and select from a list of text strings.</span></span>  
  
 [<span data-ttu-id="e1b8b-119">方法: プログラムで Windows フォーム DomainUpDown コントロールに項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-119">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 <span data-ttu-id="e1b8b-120">テキスト文字列を指定する方法について説明します、<xref:System.Windows.Forms.DomainUpDown>コントロールを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-120">Describes how to specify the text strings the <xref:System.Windows.Forms.DomainUpDown> control should display.</span></span>  
  
 [<span data-ttu-id="e1b8b-121">方法: Windows フォーム DomainUpDown コントロールから項目を削除します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-121">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 <span data-ttu-id="e1b8b-122">項目を削除する方法について説明します、<xref:System.Windows.Forms.DomainUpDown>コード内でコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-122">Describes how to delete items from the <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e1b8b-123">参照</span><span class="sxs-lookup"><span data-stu-id="e1b8b-123">Reference</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <span data-ttu-id="e1b8b-124">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-124">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 <span data-ttu-id="e1b8b-125">このクラスについて説明し、すべてのメンバーへのリンクがあります.</span><span class="sxs-lookup"><span data-stu-id="e1b8b-125">Describes this class and has links to all its members..</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e1b8b-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1b8b-126">Related Sections</span></span>  
 [<span data-ttu-id="e1b8b-127">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="e1b8b-127">Controls You Can Use On Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="e1b8b-128">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="e1b8b-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
