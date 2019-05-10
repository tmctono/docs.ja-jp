---
title: 'チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 226e805d0240236899ee0cc290f1060a3b0aa391
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211773"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="a9ff0-102">チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a9ff0-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>

<span data-ttu-id="a9ff0-103">アプリケーションを与えることができます<xref:System.Windows.Forms.ToolStrip>から派生した独自のクラスを記述することで、プロフェッショナルな外観と動作を制御、<xref:System.Windows.Forms.ToolStripProfessionalRenderer>型。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>

<span data-ttu-id="a9ff0-104">このチュートリアルを使用する方法について説明<xref:System.Windows.Forms.ToolStrip>に似た複合コントロールを作成するコントロール、**ナビゲーション ウィンドウ**Microsoft® Outlook® で提供されます。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="a9ff0-105">このチュートリアルで、次のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-105">The following tasks are illustrated in this walkthrough:</span></span>

- <span data-ttu-id="a9ff0-106">Windows コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-106">Creating a Windows Control Library project.</span></span>

- <span data-ttu-id="a9ff0-107">StackView コントロールをデザインします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-107">Designing the StackView Control.</span></span>

- <span data-ttu-id="a9ff0-108">カスタム レンダラーの実装。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-108">Implementing a Custom Renderer.</span></span>

<span data-ttu-id="a9ff0-109">完了したら、Microsoft Office® XP のコントロールのプロフェッショナルな外観のカスタム クライアントを再利用可能なコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>

