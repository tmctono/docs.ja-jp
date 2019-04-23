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
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768645"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="f618e-102">方法: DataGrid コントロールに行の詳細を追加する</span><span class="sxs-lookup"><span data-stu-id="f618e-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="f618e-103">使用する場合、<xref:System.Windows.Controls.DataGrid>コントロール、行の詳細セクションを追加してデータの表示をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="f618e-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="f618e-104">行の詳細セクションを追加するには、必要に応じて表示されるか、折りたたまれたテンプレートの一部のデータをグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="f618e-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="f618e-105">行の詳細を追加するなど、<xref:System.Windows.Controls.DataGrid>内の各行のデータの概要のみを提示する、<xref:System.Windows.Controls.DataGrid>行を選択すると、他のデータ フィールドを表示しますが、します。</span><span class="sxs-lookup"><span data-stu-id="f618e-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="f618e-106">行の詳細」セクションのテンプレートを定義する、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f618e-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="f618e-107">次の図は、行の詳細セクションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f618e-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="f618e-108">![行の詳細を表示する DataGrid](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="f618e-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="f618e-109">行詳細テンプレートは、インライン XAML、またはリソースとして定義します。</span><span class="sxs-lookup"><span data-stu-id="f618e-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="f618e-110">どちらの方法は、次の手順で表示されます。</span><span class="sxs-lookup"><span data-stu-id="f618e-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="f618e-111">テンプレートを再作成せず、プロジェクト全体でリソースとして追加されるデータ テンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f618e-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="f618e-112">インライン XAML が定義されているコントロールからアクセス可能なだけ追加されるデータ テンプレート。</span><span class="sxs-lookup"><span data-stu-id="f618e-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="f618e-113">インライン XAML を使用して行の詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="f618e-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="f618e-114">作成、<xref:System.Windows.Controls.DataGrid>データ ソースからデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f618e-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="f618e-115"><xref:System.Windows.Controls.DataGrid> 要素に、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="f618e-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="f618e-116">作成、<xref:System.Windows.DataTemplate>行の詳細セクションの外観を定義します。</span><span class="sxs-lookup"><span data-stu-id="f618e-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="f618e-117">次の XAML に示す、<xref:System.Windows.Controls.DataGrid>および定義する方法、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>インラインです。</span><span class="sxs-lookup"><span data-stu-id="f618e-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="f618e-118"><xref:System.Windows.Controls.DataGrid>表示 3 つの値行ごとに 3 つ以上の値、行が選択されているときにします。</span><span class="sxs-lookup"><span data-stu-id="f618e-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="f618e-119">次のコードに表示されるデータを選択するために使用するクエリを示しています、<xref:System.Windows.Controls.DataGrid>します。</span><span class="sxs-lookup"><span data-stu-id="f618e-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f618e-120">この例では、クエリは、顧客情報を含むエンティティからデータを選択します。</span><span class="sxs-lookup"><span data-stu-id="f618e-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="f618e-121">リソースを使用して行の詳細を表示するには</span><span class="sxs-lookup"><span data-stu-id="f618e-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="f618e-122">作成、<xref:System.Windows.Controls.DataGrid>データ ソースからデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="f618e-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="f618e-123">追加、<xref:System.Windows.FrameworkElement.Resources%2A>要素をルート要素など、<xref:System.Windows.Window>コントロールまたは<xref:System.Windows.Controls.Page>制御、または追加を<xref:System.Windows.Application.Resources%2A>要素を<xref:System.Windows.Application>App.xaml (または Application.xaml) ファイル内のクラス。</span><span class="sxs-lookup"><span data-stu-id="f618e-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="f618e-124">リソースの要素で作成、<xref:System.Windows.DataTemplate>行の詳細セクションの外観を定義します。</span><span class="sxs-lookup"><span data-stu-id="f618e-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="f618e-125">次の XAML に示す、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>で定義されている、<xref:System.Windows.Application>クラス。</span><span class="sxs-lookup"><span data-stu-id="f618e-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="f618e-126"><xref:System.Windows.DataTemplate>、設定、 [X:key ディレクティブ](../../xaml-services/x-key-directive.md)データ テンプレートを一意に識別する値にします。</span><span class="sxs-lookup"><span data-stu-id="f618e-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="f618e-127"><xref:System.Windows.Controls.DataGrid>要素、設定、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>前の手順で定義されたリソースへのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f618e-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="f618e-128">静的リソースとしてリソースを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f618e-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="f618e-129">次の XAML に示す、<xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>プロパティが、前の例のリソースに設定します。</span><span class="sxs-lookup"><span data-stu-id="f618e-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="f618e-130">可視性を設定し、行の詳細を水平方向にスクロールできないようにするには</span><span class="sxs-lookup"><span data-stu-id="f618e-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="f618e-131">必要に応じて、設定、<xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A>プロパティを<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode>値。</span><span class="sxs-lookup"><span data-stu-id="f618e-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="f618e-132">値の設定既定では、<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>します。</span><span class="sxs-lookup"><span data-stu-id="f618e-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="f618e-133">設定することができます<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible>すべての行の詳細を表示または<xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed>すべての行の詳細を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="f618e-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="f618e-134">必要に応じて、設定、<xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A>プロパティを`true`行を防ぐための詳細セクションの水平方向にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="f618e-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
