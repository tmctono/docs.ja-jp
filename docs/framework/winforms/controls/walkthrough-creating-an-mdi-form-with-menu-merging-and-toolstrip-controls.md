---
title: 'チュートリアル: メニューのマージと ToolStrip コントロールのある MDI フォームを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: 5853760231cbece27805923c009d83e16c9b0a5e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211556"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="34498-102">チュートリアル: メニューのマージと ToolStrip コントロールのある MDI フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="34498-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>

<span data-ttu-id="34498-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、マルチ ドキュメント インターフェイス (MDI) アプリケーションをサポートし、<xref:System.Windows.Forms.MenuStrip> コントロールはメニューの結合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="34498-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="34498-104">MDI フォームは、<xref:System.Windows.Forms.ToolStrip> コントロールもサポートします。</span><span class="sxs-lookup"><span data-stu-id="34498-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="34498-105">このチュートリアルを使用する方法について説明<xref:System.Windows.Forms.ToolStripPanel>を MDI フォームでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="34498-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="34498-106">フォームは、子メニューをマージするメニューもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="34498-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="34498-107">このチュートリアルで、次のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="34498-107">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="34498-108">Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-108">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="34498-109">フォームのメイン メニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-109">Creating the main menu for your form.</span></span> <span data-ttu-id="34498-110">メニューの実際の名前は異なります。</span><span class="sxs-lookup"><span data-stu-id="34498-110">The actual name of the menu will vary.</span></span>

- <span data-ttu-id="34498-111">追加、<xref:System.Windows.Forms.ToolStripPanel>への制御、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="34498-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>

- <span data-ttu-id="34498-112">子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-112">Creating a child form.</span></span>

- <span data-ttu-id="34498-113">配置<xref:System.Windows.Forms.ToolStripPanel>z オーダーでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="34498-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>

<span data-ttu-id="34498-114">メニューのマージと移動をサポートする MDI フォームが完成したら、<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>

