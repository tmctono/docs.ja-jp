---
title: 実行時間の長いワークフローを作成および実行する方法
description: この記事では、複数のワークフローインスタンスとワークフローの永続化の開始と再開をサポートする Windows フォームホストアプリケーションを作成する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0043c89-2192-43c9-986d-3ecec4dd8c9c
ms.openlocfilehash: 557b3512e534198d47c0c6f6b0a7c5f92bb71739
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419552"
---
# <a name="how-to-create-and-run-a-long-running-workflow"></a><span data-ttu-id="5c6bc-103">実行時間の長いワークフローを作成および実行する方法</span><span class="sxs-lookup"><span data-stu-id="5c6bc-103">How to create and run a long-running workflow</span></span>

<span data-ttu-id="5c6bc-104">Windows Workflow Foundation (WF) の中心的な機能の1つは、アイドル状態のワークフローをデータベースに永続化してアンロードするランタイムの機能です。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-104">One of the central features of Windows Workflow Foundation (WF) is the runtime’s ability to persist and unload idle workflows to a database.</span></span> <span data-ttu-id="5c6bc-105">[「方法: ワークフローを実行する](how-to-run-a-workflow.md)」の手順では、コンソールアプリケーションを使用したワークフローホスティングの基本について説明しています。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-105">The steps in [How to: Run a Workflow](how-to-run-a-workflow.md) demonstrated the basics of workflow hosting using a console application.</span></span> <span data-ttu-id="5c6bc-106">ワークフローの開始、ワークフロー ライフサイクル ハンドラー、およびブックマークの再開の例を紹介しました。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-106">Examples were shown of starting workflows, workflow lifecycle handlers, and resuming bookmarks.</span></span> <span data-ttu-id="5c6bc-107">ワークフローの永続化を効果的に説明するためには、複数のワークフロー インスタンスの開始と再開をサポートするより複雑なワークフロー ホストが必要です。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-107">In order to demonstrate workflow persistence effectively, a more complex workflow host is required that supports starting and resuming multiple workflow instances.</span></span> <span data-ttu-id="5c6bc-108">チュートリアルのこの手順では、複数のワークフロー インスタンスの開始と再開およびワークフローの永続化をサポートする Windows フォーム ホスト アプリケーションを作成する方法について説明します。また、この手順は、以降の手順で説明する追跡やバージョン管理などの高度な機能の基礎となります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-108">This step in the tutorial demonstrates how to create a Windows form host application that supports starting and resuming multiple workflow instances, workflow persistence, and provides a basis for the advanced features such as tracking and versioning that are demonstrated in subsequent tutorial steps.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6bc-109">このチュートリアルの手順と以降の手順では、 [「方法: ワークフローを作成する](how-to-create-a-workflow.md)」の3種類のワークフローをすべて使用します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-109">This tutorial step and the subsequent steps use all three workflow types from [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span> <span data-ttu-id="5c6bc-110">3種類すべてを完了していない場合は、 [Windows Workflow Foundation (WF45)-はじめにチュートリアル](https://go.microsoft.com/fwlink/?LinkID=248976)から完了したバージョンの手順をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-110">If you did not complete all three types you can download a completed version of the steps from [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

> [!NOTE]
> <span data-ttu-id="5c6bc-111">チュートリアルの完成したバージョンをダウンロードしたり、ビデオチュートリアルを表示したりするには、「 [Windows Workflow Foundation (WF45)-はじめにチュートリアル](https://go.microsoft.com/fwlink/?LinkID=248976)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-persistence-database"></a><span data-ttu-id="5c6bc-112">永続性データベースを作成するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-112">To create the persistence database</span></span>

1. <span data-ttu-id="5c6bc-113">SQL Server Management Studio を開き、 **.\SQLEXPRESS**などのローカルサーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-113">Open SQL Server Management Studio and connect to the local server, for example **.\SQLEXPRESS**.</span></span> <span data-ttu-id="5c6bc-114">ローカルサーバーの [**データベース**] ノードを右クリックし、[**新しいデータベース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-114">Right-click the **Databases** node on the local server, and select **New Database**.</span></span> <span data-ttu-id="5c6bc-115">新しいデータベースに**WF45GettingStartedTutorial**という名前を指定し、他のすべての値をそのまま使用して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-115">Name the new database **WF45GettingStartedTutorial**, accept all other values, and select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c6bc-116">データベースを作成する前に、ローカルサーバーに対する**Create Database**権限があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-116">Ensure that you have **Create Database** permission on the local server before creating the database.</span></span>

2. <span data-ttu-id="5c6bc-117">[**ファイル**] メニューの [**開く** **] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-117">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="5c6bc-118">次のフォルダーを参照します: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span><span class="sxs-lookup"><span data-stu-id="5c6bc-118">Browse to the following folder: *C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en*</span></span>

    <span data-ttu-id="5c6bc-119">次の2つのファイルを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-119">Select the following two files and click **Open**.</span></span>

    - <span data-ttu-id="5c6bc-120">*SqlWorkflowInstanceStoreLogic.sql*</span><span class="sxs-lookup"><span data-stu-id="5c6bc-120">*SqlWorkflowInstanceStoreLogic.sql*</span></span>

    - <span data-ttu-id="5c6bc-121">*SqlWorkflowInstanceStoreSchema.sql*</span><span class="sxs-lookup"><span data-stu-id="5c6bc-121">*SqlWorkflowInstanceStoreSchema.sql*</span></span>

3. <span data-ttu-id="5c6bc-122">[**ウィンドウ**] メニューの [ **sqlworkflowinstancestoreschema.sql** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-122">Choose **SqlWorkflowInstanceStoreSchema.sql** from the **Window** menu.</span></span> <span data-ttu-id="5c6bc-123">[**使用できるデータベース**] ドロップダウンで**WF45GettingStartedTutorial**が選択されていることを確認し、[**クエリ**] メニューの [**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-123">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

4. <span data-ttu-id="5c6bc-124">[**ウィンドウ**] メニューの [ **Sqlworkflowinstancestorelogic .sql** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-124">Choose **SqlWorkflowInstanceStoreLogic.sql** from the **Window** menu.</span></span> <span data-ttu-id="5c6bc-125">[**使用できるデータベース**] ドロップダウンで**WF45GettingStartedTutorial**が選択されていることを確認し、[**クエリ**] メニューの [**実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-125">Ensure that **WF45GettingStartedTutorial** is selected in the **Available Databases** drop-down and choose **Execute** from the **Query** menu.</span></span>

    > [!WARNING]
    > <span data-ttu-id="5c6bc-126">前の 2 つの手順を正しい順序で実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-126">It is important to perform the previous two steps in the correct order.</span></span> <span data-ttu-id="5c6bc-127">クエリが正しい順序で実行されないと、エラーが発生し、永続性データベースは正しく構成されません。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-127">If the queries are executed out of order, errors occur and the persistence database is not configured correctly.</span></span>

## <a name="to-add-the-reference-to-the-durableinstancing-assemblies"></a><span data-ttu-id="5c6bc-128">DurableInstancing アセンブリへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-128">To add the reference to the DurableInstancing assemblies</span></span>

1. <span data-ttu-id="5c6bc-129">**ソリューションエクスプローラー**で [ **NumberGuessWorkflowHost** ] を右クリックし、[**参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-129">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Add Reference**.</span></span>

2. <span data-ttu-id="5c6bc-130">[**参照の追加**] ボックスの一覧から [**アセンブリ**] を選択し、[ `DurableInstancing` **アセンブリの検索**] ボックスに「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-130">Select **Assemblies** from the **Add Reference** list, and type `DurableInstancing` into the **Search Assemblies** box.</span></span> <span data-ttu-id="5c6bc-131">これにより、アセンブリがフィルター処理され、目的の参照を簡単に選択できます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-131">This filters the assemblies and makes the desired references easier to select.</span></span>

3. <span data-ttu-id="5c6bc-132">**検索結果**の一覧で**system.activities.durableinstancing.instances**と**system.activities.durableinstancing.instances**の横のチェックボックスをオンにし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-132">Check the checkbox beside **System.Activities.DurableInstancing** and **System.Runtime.DurableInstancing** from the **Search Results** list, and click **OK**.</span></span>

## <a name="to-create-the-workflow-host-form"></a><span data-ttu-id="5c6bc-133">ワークフロー ホスト フォームを作成するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-133">To create the workflow host form</span></span>

> [!NOTE]
> <span data-ttu-id="5c6bc-134">この手順では、フォームを手動で追加して構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-134">The steps in this procedure describe how to add and configure the form manually.</span></span> <span data-ttu-id="5c6bc-135">必要に応じて、チュートリアルのソリューション ファイルをダウンロードし、完成したフォームをプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-135">If desired, you can download the solution files for the tutorial and add the completed form to the project.</span></span> <span data-ttu-id="5c6bc-136">チュートリアルファイルをダウンロードするには、 [Windows Workflow Foundation (WF45)-はじめにチュートリアル](https://go.microsoft.com/fwlink/?LinkID=248976)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-136">To download the tutorial files, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span> <span data-ttu-id="5c6bc-137">ファイルがダウンロードされたら、 **NumberGuessWorkflowHost**を右クリックし、[**参照の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-137">Once the files are downloaded, right-click **NumberGuessWorkflowHost** and choose **Add Reference**.</span></span> <span data-ttu-id="5c6bc-138">System.string および system.string への**参照を追加\*\*\*\*します。**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-138">Add a reference to **System.Windows.Forms** and **System.Drawing**.</span></span> <span data-ttu-id="5c6bc-139">これらの参照は、[**追加**]、[**新しい項目**] メニューから新しいフォームを追加した場合に自動的に追加されますが、フォームをインポートするときに手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-139">These references are added automatically if you add a new form from the **Add**, **New Item** menu, but must be added manually when importing a form.</span></span> <span data-ttu-id="5c6bc-140">参照が追加されたら、**ソリューションエクスプローラー**で [ **NumberGuessWorkflowHost** ] を右クリックし、[**追加**]、[**既存の項目**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-140">Once the references are added, right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Existing Item**.</span></span> <span data-ttu-id="5c6bc-141">`Form`プロジェクトファイル内のフォルダーを参照し、 **WorkflowHostForm.cs** (または**WorkflowHostForm**) を選択して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-141">Browse to the `Form` folder in the project files, select **WorkflowHostForm.cs** (or **WorkflowHostForm.vb**), and click **Add**.</span></span> <span data-ttu-id="5c6bc-142">フォームをインポートする場合は、次のセクションに進んで、[フォームのプロパティとヘルパーメソッドを追加](#to-add-the-properties-and-helper-methods-of-the-form)することができます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-142">If you choose to import the form, then you can skip down to the next section, [To add the properties and helper methods of the form](#to-add-the-properties-and-helper-methods-of-the-form).</span></span>

1. <span data-ttu-id="5c6bc-143">**ソリューションエクスプローラー**で [ **NumberGuessWorkflowHost** ] を右クリックし、[**追加**]、[**新しい項目**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-143">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **New Item**.</span></span>

2. <span data-ttu-id="5c6bc-144">[**インストールされ**たテンプレート] の一覧で [ **Windows フォーム**] を選択し、 `WorkflowHostForm` [**名前**] ボックスに「」と入力して、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-144">In the **Installed** templates list, choose **Windows Form**, type `WorkflowHostForm` in the **Name** box, and click **Add**.</span></span>

3. <span data-ttu-id="5c6bc-145">フォームの次のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-145">Configure the following properties on the form.</span></span>

    |<span data-ttu-id="5c6bc-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5c6bc-146">Property</span></span>|<span data-ttu-id="5c6bc-147">値</span><span class="sxs-lookup"><span data-stu-id="5c6bc-147">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="5c6bc-148">FormBorderStyle</span><span class="sxs-lookup"><span data-stu-id="5c6bc-148">FormBorderStyle</span></span>|<span data-ttu-id="5c6bc-149">FixedSingle</span><span class="sxs-lookup"><span data-stu-id="5c6bc-149">FixedSingle</span></span>|
    |<span data-ttu-id="5c6bc-150">MaximizeBox</span><span class="sxs-lookup"><span data-stu-id="5c6bc-150">MaximizeBox</span></span>|<span data-ttu-id="5c6bc-151">False</span><span class="sxs-lookup"><span data-stu-id="5c6bc-151">False</span></span>|
    |<span data-ttu-id="5c6bc-152">サイズ</span><span class="sxs-lookup"><span data-stu-id="5c6bc-152">Size</span></span>|<span data-ttu-id="5c6bc-153">400, 420</span><span class="sxs-lookup"><span data-stu-id="5c6bc-153">400, 420</span></span>|

4. <span data-ttu-id="5c6bc-154">次のコントロールを指定された順序でフォームに追加し、指示に従ってプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-154">Add the following controls to the form in the order specified and configure the properties as directed.</span></span>

    |<span data-ttu-id="5c6bc-155">Control</span><span class="sxs-lookup"><span data-stu-id="5c6bc-155">Control</span></span>|<span data-ttu-id="5c6bc-156">プロパティ: 値</span><span class="sxs-lookup"><span data-stu-id="5c6bc-156">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="5c6bc-157">**ボタン**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-157">**Button**</span></span>|<span data-ttu-id="5c6bc-158">名前: NewGame</span><span class="sxs-lookup"><span data-stu-id="5c6bc-158">Name: NewGame</span></span><br /><br /> <span data-ttu-id="5c6bc-159">場所:13、13</span><span class="sxs-lookup"><span data-stu-id="5c6bc-159">Location: 13, 13</span></span><br /><br /> <span data-ttu-id="5c6bc-160">サイズ:75、23</span><span class="sxs-lookup"><span data-stu-id="5c6bc-160">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="5c6bc-161">テキスト: 新しいゲーム</span><span class="sxs-lookup"><span data-stu-id="5c6bc-161">Text: New Game</span></span>|
    |<span data-ttu-id="5c6bc-162">**ラベル**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-162">**Label**</span></span>|<span data-ttu-id="5c6bc-163">場所:94、18</span><span class="sxs-lookup"><span data-stu-id="5c6bc-163">Location: 94, 18</span></span><br /><br /> <span data-ttu-id="5c6bc-164">Text: 1 からまでの数値を推測します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-164">Text: Guess a number from 1 to</span></span>|
    |<span data-ttu-id="5c6bc-165">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-165">**ComboBox**</span></span>|<span data-ttu-id="5c6bc-166">名前: NumberRange</span><span class="sxs-lookup"><span data-stu-id="5c6bc-166">Name: NumberRange</span></span><br /><br /> <span data-ttu-id="5c6bc-167">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="5c6bc-167">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="5c6bc-168">項目:10、100、1000</span><span class="sxs-lookup"><span data-stu-id="5c6bc-168">Items: 10, 100, 1000</span></span><br /><br /> <span data-ttu-id="5c6bc-169">場所: 228、12</span><span class="sxs-lookup"><span data-stu-id="5c6bc-169">Location: 228, 12</span></span><br /><br /> <span data-ttu-id="5c6bc-170">サイズ: 143、21</span><span class="sxs-lookup"><span data-stu-id="5c6bc-170">Size: 143, 21</span></span>|
    |<span data-ttu-id="5c6bc-171">**ラベル**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-171">**Label**</span></span>|<span data-ttu-id="5c6bc-172">場所:13、43</span><span class="sxs-lookup"><span data-stu-id="5c6bc-172">Location: 13, 43</span></span><br /><br /> <span data-ttu-id="5c6bc-173">Text: ワークフローの種類</span><span class="sxs-lookup"><span data-stu-id="5c6bc-173">Text: Workflow type</span></span>|
    |<span data-ttu-id="5c6bc-174">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-174">**ComboBox**</span></span>|<span data-ttu-id="5c6bc-175">名前: WorkflowType</span><span class="sxs-lookup"><span data-stu-id="5c6bc-175">Name: WorkflowType</span></span><br /><br /> <span data-ttu-id="5c6bc-176">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="5c6bc-176">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="5c6bc-177">Items: Statemachinenumberguessworkflow.xaml、Flowchartnumberguessworkflow.xaml、Sequentialnumberguessworkflow.xaml</span><span class="sxs-lookup"><span data-stu-id="5c6bc-177">Items: StateMachineNumberGuessWorkflow, FlowchartNumberGuessWorkflow, SequentialNumberGuessWorkflow</span></span><br /><br /> <span data-ttu-id="5c6bc-178">場所:94、40</span><span class="sxs-lookup"><span data-stu-id="5c6bc-178">Location: 94, 40</span></span><br /><br /> <span data-ttu-id="5c6bc-179">サイズ: 277、21</span><span class="sxs-lookup"><span data-stu-id="5c6bc-179">Size: 277, 21</span></span>|
    |<span data-ttu-id="5c6bc-180">**ラベル**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-180">**Label**</span></span>|<span data-ttu-id="5c6bc-181">名前: WorkflowVersion</span><span class="sxs-lookup"><span data-stu-id="5c6bc-181">Name: WorkflowVersion</span></span><br /><br /> <span data-ttu-id="5c6bc-182">場所:13、362</span><span class="sxs-lookup"><span data-stu-id="5c6bc-182">Location: 13, 362</span></span><br /><br /> <span data-ttu-id="5c6bc-183">テキスト: ワークフローバージョン</span><span class="sxs-lookup"><span data-stu-id="5c6bc-183">Text: Workflow version</span></span>|
    |<span data-ttu-id="5c6bc-184">**GroupBox**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-184">**GroupBox**</span></span>|<span data-ttu-id="5c6bc-185">場所:13、67</span><span class="sxs-lookup"><span data-stu-id="5c6bc-185">Location: 13, 67</span></span><br /><br /> <span data-ttu-id="5c6bc-186">サイズ: 358、287</span><span class="sxs-lookup"><span data-stu-id="5c6bc-186">Size: 358, 287</span></span><br /><br /> <span data-ttu-id="5c6bc-187">テキスト: ゲーム</span><span class="sxs-lookup"><span data-stu-id="5c6bc-187">Text: Game</span></span>|

    > [!NOTE]
    > <span data-ttu-id="5c6bc-188">次のコントロールを追加するときに、それらを GroupBox に配置します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-188">When adding the following controls, put them into the GroupBox.</span></span>

    |<span data-ttu-id="5c6bc-189">Control</span><span class="sxs-lookup"><span data-stu-id="5c6bc-189">Control</span></span>|<span data-ttu-id="5c6bc-190">プロパティ: 値</span><span class="sxs-lookup"><span data-stu-id="5c6bc-190">Property: Value</span></span>|
    |-------------|---------------------|
    |<span data-ttu-id="5c6bc-191">**ラベル**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-191">**Label**</span></span>|<span data-ttu-id="5c6bc-192">場所: 7、20</span><span class="sxs-lookup"><span data-stu-id="5c6bc-192">Location: 7, 20</span></span><br /><br /> <span data-ttu-id="5c6bc-193">テキスト: ワークフローインスタンス Id</span><span class="sxs-lookup"><span data-stu-id="5c6bc-193">Text: Workflow Instance Id</span></span>|
    |<span data-ttu-id="5c6bc-194">**ComboBox**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-194">**ComboBox**</span></span>|<span data-ttu-id="5c6bc-195">名前: InstanceId</span><span class="sxs-lookup"><span data-stu-id="5c6bc-195">Name: InstanceId</span></span><br /><br /> <span data-ttu-id="5c6bc-196">DropDownStyle: DropDownList</span><span class="sxs-lookup"><span data-stu-id="5c6bc-196">DropDownStyle: DropDownList</span></span><br /><br /> <span data-ttu-id="5c6bc-197">場所: 121、17</span><span class="sxs-lookup"><span data-stu-id="5c6bc-197">Location: 121, 17</span></span><br /><br /> <span data-ttu-id="5c6bc-198">サイズ: 227、21</span><span class="sxs-lookup"><span data-stu-id="5c6bc-198">Size: 227, 21</span></span>|
    |<span data-ttu-id="5c6bc-199">**ラベル**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-199">**Label**</span></span>|<span data-ttu-id="5c6bc-200">場所: 7、47</span><span class="sxs-lookup"><span data-stu-id="5c6bc-200">Location: 7, 47</span></span><br /><br /> <span data-ttu-id="5c6bc-201">Text: Guess</span><span class="sxs-lookup"><span data-stu-id="5c6bc-201">Text: Guess</span></span>|
    |<span data-ttu-id="5c6bc-202">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-202">**TextBox**</span></span>|<span data-ttu-id="5c6bc-203">名前: Guess</span><span class="sxs-lookup"><span data-stu-id="5c6bc-203">Name: Guess</span></span><br /><br /> <span data-ttu-id="5c6bc-204">場所:50、44</span><span class="sxs-lookup"><span data-stu-id="5c6bc-204">Location: 50, 44</span></span><br /><br /> <span data-ttu-id="5c6bc-205">サイズ:65、20</span><span class="sxs-lookup"><span data-stu-id="5c6bc-205">Size: 65, 20</span></span>|
    |<span data-ttu-id="5c6bc-206">**ボタン**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-206">**Button**</span></span>|<span data-ttu-id="5c6bc-207">名前: EnterGuess</span><span class="sxs-lookup"><span data-stu-id="5c6bc-207">Name: EnterGuess</span></span><br /><br /> <span data-ttu-id="5c6bc-208">場所: 121、42</span><span class="sxs-lookup"><span data-stu-id="5c6bc-208">Location: 121, 42</span></span><br /><br /> <span data-ttu-id="5c6bc-209">サイズ:75、23</span><span class="sxs-lookup"><span data-stu-id="5c6bc-209">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="5c6bc-210">Text: 「Guess」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-210">Text: Enter Guess</span></span>|
    |<span data-ttu-id="5c6bc-211">**ボタン**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-211">**Button**</span></span>|<span data-ttu-id="5c6bc-212">名前: QuitGame</span><span class="sxs-lookup"><span data-stu-id="5c6bc-212">Name: QuitGame</span></span><br /><br /> <span data-ttu-id="5c6bc-213">場所: 274、42</span><span class="sxs-lookup"><span data-stu-id="5c6bc-213">Location: 274, 42</span></span><br /><br /> <span data-ttu-id="5c6bc-214">サイズ:75、23</span><span class="sxs-lookup"><span data-stu-id="5c6bc-214">Size: 75, 23</span></span><br /><br /> <span data-ttu-id="5c6bc-215">テキスト: 終了</span><span class="sxs-lookup"><span data-stu-id="5c6bc-215">Text: Quit</span></span>|
    |<span data-ttu-id="5c6bc-216">**TextBox**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-216">**TextBox**</span></span>|<span data-ttu-id="5c6bc-217">名前: WorkflowStatus</span><span class="sxs-lookup"><span data-stu-id="5c6bc-217">Name: WorkflowStatus</span></span><br /><br /> <span data-ttu-id="5c6bc-218">場所:10、73</span><span class="sxs-lookup"><span data-stu-id="5c6bc-218">Location: 10, 73</span></span><br /><br /> <span data-ttu-id="5c6bc-219">複数行: True</span><span class="sxs-lookup"><span data-stu-id="5c6bc-219">Multiline: True</span></span><br /><br /> <span data-ttu-id="5c6bc-220">ReadOnly: True</span><span class="sxs-lookup"><span data-stu-id="5c6bc-220">ReadOnly: True</span></span><br /><br /> <span data-ttu-id="5c6bc-221">スクロールバー: 縦</span><span class="sxs-lookup"><span data-stu-id="5c6bc-221">ScrollBars: Vertical</span></span><br /><br /> <span data-ttu-id="5c6bc-222">サイズ: 338、208</span><span class="sxs-lookup"><span data-stu-id="5c6bc-222">Size: 338, 208</span></span>|

5. <span data-ttu-id="5c6bc-223">フォームの**Acceptbutton**プロパティを**enterguess**に設定します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-223">Set the **AcceptButton** property of the form to **EnterGuess**.</span></span>

 <span data-ttu-id="5c6bc-224">次の例は完成したフォームを示しています。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-224">The following example illustrates the completed form.</span></span>

 ![Windows Workflow Foundation ワークフローホストフォームのスクリーンショット。](./media/how-to-create-and-run-a-long-running-workflow/windows-workflow-foundation-workflowhostform.png)

## <a name="to-add-the-properties-and-helper-methods-of-the-form"></a><span data-ttu-id="5c6bc-226">フォームのプロパティとヘルパー メソッドを追加するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-226">To add the properties and helper methods of the form</span></span>

<span data-ttu-id="5c6bc-227">このセクションの手順では、フォーム クラスに、数値推測ワークフローの実行と再開をサポートするようフォームの UI を構成するプロパティとヘルパー メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-227">The steps in this section add properties and helper methods to the form class that configure the UI of the form to support running and resuming number guess workflows.</span></span>

1. <span data-ttu-id="5c6bc-228">**ソリューションエクスプローラー**で [ **WorkflowHostForm** ] を右クリックし、[**コードの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-228">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>

2. <span data-ttu-id="5c6bc-229">次の `using` (または `Imports`) ステートメントを、他の `using` (または `Imports`) ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-229">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Activities
    Imports System.Activities.DurableInstancing
    Imports System.Data.SqlClient
    Imports System.IO
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Activities;
    using System.Activities.DurableInstancing;
    using System.Data.SqlClient;
    using System.IO;
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="5c6bc-230">**WorkflowHostForm**クラスに次のメンバー宣言を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-230">Add the following member declarations to the **WorkflowHostForm** class.</span></span>

    ```vb
    Const connectionString = "Server=.\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI"
    Dim store As SqlWorkflowInstanceStore
    Dim workflowStarting As Boolean
    ```

    ```csharp
    const string connectionString = "Server=.\\SQLEXPRESS;Initial Catalog=WF45GettingStartedTutorial;Integrated Security=SSPI";
    SqlWorkflowInstanceStore store;
    bool workflowStarting;
    ```

    > [!NOTE]
    > <span data-ttu-id="5c6bc-231">接続文字列が異なる場合は、使用しているデータベースを参照するように `connectionString` を更新してください。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-231">If your connection string is different, update `connectionString` to refer to your database.</span></span>

4. <span data-ttu-id="5c6bc-232">`WorkflowInstanceId` プロパティを `WorkflowFormHost` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-232">Add a `WorkflowInstanceId` property to the `WorkflowFormHost` class.</span></span>

    ```vb
    Public ReadOnly Property WorkflowInstanceId() As Guid
        Get
            If InstanceId.SelectedIndex = -1 Then
                Return Guid.Empty
            Else
                Return New Guid(InstanceId.SelectedItem.ToString())
            End If
        End Get
    End Property
    ```

    ```csharp
    public Guid WorkflowInstanceId
    {
        get
        {
            return InstanceId.SelectedIndex == -1 ? Guid.Empty : (Guid)InstanceId.SelectedItem;
        }
    }
    ```

    <span data-ttu-id="5c6bc-233">コンボボックスには、 `InstanceId` 永続化されたワークフローインスタンス id の一覧が表示され、 `WorkflowInstanceId` プロパティは現在選択されているワークフローを返します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-233">The `InstanceId` combo box displays a list of persisted workflow instance ids, and the `WorkflowInstanceId` property returns the currently selected workflow.</span></span>

5. <span data-ttu-id="5c6bc-234">フォームの `Load` イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-234">Add a handler for the form `Load` event.</span></span> <span data-ttu-id="5c6bc-235">ハンドラーを追加するには、フォームの**デザインビュー**に切り替え、[**プロパティ**] ウィンドウの上部にある [**イベント**] アイコンをクリックして、[**読み込み**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-235">To add the handler, switch to **Design View** for the form, click the **Events** icon at the top of the **Properties** window, and double-click **Load**.</span></span>

    ```vb
    Private Sub WorkflowHostForm_Load(sender As Object, e As EventArgs) Handles Me.Load

    End Sub
    ```

    ```csharp
    private void WorkflowHostForm_Load(object sender, EventArgs e)
    {

    }
    ```

6. <span data-ttu-id="5c6bc-236">`WorkflowHostForm_Load` に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-236">Add the following code to `WorkflowHostForm_Load`.</span></span>

    ```vb
    ' Initialize the store and configure it so that it can be used for
    ' multiple WorkflowApplication instances.
    store = New SqlWorkflowInstanceStore(connectionString)
    WorkflowApplication.CreateDefaultInstanceOwner(store, Nothing, WorkflowIdentityFilter.Any)

    ' Set default ComboBox selections.
    NumberRange.SelectedIndex = 0
    WorkflowType.SelectedIndex = 0

    ListPersistedWorkflows()
    ```

    ```csharp
    // Initialize the store and configure it so that it can be used for
    // multiple WorkflowApplication instances.
    store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplication.CreateDefaultInstanceOwner(store, null, WorkflowIdentityFilter.Any);

    // Set default ComboBox selections.
    NumberRange.SelectedIndex = 0;
    WorkflowType.SelectedIndex = 0;

    ListPersistedWorkflows();
    ```

    <span data-ttu-id="5c6bc-237">フォームの読み込み時に、`SqlWorkflowInstanceStore` が構成され、範囲とワークフローの種類のコンボ ボックスが既定値に設定されます。さらに、永続化されたワークフロー インスタンスが `InstanceId` コンボ ボックスに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-237">When the form loads, the `SqlWorkflowInstanceStore` is configured, the range and workflow type combo boxes are set to default values, and the persisted workflow instances are added to the `InstanceId` combo box.</span></span>

7. <span data-ttu-id="5c6bc-238">`SelectedIndexChanged` の `InstanceId` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-238">Add a `SelectedIndexChanged` handler for `InstanceId`.</span></span> <span data-ttu-id="5c6bc-239">ハンドラーを追加するには、フォームの**デザインビュー**に切り替え、コンボボックスを選択し `InstanceId` 、[**プロパティ**] ウィンドウの上部にある [**イベント**] アイコンをクリックして、[ **selectedindexchanged**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-239">To add the handler, switch to **Design View** for the form, select the `InstanceId` combo box, click the **Events** icon at the top of the **Properties** window, and double-click **SelectedIndexChanged**.</span></span>

    ```vb
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged

    End Sub
    ```

    ```csharp
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)
    {

    }
    ```

8. <span data-ttu-id="5c6bc-240">`InstanceId_SelectedIndexChanged` に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-240">Add the following code to `InstanceId_SelectedIndexChanged`.</span></span> <span data-ttu-id="5c6bc-241">ユーザーがコンボ ボックスを使用してワークフローを選択するたびに、このハンドラーによってステータス ウィンドウが更新されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-241">Whenever the user selects a workflow by using the combo box this handler updates the status window.</span></span>

    ```vb
    If InstanceId.SelectedIndex = -1 Then
        Return
    End If

    ' Clear the status window.
    WorkflowStatus.Clear()

    ' Get the workflow version and display it.
    ' If the workflow is just starting then this info will not
    ' be available in the persistence store so do not try and retrieve it.
    If Not workflowStarting Then
        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        WorkflowVersion.Text = _
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)

        ' Unload the instance.
        instance.Abandon()
    End If
    ```

    ```csharp
    if (InstanceId.SelectedIndex == -1)
    {
        return;
    }

    // Clear the status window.
    WorkflowStatus.Clear();

    // Get the workflow version and display it.
    // If the workflow is just starting then this info will not
    // be available in the persistence store so do not try and retrieve it.
    if (!workflowStarting)
    {
        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);

        WorkflowVersion.Text =
            WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);

        // Unload the instance.
        instance.Abandon();
    }
    ```

9. <span data-ttu-id="5c6bc-242">次の `ListPersistedWorkflows` メソッドをフォーム クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-242">Add the following `ListPersistedWorkflows` method to the form class.</span></span>

    ```vb
    Private Sub ListPersistedWorkflows()
        Using localCon As New SqlConnection(connectionString)
            Dim localCmd As String = _
                "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]"

            Dim cmd As SqlCommand = localCon.CreateCommand()
            cmd.CommandText = localCmd
            localCon.Open()
            Using reader As SqlDataReader = cmd.ExecuteReader(CommandBehavior.CloseConnection)

                While (reader.Read())
                    ' Get the InstanceId of the persisted Workflow.
                    Dim id As Guid = Guid.Parse(reader(0).ToString())
                    InstanceId.Items.Add(id)
                End While
            End Using
        End Using
    End Sub
    ```

    ```csharp
    using (var localCon = new SqlConnection(connectionString))
    {
        string localCmd =
            "SELECT [InstanceId] FROM [System.Activities.DurableInstancing].[Instances] ORDER BY [CreationTime]";

        SqlCommand cmd = localCon.CreateCommand();
        cmd.CommandText = localCmd;
        localCon.Open();
        using (SqlDataReader reader = cmd.ExecuteReader(CommandBehavior.CloseConnection))
        {
            while (reader.Read())
            {
                // Get the InstanceId of the persisted Workflow.
                Guid id = Guid.Parse(reader[0].ToString());
                InstanceId.Items.Add(id);
            }
        }
    }
    ```

    <span data-ttu-id="5c6bc-243">`ListPersistedWorkflows` は、永続化されたワークフロー インスタンスのインスタンス ストアに対してクエリを実行し、`cboInstanceId` コンボ ボックスにインスタンス ID を追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-243">`ListPersistedWorkflows` queries the instance store for persisted workflow instances, and adds the instance ids to the `cboInstanceId` combo box.</span></span>

10. <span data-ttu-id="5c6bc-244">次の `UpdateStatus` メソッドと対応するデリゲートをフォーム クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-244">Add the following `UpdateStatus` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="5c6bc-245">このメソッドは、現在実行中のワークフローのステータスでフォーム上のステータス ウィンドウを更新します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-245">This method updates the status window on the form with the status of the currently running workflow.</span></span>

    ```vb
    Private Delegate Sub UpdateStatusDelegate(msg As String)
    Public Sub UpdateStatus(msg As String)
        ' We may be on a different thread so we need to
        ' make this call using BeginInvoke.
        If InvokeRequired Then
            BeginInvoke(New UpdateStatusDelegate(AddressOf UpdateStatus), msg)
        Else
            If Not msg.EndsWith(vbCrLf) Then
                msg = msg & vbCrLf
            End If

            WorkflowStatus.AppendText(msg)

            ' Ensure that the newly added status is visible.
            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length
            WorkflowStatus.ScrollToCaret()
        End If
    End Sub
    ```

    ```csharp
    private delegate void UpdateStatusDelegate(string msg);
    public void UpdateStatus(string msg)
    {
        // We may be on a different thread so we need to
        // make this call using BeginInvoke.
        if (InvokeRequired)
        {
            BeginInvoke(new UpdateStatusDelegate(UpdateStatus), msg);
        }
        else
        {
            if (!msg.EndsWith("\r\n"))
            {
                msg += "\r\n";
            }
            WorkflowStatus.AppendText(msg);

            WorkflowStatus.SelectionStart = WorkflowStatus.Text.Length;
            WorkflowStatus.ScrollToCaret();
        }
    }
    ```

11. <span data-ttu-id="5c6bc-246">次の `GameOver` メソッドと対応するデリゲートをフォーム クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-246">Add the following `GameOver` method and corresponding delegate to the form class.</span></span> <span data-ttu-id="5c6bc-247">ワークフローが完了すると、このメソッドは、完了したワークフローのインスタンス id を**InstanceId**コンボボックスから削除することによって、フォームの UI を更新します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-247">When a workflow completes, this method updates the form UI by removing the instance id of the completed workflow from the **InstanceId** combo box.</span></span>

    ```vb
    Private Delegate Sub GameOverDelegate()
    Private Sub GameOver()
        If InvokeRequired Then
            BeginInvoke(New GameOverDelegate(AddressOf GameOver))
        Else
            ' Remove this instance from the InstanceId combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem)
            InstanceId.SelectedIndex = -1
        End If
    End Sub
    ```

    ```csharp
    private delegate void GameOverDelegate();
    private void GameOver()
    {
        if (InvokeRequired)
        {
            BeginInvoke(new GameOverDelegate(GameOver));
        }
        else
        {
            // Remove this instance from the combo box.
            InstanceId.Items.Remove(InstanceId.SelectedItem);
            InstanceId.SelectedIndex = -1;
        }
    }
    ```

## <a name="to-configure-the-instance-store-workflow-lifecycle-handlers-and-extensions"></a><span data-ttu-id="5c6bc-248">インスタンス ストア、ワークフロー ライフサイクル ハンドラー、および拡張機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-248">To configure the instance store, workflow lifecycle handlers, and extensions</span></span>

1. <span data-ttu-id="5c6bc-249">フォーム クラスに `ConfigureWorkflowApplication` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-249">Add a `ConfigureWorkflowApplication` method to the form class.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)

    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
    }
    ```

    <span data-ttu-id="5c6bc-250">このメソッドは `WorkflowApplication` を構成し、目的の拡張機能を追加して、ワークフロー ライフサイクル イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-250">This method configures the `WorkflowApplication`, adds the desired extensions, and adds handlers for the workflow lifecycle events.</span></span>

2. <span data-ttu-id="5c6bc-251">`ConfigureWorkflowApplication` で、`SqlWorkflowInstanceStore` の `WorkflowApplication` を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-251">In `ConfigureWorkflowApplication`, specify the `SqlWorkflowInstanceStore` for the `WorkflowApplication`.</span></span>

    ```vb
    ' Configure the persistence store.
    wfApp.InstanceStore = store
    ```

    ```csharp
    // Configure the persistence store.
    wfApp.InstanceStore = store;
    ```

3. <span data-ttu-id="5c6bc-252">次に、`StringWriter` インスタンスを作成して `Extensions` の `WorkflowApplication` コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-252">Next, create a `StringWriter` instance and add it to the `Extensions` collection of the `WorkflowApplication`.</span></span> <span data-ttu-id="5c6bc-253">`StringWriter`が拡張機能に追加されると、すべてのアクティビティの出力がキャプチャされ `WriteLine` ます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-253">When a `StringWriter` is added to the extensions it captures all `WriteLine` activity output.</span></span> <span data-ttu-id="5c6bc-254">ワークフローがアイドル状態になると、`WriteLine` の出力を `StringWriter` から抽出してフォームに表示できます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-254">When the workflow becomes idle, the `WriteLine` output can be extracted from the `StringWriter` and displayed on the form.</span></span>

    ```vb
    ' Add a StringWriter to the extensions. This captures the output
    ' from the WriteLine activities so we can display it in the form.
    Dim sw As New StringWriter()
    wfApp.Extensions.Add(sw)
    ```

    ```csharp
    // Add a StringWriter to the extensions. This captures the output
    // from the WriteLine activities so we can display it in the form.
    var sw = new StringWriter();
    wfApp.Extensions.Add(sw);
    ```

4. <span data-ttu-id="5c6bc-255">`Completed` イベントの次のハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-255">Add the following handler for the `Completed` event.</span></span> <span data-ttu-id="5c6bc-256">ワークフローが正常に完了すると、数値を推測するための順番の数がステータス ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-256">When a workflow successfully completes, the number of turns taken to guess the number is displayed to the status window.</span></span> <span data-ttu-id="5c6bc-257">ワークフローが終了すると、終了の原因となった例外情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-257">If the workflow terminates, the exception information that caused the termination is displayed.</span></span> <span data-ttu-id="5c6bc-258">ハンドラーの末尾で、`GameOver` メソッドが呼び出され、完了したワークフローがワークフローの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-258">At the end of the handler the `GameOver` method is called, which removes the completed workflow from the workflow list.</span></span>

    ```vb
    wfApp.Completed = _
        Sub(e As WorkflowApplicationCompletedEventArgs)
            If e.CompletionState = ActivityInstanceState.Faulted Then
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
            ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                UpdateStatus("Workflow Canceled.")
            Else
                Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
            End If
            GameOver()
        End Sub
    ```

    ```csharp
    wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
    {
        if (e.CompletionState == ActivityInstanceState.Faulted)
        {
            UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
        }
        else if (e.CompletionState == ActivityInstanceState.Canceled)
        {
            UpdateStatus("Workflow Canceled.");
        }
        else
        {
            int turns = Convert.ToInt32(e.Outputs["Turns"]);
            UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
        }
        GameOver();
    };
    ```

5. <span data-ttu-id="5c6bc-259">次の `Aborted` ハンドラーと `OnUnhandledException` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-259">Add the following `Aborted` and `OnUnhandledException` handlers.</span></span> <span data-ttu-id="5c6bc-260">`GameOver` メソッドが `Aborted` ハンドラーから呼び出されることはありません。これは、ワークフロー インスタンスが中止された場合、そのインスタンスは終了せず、後で再開することができるためです。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-260">The `GameOver` method is not called from the `Aborted` handler because when a workflow instance is aborted, it does not terminate, and it is possible to resume the instance at a later time.</span></span>

    ```vb
    wfApp.Aborted = _
        Sub(e As WorkflowApplicationAbortedEventArgs)
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
        End Sub

    wfApp.OnUnhandledException = _
        Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
            GameOver()
            Return UnhandledExceptionAction.Terminate
        End Function
    ```

    ```csharp
    wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
    {
        UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
    };

    wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
    {
        UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
        GameOver();
        return UnhandledExceptionAction.Terminate;
    };
    ```

6. <span data-ttu-id="5c6bc-261">次の `PersistableIdle` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-261">Add the following `PersistableIdle` handler.</span></span> <span data-ttu-id="5c6bc-262">このハンドラーは、追加された `StringWriter` 拡張機能を取得し、`WriteLine` アクティビティからの出力を抽出して、ステータス ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-262">This handler retrieves the `StringWriter` extension that was added, extracts the output from the `WriteLine` activities, and displays it in the status window.</span></span>

    ```vb
    wfApp.PersistableIdle = _
        Function(e As WorkflowApplicationIdleEventArgs)
            ' Send the current WriteLine outputs to the status window.
            Dim writers = e.GetInstanceExtensions(Of StringWriter)()
            For Each writer In writers
                UpdateStatus(writer.ToString())
            Next
            Return PersistableIdleAction.Unload
        End Function
    ```

    ```csharp
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
    {
        // Send the current WriteLine outputs to the status window.
        var writers = e.GetInstanceExtensions<StringWriter>();
        foreach (var writer in writers)
        {
            UpdateStatus(writer.ToString());
        }
        return PersistableIdleAction.Unload;
    };
    ```

    <span data-ttu-id="5c6bc-263"><xref:System.Activities.PersistableIdleAction> 列挙体には、<xref:System.Activities.PersistableIdleAction.None>、<xref:System.Activities.PersistableIdleAction.Persist>、および <xref:System.Activities.PersistableIdleAction.Unload> の 3 つの値があります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-263">The <xref:System.Activities.PersistableIdleAction> enumeration has three values: <xref:System.Activities.PersistableIdleAction.None>, <xref:System.Activities.PersistableIdleAction.Persist>, and <xref:System.Activities.PersistableIdleAction.Unload>.</span></span> <span data-ttu-id="5c6bc-264"><xref:System.Activities.PersistableIdleAction.Persist> により、ワークフローは永続化されますが、ワークフローがアンロードされることはありません。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-264"><xref:System.Activities.PersistableIdleAction.Persist> causes the workflow to persist but it does not cause the workflow to unload.</span></span> <span data-ttu-id="5c6bc-265"><xref:System.Activities.PersistableIdleAction.Unload> により、ワーク フローが永続化され、アンロードされます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-265"><xref:System.Activities.PersistableIdleAction.Unload> causes the workflow to persist and be unloaded.</span></span>

    <span data-ttu-id="5c6bc-266">完成した `ConfigureWorkflowApplication` メソッドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-266">The following example is the completed `ConfigureWorkflowApplication` method.</span></span>

    ```vb
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)
        ' Configure the persistence store.
        wfApp.InstanceStore = store

        ' Add a StringWriter to the extensions. This captures the output
        ' from the WriteLine activities so we can display it in the form.
        Dim sw As New StringWriter()
        wfApp.Extensions.Add(sw)

        wfApp.Completed = _
            Sub(e As WorkflowApplicationCompletedEventArgs)
                If e.CompletionState = ActivityInstanceState.Faulted Then
                    UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}{vbCrLf}{e.TerminationException.Message}")
                ElseIf e.CompletionState = ActivityInstanceState.Canceled Then
                    UpdateStatus("Workflow Canceled.")
                Else
                    Dim turns As Integer = Convert.ToInt32(e.Outputs("Turns"))
                    UpdateStatus($"Congratulations, you guessed the number in {turns} turns.")
                End If
                GameOver()
            End Sub

        wfApp.Aborted = _
            Sub(e As WorkflowApplicationAbortedEventArgs)
                UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}{vbCrLf}{e.Reason.Message}")
            End Sub

        wfApp.OnUnhandledException = _
            Function(e As WorkflowApplicationUnhandledExceptionEventArgs)
                UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}{vbCrLf}{e.UnhandledException.Message}")
                GameOver()
                Return UnhandledExceptionAction.Terminate
            End Function

        wfApp.PersistableIdle = _
            Function(e As WorkflowApplicationIdleEventArgs)
                ' Send the current WriteLine outputs to the status window.
                Dim writers = e.GetInstanceExtensions(Of StringWriter)()
                For Each writer In writers
                    UpdateStatus(writer.ToString())
                Next
                Return PersistableIdleAction.Unload
            End Function
    End Sub
    ```

    ```csharp
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)
    {
        // Configure the persistence store.
        wfApp.InstanceStore = store;

        // Add a StringWriter to the extensions. This captures the output
        // from the WriteLine activities so we can display it in the form.
        var sw = new StringWriter();
        wfApp.Extensions.Add(sw);

        wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)
        {
            if (e.CompletionState == ActivityInstanceState.Faulted)
            {
                UpdateStatus($"Workflow Terminated. Exception: {e.TerminationException.GetType().FullName}\r\n{e.TerminationException.Message}");
            }
            else if (e.CompletionState == ActivityInstanceState.Canceled)
            {
                UpdateStatus("Workflow Canceled.");
            }
            else
            {
                int turns = Convert.ToInt32(e.Outputs["Turns"]);
                UpdateStatus($"Congratulations, you guessed the number in {turns} turns.");
            }
            GameOver();
        };

        wfApp.Aborted = delegate(WorkflowApplicationAbortedEventArgs e)
        {
            UpdateStatus($"Workflow Aborted. Exception: {e.Reason.GetType().FullName}\r\n{e.Reason.Message}");
        };

        wfApp.OnUnhandledException = delegate(WorkflowApplicationUnhandledExceptionEventArgs e)
        {
            UpdateStatus($"Unhandled Exception: {e.UnhandledException.GetType().FullName}\r\n{e.UnhandledException.Message}");
            GameOver();
            return UnhandledExceptionAction.Terminate;
        };

        wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
        {
            // Send the current WriteLine outputs to the status window.
            var writers = e.GetInstanceExtensions<StringWriter>();
            foreach (var writer in writers)
            {
                UpdateStatus(writer.ToString());
            }
            return PersistableIdleAction.Unload;
        };
    }
    ```

## <a name="to-enable-starting-and-resuming-multiple-workflow-types"></a><span data-ttu-id="5c6bc-267">複数のワークフローの種類を開始および再開できるようにするには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-267">To enable starting and resuming multiple workflow types</span></span>

<span data-ttu-id="5c6bc-268">ワークフロー インスタンスを再開するには、ホストはワークフロー定義を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-268">In order to resume a workflow instance, the host has to provide the workflow definition.</span></span> <span data-ttu-id="5c6bc-269">このチュートリアルには 3 種類のワークフローがあり、以降の手順では、これらの種類の複数のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-269">In this tutorial there are three workflow types, and subsequent tutorial steps introduce multiple versions of these types.</span></span> <span data-ttu-id="5c6bc-270">`WorkflowIdentity` を使用すると、ホスト アプリケーションは、識別情報を永続化されたワークフロー インスタンスに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-270">`WorkflowIdentity` provides a way for a host application to associate identifying information with a persisted workflow instance.</span></span> <span data-ttu-id="5c6bc-271">このセクションの手順では、永続化されたワークフロー インスタンスから対応するワークフロー定義へのワークフロー ID のマッピングに役立つユーティリティ クラスの作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-271">The steps in this section demonstrate how to create a utility class to assist with mapping the workflow identity from a persisted workflow instance to the corresponding workflow definition.</span></span> <span data-ttu-id="5c6bc-272">とのバージョン管理の詳細について `WorkflowIdentity` は、「 [WorkflowIdentity とバージョン管理の使用](using-workflowidentity-and-versioning.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-272">For more information about `WorkflowIdentity` and versioning, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

1. <span data-ttu-id="5c6bc-273">**ソリューションエクスプローラー**で [ **NumberGuessWorkflowHost** ] を右クリックし、[**追加**]、[**クラス**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-273">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="5c6bc-274">`WorkflowVersionMap`[**名前**] ボックスに「」と入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-274">Type `WorkflowVersionMap` into the **Name** box and click **Add**.</span></span>

2. <span data-ttu-id="5c6bc-275">次の `using` または `Imports` ステートメントを、他の `using` または `Imports` ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-275">Add the following `using` or `Imports` statements at the top of the file with the other `using` or `Imports` statements.</span></span>

    ```vb
    Imports System.Activities
    Imports NumberGuessWorkflowActivities
    ```

    ```csharp
    using System.Activities;
    using NumberGuessWorkflowActivities;
    ```

3. <span data-ttu-id="5c6bc-276">`WorkflowVersionMap` クラス宣言を次の宣言に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-276">Replace the `WorkflowVersionMap` class declaration with the following declaration.</span></span>

    ```vb
    Public Module WorkflowVersionMap
        Dim map As Dictionary(Of WorkflowIdentity, Activity)

        ' Current version identities.
        Public StateMachineNumberGuessIdentity As WorkflowIdentity
        Public FlowchartNumberGuessIdentity As WorkflowIdentity
        Public SequentialNumberGuessIdentity As WorkflowIdentity

        Sub New()
            map = New Dictionary(Of WorkflowIdentity, Activity)

            ' Add the current workflow version identities.
            StateMachineNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "StateMachineNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            FlowchartNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "FlowchartNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            SequentialNumberGuessIdentity = New WorkflowIdentity With
            {
                .Name = "SequentialNumberGuessWorkflow",
                .Version = New Version(1, 0, 0, 0)
            }

            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())
        End Sub

        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity
            Return map(identity)
        End Function

        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String
            Return identity.ToString()
        End Function
    End Module
    ```

    ```csharp
    public static class WorkflowVersionMap
    {
        static Dictionary<WorkflowIdentity, Activity> map;

        // Current version identities.
        static public WorkflowIdentity StateMachineNumberGuessIdentity;
        static public WorkflowIdentity FlowchartNumberGuessIdentity;
        static public WorkflowIdentity SequentialNumberGuessIdentity;

        static WorkflowVersionMap()
        {
            map = new Dictionary<WorkflowIdentity, Activity>();

            // Add the current workflow version identities.
            StateMachineNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "StateMachineNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            FlowchartNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "FlowchartNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            SequentialNumberGuessIdentity = new WorkflowIdentity
            {
                Name = "SequentialNumberGuessWorkflow",
                Version = new Version(1, 0, 0, 0)
            };

            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());
        }

        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)
        {
            return map[identity];
        }

        public static string GetIdentityDescription(WorkflowIdentity identity)
        {
            return identity.ToString();
       }
    }
    ```

    <span data-ttu-id="5c6bc-277">`WorkflowVersionMap` は、このチュートリアルの 3 つのワークフロー定義にマップされる 3 つのワークフロー ID を格納しており、以降のセクションでワークフローが開始および再開されるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-277">`WorkflowVersionMap` contains three workflow identities that map to the three workflow definitions from this tutorial and is used in the following sections when workflows are started and resumed.</span></span>

## <a name="to-start-a-new-workflow"></a><span data-ttu-id="5c6bc-278">新しいワークフローを開始するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-278">To start a new workflow</span></span>

1. <span data-ttu-id="5c6bc-279">`Click` の `NewGame` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-279">Add a `Click` handler for `NewGame`.</span></span> <span data-ttu-id="5c6bc-280">ハンドラーを追加するには、フォームの**デザインビュー**に切り替え、をダブルクリックし `NewGame` ます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-280">To add the handler, switch to **Design View** for the form, and double-click `NewGame`.</span></span> <span data-ttu-id="5c6bc-281">`NewGame_Click` ハンドラーが追加され、ビューがフォームのコード ビューに切り替わります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-281">A `NewGame_Click` handler is added and the view switches to code view for the form.</span></span> <span data-ttu-id="5c6bc-282">ユーザーがこのボタンをクリックするたびに、新しいワークフローが開始されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-282">Whenever the user clicks this button a new workflow is started.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click

    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="5c6bc-283">Click ハンドラーに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-283">Add the following code to the click handler.</span></span> <span data-ttu-id="5c6bc-284">このコードにより、引数名によってキー指定された、ワークフローの入力引数のディクショナリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-284">This code creates a dictionary of input arguments for the workflow, keyed by argument name.</span></span> <span data-ttu-id="5c6bc-285">このディクショナリには、範囲のコンボ ボックスから取得したランダムに生成された数値の範囲を含む 1 つのエントリがあります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-285">This dictionary has one entry that contains the range of the randomly generated number retrieved from the range combo box.</span></span>

    ```vb
    Dim inputs As New Dictionary(Of String, Object)()
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))
    ```

    ```csharp
    var inputs = new Dictionary<string, object>();
    inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));
    ```

3. <span data-ttu-id="5c6bc-286">次に、ワークフローを開始する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-286">Next, add the following code that starts the workflow.</span></span> <span data-ttu-id="5c6bc-287">選択されたワークフローの種類に対応する `WorkflowIdentity` とワークフロー定義が `WorkflowVersionMap` ヘルパー クラスを使用して取得されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-287">The `WorkflowIdentity` and workflow definition corresponding to the type of workflow selected are retrieved using the `WorkflowVersionMap` helper class.</span></span> <span data-ttu-id="5c6bc-288">さらに、新しい `WorkflowApplication` インスタンスを作成するには、ワークフロー定義、`WorkflowIdentity`、および入力引数のディクショナリを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-288">Next, a new `WorkflowApplication` instance is created using the workflow definition, `WorkflowIdentity`, and dictionary of input arguments.</span></span>

    ```vb
    Dim identity As WorkflowIdentity = Nothing
    Select Case WorkflowType.SelectedItem.ToString()
        Case "SequentialNumberGuessWorkflow"
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity

        Case "StateMachineNumberGuessWorkflow"
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

        Case "FlowchartNumberGuessWorkflow"
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
    End Select

    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

    Dim wfApp = New WorkflowApplication(wf, inputs, identity)
    ```

    ```csharp
    WorkflowIdentity identity = null;
    switch (WorkflowType.SelectedItem.ToString())
    {
        case "SequentialNumberGuessWorkflow":
            identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
            break;

        case "StateMachineNumberGuessWorkflow":
            identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
            break;

        case "FlowchartNumberGuessWorkflow":
            identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
            break;
    };

    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

    WorkflowApplication wfApp = new WorkflowApplication(wf, inputs, identity);
    ```

4. <span data-ttu-id="5c6bc-289">次に、ワークフローの一覧にワークフローを追加し、フォーム上にワークフローのバージョン情報を表示する次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-289">Next, add the following code which adds the workflow to the workflow list and displays the workflow's version information on the form.</span></span>

    ```vb
    ' Add the workflow to the list and display the version information.
    workflowStarting = True
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
    WorkflowVersion.Text = identity.ToString()
    workflowStarting = False
    ```

    ```csharp
    // Add the workflow to the list and display the version information.
    workflowStarting = true;
    InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
    WorkflowVersion.Text = identity.ToString();
    workflowStarting = false;
    ```

5. <span data-ttu-id="5c6bc-290">`ConfigureWorkflowApplication` を呼び出して、この `WorkflowApplication` インスタンスのインスタンス ストア、拡張機能、およびワークフロー ライフサイクル ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-290">Call `ConfigureWorkflowApplication` to configure the instance store, extensions, and workflow lifecycle handlers for this `WorkflowApplication` instance.</span></span>

    ```vb
    ' Configure the instance store, extensions, and
    ' workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)
    ```

    ```csharp
    // Configure the instance store, extensions, and
    // workflow lifecycle handlers.
    ConfigureWorkflowApplication(wfApp);
    ```

6. <span data-ttu-id="5c6bc-291">最後に、`Run` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-291">Finally, call `Run`.</span></span>

    ```vb
    ' Start the workflow.
    wfApp.Run()
    ```

    ```csharp
    // Start the workflow.
    wfApp.Run();
    ```

     <span data-ttu-id="5c6bc-292">完成した `NewGame_Click` ハンドラーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-292">The following example is the completed `NewGame_Click` handler.</span></span>

    ```vb
    Private Sub NewGame_Click(sender As Object, e As EventArgs) Handles NewGame.Click
        ' Start a new workflow.
        Dim inputs As New Dictionary(Of String, Object)()
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem))

        Dim identity As WorkflowIdentity = Nothing
        Select Case WorkflowType.SelectedItem.ToString()
            Case "SequentialNumberGuessWorkflow"
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity

            Case "StateMachineNumberGuessWorkflow"
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity

            Case "FlowchartNumberGuessWorkflow"
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity
        End Select

        Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(identity)

        Dim wfApp = New WorkflowApplication(wf, inputs, identity)

        ' Add the workflow to the list and display the version information.
        workflowStarting = True
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id)
        WorkflowVersion.Text = identity.ToString()
        workflowStarting = False

        ' Configure the instance store, extensions, and
        ' workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp)

        ' Start the workflow.
        wfApp.Run()
    End Sub
    ```

    ```csharp
    private void NewGame_Click(object sender, EventArgs e)
    {
        var inputs = new Dictionary<string, object>();
        inputs.Add("MaxNumber", Convert.ToInt32(NumberRange.SelectedItem));

        WorkflowIdentity identity = null;
        switch (WorkflowType.SelectedItem.ToString())
        {
            case "SequentialNumberGuessWorkflow":
                identity = WorkflowVersionMap.SequentialNumberGuessIdentity;
                break;

            case "StateMachineNumberGuessWorkflow":
                identity = WorkflowVersionMap.StateMachineNumberGuessIdentity;
                break;

            case "FlowchartNumberGuessWorkflow":
                identity = WorkflowVersionMap.FlowchartNumberGuessIdentity;
                break;
        };

        Activity wf = WorkflowVersionMap.GetWorkflowDefinition(identity);

        var wfApp = new WorkflowApplication(wf, inputs, identity);

        // Add the workflow to the list and display the version information.
        workflowStarting = true;
        InstanceId.SelectedIndex = InstanceId.Items.Add(wfApp.Id);
        WorkflowVersion.Text = identity.ToString();
        workflowStarting = false;

        // Configure the instance store, extensions, and
        // workflow lifecycle handlers.
        ConfigureWorkflowApplication(wfApp);

        // Start the workflow.
        wfApp.Run();
    }
    ```

## <a name="to-resume-a-workflow"></a><span data-ttu-id="5c6bc-293">ワークフローを再開するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-293">To resume a workflow</span></span>

1. <span data-ttu-id="5c6bc-294">`Click` の `EnterGuess` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-294">Add a `Click` handler for `EnterGuess`.</span></span> <span data-ttu-id="5c6bc-295">ハンドラーを追加するには、フォームの**デザインビュー**に切り替え、をダブルクリックし `EnterGuess` ます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-295">To add the handler, switch to **Design View** for the form, and double-click `EnterGuess`.</span></span> <span data-ttu-id="5c6bc-296">ユーザーがこのボタンをクリックするたびに、ワークフローが再開されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-296">Whenever the user clicks this button a workflow is resumed.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click

    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="5c6bc-297">ワークフローがワークフローの一覧で選択され、ユーザーの推定値が有効であることを確認するために、次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-297">Add the following code to ensure that a workflow is selected in the workflow list, and that the user's guess is valid.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim userGuess As Integer
    If Not Int32.TryParse(Guess.Text, userGuess) Then
        MessageBox.Show("Please enter an integer.")
        Guess.SelectAll()
        Guess.Focus()
        Return
    End If
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    int guess;
    if (!Int32.TryParse(Guess.Text, out guess))
    {
        MessageBox.Show("Please enter an integer.");
        Guess.SelectAll();
        Guess.Focus();
        return;
    }
    ```

