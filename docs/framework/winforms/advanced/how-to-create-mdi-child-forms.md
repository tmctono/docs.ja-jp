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
ms.openlocfilehash: fbc92c03da69dd452f35e5b4e00cd4a9ca17e252
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211181"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="a709b-102">方法: MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a709b-102">How to: Create MDI child forms</span></span>

<span data-ttu-id="a709b-103">MDI 子フォームの重要な要素を[マルチ ドキュメント インターフェイス (MDI) アプリケーション](multiple-document-interface-mdi-applications.md)ユーザーの操作の中心となるためです。</span><span class="sxs-lookup"><span data-stu-id="a709b-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="a709b-104">次の手順では、表示する MDI 子フォームを作成する Visual Studio を使用します、<xref:System.Windows.Forms.RichTextBox>コントロール、ほとんどのワード プロセッシング アプリケーションに似ています。</span><span class="sxs-lookup"><span data-stu-id="a709b-104">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="a709b-105"><xref:System.Windows.Forms> コントロールを、<xref:System.Windows.Forms.DataGridView> コントロールやコントロールを組み合わせたその他のコントロールで置き換えることで、さまざまな可能性のある MDI 子ウィンドウ (およびその拡張としての MDI アプリケーション) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a709b-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="a709b-106">MDI 子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a709b-106">Create MDI child forms</span></span>

