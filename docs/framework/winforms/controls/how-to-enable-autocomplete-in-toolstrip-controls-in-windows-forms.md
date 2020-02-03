---
title: '方法 : ToolStrip コントロールの AutoComplete を有効にする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: db411023ad624e4c3d60b09bdbd588c85f8e22d1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745507"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="52671-102">方法 : Windows フォームで ToolStrip コントロールの AutoComplete を有効にする</span><span class="sxs-lookup"><span data-stu-id="52671-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="52671-103">次の手順では、<xref:System.Windows.Forms.ToolStripLabel> と <xref:System.Windows.Forms.ToolStripComboBox> を結合して、最近アクセスした Web サイトなどの項目の一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="52671-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="52671-104">ユーザーがリスト内のいずれかの項目の最初の文字と一致する文字を入力すると、その項目がすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="52671-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52671-105">オートコンプリートは、<xref:System.Windows.Forms.ComboBox> や <xref:System.Windows.Forms.TextBox>などの従来のコントロールと同じように、`ToolStrip` コントロールと連動します。</span><span class="sxs-lookup"><span data-stu-id="52671-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="52671-106">ToolStrip コントロールでオートコンプリートを有効にするには</span><span class="sxs-lookup"><span data-stu-id="52671-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1. <span data-ttu-id="52671-107"><xref:System.Windows.Forms.ToolStrip> コントロールを作成し、そのコントロールに項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="52671-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. <span data-ttu-id="52671-108">フォームのサイズに関係なく常に使用できるように、ラベルの [<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>] プロパティとコンボボックスを [<xref:System.Windows.Forms.ToolStripItemOverflow.Never>] に設定します。</span><span class="sxs-lookup"><span data-stu-id="52671-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. <span data-ttu-id="52671-109"><xref:System.Windows.Forms.ToolStripComboBox> コントロールの Items コレクションに単語を追加します。</span><span class="sxs-lookup"><span data-stu-id="52671-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. <span data-ttu-id="52671-110">コンボボックスの [<xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A>] プロパティを <xref:System.Windows.Forms.AutoCompleteMode.Append>に設定します。</span><span class="sxs-lookup"><span data-stu-id="52671-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. <span data-ttu-id="52671-111">コンボボックスの [<xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A>] プロパティを <xref:System.Windows.Forms.AutoCompleteSource.ListItems>に設定します。</span><span class="sxs-lookup"><span data-stu-id="52671-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="52671-112">参照</span><span class="sxs-lookup"><span data-stu-id="52671-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [<span data-ttu-id="52671-113">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="52671-113">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="52671-114">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="52671-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="52671-115">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="52671-115">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