3. <span data-ttu-id="5c6bc-298">次に、永続化されたワークフロー インスタンスの `WorkflowApplicationInstance` を取得します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-298">Next, retrieve the `WorkflowApplicationInstance` of the persisted workflow instance.</span></span> <span data-ttu-id="5c6bc-299">`WorkflowApplicationInstance` は、ワークフロー定義にまだ関連付けられていない永続化されたワークフロー インスタンスを表します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-299">A `WorkflowApplicationInstance` represents a persisted workflow instance that has not yet been associated with a workflow definition.</span></span> <span data-ttu-id="5c6bc-300">`DefinitionIdentity` の `WorkflowApplicationInstance` には、永続化されたワークフロー インスタンスの `WorkflowIdentity` が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-300">The `DefinitionIdentity` of the `WorkflowApplicationInstance` contains the `WorkflowIdentity` of the persisted workflow instance.</span></span> <span data-ttu-id="5c6bc-301">このチュートリアルでは、`WorkflowVersionMap` を適切なワークフロー定義にマップするために、`WorkflowIdentity` ユーティリティ クラスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-301">In this tutorial, the `WorkflowVersionMap` utility class is used to map the `WorkflowIdentity` to the correct workflow definition.</span></span> <span data-ttu-id="5c6bc-302">ワークフロー定義が取得されると、`WorkflowApplication` が、適切なワークフロー定義を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-302">Once the workflow definition is retrieved, a `WorkflowApplication` is created, using the correct workflow definition.</span></span>

    ```vb
    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = _
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)
    ```

    ```csharp
    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf =
        WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);
    ```

