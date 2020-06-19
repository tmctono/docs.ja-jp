---
title: 'チュートリアル: ハイブリッド アプリケーションでのデータへのバインディング'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 0d1e66a1277e6a04d2f49ac91691160f70fb56e4
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095074"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="370ac-102">チュートリアル: ハイブリッド アプリケーションでのデータへのバインディング</span><span class="sxs-lookup"><span data-stu-id="370ac-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="370ac-103">データ ソースをコントロールにバインドすることは、Windows フォームを使用しているか [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] を使用しているかに関係なく、基になるデータへのアクセスをユーザーに提供するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="370ac-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using Windows Forms or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="370ac-104">このチュートリアルでは、Windows フォームと [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] コントロールの両方を含むハイブリッド アプリケーションでデータ バインディングを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="370ac-104">This walkthrough shows how you can use data binding in hybrid applications that include both Windows Forms and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="370ac-105">このチュートリアルでは、以下のタスクを行います。</span><span class="sxs-lookup"><span data-stu-id="370ac-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="370ac-106">プロジェクトの作成。</span><span class="sxs-lookup"><span data-stu-id="370ac-106">Creating the project.</span></span>

- <span data-ttu-id="370ac-107">データ テンプレートの定義。</span><span class="sxs-lookup"><span data-stu-id="370ac-107">Defining the data template.</span></span>

- <span data-ttu-id="370ac-108">フォームのレイアウトの指定。</span><span class="sxs-lookup"><span data-stu-id="370ac-108">Specifying the form layout.</span></span>

- <span data-ttu-id="370ac-109">データ バインディングの指定。</span><span class="sxs-lookup"><span data-stu-id="370ac-109">Specifying data bindings.</span></span>

- <span data-ttu-id="370ac-110">相互運用を使用したデータの表示。</span><span class="sxs-lookup"><span data-stu-id="370ac-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="370ac-111">データ ソースのプロジェクトへの追加。</span><span class="sxs-lookup"><span data-stu-id="370ac-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="370ac-112">データ ソースへのバインド。</span><span class="sxs-lookup"><span data-stu-id="370ac-112">Binding to the data source.</span></span>

<span data-ttu-id="370ac-113">このチュートリアルで説明するタスクの完全なコード リストについては、[ハイブリッド アプリケーションのデータ バインディングのサンプル](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370ac-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding).</span></span>

<span data-ttu-id="370ac-114">完了すると、ハイブリッド アプリケーションのデータ バインディング機能について理解できます。</span><span class="sxs-lookup"><span data-stu-id="370ac-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="370ac-115">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="370ac-115">Prerequisites</span></span>

<span data-ttu-id="370ac-116">このチュートリアルを実行するには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="370ac-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="370ac-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="370ac-117">Visual Studio.</span></span>

- <span data-ttu-id="370ac-118">Microsoft SQL Server で実行されている Northwind サンプル データベースへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="370ac-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="370ac-119">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="370ac-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="370ac-120">プロジェクトを作成し、設定するには</span><span class="sxs-lookup"><span data-stu-id="370ac-120">To create and set up the project</span></span>

1. <span data-ttu-id="370ac-121">`WPFWithWFAndDatabinding` という名前の WPF アプリケーション プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="370ac-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="370ac-122">ソリューション エクスプローラーで、次のアセンブリへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="370ac-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="370ac-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="370ac-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="370ac-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="370ac-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="370ac-125">WPF デザイナーで MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="370ac-125">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="370ac-126"><xref:System.Windows.Window> 要素に、次の Windows フォーム名前空間マップを追加します。</span><span class="sxs-lookup"><span data-stu-id="370ac-126">In the <xref:System.Windows.Window> element, add the following Windows Forms namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="370ac-127"><xref:System.Windows.FrameworkElement.Name%2A> プロパティを割り当てて、既定の <xref:System.Windows.Controls.Grid> 要素に `mainGrid` という名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="370ac-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="370ac-128">データ テンプレートの定義</span><span class="sxs-lookup"><span data-stu-id="370ac-128">Defining the Data Template</span></span>

