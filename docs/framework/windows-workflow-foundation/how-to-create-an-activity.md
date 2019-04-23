---
title: '方法: アクティビティを作成する'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 48df9b90a92468858bd3ac5498bd83fd0d57fe75
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315141"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="31f5e-102">方法: アクティビティを作成する</span><span class="sxs-lookup"><span data-stu-id="31f5e-102">How to: Create an Activity</span></span>

<span data-ttu-id="31f5e-103">アクティビティは [!INCLUDE[wf1](../../../includes/wf1-md.md)] の動作の中心的な単位です。</span><span class="sxs-lookup"><span data-stu-id="31f5e-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="31f5e-104">アクティビティの実行ロジックはマネージ コードで実装できます。または他のアクティビティを使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="31f5e-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="31f5e-105">このトピックでは、2 つのアクティビティを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="31f5e-106">最初のアクティビティは、コードを使用してその実行ロジックを実装する単純なアクティビティです。</span><span class="sxs-lookup"><span data-stu-id="31f5e-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="31f5e-107">2 番目のアクティビティの実装は他のアクティビティを使用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="31f5e-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="31f5e-108">これらのアクティビティは、チュートリアルの次の手順で使用します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-108">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="31f5e-109">チュートリアルの完成版をダウンロードするには、「 [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45) - チュートリアル入門)](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f5e-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="31f5e-110">アクティビティ ライブラリ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-110">Create the activity library project</span></span>

1. <span data-ttu-id="31f5e-111">Visual Studio を開き、選択**新規** > **プロジェクト**から、**ファイル**メニュー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-111">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="31f5e-112">**新しいプロジェクト**ダイアログで、**インストール済み**カテゴリで、 **Visual c#** > **ワークフロー** (または**Visual Basic** > **ワークフロー**)。</span><span class="sxs-lookup"><span data-stu-id="31f5e-112">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="31f5e-113">表示されない場合、**ワークフロー**テンプレートのカテゴリをインストールする必要があります、 **Windows Workflow Foundation** Visual Studio のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="31f5e-113">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="31f5e-114">選択、 **Visual Studio インストーラーを開く**の左側にあるリンク、**新しいプロジェクト**ダイアログ。</span><span class="sxs-lookup"><span data-stu-id="31f5e-114">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="31f5e-115">Visual Studio インストーラーでは、選択、**個々 のコンポーネント**タブ。その後、下、**開発アクティビティ**カテゴリを選択、 **Windows Workflow Foundation**コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="31f5e-115">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="31f5e-116">選択**変更**コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="31f5e-116">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="31f5e-117">選択、**アクティビティ ライブラリ**プロジェクト テンプレート。</span><span class="sxs-lookup"><span data-stu-id="31f5e-117">Select the **Activity Library** project template.</span></span> <span data-ttu-id="31f5e-118">型`NumberGuessWorkflowActivities`で、**名前**ボックスをクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-118">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="31f5e-119">右クリックして**Activity1.xaml**で**ソリューション エクスプ ローラー**選択**削除**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-119">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="31f5e-120">**[OK]** をクリックして確定します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-120">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="31f5e-121">ReadInt アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-121">Create the ReadInt activity</span></span>

1. <span data-ttu-id="31f5e-122">選択**新しい項目の追加**から、**プロジェクト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-122">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="31f5e-123">**インストール済み** > **一般的な項目**ノードの **ワークフロー**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-123">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="31f5e-124">選択**コード アクティビティ**から、**ワークフロー**一覧。</span><span class="sxs-lookup"><span data-stu-id="31f5e-124">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="31f5e-125">型`ReadInt`に、**名前**ボックスをクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-125">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="31f5e-126">既存の `ReadInt` 定義を次の定義に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="31f5e-126">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="31f5e-127">`ReadInt` アクティビティは、コード アクティビティ テンプレートの既定値である <xref:System.Activities.NativeActivity%601> ではなく <xref:System.Activities.CodeActivity> から派生します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-127">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="31f5e-128"><xref:System.Activities.CodeActivity%601> は、<xref:System.Activities.Activity%601.Result%2A> 引数を介して公開される 1 つの結果がアクティビティによって提供される場合に使用できますが、<xref:System.Activities.CodeActivity%601> ではブックマークの使用がサポートされていないため、<xref:System.Activities.NativeActivity%601> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="31f5e-128"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="31f5e-129">Prompt アクティビティを作成します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-129">Create the Prompt activity</span></span>

1. <span data-ttu-id="31f5e-130">キーを押して**Ctrl**+**Shift**+**B**プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="31f5e-130">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="31f5e-131">プロジェクトをビルドすると、このプロジェクトの `ReadInt` アクティビティを使用して、この手順からカスタム アクティビティをビルドできます。</span><span class="sxs-lookup"><span data-stu-id="31f5e-131">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="31f5e-132">選択**新しい項目の追加**から、**プロジェクト**メニュー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-132">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="31f5e-133">**インストール済み** > **一般的な項目**ノードの **ワークフロー**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-133">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="31f5e-134">選択**アクティビティ**から、**ワークフロー**一覧。</span><span class="sxs-lookup"><span data-stu-id="31f5e-134">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="31f5e-135">型`Prompt`に、**名前**ボックスをクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-135">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="31f5e-136">ダブルクリック**Prompt.xaml**で**ソリューション エクスプ ローラー**まだ表示されていない場合、デザイナーで表示します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-136">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="31f5e-137">クリックして**引数**を表示するアクティビティ デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="31f5e-137">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="31f5e-138">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="31f5e-138">Click **Create Argument**.</span></span>