4. <span data-ttu-id="5c6bc-303">`WorkflowApplication` が作成されたら、`ConfigureWorkflowApplication` を呼び出してインスタンス ストア、ワークフロー ライフサイクル ハンドラー、および拡張機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-303">Once the `WorkflowApplication` is created, configure the instance store, workflow lifecycle handlers, and extensions by calling `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="5c6bc-304">これらの手順は、新しい `WorkflowApplication` が作成されるたびに行う必要があります。また、ワークフロー インスタンスが `WorkflowApplication` に読み込まれる前に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-304">These steps must be done every time a new `WorkflowApplication` is created, and they must be done before the workflow instance is loaded into the `WorkflowApplication`.</span></span> <span data-ttu-id="5c6bc-305">ワークフローは、読み込まれた後、ユーザーの推定値を使用して再開されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-305">After the workflow is loaded, it is resumed with the user's guess.</span></span>

    ```vb
    ' Configure the extensions and lifecycle handlers.
    ' Do this before the instance is loaded. Once the instance is
    ' loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", userGuess)
    ```

    ```csharp
    // Configure the extensions and lifecycle handlers.
    // Do this before the instance is loaded. Once the instance is
    // loaded it is too late to add extensions.
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Resume the workflow.
    wfApp.ResumeBookmark("EnterGuess", guess);
    ```

