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
ms.openlocfilehash: 9c4195cc6f26dd10f22bacb5bcba9ca2a078499c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160629"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="00075-102">チュートリアル: メニューのマージと ToolStrip コントロールのある MDI フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="00075-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="00075-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 名前空間は、マルチ ドキュメント インターフェイス (MDI) アプリケーションをサポートし、<xref:System.Windows.Forms.MenuStrip> コントロールはメニューの結合をサポートします。</span><span class="sxs-lookup"><span data-stu-id="00075-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="00075-104">MDI フォームは、<xref:System.Windows.Forms.ToolStrip> コントロールもサポートします。</span><span class="sxs-lookup"><span data-stu-id="00075-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="00075-105">このチュートリアルを使用する方法について説明<xref:System.Windows.Forms.ToolStripPanel>を MDI フォームでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="00075-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="00075-106">フォームは、子メニューをマージするメニューもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="00075-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="00075-107">このチュートリアルで、次のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="00075-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="00075-108">Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="00075-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="00075-109">フォームのメイン メニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="00075-109">Creating the main menu for your form.</span></span> <span data-ttu-id="00075-110">メニューの実際の名前は異なります。</span><span class="sxs-lookup"><span data-stu-id="00075-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="00075-111">追加、<xref:System.Windows.Forms.ToolStripPanel>への制御、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="00075-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="00075-112">子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="00075-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="00075-113">配置<xref:System.Windows.Forms.ToolStripPanel>z オーダーでコントロールできます。</span><span class="sxs-lookup"><span data-stu-id="00075-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="00075-114">メニューのマージと移動をサポートする MDI フォームが完成したら、<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="00075-115">このトピックのコードを単一のリストとしてコピーするには、「[方法:メニューのマージと ToolStrip コントロールを MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="00075-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00075-116">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="00075-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="00075-117">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00075-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="00075-118">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00075-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="00075-119">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="00075-119">Prerequisites</span></span>  
 <span data-ttu-id="00075-120">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00075-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="00075-121">作成し、Visual Studio がインストールされているコンピューターで Windows フォーム アプリケーション プロジェクトを実行できる十分なアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="00075-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="00075-122">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="00075-122">Creating the Project</span></span>  
 <span data-ttu-id="00075-123">最初にプロジェクトを作成し、フォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="00075-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="00075-124">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="00075-124">To create the project</span></span>  
  
