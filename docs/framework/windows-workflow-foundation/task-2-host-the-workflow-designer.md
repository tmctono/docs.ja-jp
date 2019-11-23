---
title: 'タスク 2: ワークフロー デザイナーのホスティング'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 15657ad79632812d3802e4da22b9ef297d08f932
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180260"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="30bf1-102">タスク 2: ワークフロー デザイナーのホスティング</span><span class="sxs-lookup"><span data-stu-id="30bf1-102">Task 2: Host the Workflow Designer</span></span>

<span data-ttu-id="30bf1-103">このトピックでは、Windows Presentation Foundation (WPF) アプリケーションで [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] のインスタンスをホストする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="30bf1-104">このプロシージャは、デザイナーを含む**Grid**コントロールを構成し、既定の <xref:System.Activities.Statements.Sequence> アクティビティを含む <xref:System.Activities.Presentation.WorkflowDesigner> のインスタンスをプログラムによって作成し、デザイナーのメタデータを登録して、すべての組み込みアクティビティのデザイナーサポートを提供し、WPF アプリケーションで [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] をホストします。</span><span class="sxs-lookup"><span data-stu-id="30bf1-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the WPF application.</span></span>

## <a name="to-host-the-workflow-designer"></a><span data-ttu-id="30bf1-105">ワークフロー デザイナーをホストするには</span><span class="sxs-lookup"><span data-stu-id="30bf1-105">To host the workflow designer</span></span>

1. <span data-ttu-id="30bf1-106">[「タスク 1: 新しい Windows Presentation Foundation アプリケーションを作成](task-1-create-a-new-wpf-app.md)する」で作成した HostingApplication プロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="30bf1-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>

2. <span data-ttu-id="30bf1-107">[!INCLUDE[wfd2](../../../includes/wfd2-md.md)] が見やすくなるように、ウィンドウのサイズを調整します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="30bf1-108">これを行うには、デザイナーで **[mainwindow.xaml]** を選択し、F4 キーを押して **[プロパティ]** ウィンドウを表示します。次に、 **[レイアウト]** セクションで、 **[幅]** を600に、 **[高さ]** を350の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>

3. <span data-ttu-id="30bf1-109">デザイナーで **[グリッド]** パネルを選択し ( **mainwindow.xaml**内のボックスをクリック)、 **[プロパティ]** ウィンドウの上部にある **[名前]** プロパティを "grid1" に設定して、グリッド名を設定します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>

4. <span data-ttu-id="30bf1-110">**[プロパティ]** ウィンドウで、[`ColumnDefinitions`] プロパティの横にある省略記号 ( **...** ) をクリックして、 **[コレクションエディター]** ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="30bf1-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>

5. <span data-ttu-id="30bf1-111">**[コレクションエディター]** ダイアログボックスで、 **[追加]** ボタンを3回クリックして、3つの列をレイアウトに挿入します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="30bf1-112">最初の列には**ツールボックス**が含まれ、2番目の列は [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]をホストし、3番目の列はプロパティインスペクターに使用されます。</span><span class="sxs-lookup"><span data-stu-id="30bf1-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>

6. <span data-ttu-id="30bf1-113">中央の列の [`Width`] プロパティを値 "4 \*" に設定します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-113">Set the `Width` property of the middle column to the value "4\*".</span></span>

7. <span data-ttu-id="30bf1-114">**[OK]** をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="30bf1-115">次の XAML が*mainwindow.xaml*ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="30bf1-115">The following XAML is added to your *MainWindow.xaml* file:</span></span>

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. <span data-ttu-id="30bf1-116">**ソリューションエクスプローラー**で、 *mainwindow.xaml*を右クリックし、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-116">In **Solution Explorer**, right-click *MainWindow.xaml* and select **View Code**.</span></span> <span data-ttu-id="30bf1-117">次の手順に従ってコードを修正します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-117">Modify the code by following these steps:</span></span>

    1. <span data-ttu-id="30bf1-118">次の名前空間を追加します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-118">Add the following namespaces:</span></span>

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. <span data-ttu-id="30bf1-119"><xref:System.Activities.Presentation.WorkflowDesigner>のインスタンスを保持するプライベートメンバーフィールドを宣言するには、次のコードを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class:</span></span>

        ```csharp
        public partial class MainWindow : Window
        {
            private WorkflowDesigner wd;

            public MainWindow()
            {
                InitializeComponent();
            }
        }
        ```

    3. <span data-ttu-id="30bf1-120">次の `AddDesigner` メソッドを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="30bf1-121">実装では、<xref:System.Activities.Presentation.WorkflowDesigner>のインスタンスを作成し、<xref:System.Activities.Statements.Sequence> アクティビティを追加して、grid1 **Grid**の中央の列に配置します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>

        ```csharp
        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }
        ```

    4. <span data-ttu-id="30bf1-122">デザイナーのメタデータを登録して、すべてのビルトイン アクティビティにデザイナー サポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="30bf1-123">こうすることにより、ツールボックスから<xref:System.Activities.Statements.Sequence>の元の [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] アクティビティに、アクティビティをドロップできるようになります。</span><span class="sxs-lookup"><span data-stu-id="30bf1-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="30bf1-124">これを行うには、`RegisterMetadata` メソッドを `MainWindow` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class:</span></span>

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        <span data-ttu-id="30bf1-125">アクティビティデザイナーの登録の詳細については、「[方法: カスタムアクティビティデザイナーを作成](how-to-create-a-custom-activity-designer.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bf1-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>

    5. <span data-ttu-id="30bf1-126">`MainWindow` クラス コンストラクターで、前に宣言したメソッドへの呼び出しを追加して、デザイナー サポートのメタデータを登録し、<xref:System.Activities.Presentation.WorkflowDesigner> を作成します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata.
            RegisterMetadata();

            // Add the WFF Designer.
            AddDesigner();
        }
        ```

        > [!NOTE]
        > <span data-ttu-id="30bf1-127">`RegisterMetadata` メソッドは、<xref:System.Activities.Statements.Sequence> アクティビティを含むビルトイン アクティビティのデザイナーのメタデータを登録します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="30bf1-128">`AddDesigner` メソッドは <xref:System.Activities.Statements.Sequence> アクティビティを使用するので、`RegisterMetadata` メソッドを先に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="30bf1-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>

9. <span data-ttu-id="30bf1-129"><kbd>F5</kbd>キーを押して、ソリューションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="30bf1-129">Press <kbd>F5</kbd> to build and run the solution.</span></span>

10. <span data-ttu-id="30bf1-130">再ホストされたワークフローデザイナーに**ツールボックス**と**PropertyGrid**のサポートを追加する方法について[は、「タスク 3: ツールボックスと PropertyGrid のウィンドウを作成](task-3-create-the-toolbox-and-propertygrid-panes.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30bf1-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="30bf1-131">参照</span><span class="sxs-lookup"><span data-stu-id="30bf1-131">See also</span></span>

- [<span data-ttu-id="30bf1-132">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="30bf1-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="30bf1-133">タスク 1: 新しい Windows Presentation Foundation アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="30bf1-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="30bf1-134">タスク 3: ツールボックス ペインと PropertyGrid ペインの作成</span><span class="sxs-lookup"><span data-stu-id="30bf1-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
