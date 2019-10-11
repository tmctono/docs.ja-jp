---
title: タスク 3:ツールボックス ペインと PropertyGrid ペインの作成
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 402a25c1cb82c245afa94f58cefc180515622ea9
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275864"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="803d3-102">タスク 3:ツールボックス ペインと PropertyGrid ペインの作成</span><span class="sxs-lookup"><span data-stu-id="803d3-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>

<span data-ttu-id="803d3-103">このタスクでは、**ツールボックス**ペインと**PropertyGrid**ウィンドウを作成し、再ホストされた [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] に追加します。</span><span class="sxs-lookup"><span data-stu-id="803d3-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>

<span data-ttu-id="803d3-104">参考として、このトピックの最後に、ワークフローデザイナーシリーズのトピックの再[ホスト](rehosting-the-workflow-designer.md)に関する3つのタスクを完了した後に MainWindow.xaml.cs ファイルに含まれている必要があるコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="803d3-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="803d3-105">ツールボックスを作成し、グリッドに追加するには</span><span class="sxs-lookup"><span data-stu-id="803d3-105">To create the Toolbox and add it to the grid</span></span>

1. <span data-ttu-id="803d3-106">「@No__t-0Task 2:」で説明されている手順に従って、取得した HostingApplication プロジェクトを開きます。ワークフローデザイナー @ no__t-0 をホストします。</span><span class="sxs-lookup"><span data-stu-id="803d3-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md).</span></span>

2. <span data-ttu-id="803d3-107">**ソリューションエクスプローラー**ペインで、 *mainwindow.xaml*ファイルを右クリックし、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="803d3-107">In the **Solution Explorer** pane, right-click the *MainWindow.xaml* file and select **View Code**.</span></span>

3. <span data-ttu-id="803d3-108">@No__t-2 を作成し、新しい**ツールボックス**カテゴリを**ツールボックス**に追加して、<xref:System.Activities.Statements.Assign> および <xref:System.Activities.Statements.Sequence> アクティビティの種類をそのカテゴリに割り当てる、`MainWindow` クラスに `GetToolboxControl` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="803d3-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>

    ```csharp
    private ToolboxControl GetToolboxControl()
    {
        // Create the ToolBoxControl.
        var ctrl = new ToolboxControl();

        // Create a category.
        var category = new ToolboxCategory("category1");

        // Create Toolbox items.
        var tool1 =
            new ToolboxItemWrapper("System.Activities.Statements.Assign",
            typeof(Assign).Assembly.FullName, null, "Assign");

        var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
            typeof(Sequence).Assembly.FullName, null, "Sequence");

        // Add the Toolbox items to the category.
        category.Add(tool1);
        category.Add(tool2);

        // Add the category to the ToolBox control.
        ctrl.Categories.Add(category);
        return ctrl;
    }
    ```

4. <span data-ttu-id="803d3-109">グリッドの左側の列に**ツールボックス**を配置する `MainWindow` クラスにプライベート `AddToolbox` メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="803d3-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. <span data-ttu-id="803d3-110">次のコードに示すように、`MainWindow()` クラスコンストラクターに `AddToolBox` メソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="803d3-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code:</span></span>

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. <span data-ttu-id="803d3-111"><kbd>F5</kbd>キーを押して、ソリューションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="803d3-111">Press <kbd>F5</kbd> to build and run your solution.</span></span> <span data-ttu-id="803d3-112">@No__t-1 と @no__t 2 つのアクティビティを含む**ツールボックス**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="803d3-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>

## <a name="to-create-the-propertygrid"></a><span data-ttu-id="803d3-113">PropertyGrid を作成するには</span><span class="sxs-lookup"><span data-stu-id="803d3-113">To create the PropertyGrid</span></span>

1. <span data-ttu-id="803d3-114">**ソリューションエクスプローラー**ペインで、 *mainwindow.xaml*ファイルを右クリックし、 **[コードの表示]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="803d3-114">In the **Solution Explorer** pane, right-click the *MainWindow.xaml* file and select **View Code**.</span></span>

