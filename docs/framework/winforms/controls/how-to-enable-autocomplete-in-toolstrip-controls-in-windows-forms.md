---
title: '方法: Windows フォームで ToolStrip コントロールの AutoComplete を有効にします。'
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
ms.openlocfilehash: d7919bf87444ef6c4a64ee236356e762da14853f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941480"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a><span data-ttu-id="d5f65-102">方法: Windows フォームで ToolStrip コントロールの AutoComplete を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d5f65-102">How to: Enable AutoComplete in ToolStrip Controls in Windows Forms</span></span>
<span data-ttu-id="d5f65-103">次の手順を組み合わせて、<xref:System.Windows.Forms.ToolStripLabel>で、<xref:System.Windows.Forms.ToolStripComboBox>を削除できる最近など、アイテムの一覧を表示する Web サイトにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d5f65-103">The following procedure combines a <xref:System.Windows.Forms.ToolStripLabel> with a <xref:System.Windows.Forms.ToolStripComboBox> that can be dropped down to show a list of items, such as recently visited Web sites.</span></span> <span data-ttu-id="d5f65-104">リスト内の項目のいずれかの最初の文字に一致する文字を入力すると、項目がすぐに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d5f65-104">If the user types a character that matches the first character of one of the items in the list, the item is immediately displayed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5f65-105">オート コンプリートが連携`ToolStrip`など従来のコントロールで動作するのと同じ方法でコントロール<xref:System.Windows.Forms.ComboBox>と<xref:System.Windows.Forms.TextBox>します。</span><span class="sxs-lookup"><span data-stu-id="d5f65-105">Automatic completion works with `ToolStrip` controls in the same way that it works with traditional controls such as <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a><span data-ttu-id="d5f65-106">ToolStrip コントロールの AutoComplete を有効にするには</span><span class="sxs-lookup"><span data-stu-id="d5f65-106">To enable AutoComplete in a ToolStrip control</span></span>  
  
1. <span data-ttu-id="d5f65-107">作成、<xref:System.Windows.Forms.ToolStrip>を制御し、項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5f65-107">Create a <xref:System.Windows.Forms.ToolStrip> control and add items to it.</span></span>  
  
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
  
2. <span data-ttu-id="d5f65-108">設定、<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>プロパティのラベルとコンボ ボックスに<xref:System.Windows.Forms.ToolStripItemOverflow.Never>一覧が常に、フォームのサイズに関係なく使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d5f65-108">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the label and the combo box to <xref:System.Windows.Forms.ToolStripItemOverflow.Never> so that the list is always available regardless of the form's size.</span></span>  
  
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
  
3. <span data-ttu-id="d5f65-109">項目のコレクションに単語を追加、<xref:System.Windows.Forms.ToolStripComboBox>コントロール。</span><span class="sxs-lookup"><span data-stu-id="d5f65-109">Add words to the Items collection of the <xref:System.Windows.Forms.ToolStripComboBox> control.</span></span>  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. <span data-ttu-id="d5f65-110">設定、<xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A>コンボ ボックスのプロパティ<xref:System.Windows.Forms.AutoCompleteMode.Append>します。</span><span class="sxs-lookup"><span data-stu-id="d5f65-110">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteMode.Append>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. <span data-ttu-id="d5f65-111">設定、<xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A>コンボ ボックスのプロパティ<xref:System.Windows.Forms.AutoCompleteSource.ListItems>します。</span><span class="sxs-lookup"><span data-stu-id="d5f65-111">Set the <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> property of the combo box to <xref:System.Windows.Forms.AutoCompleteSource.ListItems>.</span></span>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5f65-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d5f65-112">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [<span data-ttu-id="d5f65-113">ToolStrip コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="d5f65-113">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="d5f65-114">ToolStrip コントロールのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d5f65-114">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="d5f65-115">ToolStrip テクノロジの概要</span><span class="sxs-lookup"><span data-stu-id="d5f65-115">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
