---
title: オプションのリストを表示するための Windows フォーム コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, listing options
- option lists in Windows Forms
ms.assetid: 5bc064c7-bc1f-4b62-8f4b-252f864b118e
ms.openlocfilehash: 92d5f330fbd5269e15bf52dc11ad998939aa18e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009072"
---
# <a name="windows-forms-controls-used-to-list-options"></a><span data-ttu-id="aede7-102">オプションのリストを表示するための Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="aede7-102">Windows Forms Controls Used to List Options</span></span>
<span data-ttu-id="aede7-103">選択できるオプションの一覧をユーザーに提供する場合は、Windows フォームにさまざまなコントロールを追加できます。</span><span class="sxs-lookup"><span data-stu-id="aede7-103">You can add a variety of controls to a Windows Form if you want to provide users with a list of options to choose from.</span></span> <span data-ttu-id="aede7-104">量に応じて入力すると、ユーザーを制限することができますを追加する、<xref:System.Windows.Forms.ListBox>コントロール、<xref:System.Windows.Forms.ComboBox>コントロール、または<xref:System.Windows.Forms.CheckedListBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="aede7-104">Depending on how much you want to restrict your users' input, you can add a <xref:System.Windows.Forms.ListBox> control, a <xref:System.Windows.Forms.ComboBox> control, or a <xref:System.Windows.Forms.CheckedListBox> control.</span></span> <span data-ttu-id="aede7-105">最適などのコントロールがニーズを判断するのにには、次のリンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="aede7-105">Use the following links to determine which control best suits your needs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aede7-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="aede7-106">In This Section</span></span>  
 [<span data-ttu-id="aede7-107">ListBox の代わりに Windows フォーム ComboBox を使用する場合</span><span class="sxs-lookup"><span data-stu-id="aede7-107">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 <span data-ttu-id="aede7-108">Windows フォームの制限とニーズに応じて適切なリストに基づくコントロールをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aede7-108">Recommends an appropriate list-based control depending on the needs and restrictions of your Windows Form.</span></span>  
  
 [<span data-ttu-id="aede7-109">方法: 特定のアクセス フォーム ComboBox、ListBox、または CheckedListBox コントロールの項目を Windows</span><span class="sxs-lookup"><span data-stu-id="aede7-109">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 <span data-ttu-id="aede7-110">プログラムで指定した位置にリスト内のどのアイテムが表示されますかを判断する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aede7-110">Gives instructions for programmatically determining which item in a list appears in a given position.</span></span>  
  
 [<span data-ttu-id="aede7-111">方法: 追加および削除項目、Windows からフォーム ComboBox、ListBox、または CheckedListBox コントロール</span><span class="sxs-lookup"><span data-stu-id="aede7-111">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)  
 <span data-ttu-id="aede7-112">追加またはコントロールの項目のリストから項目を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aede7-112">Gives instructions for adding or removing items from a control's list of items.</span></span>  
  
 [<span data-ttu-id="aede7-113">方法: Windows フォーム ComboBox、ListBox、または CheckedListBox コントロールのルックアップ テーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="aede7-113">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](create-a-lookup-table-for-a-wf-combobox-listbox.md)  
 <span data-ttu-id="aede7-114">表示して便利な形式のフォーム データを格納する方法についてを説明します。</span><span class="sxs-lookup"><span data-stu-id="aede7-114">Gives directions for displaying and storing form data in useful formats.</span></span>  
  
 [<span data-ttu-id="aede7-115">方法: Windows フォームの ComboBox または ListBox コントロールをデータにバインドします。</span><span class="sxs-lookup"><span data-stu-id="aede7-115">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>](how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 <span data-ttu-id="aede7-116">一覧ベースのコントロールをデータ ソースにバインドするための手順を示します。</span><span class="sxs-lookup"><span data-stu-id="aede7-116">Gives directions for binding a list-based control to a data source.</span></span>  
  
 [<span data-ttu-id="aede7-117">方法: Windows の内容を並べ替えるフォーム ComboBox、ListBox、または CheckedListBox コントロール</span><span class="sxs-lookup"><span data-stu-id="aede7-117">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 <span data-ttu-id="aede7-118">データ ソースにある一覧のデータを並べ替える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="aede7-118">Explains how to sort list data at its data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aede7-119">参照</span><span class="sxs-lookup"><span data-stu-id="aede7-119">Reference</span></span>  
 <xref:System.Windows.Forms.CheckedListBox>  
 <span data-ttu-id="aede7-120">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aede7-120">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.ComboBox>  
 <span data-ttu-id="aede7-121">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aede7-121">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.ListBox>  
 <span data-ttu-id="aede7-122">このクラスについて説明し、すべてのメンバーへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aede7-122">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aede7-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="aede7-123">Related Sections</span></span>  
 [<span data-ttu-id="aede7-124">CheckedListBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="aede7-124">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)  
 <span data-ttu-id="aede7-125">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aede7-125">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="aede7-126">ComboBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="aede7-126">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)  
 <span data-ttu-id="aede7-127">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aede7-127">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="aede7-128">ListBox コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="aede7-128">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)  
 <span data-ttu-id="aede7-129">このコントロールについて、および主な機能とプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aede7-129">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="aede7-130">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="aede7-130">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="aede7-131">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="aede7-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