5. <span data-ttu-id="5c6bc-306">最後に、Guess テキスト ボックスをクリアして、別の推定値を受け取るようにフォームを準備します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-306">Finally, clear the guess textbox and prepare the form to accept another guess.</span></span>

    ```vb
    ' Clear the Guess textbox.
    Guess.Clear()
    Guess.Focus()
    ```

    ```csharp
    // Clear the Guess textbox.
    Guess.Clear();
    Guess.Focus();
    ```

    <span data-ttu-id="5c6bc-307">完成した `EnterGuess_Click` ハンドラーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-307">The following example is the completed `EnterGuess_Click` handler.</span></span>

    ```vb
    Private Sub EnterGuess_Click(sender As Object, e As EventArgs) Handles EnterGuess.Click
        If WorkflowInstanceId = Guid.Empty Then
            MessageBox.Show("Please select a workflow.")
            Return
        End If

        Dim userGuess As Integer
        If Not Int32.TryParse(Guess.Text, userGuess) Then
            MessageBox.Show("Please enter an integer.")
            Guess.SelectAll()
            Guess.Focus()
            Return
        End If

        Dim instance As WorkflowApplicationInstance = _
            WorkflowApplication.GetInstance(WorkflowInstanceId, store)

        ' Use the persisted WorkflowIdentity to retrieve the correct workflow
        ' definition from the dictionary.
        Dim wf As Activity = _
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

        ' Associate the WorkflowApplication with the correct definition
        Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

        ' Configure the extensions and lifecycle handlers.
        ' Do this before the instance is loaded. Once the instance is
        ' loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp)

        ' Load the workflow.
        wfApp.Load(instance)

        ' Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", userGuess)

        ' Clear the Guess textbox.
        Guess.Clear()
        Guess.Focus()
    End Sub
    ```

    ```csharp
    private void EnterGuess_Click(object sender, EventArgs e)
    {
        if (WorkflowInstanceId == Guid.Empty)
        {
            MessageBox.Show("Please select a workflow.");
            return;
        }

        int guess;
        if (!Int32.TryParse(Guess.Text, out guess))
        {
            MessageBox.Show("Please enter an integer.");
            Guess.SelectAll();
            Guess.Focus();
            return;
        }

        WorkflowApplicationInstance instance =
            WorkflowApplication.GetInstance(WorkflowInstanceId, store);

        // Use the persisted WorkflowIdentity to retrieve the correct workflow
        // definition from the dictionary.
        Activity wf =
            WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

        // Associate the WorkflowApplication with the correct definition
        var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

        // Configure the extensions and lifecycle handlers.
        // Do this before the instance is loaded. Once the instance is
        // loaded it is too late to add extensions.
        ConfigureWorkflowApplication(wfApp);

        // Load the workflow.
        wfApp.Load(instance);

        // Resume the workflow.
        wfApp.ResumeBookmark("EnterGuess", guess);

        // Clear the Guess textbox.
        Guess.Clear();
        Guess.Focus();
    }
    ```

