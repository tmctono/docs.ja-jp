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
ms.openlocfilehash: 526cb509d780abdbf3db6e15504616de19daae83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336552"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="20558-102">チュートリアル: プロフェッショナル スタイルの ToolStrip コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="20558-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="20558-103">アプリケーションを与えることができます<xref:System.Windows.Forms.ToolStrip>から派生した独自のクラスを記述することで、プロフェッショナルな外観と動作を制御、<xref:System.Windows.Forms.ToolStripProfessionalRenderer>型。</span><span class="sxs-lookup"><span data-stu-id="20558-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="20558-104">このチュートリアルを使用する方法について説明<xref:System.Windows.Forms.ToolStrip>に似た複合コントロールを作成するコントロール、**ナビゲーション ウィンドウ**Microsoft® Outlook® で提供されます。</span><span class="sxs-lookup"><span data-stu-id="20558-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="20558-105">このチュートリアルで、次のタスクを示します。</span><span class="sxs-lookup"><span data-stu-id="20558-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="20558-106">Windows コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20558-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="20558-107">StackView コントロールをデザインします。</span><span class="sxs-lookup"><span data-stu-id="20558-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="20558-108">カスタム レンダラーの実装。</span><span class="sxs-lookup"><span data-stu-id="20558-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="20558-109">完了したら、Microsoft Office® XP のコントロールのプロフェッショナルな外観のカスタム クライアントを再利用可能なコントロールがあります。</span><span class="sxs-lookup"><span data-stu-id="20558-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="20558-110">このトピックのコードを単一のリストとしてコピーするには、「[方法:プロフェッショナル スタイルの ToolStrip コントロールを作成する](how-to-create-a-professionally-styled-toolstrip-control.md)します。</span><span class="sxs-lookup"><span data-stu-id="20558-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20558-111">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="20558-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="20558-112">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20558-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="20558-113">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20558-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20558-114">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="20558-114">Prerequisites</span></span>  
 <span data-ttu-id="20558-115">このチュートリアルを完了するための要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20558-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="20558-116">作成し、Visual Studio がインストールされているコンピューターで Windows フォーム アプリケーション プロジェクトを実行できる十分なアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="20558-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="20558-117">Windows コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20558-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="20558-118">最初の手順では、コントロール ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20558-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="20558-119">コントロール ライブラリ プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="20558-119">To create the control library project</span></span>  
  
