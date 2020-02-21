---
title: '方法: フローチャート ワークフローを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 0faf4d77b1ea2881ba8e029d544f2e42cf552349
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989683"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="37a30-102">方法: フローチャート ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="37a30-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="37a30-103">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="37a30-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="37a30-104">このトピックでは、<xref:System.Activities.Statements.Flowchart> アクティビティなどの組み込みアクティビティと、前の [のカスタムアクティビティの両方を使用するワークフローを作成する手順について説明します。アクティビティ](how-to-create-an-activity.md) トピックを作成します。</span><span class="sxs-lookup"><span data-stu-id="37a30-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="37a30-105">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="37a30-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37a30-106">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="37a30-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="37a30-107">このトピックを完了するには、最初に次の手順を完了する必要があり [。アクティビティ](how-to-create-an-activity.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="37a30-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37a30-108">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37a30-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="37a30-109">ワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="37a30-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="37a30-110">**ソリューションエクスプローラー**で **[NumberGuessWorkflowActivities]** を右クリックし、 **[追加]** 、 **[新しい項目]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="37a30-111">**[インストール済み]** の **[共通項目]** ノードで、 **[ワークフロー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="37a30-112">**[ワークフロー]** の一覧から **[アクティビティ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="37a30-113">**[名前]** ボックスに「`FlowchartNumberGuessWorkflow`」と入力し、 **[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37a30-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="37a30-114">**[ツールボックス]** の **[フローチャート]** セクションから**flowchart**アクティビティをドラッグし、ワークフローデザインサーフェイスの **[ここにアクティビティをドロップ]** ラベルの上にドロップします。</span><span class="sxs-lookup"><span data-stu-id="37a30-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="37a30-115">ワークフロー変数および引数を作成するには</span><span class="sxs-lookup"><span data-stu-id="37a30-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="37a30-116">**ソリューションエクスプローラー**で**flowchartnumberguessworkflow.xaml**をダブルクリックして、ワークフローをデザイナーに表示します (まだ表示されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="37a30-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="37a30-117">ワークフローデザイナーの左下にある **[引数]** をクリックして、 **[引数]** ペインを表示します。</span><span class="sxs-lookup"><span data-stu-id="37a30-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="37a30-118">**[引数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37a30-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="37a30-119">**[名前]** ボックスに「`MaxNumber`」と入力し、 **[方向]** ドロップダウンリストから **[In]** を選択します。次に、 **[引数の型]** ドロップダウンリストから **[Int32]** を選択し、enter キーを押して引数を保存します。</span><span class="sxs-lookup"><span data-stu-id="37a30-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="37a30-120">**[引数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37a30-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="37a30-121">新しく追加した `MaxNumber` 引数の下にある **[名前]** ボックスに「`Turns`」と入力し、 **[方向]** ドロップダウンリストから **[Out]** を選択します。次に、 **[引数の型]** ドロップダウンリストから **[Int32]** を選択し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="37a30-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="37a30-122">アクティビティデザイナーの左下にある **[引数]** をクリックして、 **[引数]** ペインを閉じます。</span><span class="sxs-lookup"><span data-stu-id="37a30-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="37a30-123">ワークフローデザイナーの左下にある **[変数]** をクリックして、 **[変数]** ペインを表示します。</span><span class="sxs-lookup"><span data-stu-id="37a30-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="37a30-124">**[変数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37a30-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="37a30-125">**[変数の作成]** ボックスが表示されない場合は、ワークフローデザイナー画面の [<xref:System.Activities.Statements.Flowchart>] アクティビティをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="37a30-126">**[名前]** ボックスに「`Guess`」と入力し、 **[変数の型]** ドロップダウンリストから **[Int32]** を選択します。次に、enter キーを押して変数を保存します。</span><span class="sxs-lookup"><span data-stu-id="37a30-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="37a30-127">**[変数の作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37a30-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="37a30-128">**[名前]** ボックスに「`Target`」と入力し、 **[変数の型]** ドロップダウンリストから **[Int32]** を選択します。次に、enter キーを押して変数を保存します。</span><span class="sxs-lookup"><span data-stu-id="37a30-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="37a30-129">アクティビティデザイナーの左下にある **[変数]** をクリックして、 **[変数]** ペインを閉じます。</span><span class="sxs-lookup"><span data-stu-id="37a30-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="37a30-130">ワークフロー アクティビティを追加するには</span><span class="sxs-lookup"><span data-stu-id="37a30-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="37a30-131">**ツールボックス**の **[プリミティブ]** セクションから**Assign**アクティビティをドラッグし、フローチャートの上部にある **[開始]** ノードの上にポイントします。</span><span class="sxs-lookup"><span data-stu-id="37a30-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="37a30-132">**Assign**アクティビティが**開始**ノードを超えている場合、**スタート**ノードの周囲に3つの三角形が表示されます。</span><span class="sxs-lookup"><span data-stu-id="37a30-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="37a30-133">**Assign**アクティビティを**開始**ノードのすぐ下にある三角形にドロップします。</span><span class="sxs-lookup"><span data-stu-id="37a30-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="37a30-134">これにより、2つの項目がリンクされ、フローチャートの最初のアクティビティとして**Assign**アクティビティが指定されます。</span><span class="sxs-lookup"><span data-stu-id="37a30-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="37a30-135">アクティビティは、開始ノードに手動でリンクすることにより、ワークフローの開始アクティビティとして指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="37a30-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="37a30-136">これを行うには、**開始** ノードの上にマウスポインターを移動し、**開始** ノードの上にマウスがあるときに表示される四角形の1つをクリックします。次に、接続 行を目的のアクティビティにドラッグして、表示される四角形の1つにドロップします。</span><span class="sxs-lookup"><span data-stu-id="37a30-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="37a30-137">アクティビティを開始アクティビティとして指定することもできます。それには、アクティビティを右クリックし、 **[開始ノードとして設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-137">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="37a30-138">**[To]** ボックスに「`Target`」と入力し、 **[式C#の入力]** または **[VB の式を入力]** してください ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="37a30-139">**[ツールボックス]** ウィンドウが表示されていない場合は、 **[表示]** メニューの **[ツールボックス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="37a30-140">**[ツールボックス]** の **[NumberGuessWorkflowActivities]** セクションから**prompt**アクティビティをドラッグし、前の手順の**assign**アクティビティの下にドロップして、 **prompt**アクティビティを**assign**アクティビティに接続します。</span><span class="sxs-lookup"><span data-stu-id="37a30-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="37a30-141">2 つのアクティビティを接続する方法は 3 種類あります。</span><span class="sxs-lookup"><span data-stu-id="37a30-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="37a30-142">最初の方法は、ワークフローに**Prompt**アクティビティをドロップするときに接続することです。</span><span class="sxs-lookup"><span data-stu-id="37a30-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="37a30-143">**Prompt**アクティビティをワークフローにドラッグするときは、 **assign**アクティビティの上にマウスポインターを置き、 **prompt**アクティビティが**assign**アクティビティを超えたときに表示される4つの三角形の1つにドロップします。</span><span class="sxs-lookup"><span data-stu-id="37a30-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="37a30-144">2つ目の方法は、必要な場所にあるワークフローに**Prompt**アクティビティをドロップすることです。</span><span class="sxs-lookup"><span data-stu-id="37a30-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="37a30-145">次に、 **Assign**アクティビティの上にマウスポインターを移動し、 **[プロンプト]** アクティビティに表示されている四角形の1つをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="37a30-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="37a30-146">**Assign**アクティビティの接続線が**Prompt**アクティビティの四角形の1つに接続するようにマウスをドラッグし、マウスボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="37a30-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="37a30-147">3番目の方法は最初の方法とよく似ていますが、 **Prompt**アクティビティを**ツールボックス**からドラッグするのではなく、ワークフローデザインサーフェイス上の場所からドラッグし、 **Assign**アクティビティの上にマウスポインターを移動して、表示される三角形の1つにドロップする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="37a30-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="37a30-148">**Prompt**アクティビティの [**プロパティ] ウィンドウ**で、 **[BookmarkName]** プロパティ値ボックスに引用符を含め `"EnterGuess"` 入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="37a30-149">**[Result]** プロパティ値ボックスに「`Guess`」と入力し、 **[Text]** プロパティボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="37a30-150">[**プロパティ] ウィンドウ**が表示されていない場合は、 **[表示]** メニューの **[プロパティウィンドウ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37a30-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="37a30-151">**[ツールボックス]** の **[プリミティブ]** セクションから**Assign**アクティビティをドラッグして、前の手順で説明したメソッドのいずれかを使用して接続し、 **Prompt**アクティビティの下に表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="37a30-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="37a30-152">**[To]** ボックスに「`Turns`」と入力し、 **[式のC#入力]** ボックスまたは **[VB の式を入力]** してください ボックスに `Turns + 1` します。</span><span class="sxs-lookup"><span data-stu-id="37a30-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="37a30-153">**ツールボックス**の **[フローチャート]** セクションから**Flowdecision**をドラッグし、 **Assign**アクティビティの下に接続します。</span><span class="sxs-lookup"><span data-stu-id="37a30-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="37a30-154">[**プロパティ] ウィンドウ**で、 **[条件]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="37a30-155">別の**Flowdecision**アクティビティを **ツールボックス** からドラッグして、最初の 判断 アクティビティの下にドロップします。</span><span class="sxs-lookup"><span data-stu-id="37a30-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="37a30-156">2つのアクティビティを連結します。そのためには、上部の**Flowdecision**アクティビティで**False**という名前の四角形から、2番目の**flowdecision**アクティビティの上部にある四角形をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="37a30-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="37a30-157">**Flowdecision**に**True**と**False**のラベルが表示されない場合は、 **flowdecision**の上にマウスポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="37a30-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="37a30-158">2番目の**Flowdecision**アクティビティをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="37a30-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="37a30-159">[**プロパティ] ウィンドウ**で、 **[条件]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="37a30-160">**ツールボックス**の **[プリミティブ]** セクションから2つの**WriteLine**アクティビティをドラッグし、2つの**flowdecision**アクティビティの横に並んでいるようにドロップします。</span><span class="sxs-lookup"><span data-stu-id="37a30-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="37a30-161">下の**Flowdecision**アクティビティの**真**のアクションを左端の**writeline**アクティビティに接続し、 **False**アクションを右端の**writeline**アクティビティに接続します。</span><span class="sxs-lookup"><span data-stu-id="37a30-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="37a30-162">左端の**WriteLine**アクティビティをクリックして選択し、[**プロパティ] ウィンドウ**の **[Text]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="37a30-163">**WriteLine**を、その上にある**Prompt**アクティビティの左側に接続します。</span><span class="sxs-lookup"><span data-stu-id="37a30-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="37a30-164">右の**WriteLine**アクティビティをクリックして選択し、[**プロパティ] ウィンドウ**の **[Text]** プロパティ値ボックスに次の式を入力します。</span><span class="sxs-lookup"><span data-stu-id="37a30-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="37a30-165">その上にある**Prompt**アクティビティの右側に、 **WriteLine**アクティビティを接続します。</span><span class="sxs-lookup"><span data-stu-id="37a30-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="37a30-166">次の例は完成したワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="37a30-166">The following example illustrates the completed workflow.</span></span>  
  
     ![完成した Windows Workflow Foundation フローチャートを示す図。](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="37a30-168">ワークフローをビルドするには</span><span class="sxs-lookup"><span data-stu-id="37a30-168">To build the workflow</span></span>  
  
1. <span data-ttu-id="37a30-169">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="37a30-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="37a30-170">ワークフローを実行する方法については、次のトピック「[方法」を参照してください。ワークフロー](how-to-run-a-workflow.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="37a30-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="37a30-171">[を既に完了している場合は、次の方法を実行します。異なるスタイルのワークフローを使用してワークフロー](how-to-run-a-workflow.md) ステップを実行し、この手順のフローチャートワークフローを使用して実行するには、[の「[アプリケーションをビルドして実行するに](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)は」に進んでください。ワークフロー](how-to-run-a-workflow.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="37a30-171">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a30-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="37a30-172">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="37a30-173">Windows Workflow Foundation プログラミング</span><span class="sxs-lookup"><span data-stu-id="37a30-173">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="37a30-174">ワークフローの設計</span><span class="sxs-lookup"><span data-stu-id="37a30-174">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="37a30-175">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="37a30-175">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- <span data-ttu-id="37a30-176">[方法: アクティビティ](how-to-create-an-activity.md) を作成する</span><span class="sxs-lookup"><span data-stu-id="37a30-176">[How to: Create an Activity](how-to-create-an-activity.md)</span></span>
- <span data-ttu-id="37a30-177">[方法: ワークフロー](how-to-run-a-workflow.md) を実行する</span><span class="sxs-lookup"><span data-stu-id="37a30-177">[How to: Run a Workflow](how-to-run-a-workflow.md)</span></span>