<span data-ttu-id="370ac-129"><xref:System.Windows.Controls.ListBox> コントロールには顧客のマスター リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="370ac-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="370ac-130">次のコード例では、<xref:System.Windows.Controls.ListBox> コントロールのビジュアル ツリーを制御する `ListItemsTemplate` という名前の <xref:System.Windows.DataTemplate> オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="370ac-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="370ac-131">この <xref:System.Windows.DataTemplate> は、<xref:System.Windows.Controls.ListBox> コントロールの <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> プロパティに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="370ac-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="370ac-132">データ テンプレートを定義するには</span><span class="sxs-lookup"><span data-stu-id="370ac-132">To define the data template</span></span>

- <span data-ttu-id="370ac-133">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="370ac-134">フォーム レイアウトの指定</span><span class="sxs-lookup"><span data-stu-id="370ac-134">Specifying the Form Layout</span></span>

<span data-ttu-id="370ac-135">フォーム レイアウトは、3 つの行と 3 つの列を持つグリッドによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="370ac-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="370ac-136"><xref:System.Windows.Controls.Label> コントロールは、Customers テーブルの各列を識別するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="370ac-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="370ac-137">グリッド レイアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="370ac-137">To set up the Grid layout</span></span>

- <span data-ttu-id="370ac-138">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="370ac-139">ラベル コントロールを設定するには</span><span class="sxs-lookup"><span data-stu-id="370ac-139">To set up the Label controls</span></span>

- <span data-ttu-id="370ac-140">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="370ac-141">データ バインディングの指定</span><span class="sxs-lookup"><span data-stu-id="370ac-141">Specifying Data Bindings</span></span>

<span data-ttu-id="370ac-142"><xref:System.Windows.Controls.ListBox> コントロールには顧客のマスター リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="370ac-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="370ac-143">アタッチされた `ListItemsTemplate` によって、<xref:System.Windows.Controls.TextBlock> コントロールはデータベースの `ContactName` フィールドにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="370ac-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="370ac-144">各顧客レコードの詳細は、いくつかの <xref:System.Windows.Controls.TextBox> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="370ac-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="370ac-145">データ バインディングを指定するには</span><span class="sxs-lookup"><span data-stu-id="370ac-145">To specify data bindings</span></span>

- <span data-ttu-id="370ac-146">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="370ac-147"><xref:System.Windows.Data.Binding> クラスによって、<xref:System.Windows.Controls.TextBox> コントロールはデータベースの適切なフィールドにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="370ac-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="370ac-148">相互運用を使用したデータの表示</span><span class="sxs-lookup"><span data-stu-id="370ac-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="370ac-149">選択した顧客に対応する注文は、`dataGridView1` という名前の <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="370ac-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="370ac-150">`dataGridView1` コントロールは、分離コード ファイルのデータ ソースにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="370ac-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="370ac-151"><xref:System.Windows.Forms.Integration.WindowsFormsHost> コントロールは、この Windows フォーム コントロールの親です。</span><span class="sxs-lookup"><span data-stu-id="370ac-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this Windows Forms control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="370ac-152">DataGridView コントロールにデータを表示するには</span><span class="sxs-lookup"><span data-stu-id="370ac-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="370ac-153">次の XAML を <xref:System.Windows.Controls.Grid> 要素の宣言にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="370ac-154">データ ソースのプロジェクトへの追加</span><span class="sxs-lookup"><span data-stu-id="370ac-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="370ac-155">Visual Studio を使用すると、プロジェクトにデータ ソースを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="370ac-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="370ac-156">この手順では、厳密に型指定されたデータ セットをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="370ac-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="370ac-157">選択した各テーブルのテーブル アダプターなど、他のいくつかのサポート クラスも追加されます。</span><span class="sxs-lookup"><span data-stu-id="370ac-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="370ac-158">データ ソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="370ac-158">To add the data source</span></span>