<span data-ttu-id="34498-115">このトピックのコードを単一のリストとしてコピーするには、「[方法:メニューのマージと ToolStrip コントロールを MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="34498-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34498-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34498-116">Prerequisites</span></span>

<span data-ttu-id="34498-117">Visual Studio でこのチュートリアルを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34498-117">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="34498-118">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="34498-118">Create the project</span></span>

1. <span data-ttu-id="34498-119">Visual Studio と呼ばれる Windows アプリケーション プロジェクトを作成**mdi フォーム**(**ファイル** > **新規** > **プロジェクト**  >  **Visual C#** または**Visual Basic** > **クラシック デスクトップ** >  **Windows フォーム アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="34498-119">In Visual Studio, create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="34498-120">Windows フォーム デザイナーでフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="34498-120">In the Windows Forms Designer, select the form.</span></span>

3. <span data-ttu-id="34498-121">[プロパティ] ウィンドウでの値を設定、<xref:System.Windows.Forms.Form.IsMdiContainer%2A>に`true`します。</span><span class="sxs-lookup"><span data-stu-id="34498-121">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>

## <a name="create-the-main-menu"></a><span data-ttu-id="34498-122">メイン メニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-122">Create the main menu</span></span>

<span data-ttu-id="34498-123">親 MDI フォームには、メイン メニューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="34498-123">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="34498-124">メイン メニューがという名前の項目の 1 つの menu**ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="34498-124">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="34498-125">**ウィンドウ**メニュー項目を子フォームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="34498-125">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="34498-126">子フォームのメニュー項目は、メイン メニューにマージされます。</span><span class="sxs-lookup"><span data-stu-id="34498-126">Menu items from child forms are merged into the main menu.</span></span>

1. <span data-ttu-id="34498-127">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.MenuStrip>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="34498-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>

2. <span data-ttu-id="34498-128">追加、<xref:System.Windows.Forms.ToolStripMenuItem>を<xref:System.Windows.Forms.MenuStrip>を制御し、名前を**ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="34498-128">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>

3. <span data-ttu-id="34498-129"><xref:System.Windows.Forms.MenuStrip> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="34498-129">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

4. <span data-ttu-id="34498-130">[プロパティ] ウィンドウでの値を設定、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティを`ToolStripMenuItem1`します。</span><span class="sxs-lookup"><span data-stu-id="34498-130">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>

5. <span data-ttu-id="34498-131">追加するサブ項目、**ウィンドウ**メニュー項目と、名前、サブ項目**新規**します。</span><span class="sxs-lookup"><span data-stu-id="34498-131">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>

6. <span data-ttu-id="34498-132">[プロパティ] ウィンドウで次のようにクリックします。**イベント**します。</span><span class="sxs-lookup"><span data-stu-id="34498-132">In the Properties window, click **Events**.</span></span>

7. <span data-ttu-id="34498-133">ダブルクリックして、<xref:System.Windows.Forms.ToolStripItem.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="34498-133">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

     <span data-ttu-id="34498-134">Windows フォーム デザイナーのイベント ハンドラーの生成、<xref:System.Windows.Forms.ToolStripItem.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="34498-134">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>

8. <span data-ttu-id="34498-135">イベント ハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="34498-135">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="34498-136">ToolStripPanel コントロールをツールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="34498-136">Add the ToolStripPanel control to the Toolbox</span></span>

<span data-ttu-id="34498-137">使用すると<xref:System.Windows.Forms.MenuStrip>コントロールを MDI フォームが必要で、<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-137">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="34498-138">追加する必要があります、<xref:System.Windows.Forms.ToolStripPanel>への制御、**ツールボックス**Windows フォーム デザイナーで、MDI フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-138">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="34498-139">開く、**ツールボックス**、 をクリックし、**すべての Windows フォーム** タブを使用できる Windows フォーム コントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="34498-139">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>

2. <span data-ttu-id="34498-140">ショートカット メニューを右クリックして**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="34498-140">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>

3. <span data-ttu-id="34498-141">**ツールボックス アイテムの選択** ダイアログ ボックスで、下にスクロール、**名前**列が表示されるまで**ToolStripPanel**します。</span><span class="sxs-lookup"><span data-stu-id="34498-141">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>

4. <span data-ttu-id="34498-142">チェック ボックスをオン**ToolStripPanel**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="34498-142">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>

     <span data-ttu-id="34498-143"><xref:System.Windows.Forms.ToolStripPanel>コントロールに表示され、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="34498-143">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>

## <a name="create-a-child-form"></a><span data-ttu-id="34498-144">子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-144">Create a child form</span></span>

<span data-ttu-id="34498-145">この手順では、独自に持つ別の子フォーム クラスを定義します<xref:System.Windows.Forms.MenuStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-145">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="34498-146">このフォームのメニュー項目は、親フォームのマージされます。</span><span class="sxs-lookup"><span data-stu-id="34498-146">The menu items for this form are merged with those of the parent form.</span></span>

1. <span data-ttu-id="34498-147">という名前の新しいフォームを追加`ChildForm`をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="34498-147">Add a new form named `ChildForm` to the project.</span></span>

     <span data-ttu-id="34498-148">詳細については、「[方法 :Windows フォーム プロジェクトを追加する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="34498-148">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>

2. <span data-ttu-id="34498-149">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.MenuStrip>子フォームにコントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-149">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>

3. <span data-ttu-id="34498-150">をクリックして、<xref:System.Windows.Forms.MenuStrip>コントロールのスマート タグ グリフ (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))、し、**アイテムの編集**します。</span><span class="sxs-lookup"><span data-stu-id="34498-150">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>

4. <span data-ttu-id="34498-151">**Items コレクション エディター**  ダイアログ ボックスで、新しい追加<xref:System.Windows.Forms.ToolStripMenuItem>という名前の**ChildMenuItem**子メニューにします。</span><span class="sxs-lookup"><span data-stu-id="34498-151">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>

     <span data-ttu-id="34498-152">詳細については、次を参照してください。 [ToolStrip Items コレクション エディター](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="34498-152">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>

## <a name="test-the-form"></a><span data-ttu-id="34498-153">フォームをテストします。</span><span class="sxs-lookup"><span data-stu-id="34498-153">Test the form</span></span>

1. <span data-ttu-id="34498-154">キーを押して**F5**をコンパイルして、フォームを実行します。</span><span class="sxs-lookup"><span data-stu-id="34498-154">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="34498-155">をクリックして、**ウィンドウ**メニューを開き、クリックしてメニュー項目**新規**します。</span><span class="sxs-lookup"><span data-stu-id="34498-155">Click the **Window** menu item to open the menu, and then click **New**.</span></span>

     <span data-ttu-id="34498-156">新しい子フォームは、フォームの MDI クライアント領域に作成されます。</span><span class="sxs-lookup"><span data-stu-id="34498-156">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="34498-157">子フォームのメニューは、メイン メニューにマージされます。</span><span class="sxs-lookup"><span data-stu-id="34498-157">The child form's menu is merged with the main menu.</span></span>

3. <span data-ttu-id="34498-158">子フォームを閉じます。</span><span class="sxs-lookup"><span data-stu-id="34498-158">Close the child form.</span></span>

     <span data-ttu-id="34498-159">子フォームのメニューは、メイン メニューから削除されます。</span><span class="sxs-lookup"><span data-stu-id="34498-159">The child form's menu is removed from the main menu.</span></span>

4. <span data-ttu-id="34498-160">クリックして**新規**何回か。</span><span class="sxs-lookup"><span data-stu-id="34498-160">Click **New** several times.</span></span>

     <span data-ttu-id="34498-161">子フォームが自動的に下に表示されます、**ウィンドウ**メニュー項目のため、<xref:System.Windows.Forms.MenuStrip>コントロールの<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="34498-161">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>

## <a name="add-toolstrip-support"></a><span data-ttu-id="34498-162">ToolStrip のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="34498-162">Add ToolStrip support</span></span>

<span data-ttu-id="34498-163">この手順で、4 つを追加、 <xref:System.Windows.Forms.ToolStrip> MDI 親フォームのコントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-163">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="34498-164">各<xref:System.Windows.Forms.ToolStrip>内でコントロールを追加、<xref:System.Windows.Forms.ToolStripPanel>コントロールで、フォームの端にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="34498-164">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>

1. <span data-ttu-id="34498-165">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.ToolStripPanel>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="34498-165">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>

2. <span data-ttu-id="34498-166"><xref:System.Windows.Forms.ToolStripPanel>コントロールが選択されている場合、ダブルクリックして、<xref:System.Windows.Forms.ToolStrip>を制御、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="34498-166">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>

     <span data-ttu-id="34498-167">A<xref:System.Windows.Forms.ToolStrip>でコントロールを作成、<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-167">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

3. <span data-ttu-id="34498-168"><xref:System.Windows.Forms.ToolStripPanel> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="34498-168">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

4. <span data-ttu-id="34498-169">[プロパティ] ウィンドウでのコントロールの値を変更<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Left>します。</span><span class="sxs-lookup"><span data-stu-id="34498-169">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>

     <span data-ttu-id="34498-170"><xref:System.Windows.Forms.ToolStripPanel>メイン メニューの下に、フォームの左側にドッキングを制御します。</span><span class="sxs-lookup"><span data-stu-id="34498-170">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="34498-171">MDI クライアント領域のサイズに合わせて、<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-171">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>

5. <span data-ttu-id="34498-172">手順 1. ~ 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="34498-172">Repeat steps 1 through 4.</span></span>

     <span data-ttu-id="34498-173">新しいドッキング<xref:System.Windows.Forms.ToolStripPanel>フォームの上部をコントロールします。</span><span class="sxs-lookup"><span data-stu-id="34498-173">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>

     <span data-ttu-id="34498-174"><xref:System.Windows.Forms.ToolStripPanel>コントロールがメインのメニューの下には、最初の右側にドッキングされている<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-174">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="34498-175">この手順は、正しく配置の z オーダーの重要性を示しています。<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-175">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

6. <span data-ttu-id="34498-176">さらに 2 つの手順 1. ~ 4. を繰り返します<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-176">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>

     <span data-ttu-id="34498-177">新しいドッキング<xref:System.Windows.Forms.ToolStripPanel>右、フォームの下部にあるコントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-177">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>

## <a name="arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="34498-178">ToolStripPanel コントロールを Z オーダーによる配置します。</span><span class="sxs-lookup"><span data-stu-id="34498-178">Arrange ToolStripPanel controls by Z-order</span></span>

<span data-ttu-id="34498-179">位置、ドッキングされた<xref:System.Windows.Forms.ToolStripPanel>MDI フォーム上のコントロールは、z オーダーでコントロールの位置によって決まります。</span><span class="sxs-lookup"><span data-stu-id="34498-179">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="34498-180">ドキュメント アウトライン ウィンドウでコントロールの z オーダーを簡単に配置できます。</span><span class="sxs-lookup"><span data-stu-id="34498-180">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>

1. <span data-ttu-id="34498-181">**ビュー**  メニューのをクリックして**その他の Windows**、 をクリックし、**ドキュメント アウトライン**します。</span><span class="sxs-lookup"><span data-stu-id="34498-181">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>

     <span data-ttu-id="34498-182">配置、<xref:System.Windows.Forms.ToolStripPanel>前の手順からのコントロールは非標準です。</span><span class="sxs-lookup"><span data-stu-id="34498-182">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="34498-183">これは、z オーダーが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="34498-183">This is because the z-order is not correct.</span></span> <span data-ttu-id="34498-184">ドキュメント アウトライン ウィンドウを使用すると、コントロールの z オーダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="34498-184">Use the Document Outline window to change the z-order of the controls.</span></span>

2. <span data-ttu-id="34498-185">ドキュメント アウトライン ウィンドウで、次のように選択します。 **ToolStripPanel4**します。</span><span class="sxs-lookup"><span data-stu-id="34498-185">In the Document Outline window, select **ToolStripPanel4**.</span></span>

3. <span data-ttu-id="34498-186">下向きの矢印ボタンをクリックするまで繰り返し、 **ToolStripPanel4**はリストの下部に。</span><span class="sxs-lookup"><span data-stu-id="34498-186">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>

     <span data-ttu-id="34498-187">**ToolStripPanel4**コントロールが他のコントロールの下に、フォームの下部にドッキングされています。</span><span class="sxs-lookup"><span data-stu-id="34498-187">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>

4. <span data-ttu-id="34498-188">選択**ToolStripPanel2**します。</span><span class="sxs-lookup"><span data-stu-id="34498-188">Select **ToolStripPanel2**.</span></span>

5. <span data-ttu-id="34498-189">一覧で 3 つ目のコントロールを配置する 1 回の下向きの矢印ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="34498-189">Click the down-arrow button one time to position the control third in the list.</span></span>

     <span data-ttu-id="34498-190">**ToolStripPanel2**コントロールとその他のコントロールの上のメイン メニューの下には、フォームの上部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="34498-190">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>

6. <span data-ttu-id="34498-191">さまざまなコントロール、**ドキュメント アウトライン**ウィンドウし、z オーダーで別の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="34498-191">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="34498-192">Z オーダーのドッキングされたコントロールの配置への影響に注意してください。</span><span class="sxs-lookup"><span data-stu-id="34498-192">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="34498-193">CTRL + Z を使用して、または**を元に戻す**上、**編集**変更を元に戻す メニュー。</span><span class="sxs-lookup"><span data-stu-id="34498-193">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>

## <a name="checkpoint---test-your-form"></a><span data-ttu-id="34498-194">チェックポイント - フォームをテストします。</span><span class="sxs-lookup"><span data-stu-id="34498-194">Checkpoint - test your form</span></span>

1. <span data-ttu-id="34498-195">キーを押して**F5**をコンパイルして、フォームを実行します。</span><span class="sxs-lookup"><span data-stu-id="34498-195">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="34498-196">グリップをクリックして、<xref:System.Windows.Forms.ToolStrip>を制御し、フォーム上の別の位置にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="34498-196">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>

     <span data-ttu-id="34498-197">ドラッグすることができます、<xref:System.Windows.Forms.ToolStrip>から 1 つのコントロール<xref:System.Windows.Forms.ToolStripPanel>を別のコントロール。</span><span class="sxs-lookup"><span data-stu-id="34498-197">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>

## <a name="next-steps"></a><span data-ttu-id="34498-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="34498-198">Next steps</span></span>

<span data-ttu-id="34498-199">このチュートリアルで MDI 親フォームを作成した<xref:System.Windows.Forms.ToolStrip>コントロールとメニューのマージします。</span><span class="sxs-lookup"><span data-stu-id="34498-199">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="34498-200">使用することができます、<xref:System.Windows.Forms.ToolStrip>の他のさまざまな目的のコントロール ファミリ。</span><span class="sxs-lookup"><span data-stu-id="34498-200">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="34498-201">ショートカット メニューを使用してコントロールを作成<xref:System.Windows.Forms.ContextMenuStrip>です。</span><span class="sxs-lookup"><span data-stu-id="34498-201">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="34498-202">詳細については、次を参照してください。 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="34498-202">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="34498-203">標準のメニューが自動的に設定されたフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="34498-203">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="34498-204">詳細については、「[チュートリアル:フォームに標準メニュー項目を用意する](walkthrough-providing-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="34498-204">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="34498-205">与える、<xref:System.Windows.Forms.ToolStrip>プロフェッショナルな外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="34498-205">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="34498-206">詳細については、「[方法 :アプリケーションの ToolStrip レンダラーを設定](how-to-set-the-toolstrip-renderer-for-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="34498-206">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="34498-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="34498-207">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="34498-208">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="34498-208">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="34498-209">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="34498-209">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="34498-210">方法: MDI ドロップダウン メニューに MenuStrip を挿入します。</span><span class="sxs-lookup"><span data-stu-id="34498-210">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="34498-211">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="34498-211">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
