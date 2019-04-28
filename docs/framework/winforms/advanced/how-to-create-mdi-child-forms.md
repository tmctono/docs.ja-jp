---
title: '方法: MDI 子フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 73f2004470d5d1da04199af75832cefd6348ce18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937671"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="9aebf-102">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="9aebf-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="9aebf-103">MDI 子フォームの重要な要素を[マルチ ドキュメント インターフェイス (MDI) アプリケーション](multiple-document-interface-mdi-applications.md)ユーザーの操作の中心となるためです。</span><span class="sxs-lookup"><span data-stu-id="9aebf-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="9aebf-104">次の手順では、ほとんどのワード プロセッシング アプリケーションに似ている <xref:System.Windows.Forms.RichTextBox> コントロールを表示する MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="9aebf-105"><xref:System.Windows.Forms> コントロールを、<xref:System.Windows.Forms.DataGridView> コントロールやコントロールを組み合わせたその他のコントロールで置き換えることで、さまざまな可能性のある MDI 子ウィンドウ (およびその拡張としての MDI アプリケーション) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="9aebf-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9aebf-106">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9aebf-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9aebf-107">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9aebf-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9aebf-108">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9aebf-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="9aebf-109">MDI 子フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="9aebf-109">To create MDI child forms</span></span>  
  
1. <span data-ttu-id="9aebf-110">新しい Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="9aebf-111">**プロパティ Windows** 、フォームの次のように設定します。 その<xref:System.Windows.Forms.Form.IsMdiContainer%2A>プロパティを`true`、およびその`WindowsState`プロパティを`Maximized`します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="9aebf-112">これによって、フォームが子ウィンドウの MDI コンテナーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="9aebf-112">This designates the form as an MDI container for child windows.</span></span>  
  
2. <span data-ttu-id="9aebf-113">`Toolbox` から、<xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="9aebf-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="9aebf-114">設定の`Text`プロパティを**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-114">Set its `Text` property to **File**.</span></span>  
  
3. <span data-ttu-id="9aebf-115">の隣にある省略記号 (...) をクリックして、**項目**プロパティ、およびクリック**追加**2 つの子ツール ストリップのメニュー項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="9aebf-116">設定、`Text`プロパティにこれらの項目を**新規**と**ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4. <span data-ttu-id="9aebf-117">**ソリューション エクスプ ローラー**、プロジェクトを右クリックし、] をポイント**追加**、し、[**新しい項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5. <span data-ttu-id="9aebf-118">**新しい項目の追加**ダイアログ ボックスで、 **Windows フォーム**(Visual basic または Visual c#) または**Windows フォーム アプリケーション (.NET)** (で[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、から**テンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="9aebf-118">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="9aebf-119">**名前**ボックスに、フォームの名前**Form2**します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="9aebf-120">をクリックして、**オープン**フォームをプロジェクトに追加するボタン。</span><span class="sxs-lookup"><span data-stu-id="9aebf-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9aebf-121">この手順で作成した、MDI 子フォームは、標準の Windows フォームです。</span><span class="sxs-lookup"><span data-stu-id="9aebf-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="9aebf-122">そのため、フォームの透明度を制御できる <xref:System.Windows.Forms.Form.Opacity%2A> プロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="9aebf-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="9aebf-123">ただし、<xref:System.Windows.Forms.Form.Opacity%2A> プロパティは最上位レベルのウィンドウ用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="9aebf-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="9aebf-124">描画に関する問題が発生する可能性があるため、MDI 子フォームと共に使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9aebf-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="9aebf-125">このフォームは、MDI 子フォーム用のテンプレートになります。</span><span class="sxs-lookup"><span data-stu-id="9aebf-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="9aebf-126">**Windows フォーム デザイナー**が開き、表示する**Form2**します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6. <span data-ttu-id="9aebf-127">**ツールボックス**、ドラッグ、 **RichTextBox**コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="9aebf-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7. <span data-ttu-id="9aebf-128">**プロパティ**ウィンドウで、設定、`Anchor`プロパティを**Top、Left**と`Dock`プロパティを**入力**します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="9aebf-129">これにより、フォームがサイズ変更された場合でも、<xref:System.Windows.Forms.RichTextBox> コントロールが MDI 子フォームの領域を完全に塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="9aebf-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8. <span data-ttu-id="9aebf-130">ダブルクリックして、**新規**メニュー項目を作成する、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="9aebf-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="9aebf-131">ユーザーがクリックしたときに、新しい MDI 子フォームを作成するには、次のようなコードを挿入、**新規**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="9aebf-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9aebf-132">次の例では、イベント ハンドラーが `MenuItem2` の <xref:System.Windows.Forms.Control.Click> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="9aebf-133">注意してください、アプリケーション アーキテクチャの仕様によって、**新規**メニュー項目ができない可能性があります`MenuItem2`します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     <span data-ttu-id="9aebf-134">[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)] で、次の `#include` ディレクティブを Form1.h の先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="9aebf-135">上部にあるドロップダウン リストで、**プロパティ**ウィンドウに対応するメニュー ストリップを選択、**ファイル** メニュー ストリップと、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティ ウィンドウを<xref:System.Windows.Forms.ToolStripMenuItem>します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="9aebf-136">これにより、**ウィンドウ** メニューのアクティブな子ウィンドウの横にチェック マークが付いた開いている MDI 子ウィンドウのリストを維持します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="9aebf-137">F5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-137">Press F5 to run the application.</span></span> <span data-ttu-id="9aebf-138">選択して**新規**から、**ファイル**] メニューの [新しい MDI 子フォームでの追跡、保持を作成することができます、**ウィンドウ**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="9aebf-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9aebf-139">MDI 子フォームが (通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持っていて、(通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持つ MDI 親フォーム内で開いている場合、<xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティ (およびオプションで <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティ) を設定した場合に、メニュー項目が自動的にマージされます。</span><span class="sxs-lookup"><span data-stu-id="9aebf-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="9aebf-140">両方の <xref:System.Windows.Forms.MainMenu> コンポーネント、および子フォームのすべてのメニュー項目の <xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティを <xref:System.Windows.Forms.MenuMerge.MergeItems> に設定します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="9aebf-141">また、<xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティを設定し、両方のメニューのメニュー項目が指定した順序で表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="9aebf-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="9aebf-142">さらに、MDI 親フォームを閉じた時に、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントが発生する前に、各 MDI 子フォームが <xref:System.Windows.Forms.Form.Closing> イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="9aebf-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="9aebf-143">MDI 子の <xref:System.Windows.Forms.Form.Closing> イベントをキャンセルしても、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの発生を防ぐことはできません。ただし、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの <xref:System.ComponentModel.CancelEventArgs> 引数は `true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9aebf-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="9aebf-144"><xref:System.ComponentModel.CancelEventArgs> 引数を `false` に設定することで、MDI 親レポートとすべての MDI 子フォームを強制的に閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="9aebf-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aebf-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="9aebf-145">See also</span></span>

- [<span data-ttu-id="9aebf-146">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="9aebf-146">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="9aebf-147">方法: MDI 親フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-147">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="9aebf-148">方法: アクティブな MDI 子を決定します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-148">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="9aebf-149">方法: アクティブな MDI 子ウィンドウにデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-149">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="9aebf-150">方法: MDI 子フォームを配置します。</span><span class="sxs-lookup"><span data-stu-id="9aebf-150">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