## <a name="to-terminate-a-workflow"></a><span data-ttu-id="5c6bc-308">ワークフローを終了するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-308">To terminate a workflow</span></span>

1. <span data-ttu-id="5c6bc-309">`Click` の `QuitGame` ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-309">Add a `Click` handler for `QuitGame`.</span></span> <span data-ttu-id="5c6bc-310">ハンドラーを追加するには、フォームの**デザインビュー**に切り替え、をダブルクリックし `QuitGame` ます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-310">To add the handler, switch to **Design View** for the form, and double-click `QuitGame`.</span></span> <span data-ttu-id="5c6bc-311">ユーザーがこのボタンをクリックするたびに、現在選択されているワークフローが終了します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-311">Whenever the user clicks this button the currently selected workflow is terminated.</span></span>

    ```vb
    Private Sub QuitGame_Click(sender As Object, e As EventArgs) Handles QuitGame.Click

    End Sub
    ```

    ```csharp
    private void QuitGame_Click(object sender, EventArgs e)
    {

    }
    ```

2. <span data-ttu-id="5c6bc-312">次のコードを `QuitGame_Click` ハンドラーに追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-312">Add the following code to the `QuitGame_Click` handler.</span></span> <span data-ttu-id="5c6bc-313">このコードは、まず、ワークフローの一覧でワークフローが選択されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-313">This code first checks to ensure that a workflow is selected in the workflow list.</span></span> <span data-ttu-id="5c6bc-314">その後、永続化されたインスタンスが `WorkflowApplicationInstance` に読み込まれ、`DefinitionIdentity` を使用して適切なワークフロー定義を判断し、`WorkflowApplication` を初期化します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-314">Then it loads the persisted instance into a `WorkflowApplicationInstance`, uses the `DefinitionIdentity` to determine the correct workflow definition, and then initializes the `WorkflowApplication`.</span></span> <span data-ttu-id="5c6bc-315">次に、拡張機能とワークフロー ライフサイクル ハンドラーは、`ConfigureWorkflowApplication` の呼び出しによって構成されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-315">Next the extensions and workflow lifecycle handlers are configured with a call to `ConfigureWorkflowApplication`.</span></span> <span data-ttu-id="5c6bc-316">`WorkflowApplication` は構成された後に読み込まれ、その後 `Terminate` によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-316">Once the `WorkflowApplication` is configured, it is loaded, and then `Terminate` is called.</span></span>

    ```vb
    If WorkflowInstanceId = Guid.Empty Then
        MessageBox.Show("Please select a workflow.")
        Return
    End If

    Dim instance As WorkflowApplicationInstance = _
        WorkflowApplication.GetInstance(WorkflowInstanceId, store)

    ' Use the persisted WorkflowIdentity to retrieve the correct workflow
    ' definition from the dictionary.
    Dim wf As Activity = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity)

    ' Associate the WorkflowApplication with the correct definition.
    Dim wfApp As New WorkflowApplication(wf, instance.DefinitionIdentity)

    ' Configure the extensions and lifecycle handlers.
    ConfigureWorkflowApplication(wfApp)

    ' Load the workflow.
    wfApp.Load(instance)

    ' Terminate the workflow.
    wfApp.Terminate("User resigns.")
    ```

    ```csharp
    if (WorkflowInstanceId == Guid.Empty)
    {
        MessageBox.Show("Please select a workflow.");
        return;
    }

    WorkflowApplicationInstance instance =
        WorkflowApplication.GetInstance(WorkflowInstanceId, store);

    // Use the persisted WorkflowIdentity to retrieve the correct workflow
    // definition from the dictionary.
    Activity wf = WorkflowVersionMap.GetWorkflowDefinition(instance.DefinitionIdentity);

    // Associate the WorkflowApplication with the correct definition
    var wfApp = new WorkflowApplication(wf, instance.DefinitionIdentity);

    // Configure the extensions and lifecycle handlers
    ConfigureWorkflowApplication(wfApp);

    // Load the workflow.
    wfApp.Load(instance);

    // Terminate the workflow.
    wfApp.Terminate("User resigns.");
    ```

