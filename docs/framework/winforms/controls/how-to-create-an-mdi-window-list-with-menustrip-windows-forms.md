---
title: '方法 : MenuStrip を使用して MDI ウィンドウの一覧を作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731008"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="b5940-102">方法 : MenuStrip を使用して MDI ウィンドウの一覧を作成する (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="b5940-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="b5940-103">マルチドキュメントインターフェイス (MDI) を使用して、複数のドキュメントを同時に開くことができるアプリケーションを作成し、ドキュメント間でコンテンツをコピーして貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b5940-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="b5940-104">この手順では、親の [ウィンドウ] メニューにあるすべてのアクティブな子フォームの一覧を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5940-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="b5940-105">MenuStrip で MDI ウィンドウの一覧を作成するには</span><span class="sxs-lookup"><span data-stu-id="b5940-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="b5940-106">フォームを作成し、その <xref:System.Windows.Forms.Form.IsMdiContainer%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5940-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="b5940-107">フォームに <xref:System.Windows.Forms.MenuStrip> を追加します。</span><span class="sxs-lookup"><span data-stu-id="b5940-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="b5940-108"><xref:System.Windows.Forms.MenuStrip> にトップレベルのメニュー項目を2つ追加し、それらの <xref:System.Windows.Forms.Control.Text%2A> プロパティを `&File` および `&Window`に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5940-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="b5940-109">サブメニュー項目を `&File` メニュー項目に追加し、その <xref:System.Windows.Forms.ToolStripItem.Text%2A> プロパティを「`&Open`」に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5940-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="b5940-110"><xref:System.Windows.Forms.MenuStrip> の <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> プロパティを `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>に設定します。</span><span class="sxs-lookup"><span data-stu-id="b5940-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="b5940-111">プロジェクトにフォームを追加し、必要なコントロールを追加します (別の <xref:System.Windows.Forms.MenuStrip>など)。</span><span class="sxs-lookup"><span data-stu-id="b5940-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="b5940-112"><xref:System.Windows.Forms.Control.Click> の `&New` の <xref:System.Windows.Forms.ToolStripMenuItem> イベントにイベント ハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5940-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="b5940-113">イベントハンドラー内に次のようなコードを挿入し、`Form1`の MDI 子として `Form2` の新しいインスタンスを作成して表示します。</span><span class="sxs-lookup"><span data-stu-id="b5940-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="b5940-114">イベントハンドラーを登録するには、`&New`<xref:System.Windows.Forms.ToolStripMenuItem> に次のようなコードを配置します。</span><span class="sxs-lookup"><span data-stu-id="b5940-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5940-115">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b5940-115">Compiling the Code</span></span>  
 <span data-ttu-id="b5940-116">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5940-116">This example requires:</span></span>  
  
- <span data-ttu-id="b5940-117"><xref:System.Windows.Forms.Form> と `Form1` という名前の 2 つの `Form2` コントロール。</span><span class="sxs-lookup"><span data-stu-id="b5940-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="b5940-118"><xref:System.Windows.Forms.MenuStrip> 上の `Form1` という名前の `menuStrip1` コントロールと、<xref:System.Windows.Forms.MenuStrip> 上の `Form2` という名前の `menuStrip2` コントロール。</span><span class="sxs-lookup"><span data-stu-id="b5940-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="b5940-119"><xref:System?displayProperty=nameWithType> アセンブリおよび <xref:System.Windows.Forms?displayProperty=nameWithType> アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="b5940-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5940-120">参照</span><span class="sxs-lookup"><span data-stu-id="b5940-120">See also</span></span>

- [<span data-ttu-id="b5940-121">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="b5940-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="b5940-122">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="b5940-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="b5940-123">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="b5940-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
