---
title: 'チュートリアル : ハイブリッド アプリケーションでのデータへのバインディング'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794221"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="36694-102">チュートリアル : ハイブリッド アプリケーションでのデータへのバインディング</span><span class="sxs-lookup"><span data-stu-id="36694-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="36694-103">データソースをコントロールにバインドすることは、Windows フォームと [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]のどちらを使用しているかにかかわらず、ユーザーが基になるデータにアクセスできるようにするために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="36694-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using Windows Forms or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="36694-104">このチュートリアルでは、Windows フォームと [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] の両方のコントロールを含むハイブリッドアプリケーションでデータバインディングを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36694-104">This walkthrough shows how you can use data binding in hybrid applications that include both Windows Forms and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="36694-105">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="36694-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="36694-106">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="36694-106">Creating the project.</span></span>

- <span data-ttu-id="36694-107">データテンプレートを定義しています。</span><span class="sxs-lookup"><span data-stu-id="36694-107">Defining the data template.</span></span>

- <span data-ttu-id="36694-108">フォームレイアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="36694-108">Specifying the form layout.</span></span>

- <span data-ttu-id="36694-109">データバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="36694-109">Specifying data bindings.</span></span>

- <span data-ttu-id="36694-110">相互運用を使用してデータを表示する。</span><span class="sxs-lookup"><span data-stu-id="36694-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="36694-111">プロジェクトにデータソースを追加しています。</span><span class="sxs-lookup"><span data-stu-id="36694-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="36694-112">データソースにバインドしています。</span><span class="sxs-lookup"><span data-stu-id="36694-112">Binding to the data source.</span></span>

