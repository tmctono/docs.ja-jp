---
title: '方法: アクティビティを作成する'
description: この記事では、Workflow Foundation で2つのアクティビティを作成する方法を示します。1つはコードを使用してロジックを実装し、もう1つは他のアクティビティを使用して定義します。
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: dae099d102b0c85d09a1ef8bcce56e8a9096bd20
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419591"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="041b5-103">方法: アクティビティを作成する</span><span class="sxs-lookup"><span data-stu-id="041b5-103">How to: Create an Activity</span></span>

<span data-ttu-id="041b5-104">アクティビティは [!INCLUDE[wf1](../../../includes/wf1-md.md)] の動作の中心的な単位です。</span><span class="sxs-lookup"><span data-stu-id="041b5-104">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="041b5-105">アクティビティの実行ロジックはマネージド コードで実装できます。または他のアクティビティを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="041b5-105">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="041b5-106">このトピックでは、2 つのアクティビティを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="041b5-106">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="041b5-107">最初のアクティビティは、コードを使用してその実行ロジックを実装する単純なアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="041b5-107">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="041b5-108">2 番目のアクティビティの実装は他のアクティビティを使用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="041b5-108">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="041b5-109">これらのアクティビティは、チュートリアルの次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="041b5-109">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="041b5-110">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041b5-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="041b5-111">アクティビティライブラリプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="041b5-111">Create the activity library project</span></span>