<span data-ttu-id="a9ff0-110">このトピックのコードを単一のリストとしてコピーするには、「[方法:プロフェッショナル スタイルの ToolStrip コントロールを作成する](how-to-create-a-professionally-styled-toolstrip-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9ff0-111">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a9ff0-111">Prerequisites</span></span>

<span data-ttu-id="a9ff0-112">Visual Studio でこのチュートリアルを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-112">You'll need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="a9ff0-113">コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-113">Create the control library project</span></span>

1. <span data-ttu-id="a9ff0-114">Visual Studio で、という名前の新しい Windows コントロール ライブラリ プロジェクトを作成`StackViewLibrary`です。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-114">In Visual Studio, create a new Windows Control Library project named `StackViewLibrary`.</span></span>

2. <span data-ttu-id="a9ff0-115">**ソリューション エクスプ ローラー**、選択した言語に応じて"UserControl1.cs"または「[usercontrol1.vb]」をという名前のソース ファイルを削除することによって、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-115">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>

     <span data-ttu-id="a9ff0-116">詳細については、「[方法 :削除、削除、および項目を除外](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-116">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

3. <span data-ttu-id="a9ff0-117">新しい追加<xref:System.Windows.Forms.UserControl>項目を**StackViewLibrary**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-117">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="a9ff0-118">新しいソース ファイルの基本の名前を付けます`StackView`します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-118">Give the new source file a base name of `StackView`.</span></span>

## <a name="design-the-stackview-control"></a><span data-ttu-id="a9ff0-119">StackView コントロールのデザイン</span><span class="sxs-lookup"><span data-stu-id="a9ff0-119">Design the StackView control</span></span>

<span data-ttu-id="a9ff0-120">`StackView`コントロールが 1 つの子による複合コントロール<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-120">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="a9ff0-121">複合コントロールの詳細については、次を参照してください。[カスタム コントロールのさまざまな](varieties-of-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-121">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>

1. <span data-ttu-id="a9ff0-122">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.ToolStrip>コントロールをデザイン画面。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-122">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>

2. <span data-ttu-id="a9ff0-123">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.ToolStrip>次の表に従って、コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-123">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>

    |<span data-ttu-id="a9ff0-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a9ff0-124">Property</span></span>|<span data-ttu-id="a9ff0-125">値</span><span class="sxs-lookup"><span data-stu-id="a9ff0-125">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="a9ff0-126">名前</span><span class="sxs-lookup"><span data-stu-id="a9ff0-126">Name</span></span>|`stackStrip`|
    |<span data-ttu-id="a9ff0-127">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="a9ff0-127">CanOverflow</span></span>|`false`|
    |<span data-ttu-id="a9ff0-128">ドッキング</span><span class="sxs-lookup"><span data-stu-id="a9ff0-128">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|
    |<span data-ttu-id="a9ff0-129">フォント</span><span class="sxs-lookup"><span data-stu-id="a9ff0-129">Font</span></span>|`Tahoma, 10pt, style=Bold`|
    |<span data-ttu-id="a9ff0-130">GripStyle</span><span class="sxs-lookup"><span data-stu-id="a9ff0-130">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|
    |<span data-ttu-id="a9ff0-131">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="a9ff0-131">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|
    |<span data-ttu-id="a9ff0-132">[間隔]</span><span class="sxs-lookup"><span data-stu-id="a9ff0-132">Padding</span></span>|`0, 7, 0, 0`|
    |<span data-ttu-id="a9ff0-133">RenderMode</span><span class="sxs-lookup"><span data-stu-id="a9ff0-133">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|

3. <span data-ttu-id="a9ff0-134">Windows フォーム デザイナーでクリックして、<xref:System.Windows.Forms.ToolStrip>コントロールの**追加**ボタンをクリックし、追加、<xref:System.Windows.Forms.ToolStripButton>を`stackStrip`コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-134">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>

4. <span data-ttu-id="a9ff0-135">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.ToolStripButton>次の表に従って、コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-135">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>

    |<span data-ttu-id="a9ff0-136">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a9ff0-136">Property</span></span>|<span data-ttu-id="a9ff0-137">値</span><span class="sxs-lookup"><span data-stu-id="a9ff0-137">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="a9ff0-138">名前</span><span class="sxs-lookup"><span data-stu-id="a9ff0-138">Name</span></span>|`mailStackButton`|
    |<span data-ttu-id="a9ff0-139">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="a9ff0-139">CheckOnClick</span></span>|<span data-ttu-id="a9ff0-140">true</span><span class="sxs-lookup"><span data-stu-id="a9ff0-140">true</span></span>|
    |<span data-ttu-id="a9ff0-141">CheckState</span><span class="sxs-lookup"><span data-stu-id="a9ff0-141">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|
    |<span data-ttu-id="a9ff0-142">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="a9ff0-142">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|
    |<span data-ttu-id="a9ff0-143">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="a9ff0-143">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|
    |<span data-ttu-id="a9ff0-144">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="a9ff0-144">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|
    |<span data-ttu-id="a9ff0-145">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="a9ff0-145">ImageTransparentColor</span></span>|`238, 238, 238`|
    |<span data-ttu-id="a9ff0-146">余白</span><span class="sxs-lookup"><span data-stu-id="a9ff0-146">Margin</span></span>|`0, 0, 0, 0`|
    |<span data-ttu-id="a9ff0-147">[間隔]</span><span class="sxs-lookup"><span data-stu-id="a9ff0-147">Padding</span></span>|`3, 3, 3, 3`|
    |<span data-ttu-id="a9ff0-148">テキスト</span><span class="sxs-lookup"><span data-stu-id="a9ff0-148">Text</span></span>|<span data-ttu-id="a9ff0-149">**メール**</span><span class="sxs-lookup"><span data-stu-id="a9ff0-149">**Mail**</span></span>|
    |<span data-ttu-id="a9ff0-150">TextAlign</span><span class="sxs-lookup"><span data-stu-id="a9ff0-150">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|

5. <span data-ttu-id="a9ff0-151">詳細の 3 つの手順 7.<xref:System.Windows.Forms.ToolStripButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-151">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

     <span data-ttu-id="a9ff0-152">コントロールの名前を付けます`calendarStackButton`、 `contactsStackButton`、および`tasksStackButton`します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-152">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="a9ff0-153">値を設定、<xref:System.Windows.Forms.Control.Text%2A>プロパティを**カレンダー**、**連絡先**、および**タスク**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-153">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>

## <a name="handle-events"></a><span data-ttu-id="a9ff0-154">イベントの処理</span><span class="sxs-lookup"><span data-stu-id="a9ff0-154">Handle events</span></span>

<span data-ttu-id="a9ff0-155">2 つのイベントは必ず、`StackView`コントロールが正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-155">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="a9ff0-156">処理、<xref:System.Windows.Forms.UserControl.Load>コントロールを正しく配置するイベントです。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-156">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="a9ff0-157">処理、<xref:System.Windows.Forms.ToolStripItem.Click>ごとにイベント<xref:System.Windows.Forms.ToolStripButton>提供する、`StackView`のような状態の動作を制御、<xref:System.Windows.Forms.RadioButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-157">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>

1. <span data-ttu-id="a9ff0-158">Windows フォーム デザイナーで、選択、`StackView`コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-158">In the Windows Forms Designer, select the `StackView` control.</span></span>

2. <span data-ttu-id="a9ff0-159">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-159">In the **Properties** window, click **Events**.</span></span>

3. <span data-ttu-id="a9ff0-160">Load イベントをダブルクリックして、`StackView_Load`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-160">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>

4. <span data-ttu-id="a9ff0-161">
  `StackView_Load\` イベント ハンドラーで、次のコードをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-161">In the `StackView_Load` event handler, copy and paste the following code.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]

5. <span data-ttu-id="a9ff0-162">Windows フォーム デザイナーで、選択、`mailStackButton`コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-162">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>

6. <span data-ttu-id="a9ff0-163">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-163">In the **Properties** window, click **Events**.</span></span>

7. <span data-ttu-id="a9ff0-164">クリック イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-164">Double-click the Click event.</span></span>

     <span data-ttu-id="a9ff0-165">Windows フォーム デザイナーで生成する、`mailStackButton_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-165">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>

8. <span data-ttu-id="a9ff0-166">名前の変更、`mailStackButton_Click`イベント ハンドラーを`stackButton_Click`します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-166">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>

     <span data-ttu-id="a9ff0-167">詳細については、次を参照してください。[コード シンボルのリファクタリングの名前を変更](/visualstudio/ide/reference/rename)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-167">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

9. <span data-ttu-id="a9ff0-168">次のコードを挿入、`stackButton_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-168">Insert the following code into the `stackButton_Click` event handler.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]

10. <span data-ttu-id="a9ff0-169">Windows フォーム デザイナーで、選択、`calendarStackButton`コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-169">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>

11. <span data-ttu-id="a9ff0-170">**プロパティ**ウィンドウのクリック イベントを設定、`stackButton_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-170">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>

12. <span data-ttu-id="a9ff0-171">手順 10 および 11 for、`contactsStackButton`と`tasksStackButton`コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-171">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>

## <a name="define-icons"></a><span data-ttu-id="a9ff0-172">アイコンを定義します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-172">Define icons</span></span>

<span data-ttu-id="a9ff0-173">各`StackView`ボタンに関連付けられているアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-173">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="a9ff0-174">便宜上、各アイコンは、Base64 でエンコードされた文字列としての前に逆シリアル化する、<xref:System.Drawing.Bitmap>これから作成されます。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-174">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="a9ff0-175">運用環境でリソースとしてビットマップ データを格納して、Windows フォーム デザイナーで、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-175">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="a9ff0-176">詳細については、「[方法 :Windows フォームに背景画像の追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-176">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>

1. <span data-ttu-id="a9ff0-177">コード エディターには、次のコードを挿入、`StackView`クラスの定義。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-177">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="a9ff0-178">このコードでのビットマップは初期化、<xref:System.Windows.Forms.ToolStripButton>アイコン。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-178">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]

2. <span data-ttu-id="a9ff0-179">呼び出しを追加、`InitializeImages`メソッドで、`StackView`クラスのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-179">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="implement-a-custom-renderer"></a><span data-ttu-id="a9ff0-180">カスタム レンダラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-180">Implement a custom renderer</span></span>

<span data-ttu-id="a9ff0-181">ほとんどの要素をカスタマイズすることができます、`StackView`から派生したクラスを実装する、コントロール、<xref:System.Windows.Forms.ToolStripRenderer>クラス。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-181">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="a9ff0-182">この手順では、実装、<xref:System.Windows.Forms.ToolStripProfessionalRenderer>グリップをカスタマイズおよび用のグラデーション背景を描画するクラスを<xref:System.Windows.Forms.ToolStripButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-182">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>

1. <span data-ttu-id="a9ff0-183">次のコードを挿入、`StackView`定義を制御します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-183">Insert the following code into the `StackView` control definition.</span></span>

     <span data-ttu-id="a9ff0-184">定義、`StackRenderer`クラスでオーバーライドされます、 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>、 <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>、および<xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground>カスタムの外観を生成するメソッド。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-184">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]

2. <span data-ttu-id="a9ff0-185">`StackView`コントロールのコンス トラクターの新しいインスタンスを作成、`StackRenderer`クラスし、このインスタンスに割り当てる、`stackStrip`コントロールの<xref:System.Windows.Forms.ToolStrip.Renderer%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-185">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>

     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]