1. <span data-ttu-id="370ac-159">**[データ]** メニューの **[新しいデータ ソースの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="370ac-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="370ac-160">**データ ソース構成ウィザード**で、データセットを使用して Northwind データベースへの接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="370ac-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="370ac-161">詳細については、[方法: データベース内のデータに接続する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370ac-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="370ac-162">**データ ソース構成ウィザード**で確認メッセージが表示されたら、接続文字列を `NorthwindConnectionString` という名前で保存します。</span><span class="sxs-lookup"><span data-stu-id="370ac-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="370ac-163">データベース オブジェクトを選択するように求められたら、`Customers` および `Orders` テーブルを選択し、生成されたデータセットに `NorthwindDataSet` と名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="370ac-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="370ac-164">データ ソースへのバインド</span><span class="sxs-lookup"><span data-stu-id="370ac-164">Binding to the Data Source</span></span>

<span data-ttu-id="370ac-165"><xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> コンポーネントには、アプリケーションのデータ ソース用の統一されたインターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="370ac-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="370ac-166">データ ソースへのバインドは、分離コード ファイルに実装されています。</span><span class="sxs-lookup"><span data-stu-id="370ac-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="370ac-167">データ ソースにバインドするには</span><span class="sxs-lookup"><span data-stu-id="370ac-167">To bind to the data source</span></span>

1. <span data-ttu-id="370ac-168">MainWindow.xaml.vb または MainWindow.xaml.cs という名前の分離コード ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="370ac-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="370ac-169">次のコードを `MainWindow` クラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="370ac-170">このコードでは、データベースに接続する <xref:System.Windows.Forms.BindingSource> コンポーネントと関連するヘルパー クラスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="370ac-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="370ac-171">次のコードをコンストラクターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="370ac-172">このコードでは、<xref:System.Windows.Forms.BindingSource> コンポーネントを作成して初期化します。</span><span class="sxs-lookup"><span data-stu-id="370ac-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="370ac-173">MainWindow.xaml を開きます。</span><span class="sxs-lookup"><span data-stu-id="370ac-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="370ac-174">デザイン ビューまたは XAML ビューで、<xref:System.Windows.Window> 要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="370ac-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="370ac-175">プロパティ ウィンドウの **[イベント]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="370ac-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="370ac-176"><xref:System.Windows.FrameworkElement.Loaded> イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="370ac-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="370ac-177">次のコードを <xref:System.Windows.FrameworkElement.Loaded> イベント ハンドラーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="370ac-178">このコードでは、<xref:System.Windows.Forms.BindingSource> コンポーネントをデータ コンテキストとして割り当て、`Customers` および `Orders` アダプター オブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="370ac-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="370ac-179">次のコードを `MainWindow` クラス定義にコピーします。</span><span class="sxs-lookup"><span data-stu-id="370ac-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="370ac-180">このメソッドを使用して <xref:System.Windows.Data.CollectionView.CurrentChanged> イベントを処理し、データ バインディングの現在の項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="370ac-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="370ac-181">F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="370ac-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="370ac-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="370ac-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="370ac-183">Visual Studio で XAML をデザインする</span><span class="sxs-lookup"><span data-stu-id="370ac-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="370ac-184">ハイブリッド アプリケーションのデータ バインディングのサンプル</span><span class="sxs-lookup"><span data-stu-id="370ac-184">Data Binding in Hybrid Applications Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFWithWFAndDatabinding)
- [<span data-ttu-id="370ac-185">チュートリアル: WPF での Windows フォーム複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="370ac-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="370ac-186">チュートリアル: Windows フォームでの WPF 複合コントロールのホスト</span><span class="sxs-lookup"><span data-stu-id="370ac-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
