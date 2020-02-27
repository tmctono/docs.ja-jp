---
title: 'チュートリアル : 標準メニュー項目をフォームに用意する'
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
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628775"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="96579-102">チュートリアル : 標準メニュー項目をフォームに用意する</span><span class="sxs-lookup"><span data-stu-id="96579-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>

<span data-ttu-id="96579-103">フォームの標準のメニューを <xref:System.Windows.Forms.MenuStrip> コントロールに提供できます。</span><span class="sxs-lookup"><span data-stu-id="96579-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="96579-104">このチュートリアルでは、<xref:System.Windows.Forms.MenuStrip> コントロールを使用して標準メニューを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="96579-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="96579-105">フォームは、ユーザーがメニュー項目を選択したときにも応答します。</span><span class="sxs-lookup"><span data-stu-id="96579-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="96579-106">このチュートリアルでは、次のタスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="96579-106">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="96579-107">Windows フォームプロジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="96579-107">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="96579-108">標準メニューを作成する。</span><span class="sxs-lookup"><span data-stu-id="96579-108">Creating a standard menu.</span></span>

- <span data-ttu-id="96579-109"><xref:System.Windows.Forms.StatusStrip> コントロールを作成する。</span><span class="sxs-lookup"><span data-stu-id="96579-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

- <span data-ttu-id="96579-110">メニュー項目の選択を処理しています。</span><span class="sxs-lookup"><span data-stu-id="96579-110">Handling menu item selection.</span></span>

<span data-ttu-id="96579-111">完了すると、<xref:System.Windows.Forms.StatusStrip> コントロールでメニュー項目の選択内容を表示する標準メニューを持つフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="96579-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

<span data-ttu-id="96579-112">このトピックのコードを単一のリストとしてコピーする方法については、「[方法: フォームに標準メニュー項目を提供](how-to-provide-standard-menu-items-to-a-form.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96579-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](how-to-provide-standard-menu-items-to-a-form.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96579-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="96579-113">Prerequisites</span></span>

<span data-ttu-id="96579-114">このチュートリアルを完了するには、Visual Studio が必要です。</span><span class="sxs-lookup"><span data-stu-id="96579-114">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="96579-115">プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="96579-115">Create the project</span></span>

1. <span data-ttu-id="96579-116">Visual Studio で、 **standardmenuform**という名前の Windows アプリケーションプロジェクトを作成します。このプロジェクトには、visual または**Visual Basic** > **クラシックデスクトップ** > Windows フォーム**アプリケーション**) > **visual C#** またはの**新しい** > **プロジェクト** \*\* > ます\*\*。</span><span class="sxs-lookup"><span data-stu-id="96579-116">In Visual Studio, create a Windows application project called **StandardMenuForm** (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="96579-117">Windows フォームデザイナーで、フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="96579-117">In the Windows Forms Designer, select the form.</span></span>

## <a name="create-a-standard-menu"></a><span data-ttu-id="96579-118">標準メニューを作成する</span><span class="sxs-lookup"><span data-stu-id="96579-118">Create a standard menu</span></span>

<span data-ttu-id="96579-119">Windows フォームデザイナーでは、標準のメニュー項目を使用して <xref:System.Windows.Forms.MenuStrip> コントロールを自動的に設定できます。</span><span class="sxs-lookup"><span data-stu-id="96579-119">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>

1. <span data-ttu-id="96579-120">**[ツールボックス]** から <xref:System.Windows.Forms.MenuStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="96579-120">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>

2. <span data-ttu-id="96579-121"><xref:System.Windows.Forms.MenuStrip> コントロールのデザイナーアクショングリフ (![小さい黒い矢印](./media/designer-actions-glyph.gif)) をクリックし、 **[標準項目の挿入]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="96579-121">Click the <xref:System.Windows.Forms.MenuStrip> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Insert Standard Items**.</span></span>

     <span data-ttu-id="96579-122"><xref:System.Windows.Forms.MenuStrip> コントロールには、標準のメニュー項目が設定されます。</span><span class="sxs-lookup"><span data-stu-id="96579-122">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>

3. <span data-ttu-id="96579-123">既定のメニュー項目と対応するアイコンを表示するには、 **[ファイル]** メニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96579-123">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>

## <a name="create-a-statusstrip-control"></a><span data-ttu-id="96579-124">StatusStrip コントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="96579-124">Create a StatusStrip control</span></span>

<span data-ttu-id="96579-125"><xref:System.Windows.Forms.StatusStrip> コントロールを使用して、Windows フォームアプリケーションの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="96579-125">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="96579-126">現在の例では、ユーザーが選択したメニュー項目が <xref:System.Windows.Forms.StatusStrip> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="96579-126">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>