1. <span data-ttu-id="20558-120">という名前の新しい Windows コントロール ライブラリ プロジェクトを作成`StackViewLibrary`です。</span><span class="sxs-lookup"><span data-stu-id="20558-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2. <span data-ttu-id="20558-121">**ソリューション エクスプ ローラー**、選択した言語に応じて"UserControl1.cs"または「[usercontrol1.vb]」をという名前のソース ファイルを削除することによって、プロジェクトの既定のコントロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="20558-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="20558-122">詳細については、「[方法 :削除、削除、および項目を除外](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="20558-122">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
3. <span data-ttu-id="20558-123">新しい追加<xref:System.Windows.Forms.UserControl>項目を**StackViewLibrary**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="20558-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="20558-124">新しいソース ファイルの基本の名前を付けます`StackView`します。</span><span class="sxs-lookup"><span data-stu-id="20558-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="20558-125">StackView コントロールの設計</span><span class="sxs-lookup"><span data-stu-id="20558-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="20558-126">`StackView`コントロールが 1 つの子による複合コントロール<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="20558-127">複合コントロールの詳細については、次を参照してください。[カスタム コントロールのさまざまな](varieties-of-custom-controls.md)します。</span><span class="sxs-lookup"><span data-stu-id="20558-127">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="20558-128">StackView コントロールを設計するには</span><span class="sxs-lookup"><span data-stu-id="20558-128">To design the StackView control</span></span>  
  
1. <span data-ttu-id="20558-129">**ツールボックス**、ドラッグ、<xref:System.Windows.Forms.ToolStrip>コントロールをデザイン画面。</span><span class="sxs-lookup"><span data-stu-id="20558-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2. <span data-ttu-id="20558-130">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.ToolStrip>次の表に従って、コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="20558-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="20558-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="20558-131">Property</span></span>|<span data-ttu-id="20558-132">値</span><span class="sxs-lookup"><span data-stu-id="20558-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="20558-133">名前</span><span class="sxs-lookup"><span data-stu-id="20558-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="20558-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="20558-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="20558-135">ドッキング</span><span class="sxs-lookup"><span data-stu-id="20558-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="20558-136">フォント</span><span class="sxs-lookup"><span data-stu-id="20558-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="20558-137">GripStyle</span><span class="sxs-lookup"><span data-stu-id="20558-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="20558-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="20558-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="20558-139">[間隔]</span><span class="sxs-lookup"><span data-stu-id="20558-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="20558-140">RenderMode</span><span class="sxs-lookup"><span data-stu-id="20558-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3. <span data-ttu-id="20558-141">Windows フォーム デザイナーでクリックして、<xref:System.Windows.Forms.ToolStrip>コントロールの**追加**ボタンをクリックし、追加、<xref:System.Windows.Forms.ToolStripButton>を`stackStrip`コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4. <span data-ttu-id="20558-142">**プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.ToolStripButton>次の表に従って、コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="20558-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="20558-143">プロパティ</span><span class="sxs-lookup"><span data-stu-id="20558-143">Property</span></span>|<span data-ttu-id="20558-144">値</span><span class="sxs-lookup"><span data-stu-id="20558-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="20558-145">名前</span><span class="sxs-lookup"><span data-stu-id="20558-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="20558-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="20558-146">CheckOnClick</span></span>|<span data-ttu-id="20558-147">true</span><span class="sxs-lookup"><span data-stu-id="20558-147">true</span></span>|  
    |<span data-ttu-id="20558-148">CheckState</span><span class="sxs-lookup"><span data-stu-id="20558-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="20558-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="20558-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="20558-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="20558-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="20558-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="20558-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="20558-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="20558-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="20558-153">余白</span><span class="sxs-lookup"><span data-stu-id="20558-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="20558-154">[間隔]</span><span class="sxs-lookup"><span data-stu-id="20558-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="20558-155">テキスト</span><span class="sxs-lookup"><span data-stu-id="20558-155">Text</span></span>|<span data-ttu-id="20558-156">**メール**</span><span class="sxs-lookup"><span data-stu-id="20558-156">**Mail**</span></span>|  
    |<span data-ttu-id="20558-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="20558-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5. <span data-ttu-id="20558-158">詳細の 3 つの手順 7.<xref:System.Windows.Forms.ToolStripButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="20558-159">コントロールの名前を付けます`calendarStackButton`、 `contactsStackButton`、および`tasksStackButton`します。</span><span class="sxs-lookup"><span data-stu-id="20558-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="20558-160">値を設定、<xref:System.Windows.Forms.Control.Text%2A>プロパティを**カレンダー**、**連絡先**、および**タスク**、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="20558-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="20558-161">イベントの処理</span><span class="sxs-lookup"><span data-stu-id="20558-161">Handling Events</span></span>  
 <span data-ttu-id="20558-162">2 つのイベントは必ず、`StackView`コントロールが正しく動作します。</span><span class="sxs-lookup"><span data-stu-id="20558-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="20558-163">処理、<xref:System.Windows.Forms.UserControl.Load>コントロールを正しく配置するイベントです。</span><span class="sxs-lookup"><span data-stu-id="20558-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="20558-164">処理、<xref:System.Windows.Forms.ToolStripItem.Click>ごとにイベント<xref:System.Windows.Forms.ToolStripButton>提供する、`StackView`のような状態の動作を制御、<xref:System.Windows.Forms.RadioButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="20558-165">イベントを処理するには</span><span class="sxs-lookup"><span data-stu-id="20558-165">To handle events</span></span>  
  
1. <span data-ttu-id="20558-166">Windows フォーム デザイナーで、選択、`StackView`コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2. <span data-ttu-id="20558-167">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20558-167">In the **Properties** window, click **Events**.</span></span>  
  
3. <span data-ttu-id="20558-168">Load イベントをダブルクリックして、`StackView_Load`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="20558-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4. <span data-ttu-id="20558-169">`StackView_Load` イベント ハンドラーで、次のコードをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="20558-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5. <span data-ttu-id="20558-170">Windows フォーム デザイナーで、選択、`mailStackButton`コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6. <span data-ttu-id="20558-171">**[プロパティ]** ウィンドウで、**[イベント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20558-171">In the **Properties** window, click **Events**.</span></span>  
  
7. <span data-ttu-id="20558-172">クリック イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="20558-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="20558-173">Windows フォーム デザイナーで生成する、`mailStackButton_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="20558-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8. <span data-ttu-id="20558-174">名前の変更、`mailStackButton_Click`イベント ハンドラーを`stackButton_Click`します。</span><span class="sxs-lookup"><span data-stu-id="20558-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="20558-175">詳細については、次を参照してください。[コード シンボルのリファクタリングの名前を変更](/visualstudio/ide/reference/rename)します。</span><span class="sxs-lookup"><span data-stu-id="20558-175">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
9. <span data-ttu-id="20558-176">次のコードを挿入、`stackButton_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="20558-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="20558-177">Windows フォーム デザイナーで、選択、`calendarStackButton`コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="20558-178">**プロパティ**ウィンドウのクリック イベントを設定、`stackButton_Click`イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="20558-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="20558-179">手順 10 および 11 for、`contactsStackButton`と`tasksStackButton`コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="20558-180">アイコンの定義</span><span class="sxs-lookup"><span data-stu-id="20558-180">Defining Icons</span></span>  
 <span data-ttu-id="20558-181">各`StackView`ボタンに関連付けられているアイコンがあります。</span><span class="sxs-lookup"><span data-stu-id="20558-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="20558-182">便宜上、各アイコンは、Base64 でエンコードされた文字列としての前に逆シリアル化する、<xref:System.Drawing.Bitmap>これから作成されます。</span><span class="sxs-lookup"><span data-stu-id="20558-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="20558-183">運用環境でリソースとしてビットマップ データを格納して、Windows フォーム デザイナーで、アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20558-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="20558-184">詳細については、「[方法 :Windows フォームに背景画像の追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="20558-184">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="20558-185">アイコンを定義する</span><span class="sxs-lookup"><span data-stu-id="20558-185">To define icons</span></span>  
  
1. <span data-ttu-id="20558-186">コード エディターには、次のコードを挿入、`StackView`クラスの定義。</span><span class="sxs-lookup"><span data-stu-id="20558-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="20558-187">このコードでのビットマップは初期化、<xref:System.Windows.Forms.ToolStripButton>アイコン。</span><span class="sxs-lookup"><span data-stu-id="20558-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2. <span data-ttu-id="20558-188">呼び出しを追加、`InitializeImages`メソッドで、`StackView`クラスのコンス トラクター。</span><span class="sxs-lookup"><span data-stu-id="20558-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="20558-189">カスタム レンダラーの実装</span><span class="sxs-lookup"><span data-stu-id="20558-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="20558-190">ほとんどの要素をカスタマイズすることができます、`StackView`から派生したクラスを実装する、コントロール、<xref:System.Windows.Forms.ToolStripRenderer>クラス。</span><span class="sxs-lookup"><span data-stu-id="20558-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="20558-191">この手順では、実装、<xref:System.Windows.Forms.ToolStripProfessionalRenderer>グリップをカスタマイズおよび用のグラデーション背景を描画するクラスを<xref:System.Windows.Forms.ToolStripButton>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="20558-192">カスタム レンダラーを実装するには</span><span class="sxs-lookup"><span data-stu-id="20558-192">To implement a custom renderer</span></span>  
  
1. <span data-ttu-id="20558-193">次のコードを挿入、`StackView`定義を制御します。</span><span class="sxs-lookup"><span data-stu-id="20558-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="20558-194">定義、`StackRenderer`クラスでオーバーライドされます、 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>、 <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>、および<xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground>カスタムの外観を生成するメソッド。</span><span class="sxs-lookup"><span data-stu-id="20558-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2. <span data-ttu-id="20558-195">`StackView`コントロールのコンス トラクターの新しいインスタンスを作成、`StackRenderer`クラスし、このインスタンスに割り当てる、`stackStrip`コントロールの<xref:System.Windows.Forms.ToolStrip.Renderer%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="20558-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="20558-196">StackView コントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="20558-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="20558-197">`StackView`コントロールから派生、<xref:System.Windows.Forms.UserControl>クラス。</span><span class="sxs-lookup"><span data-stu-id="20558-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="20558-198">そのため、コントロールをテストできます、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="20558-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="20558-199">詳細については、「[方法 :UserControl の実行時の動作をテスト](how-to-test-the-run-time-behavior-of-a-usercontrol.md)します。</span><span class="sxs-lookup"><span data-stu-id="20558-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="20558-200">StackView コントロールをテストするには</span><span class="sxs-lookup"><span data-stu-id="20558-200">To test the StackView control</span></span>  
  
1. <span data-ttu-id="20558-201">プロジェクトをビルドし、開始の f5 キーを押して、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="20558-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2. <span data-ttu-id="20558-202">ボタンの上にポインターを移動、`StackView`を制御して、選択した状態の外観を表示するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20558-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="20558-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="20558-203">Next Steps</span></span>  
 <span data-ttu-id="20558-204">このチュートリアルでは、Office XP のコントロールのプロフェッショナルな外観のカスタム クライアントを再利用可能なコントロールを作成しました。</span><span class="sxs-lookup"><span data-stu-id="20558-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="20558-205">使用することができます、<xref:System.Windows.Forms.ToolStrip>の他のさまざまな目的のコントロール ファミリ。</span><span class="sxs-lookup"><span data-stu-id="20558-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="20558-206">ショートカット メニューを使用してコントロールを作成<xref:System.Windows.Forms.ContextMenuStrip>です。</span><span class="sxs-lookup"><span data-stu-id="20558-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="20558-207">詳細については、次を参照してください。 [ContextMenu コンポーネントの概要](contextmenu-component-overview-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="20558-207">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="20558-208">自動的に設定された標準メニューには、フォームを作成します。</span><span class="sxs-lookup"><span data-stu-id="20558-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="20558-209">詳細については、「[チュートリアル:フォームに標準メニュー項目を用意する](walkthrough-providing-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="20558-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="20558-210">ドッキングのマルチ ドキュメント インターフェイス (MDI) フォームを作成する<xref:System.Windows.Forms.ToolStrip>コントロール。</span><span class="sxs-lookup"><span data-stu-id="20558-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="20558-211">詳細については、「[方法 :メニューのマージと ToolStrip コントロールを MDI フォームを作成](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)です。</span><span class="sxs-lookup"><span data-stu-id="20558-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20558-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="20558-212">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="20558-213">ToolStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="20558-213">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="20558-214">方法: フォームに標準メニュー項目を提供します。</span><span class="sxs-lookup"><span data-stu-id="20558-214">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
