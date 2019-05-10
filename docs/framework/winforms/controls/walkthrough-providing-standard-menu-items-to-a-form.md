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
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211505"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="84a68-102">チュートリアル: 標準メニュー項目をフォームに用意する</span><span class="sxs-lookup"><span data-stu-id="84a68-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="84a68-103">フォームの標準のメニューを <xref:System.Windows.Forms.MenuStrip> コントロールに提供できます。</span><span class="sxs-lookup"><span data-stu-id="84a68-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="84a68-104">このチュートリアルを使用する方法について説明する<xref:System.Windows.Forms.MenuStrip>標準メニューを作成するコントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="84a68-105">フォームは、ユーザーがメニュー項目を選択したときにも応答します。</span><span class="sxs-lookup"><span data-stu-id="84a68-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="84a68-106">このチュートリアルで、次のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="84a68-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="84a68-107">Windows フォーム プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="84a68-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="84a68-108">標準メニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="84a68-108">Creating a standard menu.</span></span>

- <span data-ttu-id="84a68-109">作成、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="84a68-110">メニュー項目の選択を処理します。</span><span class="sxs-lookup"><span data-stu-id="84a68-110">Handling menu item selection.</span></span>

<span data-ttu-id="84a68-111">標準のメニューにメニュー項目の選択内容を表示するフォームが完了したら、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="84a68-112">このトピックのコードを単一のリストとしてコピーするには、「[方法:フォームに標準メニュー項目を提供](how-to-provide-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="84a68-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="84a68-113">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="84a68-113">Prerequisites</span></span>

<span data-ttu-id="84a68-114">Visual Studio でこのチュートリアルを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84a68-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="84a68-115">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="84a68-115">Create the project</span></span>

1. <span data-ttu-id="84a68-116">Visual Studio と呼ばれる Windows アプリケーション プロジェクトを作成**StandardMenuForm** (**ファイル** > **新規** > **プロジェクト**  >  **Visual C#** または**Visual Basic** > **クラシック デスクトップ** >  **Windows フォーム アプリケーション**)。</span><span class="sxs-lookup"><span data-stu-id="84a68-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="84a68-117">Windows フォーム デザイナーでフォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="84a68-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="84a68-118">標準のメニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="84a68-118">Create a standard menu</span></span>

<span data-ttu-id="84a68-119">Windows フォーム デザイナーで自動的に設定できる、<xref:System.Windows.Forms.MenuStrip>標準メニュー項目を制御します。</span><span class="sxs-lookup"><span data-stu-id="84a68-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="84a68-120">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.MenuStrip>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="84a68-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="84a68-121">をクリックして、<xref:System.Windows.Forms.MenuStrip>コントロールのスマート タグ グリフ (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) を選択および**標準項目の挿入**します。</span><span class="sxs-lookup"><span data-stu-id="84a68-121">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="84a68-122"><xref:System.Windows.Forms.MenuStrip>標準メニュー項目コントロールに設定します。</span><span class="sxs-lookup"><span data-stu-id="84a68-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="84a68-123">をクリックして、**ファイル**メニュー項目をその既定のメニュー項目と対応するアイコンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a68-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="84a68-124">StatusStrip コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="84a68-124">Create a StatusStrip control</span></span>

<span data-ttu-id="84a68-125">使用して、 <xref:System.Windows.Forms.StatusStrip> Windows フォーム アプリケーションの状態を表示するコントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="84a68-126">現在の例では、ユーザーが選択したメニュー項目の表示、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="84a68-127">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.StatusStrip>コントロールをフォームにします。</span><span class="sxs-lookup"><span data-stu-id="84a68-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="84a68-128"><xref:System.Windows.Forms.StatusStrip>コントロールが自動的にフォームの下部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="84a68-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="84a68-129">をクリックして、<xref:System.Windows.Forms.StatusStrip>コントロールのドロップダウン ボタンと選択**StatusLabel**を追加する、<xref:System.Windows.Forms.ToolStripStatusLabel>への制御、<xref:System.Windows.Forms.StatusStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="84a68-130">項目の選択を処理します。</span><span class="sxs-lookup"><span data-stu-id="84a68-130">Handle item selection</span></span>

<span data-ttu-id="84a68-131">処理、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>イベント、ユーザーがメニュー項目を選択するときに応答します。</span><span class="sxs-lookup"><span data-stu-id="84a68-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="84a68-132">をクリックして、**ファイル**メニュー項目の作成で作成した標準メニュー セクション。</span><span class="sxs-lookup"><span data-stu-id="84a68-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="84a68-133">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84a68-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="84a68-134">ダブルクリックして、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>イベント。</span><span class="sxs-lookup"><span data-stu-id="84a68-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="84a68-135">Windows フォーム デザイナーのイベント ハンドラーの生成、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>イベント。</span><span class="sxs-lookup"><span data-stu-id="84a68-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="84a68-136">イベント ハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="84a68-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="84a68-137">挿入、`UpdateStatus`ユーティリティ メソッドの定義をフォームに設定します。</span><span class="sxs-lookup"><span data-stu-id="84a68-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="84a68-138">チェックポイントのフォームをテストします。</span><span class="sxs-lookup"><span data-stu-id="84a68-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="84a68-139">キーを押して**F5**をコンパイルして、フォームを実行します。</span><span class="sxs-lookup"><span data-stu-id="84a68-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="84a68-140">をクリックして、**ファイル**メニュー項目、メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="84a68-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="84a68-141">**ファイル**メニューで、これを選択する項目のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84a68-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="84a68-142"><xref:System.Windows.Forms.StatusStrip>コントロールは、選択した項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="84a68-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="84a68-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="84a68-143">Next steps</span></span>

<span data-ttu-id="84a68-144">このチュートリアルでは、標準メニューを持つフォームを作成しました。</span><span class="sxs-lookup"><span data-stu-id="84a68-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="84a68-145">使用することができます、<xref:System.Windows.Forms.ToolStrip>の他のさまざまな目的のコントロール ファミリ。</span><span class="sxs-lookup"><span data-stu-id="84a68-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="84a68-146">ショートカット メニューを使用してコントロールを作成<xref:System.Windows.Forms.ContextMenuStrip>です。</span><span class="sxs-lookup"><span data-stu-id="84a68-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="84a68-147">詳細については、次を参照してください。 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="84a68-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="84a68-148">ドッキングのマルチ ドキュメント インターフェイス (MDI) フォームを作成する<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="84a68-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="84a68-149">詳細については、「[チュートリアル:メニューのマージと ToolStrip コントロールを MDI フォームを作成する](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="84a68-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="84a68-150">与える、<xref:System.Windows.Forms.ToolStrip>プロフェッショナルな外観を制御します。</span><span class="sxs-lookup"><span data-stu-id="84a68-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="84a68-151">詳細については、「[方法 :アプリケーションの ToolStrip レンダラーを設定](how-to-set-the-toolstrip-renderer-for-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="84a68-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84a68-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="84a68-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="84a68-153">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="84a68-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