1. <span data-ttu-id="a709b-107">新しい Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a709b-107">Create a new Windows Forms project.</span></span> <span data-ttu-id="a709b-108">**プロパティ Windows** 、フォームの次のように設定します。 その<xref:System.Windows.Forms.Form.IsMdiContainer%2A>プロパティを`true`、およびその`WindowsState`プロパティを`Maximized`します。</span><span class="sxs-lookup"><span data-stu-id="a709b-108">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="a709b-109">これによって、フォームが子ウィンドウの MDI コンテナーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="a709b-109">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="a709b-110">
  `Toolbox\` から、<xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a709b-110">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="a709b-111">設定の`Text`プロパティを**ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="a709b-111">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="a709b-112">の隣にある省略記号 (...) をクリックして、**項目**プロパティ、およびクリック**追加**2 つの子ツール ストリップのメニュー項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="a709b-112">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="a709b-113">設定、`Text`プロパティにこれらの項目を**新規**と**ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="a709b-113">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="a709b-114">**ソリューション エクスプ ローラー**、プロジェクトを右クリックし、] をポイント**追加**、し、[**新しい項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="a709b-114">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>

5. <span data-ttu-id="a709b-115">**新しい項目の追加**ダイアログ ボックスで、 **Windows フォーム**(Visual basic または Visual c#) または**Windows フォーム アプリケーション (.NET)** (で[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)])、から**テンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a709b-115">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="a709b-116">**名前**ボックスに、フォームの名前**Form2**します。</span><span class="sxs-lookup"><span data-stu-id="a709b-116">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="a709b-117">をクリックして、**オープン**フォームをプロジェクトに追加するボタン。</span><span class="sxs-lookup"><span data-stu-id="a709b-117">Click the **Open** button to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a709b-118">この手順で作成した、MDI 子フォームは、標準の Windows フォームです。</span><span class="sxs-lookup"><span data-stu-id="a709b-118">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="a709b-119">そのため、フォームの透明度を制御できる <xref:System.Windows.Forms.Form.Opacity%2A> プロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="a709b-119">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="a709b-120">ただし、<xref:System.Windows.Forms.Form.Opacity%2A> プロパティは最上位レベルのウィンドウ用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="a709b-120">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="a709b-121">描画に関する問題が発生する可能性があるため、MDI 子フォームと共に使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a709b-121">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="a709b-122">このフォームは、MDI 子フォーム用のテンプレートになります。</span><span class="sxs-lookup"><span data-stu-id="a709b-122">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="a709b-123">**Windows フォーム デザイナー**が開き、表示する**Form2**します。</span><span class="sxs-lookup"><span data-stu-id="a709b-123">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="a709b-124">**ツールボックス**、ドラッグ、 **RichTextBox**コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="a709b-124">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="a709b-125">**プロパティ**ウィンドウで、設定、`Anchor`プロパティを**Top、Left**と`Dock`プロパティを**入力**します。</span><span class="sxs-lookup"><span data-stu-id="a709b-125">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="a709b-126">これにより、フォームがサイズ変更された場合でも、<xref:System.Windows.Forms.RichTextBox> コントロールが MDI 子フォームの領域を完全に塗りつぶします。</span><span class="sxs-lookup"><span data-stu-id="a709b-126">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="a709b-127">ダブルクリックして、**新規**メニュー項目を作成する、<xref:System.Windows.Forms.Control.Click>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a709b-127">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="a709b-128">ユーザーがクリックしたときに、新しい MDI 子フォームを作成するには、次のようなコードを挿入、**新規**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="a709b-128">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a709b-129">次の例では、イベント ハンドラーが `MenuItem2` の <xref:System.Windows.Forms.Control.Click> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="a709b-129">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="a709b-130">注意してください、アプリケーション アーキテクチャの仕様によって、**新規**メニュー項目ができない可能性があります`MenuItem2`します。</span><span class="sxs-lookup"><span data-stu-id="a709b-130">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

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

   <span data-ttu-id="a709b-131">C++、次の追加`#include`ディレクティブを Form1.h の先頭。</span><span class="sxs-lookup"><span data-stu-id="a709b-131">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="a709b-132">上部にあるドロップダウン リストで、**プロパティ**ウィンドウに対応するメニュー ストリップを選択、**ファイル** メニュー ストリップと、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティ ウィンドウを<xref:System.Windows.Forms.ToolStripMenuItem>します。</span><span class="sxs-lookup"><span data-stu-id="a709b-132">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="a709b-133">これにより、**ウィンドウ** メニューのアクティブな子ウィンドウの横にチェック マークが付いた開いている MDI 子ウィンドウのリストを維持します。</span><span class="sxs-lookup"><span data-stu-id="a709b-133">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="a709b-134">**F5** キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a709b-134">Press **F5** to run the application.</span></span> <span data-ttu-id="a709b-135">選択して**新規**から、**ファイル**] メニューの [新しい MDI 子フォームでの追跡、保持を作成することができます、**ウィンドウ**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="a709b-135">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a709b-136">MDI 子フォームが (通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持っていて、(通常はメニュー項目のメニュー構造を持つ) <xref:System.Windows.Forms.MainMenu> コンポーネントを持つ MDI 親フォーム内で開いている場合、<xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティ (およびオプションで <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティ) を設定した場合に、メニュー項目が自動的にマージされます。</span><span class="sxs-lookup"><span data-stu-id="a709b-136">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="a709b-137">両方の <xref:System.Windows.Forms.MainMenu> コンポーネント、および子フォームのすべてのメニュー項目の <xref:System.Windows.Forms.MenuItem.MergeType%2A> プロパティを <xref:System.Windows.Forms.MenuMerge.MergeItems> に設定します。</span><span class="sxs-lookup"><span data-stu-id="a709b-137">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="a709b-138">また、<xref:System.Windows.Forms.MenuItem.MergeOrder%2A> プロパティを設定し、両方のメニューのメニュー項目が指定した順序で表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a709b-138">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="a709b-139">さらに、MDI 親フォームを閉じた時に、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントが発生する前に、各 MDI 子フォームが <xref:System.Windows.Forms.Form.Closing> イベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="a709b-139">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="a709b-140">MDI 子の <xref:System.Windows.Forms.Form.Closing> イベントをキャンセルしても、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの発生を防ぐことはできません。ただし、MDI 親の <xref:System.Windows.Forms.Form.Closing> イベントの <xref:System.ComponentModel.CancelEventArgs> 引数は `true` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a709b-140">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="a709b-141">
  <xref:System.ComponentModel.CancelEventArgs> 引数を `false\` に設定することで、MDI 親レポートとすべての MDI 子フォームを強制的に閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="a709b-141">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a709b-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a709b-142">See also</span></span>

- [<span data-ttu-id="a709b-143">マルチ ドキュメント インターフェイス (MDI) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a709b-143">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="a709b-144">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="a709b-144">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="a709b-145">方法: アクティブな MDI 子フォームを特定する</span><span class="sxs-lookup"><span data-stu-id="a709b-145">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="a709b-146">方法: アクティブな MDI 子フォームにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="a709b-146">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="a709b-147">方法: MDI 子フォームを配置する</span><span class="sxs-lookup"><span data-stu-id="a709b-147">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