1.  <span data-ttu-id="00075-125">呼ばれる Windows アプリケーション プロジェクトを作成**mdi フォーム**(**ファイル** > **新規** > **プロジェクト** > **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォーム アプリケーション**).</span><span class="sxs-lookup"><span data-stu-id="00075-125">Create a Windows Application project called **MdiForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="00075-126">Windows フォーム デザイナーでフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="00075-126">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="00075-127">[プロパティ] ウィンドウでの値を設定、<xref:System.Windows.Forms.Form.IsMdiContainer%2A>に`true`します。</span><span class="sxs-lookup"><span data-stu-id="00075-127">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="00075-128">メイン メニューの作成</span><span class="sxs-lookup"><span data-stu-id="00075-128">Creating the Main Menu</span></span>  
 <span data-ttu-id="00075-129">親 MDI フォームには、メイン メニューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="00075-129">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="00075-130">メイン メニューがという名前の項目の 1 つの menu**ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="00075-130">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="00075-131">**ウィンドウ**メニュー項目を子フォームを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="00075-131">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="00075-132">子フォームのメニュー項目は、メイン メニューにマージされます。</span><span class="sxs-lookup"><span data-stu-id="00075-132">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="00075-133">メイン メニューを作成するには</span><span class="sxs-lookup"><span data-stu-id="00075-133">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="00075-134">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.MenuStrip>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="00075-134">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="00075-135">追加、<xref:System.Windows.Forms.ToolStripMenuItem>を<xref:System.Windows.Forms.MenuStrip>を制御し、名前を**ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="00075-135">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="00075-136"><xref:System.Windows.Forms.MenuStrip> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="00075-136">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="00075-137">[プロパティ] ウィンドウでの値を設定、<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティを`ToolStripMenuItem1`します。</span><span class="sxs-lookup"><span data-stu-id="00075-137">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="00075-138">追加するサブ項目、**ウィンドウ**メニュー項目と、名前、サブ項目**新規**します。</span><span class="sxs-lookup"><span data-stu-id="00075-138">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="00075-139">[プロパティ] ウィンドウで次のようにクリックします。**イベント**します。</span><span class="sxs-lookup"><span data-stu-id="00075-139">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="00075-140">ダブルクリックして、<xref:System.Windows.Forms.ToolStripItem.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="00075-140">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="00075-141">Windows フォーム デザイナーのイベント ハンドラーの生成、<xref:System.Windows.Forms.ToolStripItem.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="00075-141">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="00075-142">イベント ハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="00075-142">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="00075-143">ToolStripPanel コントロールをツールボックスに追加します。</span><span class="sxs-lookup"><span data-stu-id="00075-143">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="00075-144">使用すると<xref:System.Windows.Forms.MenuStrip>コントロールを MDI フォームが必要で、<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-144">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="00075-145">追加する必要があります、<xref:System.Windows.Forms.ToolStripPanel>への制御、**ツールボックス**Windows フォーム デザイナーで、MDI フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="00075-145">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="00075-146">ToolStripPanel コントロールをツールボックスに追加するには</span><span class="sxs-lookup"><span data-stu-id="00075-146">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="00075-147">開く、**ツールボックス**、 をクリックし、**すべての Windows フォーム** タブを使用できる Windows フォーム コントロールを表示します。</span><span class="sxs-lookup"><span data-stu-id="00075-147">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="00075-148">ショートカット メニューを右クリックして**アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="00075-148">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="00075-149">**ツールボックス アイテムの選択** ダイアログ ボックスで、下にスクロール、**名前**列が表示されるまで**ToolStripPanel**します。</span><span class="sxs-lookup"><span data-stu-id="00075-149">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="00075-150">チェック ボックスをオン**ToolStripPanel**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="00075-150">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="00075-151"><xref:System.Windows.Forms.ToolStripPanel>コントロールに表示され、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="00075-151">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="00075-152">子フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="00075-152">Creating a Child Form</span></span>  
 <span data-ttu-id="00075-153">この手順では、独自に持つ別の子フォーム クラスを定義します<xref:System.Windows.Forms.MenuStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-153">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="00075-154">このフォームのメニュー項目は、親フォームのマージされます。</span><span class="sxs-lookup"><span data-stu-id="00075-154">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="00075-155">子フォームを定義するには</span><span class="sxs-lookup"><span data-stu-id="00075-155">To define a child form</span></span>  
  