<span data-ttu-id="36694-113">このチュートリアルで示すタスクの完全なコード一覧については、「[ハイブリッドアプリケーションでのデータバインディングのサンプル](https://go.microsoft.com/fwlink/?LinkID=159983)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36694-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>

<span data-ttu-id="36694-114">完了すると、ハイブリッドアプリケーションのデータバインディング機能について理解できるようになります。</span><span class="sxs-lookup"><span data-stu-id="36694-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36694-115">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="36694-115">Prerequisites</span></span>

<span data-ttu-id="36694-116">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="36694-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="36694-117">Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="36694-117">Visual Studio.</span></span>

- <span data-ttu-id="36694-118">Microsoft SQL Server で実行されている Northwind サンプルデータベースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="36694-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="36694-119">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="36694-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="36694-120">プロジェクトを作成し、設定するには</span><span class="sxs-lookup"><span data-stu-id="36694-120">To create and set up the project</span></span>

1. <span data-ttu-id="36694-121">`WPFWithWFAndDatabinding`という名前の WPF アプリケーションプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="36694-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="36694-122">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="36694-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="36694-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="36694-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="36694-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="36694-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="36694-125">WPF デザイナーで Mainwindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="36694-125">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="36694-126"><xref:System.Windows.Window> 要素に、次の Windows フォーム名前空間マッピングを追加します。</span><span class="sxs-lookup"><span data-stu-id="36694-126">In the <xref:System.Windows.Window> element, add the following Windows Forms namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="36694-127"><xref:System.Windows.FrameworkElement.Name%2A> プロパティを割り当てることによって、既定の <xref:System.Windows.Controls.Grid> 要素 `mainGrid` に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="36694-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="36694-128">データテンプレートの定義</span><span class="sxs-lookup"><span data-stu-id="36694-128">Defining the Data Template</span></span>

<span data-ttu-id="36694-129">顧客のマスターリストが <xref:System.Windows.Controls.ListBox> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="36694-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="36694-130">次のコード例では、<xref:System.Windows.Controls.ListBox> コントロールのビジュアルツリーを制御する `ListItemsTemplate` という名前の <xref:System.Windows.DataTemplate> オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="36694-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="36694-131">この <xref:System.Windows.DataTemplate> は、<xref:System.Windows.Controls.ListBox> コントロールの <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="36694-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="36694-132">データテンプレートを定義するには</span><span class="sxs-lookup"><span data-stu-id="36694-132">To define the data template</span></span>

- <span data-ttu-id="36694-133">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="36694-134">フォームレイアウトの指定</span><span class="sxs-lookup"><span data-stu-id="36694-134">Specifying the Form Layout</span></span>

<span data-ttu-id="36694-135">フォームのレイアウトは、3つの行と3つの列を持つグリッドによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="36694-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="36694-136">Customers テーブルの各列を識別するために、<xref:System.Windows.Controls.Label> コントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="36694-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="36694-137">グリッドレイアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="36694-137">To set up the Grid layout</span></span>

- <span data-ttu-id="36694-138">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="36694-139">ラベルコントロールを設定するには</span><span class="sxs-lookup"><span data-stu-id="36694-139">To set up the Label controls</span></span>

- <span data-ttu-id="36694-140">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="36694-141">データバインディングの指定</span><span class="sxs-lookup"><span data-stu-id="36694-141">Specifying Data Bindings</span></span>

<span data-ttu-id="36694-142">顧客のマスターリストが <xref:System.Windows.Controls.ListBox> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="36694-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="36694-143">アタッチされた `ListItemsTemplate` は、<xref:System.Windows.Controls.TextBlock> コントロールをデータベースの `ContactName` フィールドにバインドします。</span><span class="sxs-lookup"><span data-stu-id="36694-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="36694-144">各顧客レコードの詳細が、いくつかの <xref:System.Windows.Controls.TextBox> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="36694-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="36694-145">データバインディングを指定するには</span><span class="sxs-lookup"><span data-stu-id="36694-145">To specify data bindings</span></span>

- <span data-ttu-id="36694-146">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="36694-147"><xref:System.Windows.Data.Binding> クラスは、<xref:System.Windows.Controls.TextBox> コントロールをデータベース内の適切なフィールドにバインドします。</span><span class="sxs-lookup"><span data-stu-id="36694-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="36694-148">相互運用を使用したデータの表示</span><span class="sxs-lookup"><span data-stu-id="36694-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="36694-149">選択した顧客に対応する注文が `dataGridView1`という名前の <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="36694-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="36694-150">`dataGridView1` コントロールは、分離コードファイル内のデータソースにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="36694-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="36694-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールは、この Windows フォームコントロールの親です。</span><span class="sxs-lookup"><span data-stu-id="36694-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this Windows Forms control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="36694-152">DataGridView コントロールにデータを表示するには</span><span class="sxs-lookup"><span data-stu-id="36694-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="36694-153">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="36694-154">プロジェクトへのデータソースの追加</span><span class="sxs-lookup"><span data-stu-id="36694-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="36694-155">Visual Studio を使用すると、データソースを簡単にプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="36694-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="36694-156">この手順では、厳密に型指定されたデータセットをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="36694-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="36694-157">選択した各テーブルのテーブルアダプターなど、他のいくつかのサポートクラスも追加されています。</span><span class="sxs-lookup"><span data-stu-id="36694-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="36694-158">データ ソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="36694-158">To add the data source</span></span>

1. <span data-ttu-id="36694-159">**[データ]** メニューの **[新しいデータソースの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36694-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="36694-160">**データソース構成ウィザード**で、データセットを使用して Northwind データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="36694-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="36694-161">詳細については、「 [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36694-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="36694-162">**データソース構成ウィザード**によってメッセージが表示されたら、`NorthwindConnectionString`として接続文字列を保存します。</span><span class="sxs-lookup"><span data-stu-id="36694-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="36694-163">データベースオブジェクトの選択を求めるメッセージが表示されたら、`Customers` テーブルと `Orders` テーブルを選択し、生成されたデータセットに `NorthwindDataSet`という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="36694-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="36694-164">データソースへのバインド</span><span class="sxs-lookup"><span data-stu-id="36694-164">Binding to the Data Source</span></span>

<span data-ttu-id="36694-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> コンポーネントは、アプリケーションのデータソースに対して統一されたインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="36694-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="36694-166">データソースへのバインドは、分離コードファイルに実装されています。</span><span class="sxs-lookup"><span data-stu-id="36694-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="36694-167">データソースにバインドするには</span><span class="sxs-lookup"><span data-stu-id="36694-167">To bind to the data source</span></span>

1. <span data-ttu-id="36694-168">Mainwindow.xaml または MainWindow.xaml.cs という名前の分離コードファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="36694-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="36694-169">次のコードを `MainWindow` クラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="36694-170">このコードは、データベースに接続する <xref:System.Windows.Forms.BindingSource> コンポーネントと関連付けられたヘルパークラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="36694-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="36694-171">次のコードをコンストラクターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="36694-172">このコードでは、<xref:System.Windows.Forms.BindingSource> コンポーネントを作成して初期化します。</span><span class="sxs-lookup"><span data-stu-id="36694-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="36694-173">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="36694-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="36694-174">デザインビューまたは XAML ビューで、<xref:System.Windows.Window> 要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="36694-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="36694-175">プロパティウィンドウで、 **[イベント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="36694-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="36694-176"><xref:System.Windows.FrameworkElement.Loaded> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="36694-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="36694-177">次のコードを <xref:System.Windows.FrameworkElement.Loaded> イベントハンドラーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="36694-178">このコードでは、<xref:System.Windows.Forms.BindingSource> コンポーネントをデータコンテキストとして割り当て、`Customers` および `Orders` アダプターオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="36694-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="36694-179">次のコードを `MainWindow` クラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="36694-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="36694-180">このメソッドは、<xref:System.Windows.Data.CollectionView.CurrentChanged> イベントを処理し、データバインディングの現在の項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="36694-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="36694-181">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="36694-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="36694-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="36694-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="36694-183">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="36694-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="36694-184">ハイブリッドアプリケーションでのデータバインディングのサンプル</span><span class="sxs-lookup"><span data-stu-id="36694-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)
- [<span data-ttu-id="36694-185">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="36694-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="36694-186">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="36694-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
