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
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211704"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="97a70-102">方法: UserControl の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="97a70-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="97a70-103">開発する際に、<xref:System.Windows.Forms.UserControl>実行時の動作をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97a70-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="97a70-104">別の Windows ベースのアプリケーション プロジェクトを作成し、テスト フォーム上にコントロールを配置することができますが、この手順は便利です。</span><span class="sxs-lookup"><span data-stu-id="97a70-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="97a70-105">速くて簡単方法は使用する、 **UserControl Test Container** Visual Studio で提供します。</span><span class="sxs-lookup"><span data-stu-id="97a70-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="97a70-106">このテスト コンテナーは、Windows コントロール ライブラリ プロジェクトから直接開始します。</span><span class="sxs-lookup"><span data-stu-id="97a70-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97a70-107">テスト コンテナーを読み込む、<xref:System.Windows.Forms.UserControl>コントロールには、少なくとも 1 つのパブリック コンス トラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="97a70-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="97a70-108">**UserControl Test Container**を使用して、Visual C++ のコントロールをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="97a70-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="97a70-109">UserControl の実行時の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="97a70-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="97a70-110">Visual Studio と呼ばれる Windows コントロール ライブラリ プロジェクトを作成**ファイルを開く**します。</span><span class="sxs-lookup"><span data-stu-id="97a70-110">In Visual Studio, create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="97a70-111">詳細については、次を参照してください。 [Windows コントロール ライブラリ テンプレート](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="97a70-111">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="97a70-112">**Windows フォーム デザイナー**、ドラッグ、<xref:System.Windows.Forms.Label>コントロールから、**ツールボックス**コントロールのデザイン サーフェイスにします。</span><span class="sxs-lookup"><span data-stu-id="97a70-112">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="97a70-113">キーを押して**F5**プロジェクトをビルドして実行する、 **UserControl Test Container**します。</span><span class="sxs-lookup"><span data-stu-id="97a70-113">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="97a70-114">テスト コンテナーが表示されます、<xref:System.Windows.Forms.UserControl>で、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="97a70-114">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="97a70-115">選択、<xref:System.Windows.Forms.Control.BackColor%2A>に表示されるプロパティ、<xref:System.Windows.Forms.PropertyGrid>コントロールの右側に、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="97a70-115">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="97a70-116">その値を変更`ControlDark`します。</span><span class="sxs-lookup"><span data-stu-id="97a70-116">Change its value to `ControlDark`.</span></span> <span data-ttu-id="97a70-117">コントロールが暗い色に変わることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97a70-117">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="97a70-118">その他のプロパティ値を変更してみてくださいをコントロールへの影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="97a70-118">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="97a70-119">をクリックして、**ユーザー入力コントロールのドッキング**下のチェック ボックス、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="97a70-119">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="97a70-120">コントロールのサイズのウィンドウに入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="97a70-120">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="97a70-121">テスト コンテナーのサイズを変更し、ペイン コントロールのサイズをことを確認します。</span><span class="sxs-lookup"><span data-stu-id="97a70-121">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="97a70-122">テスト コンテナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="97a70-122">Close the test container.</span></span>

7. <span data-ttu-id="97a70-123">別のユーザー コントロールを追加、**ファイルを開く**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="97a70-123">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="97a70-124">詳細については、「[方法: 既存の項目をプロジェクトに追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="97a70-124">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>

8. <span data-ttu-id="97a70-125">**Windows フォーム デザイナー**、ドラッグ、<xref:System.Windows.Forms.Button>コントロールから、**ツールボックス**コントロールのデザイン サーフェイスにします。</span><span class="sxs-lookup"><span data-stu-id="97a70-125">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="97a70-126">F5 キーを押してプロジェクトをビルドし、テスト コンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="97a70-126">Press F5 to build the project and run the test container.</span></span>

10. <span data-ttu-id="97a70-127">をクリックして、**ユーザー コントロールの選択**<xref:System.Windows.Forms.ComboBox>を 2 つのユーザー コントロールを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="97a70-127">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="97a70-128">別のプロジェクトからのテスト ユーザーのコントロール</span><span class="sxs-lookup"><span data-stu-id="97a70-128">Test user controls from another project</span></span>

<span data-ttu-id="97a70-129">現在のプロジェクトのテスト コンテナーでは、他のプロジェクトからユーザー コントロールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="97a70-129">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="97a70-130">呼ばれる Windows コントロール ライブラリ プロジェクトを作成**TestContainerExample2**します。</span><span class="sxs-lookup"><span data-stu-id="97a70-130">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="97a70-131">詳細については、次を参照してください。 [Windows コントロール ライブラリ テンプレート](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="97a70-131">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="97a70-132">**Windows フォーム デザイナー**、ドラッグ、<xref:System.Windows.Forms.RadioButton>コントロールから、**ツールボックス**コントロールのデザイン サーフェイスにします。</span><span class="sxs-lookup"><span data-stu-id="97a70-132">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="97a70-133">F5 キーを押してプロジェクトをビルドし、テスト コンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="97a70-133">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="97a70-134">テスト コンテナーが表示されます、<xref:System.Windows.Forms.UserControl>で、**プレビュー**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="97a70-134">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="97a70-135">をクリックして、**ロード**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="97a70-135">Click the **Load** button.</span></span>

5. <span data-ttu-id="97a70-136">**オープン** ダイアログ ボックスに移動**ファイルを開く**.dll で、前の手順で作成しました。</span><span class="sxs-lookup"><span data-stu-id="97a70-136">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="97a70-137">選択**ファイルを開く**.dll をクリックして、**オープン** ボタンをユーザー コントロールを読み込む</span><span class="sxs-lookup"><span data-stu-id="97a70-137">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="97a70-138">使用して、**ユーザー コントロールの選択**<xref:System.Windows.Forms.ComboBox>から 2 つのユーザー コントロール間を切り替える、**ファイルを開く**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="97a70-138">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="97a70-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="97a70-139">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="97a70-140">方法: 複合コントロールを作成</span><span class="sxs-lookup"><span data-stu-id="97a70-140">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="97a70-141">チュートリアル: Visual Basic による複合コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="97a70-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="97a70-142">チュートリアル: ビジュアルを含む複合コントロールの作成C#</span><span class="sxs-lookup"><span data-stu-id="97a70-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="97a70-143">[ユーザー コントロール デザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97a70-143">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