1. <span data-ttu-id="96579-127">**[ツールボックス]** から <xref:System.Windows.Forms.StatusStrip> コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="96579-127">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>

     <span data-ttu-id="96579-128"><xref:System.Windows.Forms.StatusStrip> コントロールは、フォームの下部に自動的にドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="96579-128">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>

2. <span data-ttu-id="96579-129"><xref:System.Windows.Forms.StatusStrip> コントロールのドロップダウンボタンをクリックし、 **[Statuslabel]** を選択して、<xref:System.Windows.Forms.StatusStrip> コントロールに <xref:System.Windows.Forms.ToolStripStatusLabel> コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="96579-129">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>

## <a name="handle-item-selection"></a><span data-ttu-id="96579-130">項目の選択の処理</span><span class="sxs-lookup"><span data-stu-id="96579-130">Handle item selection</span></span>

<span data-ttu-id="96579-131">ユーザーがメニュー項目を選択したときに応答する <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> イベントを処理します。</span><span class="sxs-lookup"><span data-stu-id="96579-131">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>

1. <span data-ttu-id="96579-132">「標準メニューの作成」セクションで作成した **[ファイル]** メニュー項目をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96579-132">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>

2. <span data-ttu-id="96579-133">**[プロパティ]** ウィンドウで、 **[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="96579-133">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="96579-134"><xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="96579-134">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

     <span data-ttu-id="96579-135">Windows フォームデザイナーは、<xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> イベントのイベントハンドラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="96579-135">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>

4. <span data-ttu-id="96579-136">イベントハンドラーに次のコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="96579-136">Insert the following code into the event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. <span data-ttu-id="96579-137">`UpdateStatus` ユーティリティメソッドの定義をフォームに挿入します。</span><span class="sxs-lookup"><span data-stu-id="96579-137">Insert the `UpdateStatus` utility method definition into the form.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a><span data-ttu-id="96579-138">チェックポイント-フォームのテスト</span><span class="sxs-lookup"><span data-stu-id="96579-138">Checkpoint -test your form</span></span>

1. <span data-ttu-id="96579-139">**F5**キーを押して、フォームをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="96579-139">Press **F5** to compile and run your form.</span></span>

2. <span data-ttu-id="96579-140">**[ファイル]** メニュー項目をクリックして、メニューを開きます。</span><span class="sxs-lookup"><span data-stu-id="96579-140">Click the **File** menu item to open the menu.</span></span>

3. <span data-ttu-id="96579-141">**[ファイル]** メニューのいずれかの項目をクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="96579-141">On the **File** menu, click one of the items to select it.</span></span>

     <span data-ttu-id="96579-142"><xref:System.Windows.Forms.StatusStrip> コントロールには、選択した項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="96579-142">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96579-143">次のステップ:</span><span class="sxs-lookup"><span data-stu-id="96579-143">Next steps</span></span>

<span data-ttu-id="96579-144">このチュートリアルでは、標準メニューを使用してフォームを作成しました。</span><span class="sxs-lookup"><span data-stu-id="96579-144">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="96579-145"><xref:System.Windows.Forms.ToolStrip> のコントロールファミリは、他のさまざまな用途に使用できます。</span><span class="sxs-lookup"><span data-stu-id="96579-145">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="96579-146"><xref:System.Windows.Forms.ContextMenuStrip>を使用して、コントロールのショートカットメニューを作成します。</span><span class="sxs-lookup"><span data-stu-id="96579-146">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="96579-147">詳細については、「 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96579-147">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="96579-148">ドッキング <xref:System.Windows.Forms.ToolStrip> コントロールを使用して、マルチドキュメントインターフェイス (MDI) フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="96579-148">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="96579-149">詳細については、「[チュートリアル: メニューのマージと ToolStrip コントロールを使用した MDI フォームの作成](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96579-149">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

- <span data-ttu-id="96579-150"><xref:System.Windows.Forms.ToolStrip> コントロールにプロフェッショナルな外観を与えます。</span><span class="sxs-lookup"><span data-stu-id="96579-150">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="96579-151">詳細については、「[方法: アプリケーションの ToolStrip レンダラーを設定する](how-to-set-the-toolstrip-renderer-for-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96579-151">For more information, see [How to: Set the ToolStrip Renderer for an Application](how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96579-152">参照</span><span class="sxs-lookup"><span data-stu-id="96579-152">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="96579-153">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="96579-153">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
