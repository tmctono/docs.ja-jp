---
title: DomainUpDown コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 851c02747a2414e34a5e9d35bdc7d1df916efce0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718897"
---
# <a name="domainupdown-control-overview-windows-forms"></a><span data-ttu-id="ccf9b-102">DomainUpDown コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ccf9b-102">DomainUpDown Control Overview (Windows Forms)</span></span>
<span data-ttu-id="ccf9b-103">Windows フォーム<xref:System.Windows.Forms.DomainUpDown>コントロールが本質的には、テキスト ボックスの組み合わせで、一覧内を上下に移動するボタンのペア。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-103">The Windows Forms <xref:System.Windows.Forms.DomainUpDown> control is essentially a combination of a text box and a pair of buttons for moving up or down through a list.</span></span> <span data-ttu-id="ccf9b-104">コントロールは、表示し、選択肢の一覧からテキスト文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-104">The control displays and sets a text string from a list of choices.</span></span> <span data-ttu-id="ccf9b-105">ユーザーは、一覧内を移動するボタンと下矢印をクリックすると、上下の矢印キーを押して、または、リスト内の項目に一致する文字列を入力して、文字列を選択できます。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-105">The user can select the string by clicking up and down buttons to move through a list, by pressing the UP and DOWN ARROW keys, or by typing a string that matches an item in the list.</span></span> <span data-ttu-id="ccf9b-106">このコントロールの用途の 1 つは、名のアルファベット順に並べ替えられたリストから項目を選択するためです。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-106">One possible use for this control is for selecting items from an alphabetically sorted list of names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccf9b-107">一覧を並べ替えるには、設定、<xref:System.Windows.Forms.DomainUpDown.Sorted%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-107">To sort the list, set the <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="ccf9b-108">このコントロールの機能は、リスト ボックスまたはコンボ ボックスによく似ていますが、非常に小さい領域を占めます。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-108">The function of this control is very similar to the list box or combo box, but it takes up very little space.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="ccf9b-109">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="ccf9b-109">Key Properties</span></span>  
 <span data-ttu-id="ccf9b-110">コントロールのプロパティは<xref:System.Windows.Forms.DomainUpDown.Items%2A>、 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>、および<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-110">The key properties of the control are <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, and <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>.</span></span> <span data-ttu-id="ccf9b-111"><xref:System.Windows.Forms.DomainUpDown.Items%2A>プロパティに文字列値を持つが、コントロールに表示されるオブジェクトの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-111">The <xref:System.Windows.Forms.DomainUpDown.Items%2A> property contains the list of objects whose text values are displayed in the control.</span></span> <span data-ttu-id="ccf9b-112">場合<xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>に設定されている`false`コントロールは、ユーザーが型し、リスト内の値に一致するテキストを自動的に完了します。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-112">If <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> is set to `false`, the control automatically completes text that the user types and matches it to a value in the list.</span></span> <span data-ttu-id="ccf9b-113">場合<xref:System.Windows.Forms.DomainUpDown.Wrap%2A>に設定されている`true`、過去の最後の項目スクロールをクリックすると、最初の項目の一覧で、またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-113">If <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> is set to `true`, scrolling past the last item will take you to the first item in the list and vice versa.</span></span> <span data-ttu-id="ccf9b-114">コントロールの主要なメソッドは<xref:System.Windows.Forms.DomainUpDown.UpButton%2A>と<xref:System.Windows.Forms.DomainUpDown.DownButton%2A>します。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-114">The key methods of the control are <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> and <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.</span></span>  
  
 <span data-ttu-id="ccf9b-115">このコントロールには、テキスト文字列のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-115">This control displays only text strings.</span></span> <span data-ttu-id="ccf9b-116">数値の値を表示するコントロールを実行する場合に、使用、<xref:System.Windows.Forms.NumericUpDown>コントロール。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-116">If you want a control that displays numeric values, use the <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="ccf9b-117">詳細については、次を参照してください。 [NumericUpDown コントロールの概要](numericupdown-control-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="ccf9b-117">For more information, see [NumericUpDown Control Overview](numericupdown-control-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf9b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="ccf9b-118">See also</span></span>
- <xref:System.Windows.Forms.DomainUpDown>
- [<span data-ttu-id="ccf9b-119">DomainUpDown コントロール</span><span class="sxs-lookup"><span data-stu-id="ccf9b-119">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