1. <span data-ttu-id="041b5-112">Visual Studio を開き**New**  >  、[**ファイル**] メニューの [新しい**プロジェクト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-112">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="041b5-113">[**新しいプロジェクト**] ダイアログの [**インストール済み**] カテゴリで、[ **Visual C#**  >  **ワークフロー** ] (または**Visual Basic**  >  **ワークフロー**) を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-113">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="041b5-114">[**ワークフロー**テンプレート] カテゴリが表示されない場合は、Visual Studio の**Windows Workflow Foundation**コンポーネントのインストールが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="041b5-114">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="041b5-115">[**新しいプロジェクト**] ダイアログの左側にある [ **Visual Studio インストーラーを開く**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-115">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="041b5-116">Visual Studio インストーラーで、[**個々のコンポーネント**] タブを選択します。次に、[**開発アクティビティ**] カテゴリで、[ **Windows Workflow Foundation** ] コンポーネントを選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-116">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="041b5-117">[**変更**] を選択してコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="041b5-117">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="041b5-118">[**アクティビティライブラリ**] プロジェクトテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-118">Select the **Activity Library** project template.</span></span> <span data-ttu-id="041b5-119">[**名前**] ボックスに「`NumberGuessWorkflowActivities`」と入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-119">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="041b5-120">**ソリューション エクスプローラー**で、[**Activity1.xaml**] を右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-120">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="041b5-121">[**OK**] をクリックして確定します。</span><span class="sxs-lookup"><span data-stu-id="041b5-121">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="041b5-122">ReadInt アクティビティを作成する</span><span class="sxs-lookup"><span data-stu-id="041b5-122">Create the ReadInt activity</span></span>

1. <span data-ttu-id="041b5-123">[**プロジェクト**] メニューの [**新しい項目の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-123">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="041b5-124">[**インストールされている**  >  **共通項目**] ノードで、[**ワークフロー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-124">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="041b5-125">[**ワークフロー** ] の一覧から [**コードアクティビティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-125">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="041b5-126">[**名前**] ボックスに「`ReadInt`」と入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-126">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="041b5-127">既存の `ReadInt` 定義を次の定義に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="041b5-127">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="041b5-128">`ReadInt` アクティビティは、コード アクティビティ テンプレートの既定値である <xref:System.Activities.NativeActivity%601> ではなく <xref:System.Activities.CodeActivity> から派生します。</span><span class="sxs-lookup"><span data-stu-id="041b5-128">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="041b5-129"><xref:System.Activities.CodeActivity%601> は、<xref:System.Activities.Activity%601.Result%2A> 引数を介して公開される 1 つの結果がアクティビティによって提供される場合に使用できますが、<xref:System.Activities.CodeActivity%601> ではブックマークの使用がサポートされていないため、<xref:System.Activities.NativeActivity%601> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="041b5-129"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="041b5-130">Prompt アクティビティを作成する</span><span class="sxs-lookup"><span data-stu-id="041b5-130">Create the Prompt activity</span></span>

1. <span data-ttu-id="041b5-131">**Ctrl** + **Shift** + **B**キーを押して、プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="041b5-131">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="041b5-132">プロジェクトをビルドすると、このプロジェクトの `ReadInt` アクティビティを使用して、この手順からカスタム アクティビティをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="041b5-132">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="041b5-133">[**プロジェクト**] メニューの [**新しい項目の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-133">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="041b5-134">[**インストールされている**  >  **共通項目**] ノードで、[**ワークフロー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-134">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="041b5-135">[**ワークフロー**] 一覧から [**アクティビティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-135">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="041b5-136">[**名前**] ボックスに「`Prompt`」と入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-136">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="041b5-137">**ソリューションエクスプローラー**で [ **Prompt .xaml** ] をダブルクリックしてデザイナーに表示します (まだ表示されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="041b5-137">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="041b5-138">アクティビティ デザイナーの左下にある [**引数**] をクリックして、[**引数**] ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="041b5-138">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="041b5-139">[**Create Argument**] (引数の作成) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-139">Click **Create Argument**.</span></span>

8. <span data-ttu-id="041b5-140">[名前] ボックスに「」と入力し、[ `BookmarkName` **方向**] ドロップダウンリストから [ **In** ] を選択します。次に、[**引数の型**] ドロップダウンリストから [**文字列**] を選択し **、enter**キーを押して引数を保存します。 **Name**</span><span class="sxs-lookup"><span data-stu-id="041b5-140">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="041b5-141">[**Create Argument**] (引数の作成) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-141">Click **Create Argument**.</span></span>

10. <span data-ttu-id="041b5-142">`Result`新しく追加された引数の下にある [**名前**] ボックスに「」と入力し、 `BookmarkName` [**方向**] ドロップダウンリストから [ **Out** ] を選択します。次に、[**引数の型**] ドロップダウンリストから [ **Int32** ] を選択し **、enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="041b5-142">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="041b5-143">[**Create Argument**] (引数の作成) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-143">Click **Create Argument**.</span></span>

12. <span data-ttu-id="041b5-144">[名前] ボックスに「」と入力し、[ `Text` **方向**] ドロップダウンリストから [ **In** ] を選択します。次に、[**引数の型**] ドロップダウンリストから [**文字列**] を選択し **、enter**キーを押して引数を保存します。 **Name**</span><span class="sxs-lookup"><span data-stu-id="041b5-144">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="041b5-145">これら 3 つの引数は、次の手順で、<xref:System.Activities.Statements.WriteLine> アクティビティに追加される `ReadInt` アクティビティと `Prompt` アクティビティの対応する引数にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="041b5-145">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="041b5-146">アクティビティ デザイナーの左下にある [**引数**] をクリックして、[**引数**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="041b5-146">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="041b5-147">[**ツールボックス**] の [**制御フロー** ] セクションから**Sequence**アクティビティをドラッグし、 **Prompt**アクティビティデザイナーの [**ここにアクティビティをドロップ**] ラベルの上にドロップします。</span><span class="sxs-lookup"><span data-stu-id="041b5-147">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="041b5-148">[**ツールパレット**] ウィンドウが表示されていない場合は、[**表示**] メニューから [**ツールパレット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="041b5-148">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="041b5-149">**ツールボックス**の [**プリミティブ**] セクションから**WriteLine**アクティビティをドラッグし、 **Sequence**アクティビティの [ここに**アクティビティをドロップ**] ラベルにドロップします。</span><span class="sxs-lookup"><span data-stu-id="041b5-149">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="041b5-150">[プロパティ] ウィンドウの [ **WriteLine** C# の式を入力するか、VB の式を入力してください] ボックスに「」と入力し、WriteLine アクティビティの**Text**引数を**Prompt**アクティビティの**text**引数にバインド `Text` します。次に、 **tab**キーを2回押します。 **Enter a C# expression** **Enter a VB expression** **Properties**</span><span class="sxs-lookup"><span data-stu-id="041b5-150">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="041b5-151">これで、IntelliSense リスト メンバー ウィンドウを閉じ、プロパティから選択を外してプロパティ値を保存します。</span><span class="sxs-lookup"><span data-stu-id="041b5-151">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="041b5-152">このプロパティは `Text` 、アクティビティ自体の [C# の**式を入力**するか、 **VB の式を入力**してください] ボックスに「」と入力して設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="041b5-152">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="041b5-153">[**プロパティ] ウィンドウ**が表示されていない場合は、[**表示**] メニューの [**プロパティウィンドウ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="041b5-153">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="041b5-154">**ツールボックス**の [ **NumberGuessWorkflowActivities** ] セクションから**readint**アクティビティをドラッグし、 **WriteLine**アクティビティに従うように**Sequence**アクティビティにドロップします。</span><span class="sxs-lookup"><span data-stu-id="041b5-154">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="041b5-155">[ **Prompt** **BookmarkName** **BookmarkName**プロパティ] ウィンドウで BookmarkName 引数の右にある [VB の式を入力してください] ボックスに「」と入力し、tab キーを2回押して、IntelliSense の一覧のメンバーウィンドウを閉じ、プロパティを保存して、 **Readint**アクティビティの BookmarkName 引数を Prompt アクティビティの BookmarkName 引数にバインド `BookmarkName` します。 **Enter a VB expression** **BookmarkName** **Properties Window** **Tab**</span><span class="sxs-lookup"><span data-stu-id="041b5-155">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="041b5-156">[ **Prompt** **Result**プロパティ**Result** ] ウィンドウで result 引数の右側にある [VB の式を入力してください] ボックスに「」と入力して、 **Readint**アクティビティの result 引数を Prompt アクティビティの result 引数にバインドし、 `Result` **tab**キーを2回押します。 **Enter a VB expression** **Result** **Properties Window**</span><span class="sxs-lookup"><span data-stu-id="041b5-156">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="041b5-157">**Ctrl** + **Shift** + **B**キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="041b5-157">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="041b5-158">次のステップ</span><span class="sxs-lookup"><span data-stu-id="041b5-158">Next steps</span></span>

<span data-ttu-id="041b5-159">これらのアクティビティを使用してワークフローを作成する方法については、チュートリアルの次の手順「[方法: ワークフローを作成](how-to-create-a-workflow.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="041b5-159">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="041b5-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="041b5-160">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="041b5-161">カスタム アクティビティの設計と実装</span><span class="sxs-lookup"><span data-stu-id="041b5-161">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="041b5-162">はじめにチュートリアル</span><span class="sxs-lookup"><span data-stu-id="041b5-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="041b5-163">方法: ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="041b5-163">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="041b5-164">カスタム アクティビティ デザイナーでの ExpressionTextBox の使用</span><span class="sxs-lookup"><span data-stu-id="041b5-164">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
