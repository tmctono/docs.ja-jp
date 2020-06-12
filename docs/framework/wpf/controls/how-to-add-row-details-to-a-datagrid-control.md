---
title: '方法: DataGrid コントロールに行の詳細を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: 4db414e1907d42071f7251c390077d4020fa577c
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559678"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="ed1b3-102">方法: DataGrid コントロールに行の詳細を追加する</span><span class="sxs-lookup"><span data-stu-id="ed1b3-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="ed1b3-103"><xref:System.Windows.Controls.DataGrid> コントロールを使用する場合、行の詳細セクションを追加することで、データの表示をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="ed1b3-104">行の詳細セクションを追加すると、一部のデータをテンプレートにグループ化し、必要に応じて表示するか折りたたむことができます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="ed1b3-105">たとえば、行の詳細を <xref:System.Windows.Controls.DataGrid> に追加すると、<xref:System.Windows.Controls.DataGrid> の各行にはデータの概要のみが表示されますが、ユーザーが行を選択すると、より多くのデータ フィールドが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="ed1b3-106">行の詳細セクションのテンプレートは、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> プロパティで定義します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="ed1b3-107">次の図は、行の詳細セクションの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="ed1b3-108">![行の詳細が表示された DataGrid](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="ed1b3-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="ed1b3-109">行の詳細テンプレートは、インライン XAML またはリソースとして定義します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="ed1b3-110">両方の方法について次の手順で示します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="ed1b3-111">リソースとして追加されたデータ テンプレートは、テンプレートを再作成することなく、プロジェクト全体で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="ed1b3-112">インライン XAML として追加されたデータ テンプレートは、それが定義されているコントロールからのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="ed1b3-113">インライン XAML を使用して行の詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="ed1b3-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="ed1b3-114">データ ソースからのデータを表示する <xref:System.Windows.Controls.DataGrid> を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="ed1b3-115"><xref:System.Windows.Controls.DataGrid> 要素に、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="ed1b3-116">行の詳細セクションの外観を定義する <xref:System.Windows.DataTemplate> を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="ed1b3-117">次の XAML は、<xref:System.Windows.Controls.DataGrid> と <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> をインラインで定義する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="ed1b3-118"><xref:System.Windows.Controls.DataGrid> を使用すると、各行に 3 つの値が表示され、行を選択するとさらに 3 つの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="ed1b3-119">次のコードは、<xref:System.Windows.Controls.DataGrid> に表示されるデータを選択するために使用されるクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="ed1b3-120">この例では、クエリによって顧客情報を含むエンティティからデータが選択されます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="ed1b3-121">リソースを使用して行の詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="ed1b3-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="ed1b3-122">データ ソースからのデータを表示する <xref:System.Windows.Controls.DataGrid> を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="ed1b3-123"><xref:System.Windows.FrameworkElement.Resources%2A> 要素を <xref:System.Windows.Window> コントロールや <xref:System.Windows.Controls.Page> コントロールなどのルート要素に追加するか、<xref:System.Windows.Application.Resources%2A> 要素を App.xaml (または Application.xaml) ファイルの <xref:System.Windows.Application> クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="ed1b3-124">resources 要素に、行の詳細セクションの外観を定義する <xref:System.Windows.DataTemplate> を作成します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="ed1b3-125">次の XAML は、<xref:System.Windows.Application> クラスで定義された <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> を示しています。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="ed1b3-126"><xref:System.Windows.DataTemplate> に対して、[x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) をデータ テンプレートを一意に識別する値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="ed1b3-127"><xref:System.Windows.Controls.DataGrid> 要素で、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> プロパティを前の手順で定義したリソースに設定します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="ed1b3-128">リソースを静的リソースとして割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="ed1b3-129">次の XAML は、前の例のリソースに設定された <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> プロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="ed1b3-130">可視性を設定し、行の詳細が水平方向にスクロールしないようにするには</span><span class="sxs-lookup"><span data-stu-id="ed1b3-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="ed1b3-131">必要に応じて <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> プロパティを <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> 値に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="ed1b3-132">既定では、この値は <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected> に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="ed1b3-133">すべての行の詳細を表示するには <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> に、すべての行の詳細を非表示にするには <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="ed1b3-134">必要に応じて、<xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> プロパティを `true` に設定して、行の詳細セクションが水平方向にスクロールしないようにします。</span><span class="sxs-lookup"><span data-stu-id="ed1b3-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
