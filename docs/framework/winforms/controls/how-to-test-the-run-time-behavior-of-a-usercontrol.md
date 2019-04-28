---
title: '方法: UserControl の実行時の動作をテストする'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 15b37c71e6643b588c0378510965a9a3e7cb56e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672576"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="a4094-102">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="a4094-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="a4094-103">開発する際に、<xref:System.Windows.Forms.UserControl>実行時の動作をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4094-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="a4094-104">別の Windows ベースのアプリケーション プロジェクトを作成し、テスト フォーム上にコントロールを配置することができますが、この手順は便利です。</span><span class="sxs-lookup"><span data-stu-id="a4094-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="a4094-105">速くて簡単方法は使用する、 **UserControl Test Container** Visual Studio で提供します。</span><span class="sxs-lookup"><span data-stu-id="a4094-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="a4094-106">このテスト コンテナーは、Windows コントロール ライブラリ プロジェクトから直接開始します。</span><span class="sxs-lookup"><span data-stu-id="a4094-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4094-107">テスト コンテナーを読み込む、<xref:System.Windows.Forms.UserControl>コントロールには、少なくとも 1 つのパブリック コンス トラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4094-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4094-108">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a4094-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a4094-109">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4094-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a4094-110">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4094-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4094-111">使用して、Visual C のコントロールをテストすることはできません、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="a4094-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="a4094-112">UserControl の実行時の動作をテストするには</span><span class="sxs-lookup"><span data-stu-id="a4094-112">To test the run-time behavior of a UserControl</span></span>  
  
1. <span data-ttu-id="a4094-113">呼ばれる Windows コントロール ライブラリ プロジェクトを作成**ファイルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="a4094-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="a4094-114">詳細については、次を参照してください。 [Windows コントロール ライブラリ テンプレート](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a4094-114">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="a4094-115">**Windows フォーム デザイナー**、ドラッグ、<xref:System.Windows.Forms.Label>コントロールから、**ツールボックス**コントロールのデザイン サーフェイスにします。</span><span class="sxs-lookup"><span data-stu-id="a4094-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3. <span data-ttu-id="a4094-116">F5 キーを押してプロジェクトをビルドして実行する、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="a4094-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="a4094-117">テスト コンテナーが表示されます、<xref:System.Windows.Forms.UserControl>で、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a4094-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4. <span data-ttu-id="a4094-118">選択、<xref:System.Windows.Forms.Control.BackColor%2A>に表示されるプロパティ、<xref:System.Windows.Forms.PropertyGrid>コントロールの右側に、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a4094-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="a4094-119">その値を変更`ControlDark`します。</span><span class="sxs-lookup"><span data-stu-id="a4094-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="a4094-120">コントロールが暗い色に変わることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4094-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="a4094-121">その他のプロパティ値を変更してみてくださいをコントロールへの影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="a4094-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5. <span data-ttu-id="a4094-122">をクリックして、**ユーザー入力コントロールのドッキング**下のチェック ボックス、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a4094-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="a4094-123">コントロールのサイズのウィンドウに入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4094-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="a4094-124">テスト コンテナーのサイズを変更し、ペイン コントロールのサイズをことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a4094-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6. <span data-ttu-id="a4094-125">テスト コンテナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a4094-125">Close the test container.</span></span>  
  
7. <span data-ttu-id="a4094-126">別のユーザー コントロールを追加、**ファイルを開く**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a4094-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="a4094-127">詳細については、「[方法: 既存の項目をプロジェクトに追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a4094-127">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>  
  
8. <span data-ttu-id="a4094-128">**Windows フォーム デザイナー**、ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**コントロールのデザイン サーフェイスにします。</span><span class="sxs-lookup"><span data-stu-id="a4094-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="a4094-129">F5 キーを押してプロジェクトをビルドし、テスト コンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="a4094-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="a4094-130">をクリックして、**ユーザー コントロールの選択**<xref:System.Windows.Forms.ComboBox>を 2 つのユーザー コントロールを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="a4094-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="a4094-131">別のプロジェクトからユーザー コントロールのテスト</span><span class="sxs-lookup"><span data-stu-id="a4094-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="a4094-132">現在のプロジェクトのテスト コンテナーでは、他のプロジェクトからユーザー コントロールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a4094-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="a4094-133">別のプロジェクトからユーザー コントロールをテストするには</span><span class="sxs-lookup"><span data-stu-id="a4094-133">To test user controls from another project</span></span>  
  
1. <span data-ttu-id="a4094-134">呼ばれる Windows コントロール ライブラリ プロジェクトを作成**TestContainerExample2**します。</span><span class="sxs-lookup"><span data-stu-id="a4094-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="a4094-135">詳細については、次を参照してください。 [Windows コントロール ライブラリ テンプレート](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a4094-135">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="a4094-136">**Windows フォーム デザイナー**、ドラッグ、<xref:System.Windows.Forms.RadioButton>コントロールから、**ツールボックス**コントロールのデザイン サーフェイスにします。</span><span class="sxs-lookup"><span data-stu-id="a4094-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3. <span data-ttu-id="a4094-137">F5 キーを押してプロジェクトをビルドし、テスト コンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="a4094-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="a4094-138">テスト コンテナーが表示されます、<xref:System.Windows.Forms.UserControl>で、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="a4094-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4. <span data-ttu-id="a4094-139">をクリックして、**ロード**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4094-139">Click the **Load** button.</span></span>  
  
5. <span data-ttu-id="a4094-140">**オープン** ダイアログ ボックスに移動**ファイルを開く**.dll で、前の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="a4094-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="a4094-141">選択**ファイルを開く**.dll をクリックして、**オープン** ボタンをユーザー コントロールを読み込む</span><span class="sxs-lookup"><span data-stu-id="a4094-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6. <span data-ttu-id="a4094-142">使用して、**ユーザー コントロールの選択**<xref:System.Windows.Forms.ComboBox>から 2 つのユーザー コントロール間を切り替える、**ファイルを開く**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="a4094-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4094-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4094-143">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="a4094-144">方法: 複合コントロールを作成</span><span class="sxs-lookup"><span data-stu-id="a4094-144">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="a4094-145">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a4094-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="a4094-146">チュートリアル: ビジュアルを含む複合コントロールの作成C#</span><span class="sxs-lookup"><span data-stu-id="a4094-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="a4094-147">[ユーザー コントロール デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4094-147">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