8. <span data-ttu-id="31f5e-139">型`BookmarkName`に、**名前**ボックスで、**で**から、**方向**ドロップダウン リストで、**文字列**から**引数の型**ドロップダウン リスト、およびキーを押します**Enter**引数を保存します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-139">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="31f5e-140">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="31f5e-140">Click **Create Argument**.</span></span>

10. <span data-ttu-id="31f5e-141">型`Result`に、**名前**新しく追加されたの下にあるボックス`BookmarkName`引数で、**アウト**から、**方向**ドロップダウン リストで、**Int32**から、**引数の型**ドロップダウン リスト、およびキーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-141">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="31f5e-142">クリックして**引数の作成**です。</span><span class="sxs-lookup"><span data-stu-id="31f5e-142">Click **Create Argument**.</span></span>

12. <span data-ttu-id="31f5e-143">型`Text`に、**名前**ボックスで、**で**から、**方向**ドロップダウン リストで、**文字列**から**引数の型**ドロップダウン リスト、およびキーを押します**Enter**引数を保存します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-143">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="31f5e-144">これら 3 つの引数は、次の手順で、<xref:System.Activities.Statements.WriteLine> アクティビティに追加される `ReadInt` アクティビティと `Prompt` アクティビティの対応する引数にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="31f5e-144">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="31f5e-145">クリックして**引数**を閉じるアクティビティ デザイナーの左下で、**引数**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="31f5e-145">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="31f5e-146">ドラッグ、**シーケンス**からのアクティビティ、**制御フロー**のセクション、**ツールボックス**にドロップし、**ここにアクティビティをドロップ**のラベル、**プロンプト**アクティビティ デザイナー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-146">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="31f5e-147">場合、**ツールボックス**ウィンドウが表示されない場合、選択**ツールボックス**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-147">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="31f5e-148">ドラッグ、 **WriteLine**からのアクティビティ、**プリミティブ**のセクション、**ツールボックス**にドロップし、**ここにアクティビティをドロップ**のラベル、**シーケンス**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="31f5e-148">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="31f5e-149">バインド、**テキスト**の引数、 **WriteLine**アクティビティを**テキスト**の引数、**プロンプト**」と入力してアクティビティ`Text`**c# 式を入力します**または**VB の式を入力します**ボックスに、**プロパティ**ウィンドウ、およびキーを押します、**タブ**。2 回のキー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-149">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="31f5e-150">これで、IntelliSense リスト メンバー ウィンドウを閉じ、プロパティから選択を外してプロパティ値を保存します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-150">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="31f5e-151">このプロパティは、」と入力して設定することもできます`Text`に、 **c# 式を入力します**または**VB の式を入力します。** ボックスに、アクティビティ自体。</span><span class="sxs-lookup"><span data-stu-id="31f5e-151">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="31f5e-152">場合、**プロパティ ウィンドウ**が表示されている、選択**プロパティ ウィンドウ**から、**ビュー**メニュー。</span><span class="sxs-lookup"><span data-stu-id="31f5e-152">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="31f5e-153">ドラッグ、 **ReadInt**からのアクティビティ、 **NumberGuessWorkflowActivities**のセクション、**ツールボックス**にドロップし、**シーケンス**アクティビティの後になるように、 **WriteLine**アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="31f5e-153">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="31f5e-154">バインド、 **BookmarkName**の引数、 **ReadInt**アクティビティを**BookmarkName**の引数、**プロンプト** 」と入力してアクティビティ`BookmarkName`に、 **VB の式を入力します**の右側のボックスに、 **BookmarkName**引数、**プロパティ ウィンドウ**、し、キーを押します **。タブ**IntelliSense リスト メンバー ウィンドウを閉じるし、プロパティの保存を 2 回のキーします。</span><span class="sxs-lookup"><span data-stu-id="31f5e-154">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="31f5e-155">バインド、**結果**の引数、 **ReadInt**アクティビティを**結果**の引数、**プロンプト**」と入力してアクティビティ`Result`**VB の式を入力します**の右側のボックスに、**結果**の引数、**プロパティ ウィンドウ**、し、キーを押します、 **タブ。** 2 回のキーします。</span><span class="sxs-lookup"><span data-stu-id="31f5e-155">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="31f5e-156">キーを押して**Ctrl**+**Shift**+**B**ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="31f5e-156">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="31f5e-157">次の手順</span><span class="sxs-lookup"><span data-stu-id="31f5e-157">Next steps</span></span>

<span data-ttu-id="31f5e-158">これらのアクティビティを使用してワークフローを作成する方法については、チュートリアルでは、次の手順を参照してください[方法。ワークフロー作成](how-to-create-a-workflow.md)です。</span><span class="sxs-lookup"><span data-stu-id="31f5e-158">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="31f5e-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="31f5e-159">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="31f5e-160">カスタム アクティビティの設計と実装</span><span class="sxs-lookup"><span data-stu-id="31f5e-160">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="31f5e-161">チュートリアル入門</span><span class="sxs-lookup"><span data-stu-id="31f5e-161">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="31f5e-162">方法: ワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="31f5e-162">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="31f5e-163">カスタム アクティビティ デザイナーでの ExpressionTextBox の使用</span><span class="sxs-lookup"><span data-stu-id="31f5e-163">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)