2. <span data-ttu-id="803d3-115">@No__t-0 メソッドを `MainWindow` クラスに追加して、グリッドの右端の列に **[PropertyGrid]** ペインを配置します。</span><span class="sxs-lookup"><span data-stu-id="803d3-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid:</span></span>

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. <span data-ttu-id="803d3-116">次のコードに示すように、`MainWindow()` クラスコンストラクターに `AddPropertyInspector` メソッドの呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="803d3-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code:</span></span>

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();
        this.AddToolBox();

        this.AddPropertyInspector();
    }
    ```

4. <span data-ttu-id="803d3-117"><kbd>F5</kbd>キーを押して、ソリューションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="803d3-117">Press <kbd>F5</kbd> to build and run the solution.</span></span> <span data-ttu-id="803d3-118">**[ツールボックス]** 、ワークフローデザインキャンバス、および  **[PropertyGrid]** の各ウィンドウがすべて表示されます。また、@no__t 2 アクティビティまたは @no__t 3 アクティビティをデザインキャンバスにドラッグすると、強調表示されたアクティビティに応じてプロパティグリッドが更新されます。</span><span class="sxs-lookup"><span data-stu-id="803d3-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>

## <a name="example"></a><span data-ttu-id="803d3-119">例</span><span class="sxs-lookup"><span data-stu-id="803d3-119">Example</span></span>

<span data-ttu-id="803d3-120">*MainWindow.xaml.cs*ファイルには、次のコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="803d3-120">The *MainWindow.xaml.cs* file should now contain the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;
// dlls added.
using System.Activities;
using System.Activities.Core.Presentation;
using System.Activities.Presentation;
using System.Activities.Presentation.Metadata;
using System.Activities.Presentation.Toolbox;
using System.Activities.Statements;
using System.ComponentModel;

namespace HostingApplication
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        private WorkflowDesigner wd;

        public MainWindow()
        {
            InitializeComponent();
            RegisterMetadata();
            AddDesigner();
            this.AddToolBox();
            this.AddPropertyInspector();
        }

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

        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }

        private ToolboxControl GetToolboxControl()
        {
            // Create the ToolBoxControl.
            var ctrl = new ToolboxControl();

            // Create a category.
            var category = new ToolboxCategory("category1");

            // Create Toolbox items.
            var tool1 =
                new ToolboxItemWrapper("System.Activities.Statements.Assign",
                typeof(Assign).Assembly.FullName, null, "Assign");

            var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
                typeof(Sequence).Assembly.FullName, null, "Sequence");

            // Add the Toolbox items to the category.
            category.Add(tool1);
            category.Add(tool2);

            // Add the category to the ToolBox control.
            ctrl.Categories.Add(category);
            return ctrl;
        }

        private void AddToolBox()
        {
            ToolboxControl tc = GetToolboxControl();
            Grid.SetColumn(tc, 0);
            grid1.Children.Add(tc);
        }

        private void AddPropertyInspector()
        {
            Grid.SetColumn(wd.PropertyInspectorView, 2);
            grid1.Children.Add(wd.PropertyInspectorView);
        }

    }
}
```

## <a name="see-also"></a><span data-ttu-id="803d3-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="803d3-121">See also</span></span>

- [<span data-ttu-id="803d3-122">ワークフロー デザイナーのホスト変更</span><span class="sxs-lookup"><span data-stu-id="803d3-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- <span data-ttu-id="803d3-123">[Task 1:新しい Windows Presentation Foundation アプリケーションの作成 @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="803d3-123">[Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md)</span></span>
- <span data-ttu-id="803d3-124">[Task 2:ワークフローデザイナー @ no__t をホストします。</span><span class="sxs-lookup"><span data-stu-id="803d3-124">[Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md)</span></span>
