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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180205"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="2eade-102">方法: UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="2eade-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="2eade-103">@No__t 0 を開発する場合は、実行時の動作をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2eade-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="2eade-104">別個の Windows ベースのアプリケーションプロジェクトを作成し、テストフォームにコントロールを配置することはできますが、この手順は不便です。</span><span class="sxs-lookup"><span data-stu-id="2eade-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="2eade-105">Visual Studio によって提供される**UserControl テストコンテナー**を使用する方が、より高速で簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="2eade-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="2eade-106">このテストコンテナーは、Windows コントロールライブラリプロジェクトから直接開始します。</span><span class="sxs-lookup"><span data-stu-id="2eade-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2eade-107">テストコンテナーが @no__t 0 を読み込むには、コントロールに少なくとも1つのパブリックコンストラクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="2eade-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="2eade-108">**UserControl Test Container**を使用して、Visual C++ のコントロールをテストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2eade-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="2eade-109">UserControl の実行時の動作をテストする</span><span class="sxs-lookup"><span data-stu-id="2eade-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="2eade-110">Visual Studio で、Windows コントロールライブラリプロジェクトを作成し、 **TestContainerExample**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eade-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="2eade-111">**Windows フォームデザイナー**で、 **[ツールボックス]** からコントロールのデザインサーフェイスに @no__t 1 コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2eade-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="2eade-112"><kbd>F5</kbd>キーを押してプロジェクトをビルドし、 **UserControl テストコンテナー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="2eade-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="2eade-113">テストコンテナーが、**プレビュー**ウィンドウに @no__t 0 で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2eade-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="2eade-114">**プレビュー**ウィンドウの右側にある <xref:System.Windows.Forms.PropertyGrid> コントロールに表示される <xref:System.Windows.Forms.Control.BackColor%2A> プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="2eade-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="2eade-115">値を**ControlDark**に変更します。</span><span class="sxs-lookup"><span data-stu-id="2eade-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="2eade-116">コントロールが濃い色に変化することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2eade-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="2eade-117">他のプロパティ値を変更し、コントロールに対する影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="2eade-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="2eade-118">**プレビュー**ウィンドウの下にある **[Dock Fill User Control]** チェックボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eade-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="2eade-119">ウィンドウに合わせてコントロールのサイズが変更されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2eade-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="2eade-120">テストコンテナーのサイズを変更し、ウィンドウのサイズが変更されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2eade-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="2eade-121">テストコンテナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2eade-121">Close the test container.</span></span>

7. <span data-ttu-id="2eade-122">**TestContainerExample**プロジェクトに別のユーザーコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="2eade-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="2eade-123">**Windows フォームデザイナー**で、 **[ツールボックス]** からコントロールのデザインサーフェイスに @no__t 1 コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2eade-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="2eade-124"><kbd>F5</kbd>キーを押してプロジェクトをビルドし、テストコンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eade-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="2eade-125">2つのユーザーコントロールを切り替えるには、 **[ユーザーコントロールの選択]** <xref:System.Windows.Forms.ComboBox> をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eade-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="2eade-126">別のプロジェクトからユーザーコントロールをテストする</span><span class="sxs-lookup"><span data-stu-id="2eade-126">Test user controls from another project</span></span>

<span data-ttu-id="2eade-127">現在のプロジェクトのテストコンテナー内の他のプロジェクトからユーザーコントロールをテストできます。</span><span class="sxs-lookup"><span data-stu-id="2eade-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="2eade-128">Visual Studio で、Windows コントロールライブラリプロジェクトを作成し、 **TestContainerExample2**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2eade-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="2eade-129">**Windows フォームデザイナー**で、 **[ツールボックス]** からコントロールのデザインサーフェイスに @no__t 1 コントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="2eade-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="2eade-130"><kbd>F5</kbd>キーを押してプロジェクトをビルドし、テストコンテナーを実行します。</span><span class="sxs-lookup"><span data-stu-id="2eade-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="2eade-131">テストコンテナーが、**プレビュー**ウィンドウに @no__t 0 で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2eade-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="2eade-132">**[読み込み]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2eade-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="2eade-133">**[開く]** ダイアログボックスで、前の手順で作成した TestContainerExample に移動し*ます*。</span><span class="sxs-lookup"><span data-stu-id="2eade-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="2eade-134">*TestContainerExample*を選択し、 **[開く]** ボタンをクリックしてユーザーコントロールを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2eade-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="2eade-135">**TestContainerExample**プロジェクトの2つのユーザーコントロールを切り替えるには、 **[ユーザーの選択] コントロール**<xref:System.Windows.Forms.ComboBox> を使用します。</span><span class="sxs-lookup"><span data-stu-id="2eade-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="2eade-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2eade-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <span data-ttu-id="2eade-137">[2 つのオブジェクトが等しいかどうかをテストする方法複合コントロールを作成する @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="2eade-137">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>
- <span data-ttu-id="2eade-138">[チュートリアル: 複合コントロールの作成 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="2eade-138">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>
- <span data-ttu-id="2eade-139">[ユーザーコントロールデザイナー](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2eade-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
