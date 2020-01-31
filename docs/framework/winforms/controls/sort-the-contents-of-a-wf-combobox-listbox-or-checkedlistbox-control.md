---
title: ComboBox、ListBox、または CheckedListBox コントロールの内容を並べ替える
ms.date: 03/30/2017
helpviewer_keywords:
- CheckedListBox control [Windows Forms], sorting
- ComboBox control [Windows Forms], sorting contents
- combo boxes [Windows Forms], sorting contents
- list boxes [Windows Forms], sorting contents
- ListBox control [Windows Forms], sorting contents
ms.assetid: c268e387-3d1d-4d86-a940-19f6673c8d06
ms.openlocfilehash: dee969d777edf76434622fe632f7e934987a1dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742953"
---
# <a name="how-to-sort-the-contents-of-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="c85ad-102">方法 : Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールを並べ替える</span><span class="sxs-lookup"><span data-stu-id="c85ad-102">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="c85ad-103">Windows フォームコントロールは、データバインドされている場合は並べ替えられません。</span><span class="sxs-lookup"><span data-stu-id="c85ad-103">Windows Forms controls do not sort when they are data-bound.</span></span> <span data-ttu-id="c85ad-104">並べ替えられたデータを表示するには、並べ替えをサポートするデータソースを使用し、データソースの並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="c85ad-104">To display sorted data, use a data source that supports sorting and then have the data source sort it.</span></span> <span data-ttu-id="c85ad-105">並べ替えをサポートするデータソースは、データビュー、データビューマネージャー、および並べ替えられた配列です。</span><span class="sxs-lookup"><span data-stu-id="c85ad-105">Data sources that support sorting are data views, data view managers, and sorted arrays.</span></span>  
  
 <span data-ttu-id="c85ad-106">コントロールがデータバインドされていない場合は、並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="c85ad-106">If the control is not data-bound, you can sort it.</span></span>  
  
### <a name="to-sort-the-list"></a><span data-ttu-id="c85ad-107">リストを並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="c85ad-107">To sort the list</span></span>  
  
1. <span data-ttu-id="c85ad-108">`Sorted` プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="c85ad-108">Set the `Sorted` property to `true`.</span></span>  
  
     <span data-ttu-id="c85ad-109">この設定により、既存のすべてのリスト項目が並べ替えられた順序で再配置されます。</span><span class="sxs-lookup"><span data-stu-id="c85ad-109">This setting repositions all existing list items in sorted order.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85ad-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c85ad-110">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [<span data-ttu-id="c85ad-111">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="c85ad-111">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="c85ad-112">方法: Windows フォームの ComboBox、ListBox、または CheckedListBox コントロールに項目を追加または削除する</span><span class="sxs-lookup"><span data-stu-id="c85ad-112">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="c85ad-113">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="c85ad-113">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [<span data-ttu-id="c85ad-114">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="c85ad-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