## <a name="test-the-stackview-control"></a><span data-ttu-id="a9ff0-186">StackView コントロールをテストします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-186">Test the StackView control</span></span>

<span data-ttu-id="a9ff0-187">`StackView`コントロールから派生、<xref:System.Windows.Forms.UserControl>クラス。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-187">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="a9ff0-188">そのため、コントロールをテストできます、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-188">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="a9ff0-189">詳細については、「[方法 :UserControl の実行時の動作をテスト](how-to-test-the-run-time-behavior-of-a-usercontrol.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-189">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

1. <span data-ttu-id="a9ff0-190">キーを押して**F5** 、プロジェクトをビルドし、開始、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-190">Press **F5** to build the project and start the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="a9ff0-191">ボタンの上にポインターを移動、`StackView`を制御して、選択した状態の外観を表示するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-191">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9ff0-192">次の手順</span><span class="sxs-lookup"><span data-stu-id="a9ff0-192">Next steps</span></span>

<span data-ttu-id="a9ff0-193">このチュートリアルでは、Office XP のコントロールのプロフェッショナルな外観のカスタム クライアントを再利用可能なコントロールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-193">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="a9ff0-194">使用することができます、<xref:System.Windows.Forms.ToolStrip>の他のさまざまな目的のコントロール ファミリ。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-194">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>

- <span data-ttu-id="a9ff0-195">ショートカット メニューを使用してコントロールを作成<xref:System.Windows.Forms.ContextMenuStrip>です。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-195">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="a9ff0-196">詳細については、次を参照してください。 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-196">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

- <span data-ttu-id="a9ff0-197">自動的に設定された標準メニューには、フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-197">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="a9ff0-198">詳細については、「[チュートリアル:フォームに標準メニュー項目を用意する](walkthrough-providing-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-198">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>

- <span data-ttu-id="a9ff0-199">ドッキングのマルチ ドキュメント インターフェイス (MDI) フォームを作成する<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-199">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="a9ff0-200">詳細については、「[方法 :メニューのマージと ToolStrip コントロールを MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-200">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9ff0-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9ff0-201">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="a9ff0-202">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="a9ff0-202">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="a9ff0-203">方法: フォームに標準メニュー項目を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9ff0-203">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
