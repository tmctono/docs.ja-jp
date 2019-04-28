---
title: 'チュートリアル: 標準メニュー項目をフォームに用意する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: b4957a3f2efcb31594806a188e3d3bb10c2dac09
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792211"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="8ad0f-102">チュートリアル: 標準メニュー項目をフォームに用意する</span><span class="sxs-lookup"><span data-stu-id="8ad0f-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="8ad0f-103">フォームの標準のメニューを <xref:System.Windows.Forms.MenuStrip> コントロールに提供できます。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="8ad0f-104">このチュートリアルを使用する方法について説明する<xref:System.Windows.Forms.MenuStrip>標準メニューを作成するコントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="8ad0f-105">フォームは、ユーザーがメニュー項目を選択したときにも応答します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="8ad0f-106">このチュートリアルで、次のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
- <span data-ttu-id="8ad0f-107">Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-107">Creating a Windows Forms project.</span></span>  
  
- <span data-ttu-id="8ad0f-108">標準メニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-108">Creating a standard menu.</span></span>  
  
- <span data-ttu-id="8ad0f-109">作成、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
- <span data-ttu-id="8ad0f-110">メニュー項目の選択を処理します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="8ad0f-111">標準のメニューにメニュー項目の選択内容を表示するフォームが完了したら、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="8ad0f-112">このトピックのコードを単一のリストとしてコピーするには、「[方法:フォームに標準メニュー項目を提供](how-to-provide-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ad0f-113">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8ad0f-114">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8ad0f-115">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-115">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8ad0f-116">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8ad0f-116">Prerequisites</span></span>  
 <span data-ttu-id="8ad0f-117">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-117">In order to complete this walkthrough, you will need:</span></span>  
  
- <span data-ttu-id="8ad0f-118">作成し、Visual Studio がインストールされているコンピューターで Windows フォーム アプリケーション プロジェクトを実行できる十分なアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="8ad0f-119">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="8ad0f-119">Creating the Project</span></span>  
 <span data-ttu-id="8ad0f-120">最初にプロジェクトを作成し、フォームを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="8ad0f-121">プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ad0f-121">To create the project</span></span>  
  
1. <span data-ttu-id="8ad0f-122">いう Windows アプリケーション プロジェクトを作成する**StandardMenuForm** (**ファイル** > **新規** > **プロジェクト** >  **Visual c#** または**Visual Basic** > **クラシック デスクトップ** > **Windows フォームアプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-122">Create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="8ad0f-123">Windows フォーム デザイナーでフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-123">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="8ad0f-124">標準メニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-124">Creating a Standard Menu</span></span>  
 <span data-ttu-id="8ad0f-125">Windows フォーム デザイナーで自動的に設定できる、<xref:System.Windows.Forms.MenuStrip>標準メニュー項目を制御します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-125">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="8ad0f-126">標準メニューを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ad0f-126">To create a standard menu</span></span>  
  
1. <span data-ttu-id="8ad0f-127">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.MenuStrip>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2. <span data-ttu-id="8ad0f-128">をクリックして、<xref:System.Windows.Forms.MenuStrip>コントロールのスマート タグ グリフ (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) を選択および**標準項目の挿入**します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-128">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="8ad0f-129"><xref:System.Windows.Forms.MenuStrip>標準メニュー項目コントロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-129">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3. <span data-ttu-id="8ad0f-130">をクリックして、**ファイル**メニュー項目をその既定のメニュー項目と対応するアイコンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-130">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="8ad0f-131">StatusStrip コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-131">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="8ad0f-132">使用して、 <xref:System.Windows.Forms.StatusStrip> Windows フォーム アプリケーションの状態を表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-132">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="8ad0f-133">現在の例では、ユーザーが選択したメニュー項目の表示、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-133">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="8ad0f-134">StatusStrip コントロールを作成するには</span><span class="sxs-lookup"><span data-stu-id="8ad0f-134">To create a StatusStrip control</span></span>  
  
1. <span data-ttu-id="8ad0f-135">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.StatusStrip>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="8ad0f-136"><xref:System.Windows.Forms.StatusStrip>コントロールが自動的にフォームの下部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-136">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2. <span data-ttu-id="8ad0f-137">をクリックして、<xref:System.Windows.Forms.StatusStrip>コントロールのドロップダウン ボタンと選択**StatusLabel**を追加する、<xref:System.Windows.Forms.ToolStripStatusLabel>への制御、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-137">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="8ad0f-138">処理項目の選択</span><span class="sxs-lookup"><span data-stu-id="8ad0f-138">Handling Item Selection</span></span>  
 <span data-ttu-id="8ad0f-139">処理、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>イベント、ユーザーがメニュー項目を選択するときに応答します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-139">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="8ad0f-140">項目の選択を処理するには</span><span class="sxs-lookup"><span data-stu-id="8ad0f-140">To handle item selection</span></span>  
  
1. <span data-ttu-id="8ad0f-141">をクリックして、**ファイル**メニュー項目の作成で作成した標準メニュー セクション。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-141">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2. <span data-ttu-id="8ad0f-142">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-142">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="8ad0f-143">ダブルクリックして、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>イベント。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-143">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="8ad0f-144">Windows フォーム デザイナーのイベント ハンドラーの生成、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>イベント。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-144">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4. <span data-ttu-id="8ad0f-145">イベント ハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-145">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5. <span data-ttu-id="8ad0f-146">挿入、`UpdateStatus`ユーティリティ メソッドの定義をフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-146">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="8ad0f-147">チェックポイント</span><span class="sxs-lookup"><span data-stu-id="8ad0f-147">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="8ad0f-148">フォームをテストするには</span><span class="sxs-lookup"><span data-stu-id="8ad0f-148">To test your form</span></span>  
  
1. <span data-ttu-id="8ad0f-149">コンパイルして、フォームを実行するには、f5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-149">Press F5 to compile and run your form.</span></span>  
  
2. <span data-ttu-id="8ad0f-150">をクリックして、**ファイル**メニュー項目、メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-150">Click the **File** menu item to open the menu.</span></span>  
  
3. <span data-ttu-id="8ad0f-151">**ファイル**メニューで、これを選択する項目のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-151">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="8ad0f-152"><xref:System.Windows.Forms.StatusStrip>コントロールは、選択した項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-152">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8ad0f-153">次の手順</span><span class="sxs-lookup"><span data-stu-id="8ad0f-153">Next Steps</span></span>  
 <span data-ttu-id="8ad0f-154">このチュートリアルでは、標準メニューを持つフォームを作成しました。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-154">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="8ad0f-155">使用することができます、<xref:System.Windows.Forms.ToolStrip>の他のさまざまな目的のコントロール ファミリ。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-155">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
- <span data-ttu-id="8ad0f-156">ショートカット メニューを使用してコントロールを作成<xref:System.Windows.Forms.ContextMenuStrip>です。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-156">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="8ad0f-157">詳細については、次を参照してください。 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-157">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
- <span data-ttu-id="8ad0f-158">ドッキングのマルチ ドキュメント インターフェイス (MDI) フォームを作成する<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-158">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="8ad0f-159">詳細については、「[チュートリアル:メニューのマージと ToolStrip コントロールを MDI フォームを作成する](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-159">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
- <span data-ttu-id="8ad0f-160">与える、<xref:System.Windows.Forms.ToolStrip>プロフェッショナルな外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-160">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="8ad0f-161">詳細については、「[方法 :アプリケーションの ToolStrip レンダラーを設定](how-to-set-the-toolstrip-renderer-for-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="8ad0f-161">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad0f-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ad0f-162">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="8ad0f-163">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="8ad0f-163">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
