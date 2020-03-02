---
title: '方法: シーケンシャル ワークフローを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 61e3f01b1259536ff15d71526e91aef42069722e
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989702"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="2530d-102">方法: シーケンシャル ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="2530d-102">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="2530d-103">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="2530d-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="2530d-104">このトピックでは、<xref:System.Activities.Statements.Sequence> アクティビティなどの組み込みアクティビティと、前の [のカスタムアクティビティの両方を使用するワークフローを作成する手順について説明します。アクティビティ](how-to-create-an-activity.md) トピックを作成します。</span><span class="sxs-lookup"><span data-stu-id="2530d-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="2530d-105">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="2530d-105">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="2530d-106">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="2530d-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="2530d-107">このトピックを完了するには、最初に次の手順を完了する必要があり [。アクティビティ](how-to-create-an-activity.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="2530d-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2530d-108">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2530d-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="2530d-109">ワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="2530d-109">To create the workflow</span></span>

1. <span data-ttu-id="2530d-110">**ソリューションエクスプローラー**で **[NumberGuessWorkflowActivities]** を右クリックし、 **[追加]** 、 **[新しい項目]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="2530d-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="2530d-111">**[インストール済み]** の **[共通項目]** ノードで、 **[ワークフロー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2530d-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="2530d-112">**[ワークフロー]** の一覧から **[アクティビティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2530d-112">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="2530d-113">**[名前]** ボックスに「`SequentialNumberGuessWorkflow`」と入力し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2530d-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="2530d-114">**[ツールボックス]** の **[制御フロー]** セクションから**Sequence**アクティビティをドラッグし、ワークフローデザインサーフェイスの **[ここにアクティビティをドロップ]** ラベルの上にドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="2530d-115">ワークフロー変数および引数を作成するには</span><span class="sxs-lookup"><span data-stu-id="2530d-115">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="2530d-116">**ソリューションエクスプローラー**で**sequentialnumberguessworkflow.xaml**をダブルクリックして、ワークフローをデザイナーに表示します (まだ表示されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="2530d-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="2530d-117">ワークフローデザイナーの左下にある **[引数]** をクリックして、 **[引数]** ペインを表示します。</span><span class="sxs-lookup"><span data-stu-id="2530d-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="2530d-118">**[引数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2530d-118">Click **Create Argument**.</span></span>

4. <span data-ttu-id="2530d-119">**[名前]** ボックスに「`MaxNumber`」と入力し、 **[方向]** ドロップダウンリストから **[In]** を選択します。次に、 **[引数の型]** ドロップダウンリストから **[Int32]** を選択し、enter キーを押して引数を保存します。</span><span class="sxs-lookup"><span data-stu-id="2530d-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="2530d-120">**[引数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2530d-120">Click **Create Argument**.</span></span>

6. <span data-ttu-id="2530d-121">新しく追加した `MaxNumber` 引数の下にある **[名前]** ボックスに「`Turns`」と入力し、 **[方向]** ドロップダウンリストから **[Out]** を選択します。次に、 **[引数の型]** ドロップダウンリストから **[Int32]** を選択し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2530d-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="2530d-122">アクティビティデザイナーの左下にある **[引数]** をクリックして、 **[引数]** ペインを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2530d-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="2530d-123">ワークフローデザイナーの左下にある **[変数]** をクリックして、 **[変数]** ペインを表示します。</span><span class="sxs-lookup"><span data-stu-id="2530d-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="2530d-124">**[変数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2530d-124">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2530d-125">**[変数の作成]** ボックスが表示されない場合は、ワークフローデザイナー画面で**Sequence**アクティビティをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="2530d-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="2530d-126">**[名前]** ボックスに「`Guess`」と入力し、 **[変数の型]** ドロップダウンリストから **[Int32]** を選択します。次に、enter キーを押して変数を保存します。</span><span class="sxs-lookup"><span data-stu-id="2530d-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="2530d-127">**[変数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2530d-127">Click **Create Variable**.</span></span>

12. <span data-ttu-id="2530d-128">**[名前]** ボックスに「`Target`」と入力し、 **[変数の型]** ドロップダウンリストから **[Int32]** を選択します。次に、enter キーを押して変数を保存します。</span><span class="sxs-lookup"><span data-stu-id="2530d-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="2530d-129">アクティビティデザイナーの左下にある **[変数]** をクリックして、 **[変数]** ペインを閉じます。</span><span class="sxs-lookup"><span data-stu-id="2530d-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="2530d-130">ワークフロー アクティビティを追加するには</span><span class="sxs-lookup"><span data-stu-id="2530d-130">To add the workflow activities</span></span>

1. <span data-ttu-id="2530d-131">**ツールボックス**の **[プリミティブ]** セクションから**Assign**アクティビティをドラッグし、 **Sequence**アクティビティにドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="2530d-132">**[To]** ボックスに「`Target`」と入力し、 **[式C#の入力]** または **[VB の式を入力]** してください ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="2530d-133">**[ツールボックス]** ウィンドウが表示されていない場合は、 **[表示]** メニューの **[ツールボックス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2530d-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="2530d-134">**ツールボックス**の **[制御フロー]** セクションから**dowhile**アクティビティをドラッグし、 **Assign**アクティビティの下になるようにワークフローにドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="2530d-135">**Dowhile**アクティビティの **[Condition]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="2530d-136"><xref:System.Activities.Statements.DoWhile> アクティビティはその子アクティビティを実行し、その <xref:System.Activities.Statements.DoWhile.Condition%2A> を評価します。</span><span class="sxs-lookup"><span data-stu-id="2530d-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="2530d-137"><xref:System.Activities.Statements.DoWhile.Condition%2A> が `True` と評価される場合、<xref:System.Activities.Statements.DoWhile> 内のアクティビティが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="2530d-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="2530d-138">この例では、ユーザーの推定値が評価され、推定値が正しいと判断されるまで <xref:System.Activities.Statements.DoWhile> が続行されます。</span><span class="sxs-lookup"><span data-stu-id="2530d-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="2530d-139">**[ツールボックス]** の **[NumberGuessWorkflowActivities]** セクションから**Prompt**アクティビティをドラッグし、前の手順の**dowhile**アクティビティにドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="2530d-140">[**プロパティ] ウィンドウ**で、 **Prompt**アクティビティの **[BookmarkName]** プロパティ値ボックスに引用符を含む `"EnterGuess"` を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="2530d-141">**[Result]** プロパティ値ボックスに「`Guess`」と入力し、 **[Text]** プロパティボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="2530d-142">[**プロパティ] ウィンドウ**が表示されていない場合は、 **[表示]** メニューの **[プロパティウィンドウ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2530d-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="2530d-143">**ツールボックス**の **[プリミティブ]** セクションから**Assign**アクティビティをドラッグして、 **Prompt**アクティビティに続くように**dowhile**アクティビティにドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2530d-144">**Assign**アクティビティを削除すると、ワークフローデザイナーが、 **Prompt**アクティビティと新しく追加された**Assign**アクティビティの両方を含む**Sequence**アクティビティを自動的に追加することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2530d-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="2530d-145">**[To]** ボックスに「`Turns`」と入力し、 **[式のC#入力]** ボックスまたは **[VB の式を入力]** してください ボックスに `Turns + 1` します。</span><span class="sxs-lookup"><span data-stu-id="2530d-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="2530d-146">**[ツールボックス]** の **[制御フロー]** セクションから**If**アクティビティをドラッグし、新しく追加した**Assign**アクティビティの後になるように**Sequence**アクティビティにドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="2530d-147">**If**アクティビティの **[Condition]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="2530d-148">**ツールボックス**の **[制御フロー]** セクションから別の**if**アクティビティをドラッグし、最初の**if**アクティビティの**Then**セクションにドロップします。</span><span class="sxs-lookup"><span data-stu-id="2530d-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="2530d-149">新しく追加された**If**アクティビティの **[Condition]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="2530d-150">**ツールボックス**の **[プリミティブ]** セクションから2つの**WriteLine**アクティビティをドラッグしてドロップします。1つは、新しく追加した**If**アクティビティの**Then**セクションにあり、もう1つは**Else**セクションにあります。</span><span class="sxs-lookup"><span data-stu-id="2530d-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="2530d-151">**[Then** ] セクションで **[WriteLine]** アクティビティをクリックして選択し、 **[Text]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="2530d-152">**[Else]** セクションの**WriteLine**アクティビティをクリックして選択し、 **[Text]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="2530d-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="2530d-153">完成したワークフローの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2530d-153">The following example illustrates the completed workflow:</span></span>

     ![完成したシーケンシャルワークフローを示すスクリーンショット。](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="2530d-155">ワークフローをビルドするには</span><span class="sxs-lookup"><span data-stu-id="2530d-155">To build the workflow</span></span>

1. <span data-ttu-id="2530d-156">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2530d-156">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="2530d-157">ワークフローを実行する方法については、次のトピック「[方法」を参照してください。ワークフロー](how-to-run-a-workflow.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="2530d-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="2530d-158">[を既に完了している場合は、次の方法を実行します。異なるスタイルのワークフローを使用してワークフロー](how-to-run-a-workflow.md) ステップを実行し、この手順のシーケンシャルワークフローを使用して実行するには、の「[アプリケーションをビルドして実行するに](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)[は」に進んでください: ワークフロー を実行します](how-to-run-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="2530d-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2530d-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="2530d-159">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="2530d-160">Windows Workflow Foundation プログラミング</span><span class="sxs-lookup"><span data-stu-id="2530d-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="2530d-161">ワークフローの設計</span><span class="sxs-lookup"><span data-stu-id="2530d-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="2530d-162">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="2530d-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="2530d-163">方法: アクティビティ を作成する</span><span class="sxs-lookup"><span data-stu-id="2530d-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="2530d-164">方法: ワークフロー を実行する</span><span class="sxs-lookup"><span data-stu-id="2530d-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
