---
title: ComboBox と ListBox
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
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739931"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="bb970-102">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="bb970-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="bb970-103"><xref:System.Windows.Forms.ComboBox> と <xref:System.Windows.Forms.ListBox> のコントロールには同様の動作があり、場合によっては交換可能である場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bb970-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="bb970-104">ただし、タスクにより適切なものがある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bb970-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="bb970-105">一般的に、コンボボックスは、推奨される選択肢のリストがある場合に適しています。また、リストボックスは、入力を一覧の内容に限定する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="bb970-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="bb970-106">コンボボックスにはテキストボックスフィールドが含まれているので、一覧にない選択肢を入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb970-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="bb970-107">例外は、<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> プロパティが <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>に設定されている場合です。</span><span class="sxs-lookup"><span data-stu-id="bb970-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="bb970-108">この場合、最初の文字を入力すると、コントロールによって項目が選択されます。</span><span class="sxs-lookup"><span data-stu-id="bb970-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="bb970-109">また、コンボボックスでは、フォーム上の領域が節約されます。</span><span class="sxs-lookup"><span data-stu-id="bb970-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="bb970-110">ユーザーが下矢印をクリックするまでは完全な一覧が表示されないため、コンボボックスは、リストボックスが収まらない小さなスペースに簡単に収めることができます。</span><span class="sxs-lookup"><span data-stu-id="bb970-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="bb970-111">例外は、<xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> プロパティが <xref:System.Windows.Forms.ComboBoxStyle.Simple>に設定されている場合です。完全な一覧が表示されます。コンボボックスは、リストボックスの場合よりも多くの領域を必要とします。</span><span class="sxs-lookup"><span data-stu-id="bb970-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb970-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb970-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="bb970-113">方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="bb970-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="bb970-114">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える</span><span class="sxs-lookup"><span data-stu-id="bb970-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="bb970-115">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="bb970-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