## <a name="to-build-and-run-the-application"></a><span data-ttu-id="5c6bc-317">アプリケーションをビルドして実行するには</span><span class="sxs-lookup"><span data-stu-id="5c6bc-317">To build and run the application</span></span>

1. <span data-ttu-id="5c6bc-318">**ソリューションエクスプローラー**で**Program.cs** (または module1.vb) をダブルクリックして、コードを表示**します。**</span><span class="sxs-lookup"><span data-stu-id="5c6bc-318">Double-click **Program.cs** (or **Module1.vb**) in **Solution Explorer** to display the code.</span></span>

2. <span data-ttu-id="5c6bc-319">次の `using` (または `Imports`) ステートメントを、他の `using` (または `Imports`) ステートメントを含むファイルの先頭に追加します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-319">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>

    ```vb
    Imports System.Windows.Forms
    ```

    ```csharp
    using System.Windows.Forms;
    ```

3. <span data-ttu-id="5c6bc-320">[「方法: ワークフローを実行する」の手順に](how-to-run-a-workflow.md)従って、既存のワークフローホスティングコードを削除またはコメントアウトし、次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-320">Remove or comment out the existing workflow hosting code from [How to: Run a Workflow](how-to-run-a-workflow.md), and replace it with the following code.</span></span>

    ```vb
    Sub Main()
        Application.EnableVisualStyles()
        Application.Run(New WorkflowHostForm())
    End Sub
    ```

    ```csharp
    static void Main(string[] args)
    {
        Application.EnableVisualStyles();
        Application.Run(new WorkflowHostForm());
    }
    ```

