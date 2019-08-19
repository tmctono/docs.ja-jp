---
title: '方法: MDI 子フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- CSharp
- CPP
- VB
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: f5e8682caf658d159f044528f040b99676355448
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040108"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="2e75d-102">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="2e75d-102">How to: Create MDI child forms</span></span>

<span data-ttu-id="2e75d-103">MDI 子フォームは、ユーザー操作の中心であるため、[マルチドキュメントインターフェイス (mdi) アプリケーション](multiple-document-interface-mdi-applications.md)の重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="2e75d-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="2e75d-104">次の手順では、Visual Studio を使用して、ほとんどのワードプロセッシングアプリケーションと<xref:System.Windows.Forms.RichTextBox>同様に、コントロールを表示する MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-104">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="2e75d-105">コントロールを<xref:System.Windows.Forms.DataGridView>コントロール<xref:System.Windows.Forms>やコントロールの組み合わせなどの他のコントロールに置き換えることにより、さまざまな可能性を持つ mdi 子ウィンドウ (および拡張機能、mdi アプリケーション) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-105">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="2e75d-106">MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="2e75d-106">Create MDI child forms</span></span>

1. <span data-ttu-id="2e75d-107">Visual Studio で新しい Windows フォームアプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-107">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="2e75d-108">フォームの **[プロパティ**] ウィンドウで<xref:System.Windows.Forms.Form.IsMdiContainer%2A> 、 `WindowsState`プロパティをに`true` 、プロパティをに`Maximized`設定します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-108">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="2e75d-109">これによって、フォームが子ウィンドウの MDI コンテナーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-109">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="2e75d-110">  `Toolbox` から、<xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2e75d-110">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="2e75d-111">その`Text`プロパティを**File**に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-111">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="2e75d-112">**Items**プロパティの横にある省略記号 ([...]) をクリックし、[**追加**] をクリックして、2つの子ツールストリップメニュー項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-112">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="2e75d-113">これらの項目の プロパティを新規およびウィンドウに設定し`Text`ます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-113">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="2e75d-114">**ソリューション エクスプローラー**で、プロジェクトを右クリックし、 **[追加]**  >  **[新しい項目]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-114">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="2e75d-115">[**新しい項目の追加**] ダイアログボックスで、[ **Windows フォーム**] (Visual Basic またC#は visual では) を選択するか、 C++[**テンプレート**] ペインの [**アプリケーション (.net)** ] (visual の場合) を Windows フォームます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-115">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="2e75d-116">[**名前**] ボックスに、「 **Form2**」という形式で名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-116">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="2e75d-117">[**開く**] を選択して、フォームをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-117">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e75d-118">この手順で作成した、MDI 子フォームは、標準の Windows フォームです。</span><span class="sxs-lookup"><span data-stu-id="2e75d-118">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="2e75d-119">そのため、フォームの透明度を制御できる <xref:System.Windows.Forms.Form.Opacity%2A> プロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="2e75d-119">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="2e75d-120">ただし、<xref:System.Windows.Forms.Form.Opacity%2A> プロパティは最上位レベルのウィンドウ用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="2e75d-120">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="2e75d-121">描画に関する問題が発生する可能性があるため、MDI 子フォームと共に使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2e75d-121">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="2e75d-122">このフォームは、MDI 子フォーム用のテンプレートになります。</span><span class="sxs-lookup"><span data-stu-id="2e75d-122">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="2e75d-123">**Windows フォームデザイナー**が開き、 **Form2**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-123">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="2e75d-124">**ツールボックス**から、 **RichTextBox**コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2e75d-124">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="2e75d-125">[**プロパティ**] ウィンドウ`Anchor`で、プロパティを [ `Dock`上]、[左]、プロパティを [**塗りつぶし**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-125">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="2e75d-126">これにより、フォームがサイズ変更された場合でも、<xref:System.Windows.Forms.RichTextBox> コントロールが MDI 子フォームの領域を完全に塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="2e75d-126">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="2e75d-127">[**新規**] メニュー項目をダブルクリックし<xref:System.Windows.Forms.Control.Click>て、そのイベントハンドラーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-127">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="2e75d-128">次のようなコードを挿入して、ユーザーが [**新規**] メニュー項目をクリックしたときに新しい MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-128">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2e75d-129">次の例では、イベント ハンドラーが `MenuItem2` の <xref:System.Windows.Forms.Control.Click> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-129">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="2e75d-130">アプリケーションアーキテクチャの詳細によっては、**新しい**メニュー項目が表示さ`MenuItem2`れない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e75d-130">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

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

   <span data-ttu-id="2e75d-131">でC++、Form1 の先頭`#include`に次のディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-131">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="2e75d-132">[**プロパティ**] ウィンドウの上部にあるドロップダウンリストで、[**ファイル**] メニューストリップに対応するメニューストリップを選択<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>し、プロパティをウィンドウ<xref:System.Windows.Forms.ToolStripMenuItem>に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-132">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="2e75d-133">これにより、**ウィンドウ**メニューで、アクティブな子ウィンドウの横にチェックマークが付いた、開いている MDI 子ウィンドウの一覧を保持できます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-133">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="2e75d-134">**F5** キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-134">Press **F5** to run the application.</span></span> <span data-ttu-id="2e75d-135">[**ファイル**] メニューの [**新規**作成] を選択すると、新しい MDI 子フォームを作成できます。この子フォームは、[**ウィンドウ**] メニュー項目に記録されます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-135">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e75d-136">MDI 子フォームが (通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持っていて、(通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持つ MDI 親フォーム内で開いている場合、<xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティ (およびオプションで <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティ) を設定した場合に、メニュー項目が自動的にマージされます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-136">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="2e75d-137">両方の <xref:System.Windows.Forms.MainMenu> コンポーネント、および子フォームのすべてのメニュー項目の <xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティを <xref:System.Windows.Forms.MenuMerge.MergeItems> に設定します。</span><span class="sxs-lookup"><span data-stu-id="2e75d-137">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="2e75d-138">また、<xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティを設定し、両方のメニューのメニュー項目が指定した順序で表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2e75d-138">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="2e75d-139">さらに、MDI 親フォームを閉じた時に、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントが発生する前に、各 MDI 子フォームが <xref:System.Windows.Forms.Form.Closing> イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-139">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="2e75d-140">MDI 子の <xref:System.Windows.Forms.Form.Closing> イベントをキャンセルしても、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの発生を防ぐことはできません。ただし、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの <xref:System.ComponentModel.CancelEventArgs> 引数は `true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-140">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="2e75d-141">  <xref:System.ComponentModel.CancelEventArgs> 引数を `false` に設定することで、MDI 親レポートとすべての MDI 子フォームを強制的に閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="2e75d-141">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e75d-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e75d-142">See also</span></span>

- [<span data-ttu-id="2e75d-143">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2e75d-143">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="2e75d-144">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="2e75d-144">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="2e75d-145">方法: アクティブな MDI 子フォームを特定する</span><span class="sxs-lookup"><span data-stu-id="2e75d-145">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="2e75d-146">方法: アクティブな MDI 子フォームにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="2e75d-146">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="2e75d-147">方法: MDI 子フォームを配置する</span><span class="sxs-lookup"><span data-stu-id="2e75d-147">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
