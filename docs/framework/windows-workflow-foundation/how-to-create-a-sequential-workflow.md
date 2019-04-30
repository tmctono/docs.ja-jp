---
title: '方法: シーケンシャル ワークフローの作成'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: c8a16dc0269fbd768a73e99f15f53e38c207a8d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945596"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="2c841-102">方法: シーケンシャル ワークフローの作成</span><span class="sxs-lookup"><span data-stu-id="2c841-102">How to: Create a Sequential Workflow</span></span>
<span data-ttu-id="2c841-103">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="2c841-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="2c841-104">このトピックでなど両方の組み込みのアクティビティを使用するワークフローを作成する手順、<xref:System.Activities.Statements.Sequence>アクティビティ、およびカスタム アクティビティ、前の[方法。アクティビティ作成](how-to-create-an-activity.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="2c841-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="2c841-105">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="2c841-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c841-106">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="2c841-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="2c841-107">このトピックを完了する必要がありますを完了して[方法。アクティビティ作成](how-to-create-an-activity.md)です。</span><span class="sxs-lookup"><span data-stu-id="2c841-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c841-108">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c841-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="to-create-the-workflow"></a><span data-ttu-id="2c841-109">ワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="2c841-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="2c841-110">右クリック**NumberGuessWorkflowActivities**で**ソリューション エクスプ ローラー**選択**追加**、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="2c841-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="2c841-111">**インストール済み**、**一般的な項目**ノードの **ワークフロー**します。</span><span class="sxs-lookup"><span data-stu-id="2c841-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="2c841-112">選択**アクティビティ**から、**ワークフロー**一覧。</span><span class="sxs-lookup"><span data-stu-id="2c841-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="2c841-113">型`SequentialNumberGuessWorkflow`に、**名前**ボックスし、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="2c841-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="2c841-114">ドラッグ、**シーケンス**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**にドロップし、**ここにアクティビティをドロップ**のラベルをワークフロー デザイン サーフェイス。</span><span class="sxs-lookup"><span data-stu-id="2c841-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="2c841-115">ワークフロー変数および引数を作成するには</span><span class="sxs-lookup"><span data-stu-id="2c841-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="2c841-116">ダブルクリック**SequentialNumberGuessWorkflow.xaml**で**ソリューション エクスプ ローラー**まだ表示されていない場合に、デザイナーでワークフローを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c841-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="2c841-117">クリックして**引数**を表示するワークフロー デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2c841-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="2c841-118">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="2c841-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="2c841-119">型`MaxNumber`に、**名前**ボックスで、**で**から、**方向**ドロップダウン リストで、 **Int32** から**引数の型**ドロップダウン リスト、および引数を保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2c841-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="2c841-120">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="2c841-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="2c841-121">型`Turns`に、**名前**新しく追加された下にあるボックス`MaxNumber`引数で、**アウト**から、**方向**選択ドロップダウンリスト**Int32**から、**引数の型**ドロップダウン リスト、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2c841-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="2c841-122">クリックして**引数**を閉じるアクティビティ デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2c841-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="2c841-123">クリックして**変数**を表示するワークフロー デザイナーの左下で、**変数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2c841-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="2c841-124">クリックして**変数作成**です。</span><span class="sxs-lookup"><span data-stu-id="2c841-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="2c841-125">ない場合は**変数の作成**ボックスが表示されたら、をクリックして、**シーケンス**ことを選択するには、ワークフロー デザイナー画面上のアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="2c841-126">型`Guess`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2c841-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="2c841-127">クリックして**変数作成**です。</span><span class="sxs-lookup"><span data-stu-id="2c841-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="2c841-128">型`Target`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2c841-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="2c841-129">クリックして**変数**を閉じるアクティビティ デザイナーの左下で、**変数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="2c841-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="2c841-130">ワークフロー アクティビティを追加するには</span><span class="sxs-lookup"><span data-stu-id="2c841-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="2c841-131">ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**シーケンス**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="2c841-132">型`Target`に、**に**ボックスし、次の式を**c# 式を入力します**または**VB の式を入力します。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="2c841-133">場合、**ツールボックス**ウィンドウが表示されない場合、選択**ツールボックス**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="2c841-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="2c841-134">ドラッグ、 **DoWhile**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**下に、ワークフローにドロップし、**割り当てる**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>  
  
