---
title: ListBox の代わりに Windows フォーム ComboBox を使用する場合
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 5dc7778f43c01fd28a14489a7b4179dd851568b2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702998"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="e97f6-102">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="e97f6-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="e97f6-103"><xref:System.Windows.Forms.ComboBox>と<xref:System.Windows.Forms.ListBox>コントロールが似たような動作、およびいくつかの場合は互換性にあります。</span><span class="sxs-lookup"><span data-stu-id="e97f6-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="e97f6-104">ただしはどちらか一方のタスクをより適切な時間があります。</span><span class="sxs-lookup"><span data-stu-id="e97f6-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="e97f6-105">一般に、コンボ ボックスは、推奨される選択肢は、の一覧があるし、リスト ボックスは、一覧にあるものへの入力を制限する場合に適切なときに適しています。</span><span class="sxs-lookup"><span data-stu-id="e97f6-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="e97f6-106">コンボ ボックスには、一覧にない選択肢を入力するためのテキスト ボックスのフィールドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e97f6-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="e97f6-107">例外は、<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>プロパティに設定されて<xref:System.Windows.Forms.ComboBoxStyle.DropDownList>します。</span><span class="sxs-lookup"><span data-stu-id="e97f6-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="e97f6-108">その場合は、コントロールによって項目が選択の最初の文字を入力する場合。</span><span class="sxs-lookup"><span data-stu-id="e97f6-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="e97f6-109">さらに、コンボ ボックスは、フォームの領域を節約します。</span><span class="sxs-lookup"><span data-stu-id="e97f6-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="e97f6-110">下矢印をクリックするまでは完全な一覧が表示されないため、コンボ ボックスに簡単にリスト ボックスが収まらない小さなスペースに収まります。</span><span class="sxs-lookup"><span data-stu-id="e97f6-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="e97f6-111">例外は、ときに、<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>プロパティに設定されて<xref:System.Windows.Forms.ComboBoxStyle.Simple>: 完全な一覧が表示され、コンボ ボックスは、リスト ボックスよりも領域を増やす。</span><span class="sxs-lookup"><span data-stu-id="e97f6-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e97f6-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e97f6-112">See also</span></span>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="e97f6-113">方法: 追加および削除項目、Windows からフォーム ComboBox、ListBox、または CheckedListBox コントロール</span><span class="sxs-lookup"><span data-stu-id="e97f6-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="e97f6-114">方法: Windows の内容を並べ替えるフォーム ComboBox、ListBox、または CheckedListBox コントロール</span><span class="sxs-lookup"><span data-stu-id="e97f6-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="e97f6-115">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="e97f6-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
