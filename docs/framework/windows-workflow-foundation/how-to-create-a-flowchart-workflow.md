---
title: '方法: フローチャート ワークフローを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 10483c747e0f86816db6f03dd8df17472f31f15c
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063770"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="e3c8f-102">方法: フローチャート ワークフローを作成する</span><span class="sxs-lookup"><span data-stu-id="e3c8f-102">How to: Create a Flowchart Workflow</span></span>
<span data-ttu-id="e3c8f-103">ワークフローは、ビルトイン アクティビティおよびカスタム アクティビティから構築できます。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="e3c8f-104">このトピックでなど両方の組み込みのアクティビティを使用するワークフローを作成する手順、<xref:System.Activities.Statements.Flowchart>アクティビティ、およびカスタム アクティビティ、前の[方法。アクティビティ作成](how-to-create-an-activity.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="e3c8f-105">このワークフローは、数値推測ゲームをモデル化しています。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3c8f-106">チュートリアル入門の各トピックは、前のトピックに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="e3c8f-107">このトピックを完了する必要がありますを完了して[方法。アクティビティ作成](how-to-create-an-activity.md)です。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3c8f-108">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="e3c8f-109">ワークフローを作成するには</span><span class="sxs-lookup"><span data-stu-id="e3c8f-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="e3c8f-110">右クリック**NumberGuessWorkflowActivities**で**ソリューション エクスプ ローラー**選択**追加**、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="e3c8f-111">**インストール済み**、**一般的な項目**ノードの **ワークフロー**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="e3c8f-112">選択**アクティビティ**から、**ワークフロー**一覧。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="e3c8f-113">型`FlowchartNumberGuessWorkflow`に、**名前**ボックスし、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="e3c8f-114">ドラッグ、**フローチャート**からのアクティビティ、**フローチャート**のセクション、**ツールボックス**にドロップし、**ここにアクティビティをドロップ**のラベルをワークフロー デザイン サーフェイス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="e3c8f-115">ワークフロー変数および引数を作成するには</span><span class="sxs-lookup"><span data-stu-id="e3c8f-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="e3c8f-116">ダブルクリック**FlowchartNumberGuessWorkflow.xaml**で**ソリューション エクスプ ローラー**まだ表示されていない場合に、デザイナーでワークフローを表示します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="e3c8f-117">クリックして**引数**を表示するワークフロー デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="e3c8f-118">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="e3c8f-119">型`MaxNumber`に、**名前**ボックスで、**で**から、**方向**ドロップダウン リストで、 **Int32** から**引数の型**ドロップダウン リスト、および引数を保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="e3c8f-120">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="e3c8f-121">型`Turns`に、**名前**新しく追加された下にあるボックス`MaxNumber`引数で、**アウト**から、**方向**選択ドロップダウンリスト**Int32**から、**引数の型**ドロップダウン リスト、および ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="e3c8f-122">クリックして**引数**を閉じるアクティビティ デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="e3c8f-123">クリックして**変数**を表示するワークフロー デザイナーの左下で、**変数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="e3c8f-124">クリックして**変数作成**です。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e3c8f-125">ない場合は**変数の作成**ボックスが表示されたら、をクリックして、<xref:System.Activities.Statements.Flowchart>ことを選択するには、ワークフロー デザイナー画面上のアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="e3c8f-126">型`Guess`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="e3c8f-127">クリックして**変数作成**です。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="e3c8f-128">型`Target`に、**名前**ボックスで、 **Int32**から、**変数の型**ドロップダウン リスト、および、変数に保存するには ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="e3c8f-129">クリックして**変数**を閉じるアクティビティ デザイナーの左下で、**変数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="e3c8f-130">ワークフロー アクティビティを追加するには</span><span class="sxs-lookup"><span data-stu-id="e3c8f-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="e3c8f-131">ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**上にマウス ポインターと、**開始**の上部には、ノード、フローチャート。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="e3c8f-132">ときに、**割り当てる**経由でのアクティビティは、**開始**ノードを囲む 3 つの三角形が表示されます、**開始**ノード。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="e3c8f-133">削除、**割り当てる**すぐ下にある三角形のアクティビティ、**開始**ノード。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="e3c8f-134">これは、2 つの項目をまとめてリンクし、指定、**割り当てる**フローチャート内の最初のアクティビティとしてアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3c8f-135">アクティビティは、開始ノードに手動でリンクすることにより、ワークフローの開始アクティビティとして指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="e3c8f-136">これを行うには、マウス ポインターを置き、**開始**ノード上にマウスがときに表示される四角形のいずれかを**開始**ノード、およびドラッグ、接続まで、必要なアクティビティの行し、のいずれかの上にドロップ表示される四角形。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="e3c8f-137">It を右クリックして、開始アクティビティとしてアクティビティを指定することも**開始ノードとして設定**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-137">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="e3c8f-138">型`Target`に、**に**ボックスし、次の式を**c# 式を入力します**または**VB の式を入力します。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="e3c8f-139">場合、**ツールボックス**ウィンドウが表示されない場合、選択**ツールボックス**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="e3c8f-140">ドラッグ、**プロンプト**からのアクティビティ、 **NumberGuessWorkflowActivities**のセクション、**ツールボックス**、下にドロップ、**割り当てる**アクティビティ前の手順との接続、**プロンプト**アクティビティを**割り当てる**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="e3c8f-141">2 つのアクティビティを接続する方法は 3 種類あります。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="e3c8f-142">最初の方法は、ドロップするときに、それらを接続する、**プロンプト**ワークフローのアクティビティをします。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="e3c8f-143">ドラッグする、**プロンプト**、ワークフローにアクティビティ上に置き、**割り当てる**アクティビティのときに表示される 4 つの三角形の 1 つにドロップし、**プロンプト**アクティビティが経由では、**割り当てる**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="e3c8f-144">2 つ目の方法は、削除する、**プロンプト**アクティビティ、ワークフローの目的の場所。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="e3c8f-145">次に、マウス ポインターを置き、**割り当てる**アクティビティと 1 つ下に表示される四角形のドラッグ、**プロンプト**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="e3c8f-146">線を接続するため、マウスをドラッグ、**割り当てる**の四角形のいずれかに接続するアクティビティ、**プロンプト**アクティビティ、およびマウス ボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="e3c8f-147">3 番目の方法にドラッグする代わりに、最初の方法とよく似ていますが、**プロンプト**からのアクティビティ、**ツールボックス**、ワークフロー デザイン サーフェイス上の場所からドラッグして、上にマウスポインターをします。**割り当てる**アクティビティ、表示される三角形のいずれかにドロップします。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="e3c8f-148">**プロパティ ウィンドウ**の**プロンプト**アクティビティで、「`"EnterGuess"`に引用符を含む、 **BookmarkName**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="e3c8f-149">型`Guess`に、**結果**プロパティの値のボックスとには、次の式を入力、**テキスト**プロパティ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="e3c8f-150">場合、**プロパティ ウィンドウ**が表示されている、選択**プロパティ ウィンドウ**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="e3c8f-151">ドラッグ、**割り当てる**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**下に、前の手順で説明する方法のいずれかを使用して接続と**プロンプト**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="e3c8f-152">型`Turns`に、**に**ボックスと`Turns + 1`に、 **c# 式を入力します**または**VB の式を入力します。** ボックス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="e3c8f-153">ドラッグ、 **FlowDecision**から、**フローチャート**のセクション、**ツールボックス**下に接続し、**割り当てる**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="e3c8f-154">**プロパティ ウィンドウ**には、次の式を入力、**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="e3c8f-155">もう 1 つドラッグ**FlowDecision**からのアクティビティ、**ツールボックス**と 1 つ目の下にドロップします。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="e3c8f-156">ラベルがついた四角形からドラッグして、2 つのアクティビティを接続**False**上にある**FlowDecision** 、2 つ目の上部にある四角形をアクティビティ**FlowDecision**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e3c8f-157">表示されない場合、 **True**と**False**ラベル、 **FlowDecision**、マウス ポインターを置き、 **FlowDecision**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="e3c8f-158">2 つ目のクリックして**FlowDecision**アクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="e3c8f-159">**プロパティ ウィンドウ**には、次の式を入力、**条件**プロパティ値ボックス。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
10. <span data-ttu-id="e3c8f-160">2 つをドラッグして**WriteLine**からアクティビティ、**プリミティブ**のセクション、**ツールボックス**も並行して 2 つ下されるようにドロップして**FlowDecision**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="e3c8f-161">接続、 **True**アクションの下部にある**FlowDecision**左端にアクティビティ**WriteLine**アクティビティ、および**False**アクションを右端**WriteLine**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="e3c8f-162">最も左クリックして**WriteLine**アクティビティを選択し、次の式を入力、**テキスト**プロパティ値ボックスに、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="e3c8f-163">接続、 **WriteLine**の左側に、**プロンプト**上にあるアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="e3c8f-164">最も右クリック**WriteLine**アクティビティを選択し、次の式を入力、**テキスト**プロパティ値ボックスに、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="e3c8f-165">接続、 **WriteLine**の右側にあるアクティビティ、**プロンプト**その上アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="e3c8f-166">次の例は完成したワークフローを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-166">The following example illustrates the completed workflow.</span></span>  
  
     ![完成した Windows Workflow Foundation のフローチャートを示す図。](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="e3c8f-168">ワークフローをビルドするには</span><span class="sxs-lookup"><span data-stu-id="e3c8f-168">To build the workflow</span></span>  
  
1. <span data-ttu-id="e3c8f-169">Ctrl キーと Shift キーを押しながら B キーを押して、ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="e3c8f-170">ワークフローを実行する方法について、次のトピックをご覧ください[方法。ワークフローを実行する](how-to-run-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="e3c8f-171">既に完了している場合、[方法。ワークフローを実行する](how-to-run-a-workflow.md)ステップのワークフローのさまざまなスタイルと共に、フローチャート ワークフローがこの手順を使用してを実行してに進んで、 [、アプリケーションをビルドして実行](how-to-run-a-workflow.md#BKMK_ToRunTheApplication)のセクション[方法。ワークフローを実行する](how-to-run-a-workflow.md)します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-171">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c8f-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3c8f-172">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="e3c8f-173">Windows Workflow Foundation プログラミング</span><span class="sxs-lookup"><span data-stu-id="e3c8f-173">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="e3c8f-174">ワークフローの設計</span><span class="sxs-lookup"><span data-stu-id="e3c8f-174">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="e3c8f-175">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="e3c8f-175">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="e3c8f-176">方法: アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-176">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="e3c8f-177">方法: ワークフローを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3c8f-177">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