3. <span data-ttu-id="2c841-135">次の式を入力、 **DoWhile**アクティビティの**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <span data-ttu-id="2c841-136"><xref:System.Activities.Statements.DoWhile> アクティビティはその子アクティビティを実行し、その <xref:System.Activities.Statements.DoWhile.Condition%2A> を評価します。</span><span class="sxs-lookup"><span data-stu-id="2c841-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="2c841-137"><xref:System.Activities.Statements.DoWhile.Condition%2A> が `True` と評価される場合、<xref:System.Activities.Statements.DoWhile> 内のアクティビティが再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="2c841-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="2c841-138">この例では、ユーザーの推定値が評価され、推定値が正しいと判断されるまで <xref:System.Activities.Statements.DoWhile> が続行されます。</span><span class="sxs-lookup"><span data-stu-id="2c841-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>  
  
4. <span data-ttu-id="2c841-139">ドラッグ、**プロンプト**からのアクティビティ、 **NumberGuessWorkflowActivities**のセクション、**ツールボックス**にドロップし、 **DoWhile**アクティビティ前の手順。</span><span class="sxs-lookup"><span data-stu-id="2c841-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>  
  
5. <span data-ttu-id="2c841-140">**プロパティ ウィンドウ**、型`"EnterGuess"`に引用符を含む、 **BookmarkName**のプロパティ値ボックスに、**プロンプト**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="2c841-141">型`Guess`に、**結果**プロパティの値のボックスとには、次の式を入力、**テキスト**プロパティ ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="2c841-142">場合、**プロパティ ウィンドウ**が表示されている、選択**プロパティ ウィンドウ**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="2c841-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
6. <span data-ttu-id="2c841-143">ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、 **DoWhile**アクティビティの後になるように、**プロンプト**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c841-144">ドロップすると、**割り当てる**アクティビティをワークフロー デザイナーが自動的に追加する方法を確認、**シーケンス**両方を含むアクティビティ、**プロンプト**アクティビティと新しく追加されました。**割り当てる**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>  
  
7. <span data-ttu-id="2c841-145">型`Turns`に、**に**ボックスと`Turns + 1`に、 **c# 式を入力します**または**VB の式を入力します。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
8. <span data-ttu-id="2c841-146">ドラッグ、**場合**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**にドロップし、**シーケンス**アクティビティの後になるように、新しく追加された**割り当てる**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>  
  
9. <span data-ttu-id="2c841-147">次の式を入力、**場合**アクティビティの**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. <span data-ttu-id="2c841-148">もう 1 つドラッグ**場合**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**にドロップし、**し**最初のセクション**場合**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2c841-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>  
  
11. <span data-ttu-id="2c841-149">新しく追加された次の式を入力**場合**アクティビティの**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
12. <span data-ttu-id="2c841-150">2 つをドラッグして**WriteLine**アクティビティから、**プリミティブ**のセクション、**ツールボックス**で 1 つがされるようにドロップし、**し**のセクション新しく追加された**場合**、もう 1 つは、 **Else**セクション。</span><span class="sxs-lookup"><span data-stu-id="2c841-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>  
  
13. <span data-ttu-id="2c841-151">をクリックして、 **WriteLine**内のアクティビティ、**し**セクションを選択しとには、次の式を入力、**テキスト**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
14. <span data-ttu-id="2c841-152">をクリックして、 **WriteLine**内のアクティビティ、 **Else**セクションを選択しとには、次の式を入力、**テキスト**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="2c841-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
     <span data-ttu-id="2c841-153">次の例は、完了したワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="2c841-153">The following example illustrates the completed workflow:</span></span>  
  
     ![完成したシーケンシャル ワークフローを示すスクリーン ショット。](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)  
  
## <a name="to-build-the-workflow"></a><span data-ttu-id="2c841-155">ワークフローをビルドするには</span><span class="sxs-lookup"><span data-stu-id="2c841-155">To build the workflow</span></span>  
  
1. <span data-ttu-id="2c841-156">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="2c841-156">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="2c841-157">ワークフローを実行する方法について、次のトピックをご覧ください[方法。ワークフローを実行する](how-to-run-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c841-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="2c841-158">既に完了している場合、[方法。ワークフローを実行する](how-to-run-a-workflow.md)さまざまなスタイルのワークフローにステップ イン、シーケンシャル ワークフローこの手順を使用してを実行してに進んで、 [、アプリケーションをビルドして実行](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)のセクション[方法。ワークフローを実行する](how-to-run-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c841-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c841-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c841-159">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="2c841-160">Windows Workflow Foundation プログラミング</span><span class="sxs-lookup"><span data-stu-id="2c841-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="2c841-161">ワークフローの設計</span><span class="sxs-lookup"><span data-stu-id="2c841-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="2c841-162">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="2c841-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="2c841-163">方法: アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c841-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="2c841-164">方法: ワークフローを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c841-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