4. <span data-ttu-id="5c6bc-321">**ソリューションエクスプローラー**で [ **NumberGuessWorkflowHost** ] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-321">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Properties**.</span></span> <span data-ttu-id="5c6bc-322">[**アプリケーション**] タブで、[**出力の種類**] に [ **Windows アプリケーション**] を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-322">In the **Application** tab, specify **Windows Application** for the **Output type**.</span></span> <span data-ttu-id="5c6bc-323">この手順は省略可能ですが、省略した場合は、フォームに加えてコンソール ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-323">This step is optional, but if it is not followed the console window is displayed in addition to the form.</span></span>

5. <span data-ttu-id="5c6bc-324">Ctrl キーと Shift キーを押しながら B キーを押してアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-324">Press Ctrl+Shift+B to build the application.</span></span>

6. <span data-ttu-id="5c6bc-325">**NumberGuessWorkflowHost**がスタートアップアプリケーションとして設定されていることを確認し、Ctrl キーを押しながら F5 キーを押してアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-325">Ensure that **NumberGuessWorkflowHost** is set as the startup application, and press Ctrl+F5 to start the application.</span></span>

7. <span data-ttu-id="5c6bc-326">推測ゲームの範囲と開始するワークフローの種類を選択し、[**新しいゲーム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-326">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="5c6bc-327">[**推定**] ボックスに推測を入力し、[**ジャンプ**] をクリックして推測を送信します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-327">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="5c6bc-328">`WriteLine` アクティビティからの出力がフォームに表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-328">Note that the output from the `WriteLine` activities is displayed on the form.</span></span>

8. <span data-ttu-id="5c6bc-329">さまざまなワークフローの種類と数値の範囲を使用して複数のワークフローを開始し、いくつかの推測を入力して、[**ワークフローインスタンス Id** ] リストから選択してワークフローを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-329">Start several workflows using different workflow types and number ranges, enter some guesses, and switch between the workflows by selecting from the **Workflow Instance Id** list.</span></span>

    <span data-ttu-id="5c6bc-330">新しいワークフローに切り替えると、前の推定値とワークフローの進行状況はステータス ウィンドウに表示されません。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-330">Note that when you switch to a new workflow, the previous guesses and progress of the workflow are not displayed in the status window.</span></span> <span data-ttu-id="5c6bc-331">ステータスが利用できない理由は、ステータスがキャプチャされず、どこにも保存されないためです。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-331">The reason the status is not available is because it is not captured and saved anywhere.</span></span> <span data-ttu-id="5c6bc-332">チュートリアルの次の手順「[方法: カスタム追跡参加要素を作成](how-to-create-a-custom-tracking-participant.md)する」では、この情報を保存するカスタム追跡参加要素を作成します。</span><span class="sxs-lookup"><span data-stu-id="5c6bc-332">In the next step of the tutorial, [How to: Create a Custom Tracking Participant](how-to-create-a-custom-tracking-participant.md), you create a custom tracking participant that saves this information.</span></span>