1.  <span data-ttu-id="00075-156">という名前の新しいフォームを追加`ChildForm`をプロジェクトにします。</span><span class="sxs-lookup"><span data-stu-id="00075-156">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="00075-157">詳細については、「[方法 :Windows フォーム プロジェクトを追加する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="00075-157">For more information, see [How to: Add Windows Forms to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="00075-158">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.MenuStrip>子フォームにコントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-158">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="00075-159">をクリックして、<xref:System.Windows.Forms.MenuStrip>コントロールのスマート タグ グリフ (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))、し、**アイテムの編集**します。</span><span class="sxs-lookup"><span data-stu-id="00075-159">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="00075-160">**Items コレクション エディター**  ダイアログ ボックスで、新しい追加<xref:System.Windows.Forms.ToolStripMenuItem>という名前の**ChildMenuItem**子メニューにします。</span><span class="sxs-lookup"><span data-stu-id="00075-160">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="00075-161">詳細については、次を参照してください。 [ToolStrip Items コレクション エディター](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="00075-161">For more information, see [ToolStrip Items Collection Editor](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="00075-162">フォームのテスト</span><span class="sxs-lookup"><span data-stu-id="00075-162">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="00075-163">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="00075-163">To test your form</span></span>  
  
1.  <span data-ttu-id="00075-164">コンパイルして、フォームを実行するには、f5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="00075-164">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="00075-165">をクリックして、**ウィンドウ**メニューを開き、クリックしてメニュー項目**新規**します。</span><span class="sxs-lookup"><span data-stu-id="00075-165">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="00075-166">新しい子フォームは、フォームの MDI クライアント領域に作成されます。</span><span class="sxs-lookup"><span data-stu-id="00075-166">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="00075-167">子フォームのメニューは、メイン メニューにマージされます。</span><span class="sxs-lookup"><span data-stu-id="00075-167">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="00075-168">子フォームを閉じます。</span><span class="sxs-lookup"><span data-stu-id="00075-168">Close the child form.</span></span>  
  
     <span data-ttu-id="00075-169">子フォームのメニューは、メイン メニューから削除されます。</span><span class="sxs-lookup"><span data-stu-id="00075-169">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="00075-170">クリックして**新規**何回か。</span><span class="sxs-lookup"><span data-stu-id="00075-170">Click **New** several times.</span></span>  
  
     <span data-ttu-id="00075-171">子フォームが自動的に下に表示されます、**ウィンドウ**メニュー項目のため、<xref:System.Windows.Forms.MenuStrip>コントロールの<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>プロパティが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="00075-171">The child forms are automatically listed under the **Window** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="00075-172">ToolStrip のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="00075-172">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="00075-173">この手順で、4 つを追加、 <xref:System.Windows.Forms.ToolStrip> MDI 親フォームのコントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-173">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="00075-174">各<xref:System.Windows.Forms.ToolStrip>内でコントロールを追加、<xref:System.Windows.Forms.ToolStripPanel>コントロールで、フォームの端にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="00075-174">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="00075-175">MDI 親フォームに ToolStrip コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="00075-175">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="00075-176">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.ToolStripPanel>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="00075-176">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="00075-177"><xref:System.Windows.Forms.ToolStripPanel>コントロールが選択されている場合、ダブルクリックして、<xref:System.Windows.Forms.ToolStrip>を制御、**ツールボックス**します。</span><span class="sxs-lookup"><span data-stu-id="00075-177">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="00075-178">A<xref:System.Windows.Forms.ToolStrip>でコントロールを作成、<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-178">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="00075-179"><xref:System.Windows.Forms.ToolStripPanel> コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="00075-179">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="00075-180">[プロパティ] ウィンドウでのコントロールの値を変更<xref:System.Windows.Forms.Control.Dock%2A>プロパティを<xref:System.Windows.Forms.DockStyle.Left>します。</span><span class="sxs-lookup"><span data-stu-id="00075-180">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="00075-181"><xref:System.Windows.Forms.ToolStripPanel>メイン メニューの下に、フォームの左側にドッキングを制御します。</span><span class="sxs-lookup"><span data-stu-id="00075-181">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="00075-182">MDI クライアント領域のサイズに合わせて、<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-182">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="00075-183">手順 1. ~ 4. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="00075-183">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="00075-184">新しいドッキング<xref:System.Windows.Forms.ToolStripPanel>フォームの上部をコントロールします。</span><span class="sxs-lookup"><span data-stu-id="00075-184">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="00075-185"><xref:System.Windows.Forms.ToolStripPanel>コントロールがメインのメニューの下には、最初の右側にドッキングされている<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-185">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="00075-186">この手順は、正しく配置の z オーダーの重要性を示しています。<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-186">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="00075-187">さらに 2 つの手順 1. ~ 4. を繰り返します<xref:System.Windows.Forms.ToolStripPanel>コントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-187">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="00075-188">新しいドッキング<xref:System.Windows.Forms.ToolStripPanel>右、フォームの下部にあるコントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-188">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="00075-189">Z オーダーで ToolStripPanel コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="00075-189">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="00075-190">位置、ドッキングされた<xref:System.Windows.Forms.ToolStripPanel>MDI フォーム上のコントロールは、z オーダーでコントロールの位置によって決まります。</span><span class="sxs-lookup"><span data-stu-id="00075-190">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="00075-191">ドキュメント アウトライン ウィンドウでコントロールの z オーダーを簡単に配置できます。</span><span class="sxs-lookup"><span data-stu-id="00075-191">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="00075-192">Z オーダーで ToolStripPanel コントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="00075-192">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="00075-193">**ビュー**  メニューのをクリックして**その他の Windows**、 をクリックし、**ドキュメント アウトライン**します。</span><span class="sxs-lookup"><span data-stu-id="00075-193">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="00075-194">配置、<xref:System.Windows.Forms.ToolStripPanel>前の手順からのコントロールは非標準です。</span><span class="sxs-lookup"><span data-stu-id="00075-194">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="00075-195">これは、z オーダーが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="00075-195">This is because the z-order is not correct.</span></span> <span data-ttu-id="00075-196">ドキュメント アウトライン ウィンドウを使用すると、コントロールの z オーダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="00075-196">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="00075-197">ドキュメント アウトライン ウィンドウで、次のように選択します。 **ToolStripPanel4**します。</span><span class="sxs-lookup"><span data-stu-id="00075-197">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="00075-198">下向きの矢印ボタンをクリックするまで繰り返し、 **ToolStripPanel4**はリストの下部に。</span><span class="sxs-lookup"><span data-stu-id="00075-198">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="00075-199">**ToolStripPanel4**コントロールが他のコントロールの下に、フォームの下部にドッキングされています。</span><span class="sxs-lookup"><span data-stu-id="00075-199">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="00075-200">選択**ToolStripPanel2**します。</span><span class="sxs-lookup"><span data-stu-id="00075-200">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="00075-201">一覧で 3 つ目のコントロールを配置する 1 回の下向きの矢印ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="00075-201">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="00075-202">**ToolStripPanel2**コントロールとその他のコントロールの上のメイン メニューの下には、フォームの上部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="00075-202">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="00075-203">さまざまなコントロール、**ドキュメント アウトライン**ウィンドウし、z オーダーで別の位置に移動します。</span><span class="sxs-lookup"><span data-stu-id="00075-203">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="00075-204">Z オーダーのドッキングされたコントロールの配置への影響に注意してください。</span><span class="sxs-lookup"><span data-stu-id="00075-204">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="00075-205">CTRL + Z を使用して、または**を元に戻す**上、**編集**変更を元に戻す メニュー。</span><span class="sxs-lookup"><span data-stu-id="00075-205">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="00075-206">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="00075-206">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="00075-207">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="00075-207">To test your form</span></span>  
  
1.  <span data-ttu-id="00075-208">コンパイルして、フォームを実行するには、f5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="00075-208">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="00075-209">グリップをクリックして、<xref:System.Windows.Forms.ToolStrip>を制御し、フォーム上の別の位置にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="00075-209">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="00075-210">ドラッグすることができます、<xref:System.Windows.Forms.ToolStrip>から 1 つのコントロール<xref:System.Windows.Forms.ToolStripPanel>を別のコントロール。</span><span class="sxs-lookup"><span data-stu-id="00075-210">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="00075-211">次の手順</span><span class="sxs-lookup"><span data-stu-id="00075-211">Next Steps</span></span>  
 <span data-ttu-id="00075-212">このチュートリアルで MDI 親フォームを作成した<xref:System.Windows.Forms.ToolStrip>コントロールとメニューのマージします。</span><span class="sxs-lookup"><span data-stu-id="00075-212">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="00075-213">使用することができます、<xref:System.Windows.Forms.ToolStrip>の他のさまざまな目的のコントロール ファミリ。</span><span class="sxs-lookup"><span data-stu-id="00075-213">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="00075-214">ショートカット メニューを使用してコントロールを作成<xref:System.Windows.Forms.ContextMenuStrip>です。</span><span class="sxs-lookup"><span data-stu-id="00075-214">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="00075-215">詳細については、次を参照してください。 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="00075-215">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="00075-216">標準のメニューが自動的に設定されたフォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="00075-216">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="00075-217">詳細については、「[チュートリアル:フォームに標準メニュー項目を用意する](walkthrough-providing-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="00075-217">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="00075-218">与える、<xref:System.Windows.Forms.ToolStrip>プロフェッショナルな外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="00075-218">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="00075-219">詳細については、「[方法 :アプリケーションの ToolStrip レンダラーを設定](how-to-set-the-toolstrip-renderer-for-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="00075-219">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00075-220">関連項目</span><span class="sxs-lookup"><span data-stu-id="00075-220">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="00075-221">方法: MDI 親フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="00075-221">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="00075-222">方法: MDI 子フォームを作成する</span><span class="sxs-lookup"><span data-stu-id="00075-222">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="00075-223">方法: MDI ドロップダウン メニューに MenuStrip を挿入する</span><span class="sxs-lookup"><span data-stu-id="00075-223">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [<span data-ttu-id="00075-224">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="00075-224">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
