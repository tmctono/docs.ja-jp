---
title: '方法: デザイナーを使ってデータ ソースに Windows フォーム DataGrid コントロールをバインドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: fe54c650e1d19f36d681053c7da47e12527c5827
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320887"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="26010-102">方法: デザイナーを使ってデータ ソースに Windows フォーム DataGrid コントロールをバインドする</span><span class="sxs-lookup"><span data-stu-id="26010-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="26010-103"><xref:System.Windows.Forms.DataGridView> コントロールは、<xref:System.Windows.Forms.DataGrid> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.DataGrid> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="26010-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="26010-104">詳細については、「[Windows フォームの DataGridView コントロールと DataGrid コントロールの違いについて](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26010-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="26010-105">Windows フォーム<xref:System.Windows.Forms.DataGrid>コントロールが具体的には、データ ソースから情報を表示するように設計します。</span><span class="sxs-lookup"><span data-stu-id="26010-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="26010-106">デザイン時に設定して、コントロールをバインドする、<xref:System.Windows.Forms.DataGrid.DataSource%2A>と<xref:System.Windows.Forms.DataGrid.DataMember%2A>プロパティ、または呼び出すことによって実行時に、<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="26010-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="26010-107">さまざまなデータ ソースからデータを表示できますが、最も一般的なソース、データセットとデータのビューです。</span><span class="sxs-lookup"><span data-stu-id="26010-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="26010-108">デザイン時にデータ ソースが使用可能な場合: たとえば、フォームには、データセットまたはデータ ビューのインスタンスが含まれている場合: グリッドは、デザイン時に、データ ソースにバインドできます。</span><span class="sxs-lookup"><span data-stu-id="26010-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="26010-109">グリッドで、データの見た目をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="26010-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="26010-110">グリッドは実行時にプログラムでバインドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="26010-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="26010-111">これは、実行時に取得した情報に基づくデータ ソースを設定する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="26010-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="26010-112">たとえば、アプリケーション ユーザーに表示するテーブルの名前を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="26010-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="26010-113">場所、データ ソースがデザイン時に存在しない状況で必要です。</span><span class="sxs-lookup"><span data-stu-id="26010-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="26010-114">これには、配列、コレクション、型指定されていないデータセット、およびデータ リーダーなどのデータ ソースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="26010-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="26010-115">次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.DataGrid>コントロール。</span><span class="sxs-lookup"><span data-stu-id="26010-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="26010-116">このようなプロジェクトの設定の詳細については、次を参照してください。[方法。Windows フォーム アプリケーション プロジェクトを作成](/visualstudio/ide/step-1-create-a-windows-forms-application-project)と[方法。Windows フォームにコントロールを追加](how-to-add-controls-to-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="26010-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="26010-117">Visual Studio 2005 で、<xref:System.Windows.Forms.DataGrid>制御されていない、**ツールボックス**既定。</span><span class="sxs-lookup"><span data-stu-id="26010-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="26010-118">追加の詳細については、次を参照してください。[方法。項目をツールボックスに追加](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="26010-118">For information about adding it, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="26010-119">さらに、Visual Studio 2005 で使用できます、**データソース**デザイン時のデータ バインディングのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="26010-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="26010-120">詳細については、次を参照してください。 [Visual Studio でのデータ コントロールをバインド](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)します。</span><span class="sxs-lookup"><span data-stu-id="26010-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26010-121">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="26010-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="26010-122">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26010-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="26010-123">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26010-123">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="26010-124">デザイナーで 1 つのテーブルへ DataGrid コントロールのデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="26010-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1. <span data-ttu-id="26010-125">コントロールの設定<xref:System.Windows.Forms.DataGrid.DataSource%2A>プロパティにバインドするデータ項目を格納するオブジェクトをします。</span><span class="sxs-lookup"><span data-stu-id="26010-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2. <span data-ttu-id="26010-126">データ ソースがデータセットの場合は、設定、<xref:System.Windows.Forms.DataGrid.DataMember%2A>プロパティにバインドするテーブルの名前にします。</span><span class="sxs-lookup"><span data-stu-id="26010-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3. <span data-ttu-id="26010-127">データ ソースがデータセットまたはデータセットのテーブルに基づくデータ ビューの場合は、データセットを挿入するためのフォームにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="26010-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="26010-128">実際に使用するコードは、データセットがデータを取得する場所に依存します。</span><span class="sxs-lookup"><span data-stu-id="26010-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="26010-129">通常、呼び出す場合は、データセットをデータベースから直接登録されている、`Fill`メソッドという名前のデータセットを設定します次のコード例のように、データ アダプターの`DsCategories1`:。</span><span class="sxs-lookup"><span data-stu-id="26010-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4. <span data-ttu-id="26010-130">(省略可能)グリッドに適切なテーブルのスタイルおよび列のスタイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="26010-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="26010-131">テーブル スタイルがない場合は、テーブルが表示されますが、最低限の書式と表示されているすべての列。</span><span class="sxs-lookup"><span data-stu-id="26010-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="26010-132">デザイナーでデータセットの複数のテーブルへ DataGrid コントロールのデータをバインドする</span><span class="sxs-lookup"><span data-stu-id="26010-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1. <span data-ttu-id="26010-133">コントロールの設定<xref:System.Windows.Forms.DataGrid.DataSource%2A>プロパティにバインドするデータ項目を格納するオブジェクトをします。</span><span class="sxs-lookup"><span data-stu-id="26010-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2. <span data-ttu-id="26010-134">(リレーションシップ オブジェクトが含まれている) 場合は、データセットに関連するテーブルが含まれる場合、設定、<xref:System.Windows.Forms.DataGrid.DataMember%2A>プロパティを親テーブルの名前にします。</span><span class="sxs-lookup"><span data-stu-id="26010-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3. <span data-ttu-id="26010-135">データセットを挿入するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="26010-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26010-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="26010-136">See also</span></span>

- [<span data-ttu-id="26010-137">DataGrid コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="26010-137">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="26010-138">方法: Windows フォームの DataGrid コントロールにテーブルと列を追加します。</span><span class="sxs-lookup"><span data-stu-id="26010-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="26010-139">DataGrid コントロール</span><span class="sxs-lookup"><span data-stu-id="26010-139">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="26010-140">Windows フォームでのデータ バインディング</span><span class="sxs-lookup"><span data-stu-id="26010-140">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="26010-141">Visual Studio でのデータへのアクセス</span><span class="sxs-lookup"><span data-stu-id="26010-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
