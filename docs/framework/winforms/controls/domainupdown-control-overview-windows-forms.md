---
title: DomainUpDown コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745863"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="3a4ea-102">DomainUpDown コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="3a4ea-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="3a4ea-103">Windows フォーム <xref:System.Windows.Forms.DomainUpDown> コントロールは、基本的には、テキストボックスと、リストを上または下に移動するためのボタンの組み合わせで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="3a4ea-104">コントロールは、選択肢の一覧からテキスト文字列を表示して設定します。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="3a4ea-105">ユーザーは上下のボタンをクリックして一覧内を移動し、上下の方向キーを押すか、リスト内の項目に一致する文字列を入力することで、文字列を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="3a4ea-106">このコントロールの1つの使用方法は、アルファベット順に並べ替えられた名前のリストから項目を選択することです。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a4ea-107">リストを並べ替えるには、<xref:System.Windows.Forms.DomainUpDown.Sorted%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="3a4ea-108">このコントロールの機能は、リストボックスまたはコンボボックスとよく似ていますが、スペースが非常に小さくなります。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="3a4ea-109">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="3a4ea-109">Key Properties</span></span>  
 <span data-ttu-id="3a4ea-110">コントロールのキープロパティは、<xref:System.Windows.Forms.DomainUpDown.Items%2A>、<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>、および <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>です。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="3a4ea-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A> プロパティには、コントロールにテキスト値が表示されるオブジェクトの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="3a4ea-112"><xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> が `false`に設定されている場合、コントロールは、ユーザーが入力してリスト内の値と照合するテキストを自動的に完了します。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="3a4ea-113"><xref:System.Windows.Forms.DomainUpDown.Wrap%2A> が `true`に設定されている場合、最後の項目を超えてスクロールすると、リストの最初の項目に移動します (その逆も同様)。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="3a4ea-114">コントロールの主要なメソッドは <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> と <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>です。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="3a4ea-115">このコントロールは、テキスト文字列のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-115">This control displays only text strings.</span></span> <span data-ttu-id="3a4ea-116">数値を表示するコントロールが必要な場合は、<xref:System.Windows.Forms.NumericUpDown> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="3a4ea-117">詳細については、「 [NumericUpDown Control の概要](numericupdown-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a4ea-117">For more information, see [NumericUpDown Control Overview](numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4ea-118">参照</span><span class="sxs-lookup"><span data-stu-id="3a4ea-118">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="3a4ea-119">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="3a4ea-119">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
