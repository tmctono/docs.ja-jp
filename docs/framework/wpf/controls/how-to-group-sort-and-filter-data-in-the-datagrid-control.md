---
title: '方法: DataGrid コントロールでデータをグループ化、並べ替え、およびフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 622b64fd7738b02cd72131e7e9fe91c04314b1d0
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559475"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="fc540-102">方法: DataGrid コントロールでデータをグループ化、並べ替え、およびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fc540-102">How to: Group, sort, and filter data in the DataGrid control</span></span>

<span data-ttu-id="fc540-103">多くの場合、データをグループ化、並べ替え、およびフィルター処理することで、<xref:System.Windows.Controls.DataGrid> のデータをさまざまな方法で表示すると便利です。</span><span class="sxs-lookup"><span data-stu-id="fc540-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="fc540-104"><xref:System.Windows.Controls.DataGrid>内のデータをグループ化、並べ替え、およびフィルター処理するには、これらの関数をサポートする <xref:System.Windows.Data.CollectionView> にバインドします。</span><span class="sxs-lookup"><span data-stu-id="fc540-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="fc540-105">その後、基になるソースデータに影響を与えることなく、<xref:System.Windows.Data.CollectionView> のデータを操作できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="fc540-106">コレクションビューでの変更は、<xref:System.Windows.Controls.DataGrid> ユーザーインターフェイス (UI) に反映されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>

<span data-ttu-id="fc540-107"><xref:System.Windows.Data.CollectionView> クラスは、<xref:System.Collections.IEnumerable> インターフェイスを実装するデータソースに対してグループ化および並べ替え機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc540-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="fc540-108"><xref:System.Windows.Data.CollectionViewSource> クラスを使用すると、XAML から <xref:System.Windows.Data.CollectionView> のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>

<span data-ttu-id="fc540-109">この例では、`Task` オブジェクトのコレクションが <xref:System.Windows.Data.CollectionViewSource>にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="fc540-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="fc540-110"><xref:System.Windows.Data.CollectionViewSource> は、<xref:System.Windows.Controls.DataGrid>の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> として使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="fc540-111">グループ化、並べ替え、およびフィルター処理は <xref:System.Windows.Data.CollectionViewSource> で実行され、<xref:System.Windows.Controls.DataGrid> UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="fc540-112">![DataGrid でのグループ化されたデータ](././media/wpf-datagridgroups.png "WPF_DataGridGroups")DataGrid でのグループ化されたデータ</span><span class="sxs-lookup"><span data-stu-id="fc540-112">![Grouped data in a DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Grouped data in a DataGrid</span></span>

## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="fc540-113">ItemsSource としての CollectionViewSource の使用</span><span class="sxs-lookup"><span data-stu-id="fc540-113">Using a CollectionViewSource as an ItemsSource</span></span>

<span data-ttu-id="fc540-114"><xref:System.Windows.Controls.DataGrid> コントロールのデータをグループ化、並べ替え、およびフィルター処理するには、これらの関数をサポートする <xref:System.Windows.Data.CollectionView> に <xref:System.Windows.Controls.DataGrid> をバインドします。</span><span class="sxs-lookup"><span data-stu-id="fc540-114">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="fc540-115">この例では、<xref:System.Windows.Controls.DataGrid> は `Task` オブジェクトの <xref:System.Collections.Generic.List%601> に対してこれらの関数を提供する <xref:System.Windows.Data.CollectionViewSource> にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="fc540-115">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="fc540-116">DataGrid を CollectionViewSource にバインドするには</span><span class="sxs-lookup"><span data-stu-id="fc540-116">To bind a DataGrid to a CollectionViewSource</span></span>

1. <span data-ttu-id="fc540-117"><xref:System.Collections.IEnumerable> インターフェイスを実装するデータコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc540-117">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>

    <span data-ttu-id="fc540-118"><xref:System.Collections.Generic.List%601> を使用してコレクションを作成する場合は、<xref:System.Collections.Generic.List%601>のインスタンスをインスタンス化するのではなく、<xref:System.Collections.Generic.List%601> から継承する新しいクラスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc540-118">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="fc540-119">これにより、XAML でコレクションにデータをバインドできるようになります。</span><span class="sxs-lookup"><span data-stu-id="fc540-119">This enables you to data bind to the collection in XAML.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fc540-120">コレクション内のオブジェクトは、プロパティの変更や編集に正しく応答するため <xref:System.Windows.Controls.DataGrid> に、<xref:System.ComponentModel.INotifyPropertyChanged> 変更されたインターフェイスと <xref:System.ComponentModel.IEditableObject> インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc540-120">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="fc540-121">詳細については、「[プロパティの変更通知を実装する](../data/how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc540-121">For more information, see [Implement Property Change Notification](../data/how-to-implement-property-change-notification.md).</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. <span data-ttu-id="fc540-122">XAML で、コレクションクラスのインスタンスを作成し、 [X:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)を設定します。</span><span class="sxs-lookup"><span data-stu-id="fc540-122">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md).</span></span>

3. <span data-ttu-id="fc540-123">XAML で、<xref:System.Windows.Data.CollectionViewSource> クラスのインスタンスを作成し、 [X:Key ディレクティブ](../../../desktop-wpf/xaml-services/xkey-directive.md)を設定し、コレクションクラスのインスタンスを <xref:System.Windows.Data.CollectionViewSource.Source%2A>として設定します。</span><span class="sxs-lookup"><span data-stu-id="fc540-123">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. <span data-ttu-id="fc540-124"><xref:System.Windows.Controls.DataGrid> クラスのインスタンスを作成し、<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> プロパティを <xref:System.Windows.Data.CollectionViewSource>に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc540-124">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. <span data-ttu-id="fc540-125">コードから <xref:System.Windows.Data.CollectionViewSource> にアクセスするには、<xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> メソッドを使用して <xref:System.Windows.Data.CollectionViewSource>への参照を取得します。</span><span class="sxs-lookup"><span data-stu-id="fc540-125">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="fc540-126">DataGrid でのアイテムのグループ化</span><span class="sxs-lookup"><span data-stu-id="fc540-126">Grouping items in a DataGrid</span></span>

<span data-ttu-id="fc540-127"><xref:System.Windows.Controls.DataGrid>で項目をグループ化する方法を指定するには、<xref:System.Windows.Data.PropertyGroupDescription> の種類を使用して、ソースビュー内の項目をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="fc540-127">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>

### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="fc540-128">XAML を使用して DataGrid の項目をグループ化するには</span><span class="sxs-lookup"><span data-stu-id="fc540-128">To group items in a DataGrid using XAML</span></span>

1. <span data-ttu-id="fc540-129">グループ化するプロパティを指定する <xref:System.Windows.Data.PropertyGroupDescription> を作成します。</span><span class="sxs-lookup"><span data-stu-id="fc540-129">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="fc540-130">プロパティは、XAML またはコードで指定できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-130">You can specify the property in XAML or in code.</span></span>

   1. <span data-ttu-id="fc540-131">XAML で、<xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> をグループ化するプロパティの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc540-131">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>

   2. <span data-ttu-id="fc540-132">コードで、group by にプロパティの名前をコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="fc540-132">In code, pass the name of the property to group by to the constructor.</span></span>

2. <span data-ttu-id="fc540-133"><xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> コレクションに <xref:System.Windows.Data.PropertyGroupDescription> を追加します。</span><span class="sxs-lookup"><span data-stu-id="fc540-133">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="fc540-134"><xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> コレクションに <xref:System.Windows.Data.PropertyGroupDescription> のインスタンスを追加して、グループ化のレベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc540-134">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. <span data-ttu-id="fc540-135">グループを削除するには、<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> コレクションから <xref:System.Windows.Data.PropertyGroupDescription> を削除します。</span><span class="sxs-lookup"><span data-stu-id="fc540-135">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

5. <span data-ttu-id="fc540-136">すべてのグループを削除するには、<xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> コレクションの <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc540-136">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

<span data-ttu-id="fc540-137">項目が <xref:System.Windows.Controls.DataGrid>にグループ化されている場合は、各グループの外観を指定する <xref:System.Windows.Controls.GroupStyle> を定義できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-137">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="fc540-138"><xref:System.Windows.Controls.GroupStyle> を適用するには、DataGrid の <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="fc540-138">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="fc540-139">複数のレベルのグループ化を使用している場合は、各グループレベルに異なるスタイルを適用できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-139">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="fc540-140">スタイルは、定義されている順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-140">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="fc540-141">たとえば、2つのスタイルを定義した場合、最初のスタイルがトップレベルの行グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-141">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="fc540-142">2番目のスタイルは、2番目のレベルのすべての行グループに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-142">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="fc540-143"><xref:System.Windows.Controls.GroupStyle> の <xref:System.Windows.FrameworkElement.DataContext%2A> は、グループが表す <xref:System.Windows.Data.CollectionViewGroup> です。</span><span class="sxs-lookup"><span data-stu-id="fc540-143">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>

### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="fc540-144">行グループヘッダーの外観を変更するには</span><span class="sxs-lookup"><span data-stu-id="fc540-144">To change the appearance of row group headers</span></span>

1. <span data-ttu-id="fc540-145">行グループの外観を定義する <xref:System.Windows.Controls.GroupStyle> を作成します。</span><span class="sxs-lookup"><span data-stu-id="fc540-145">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>

2. <span data-ttu-id="fc540-146">`<DataGrid.GroupStyle>` タグ内に <xref:System.Windows.Controls.GroupStyle> を配置します。</span><span class="sxs-lookup"><span data-stu-id="fc540-146">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="fc540-147">DataGrid でのアイテムの並べ替え</span><span class="sxs-lookup"><span data-stu-id="fc540-147">Sorting items in a DataGrid</span></span>

<span data-ttu-id="fc540-148"><xref:System.Windows.Controls.DataGrid>での項目の並べ替え方法を指定するには、<xref:System.ComponentModel.SortDescription> の種類を使用して、ソースビュー内の項目を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="fc540-148">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>

### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="fc540-149">DataGrid 内の項目を並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="fc540-149">To sort items in a DataGrid</span></span>

1. <span data-ttu-id="fc540-150">並べ替えの基準となるプロパティを指定する <xref:System.ComponentModel.SortDescription> を作成します。</span><span class="sxs-lookup"><span data-stu-id="fc540-150">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="fc540-151">プロパティは、XAML またはコードで指定できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-151">You can specify the property in XAML or in code.</span></span>

    1. <span data-ttu-id="fc540-152">XAML で、<xref:System.ComponentModel.SortDescription.PropertyName%2A> を、並べ替えの基準となるプロパティの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="fc540-152">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>

    2. <span data-ttu-id="fc540-153">コードで、プロパティの名前を渡して、並べ替え、および <xref:System.ComponentModel.ListSortDirection> をコンストラクターに渡します。</span><span class="sxs-lookup"><span data-stu-id="fc540-153">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>

2. <span data-ttu-id="fc540-154"><xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> コレクションに <xref:System.ComponentModel.SortDescription> を追加します。</span><span class="sxs-lookup"><span data-stu-id="fc540-154">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="fc540-155">追加のプロパティで並べ替えるために、<xref:System.ComponentModel.SortDescription> のインスタンスを <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="fc540-155">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="fc540-156">DataGrid での項目のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="fc540-156">Filtering items in a DataGrid</span></span>

<span data-ttu-id="fc540-157"><xref:System.Windows.Data.CollectionViewSource>を使用して <xref:System.Windows.Controls.DataGrid> 内の項目をフィルター処理するには、<xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> イベントのハンドラーにフィルター処理ロジックを指定します。</span><span class="sxs-lookup"><span data-stu-id="fc540-157">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="fc540-158">DataGrid の項目をフィルター処理するには</span><span class="sxs-lookup"><span data-stu-id="fc540-158">To filter items in a DataGrid</span></span>

1. <span data-ttu-id="fc540-159"><xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> イベントのハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fc540-159">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>

2. <span data-ttu-id="fc540-160"><xref:System.Windows.Data.CollectionViewSource.Filter> イベントハンドラーで、フィルター処理ロジックを定義します。</span><span class="sxs-lookup"><span data-stu-id="fc540-160">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>

    <span data-ttu-id="fc540-161">フィルターは、ビューが更新されるたびに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-161">The filter will be applied every time the view is refreshed.</span></span>

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

<span data-ttu-id="fc540-162">または、フィルター処理ロジックを提供するメソッドを作成し、フィルターを適用するように <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> プロパティを設定することによって、<xref:System.Windows.Controls.DataGrid> 内の項目をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="fc540-162">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="fc540-163">このメソッドの例については、「[ビュー内のデータをフィルター処理](../data/how-to-filter-data-in-a-view.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc540-163">To see an example of this method, see [Filter Data in a View](../data/how-to-filter-data-in-a-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="fc540-164">使用例</span><span class="sxs-lookup"><span data-stu-id="fc540-164">Example</span></span>

<span data-ttu-id="fc540-165">次の例では、<xref:System.Windows.Data.CollectionViewSource> 内の `Task` データをグループ化、並べ替え、およびフィルター処理し、<xref:System.Windows.Controls.DataGrid>でグループ化、並べ替え、およびフィルター選択された `Task` データを表示します。</span><span class="sxs-lookup"><span data-stu-id="fc540-165">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="fc540-166"><xref:System.Windows.Data.CollectionViewSource> は、<xref:System.Windows.Controls.DataGrid>の <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> として使用されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-166">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="fc540-167">グループ化、並べ替え、およびフィルター処理は <xref:System.Windows.Data.CollectionViewSource> で実行され、<xref:System.Windows.Controls.DataGrid> UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc540-167">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>

<span data-ttu-id="fc540-168">この例をテストするには、プロジェクト名と一致するように DGGroupSortFilterExample 名を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc540-168">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="fc540-169">Visual Basic を使用する場合は、<xref:System.Windows.Window> のクラス名を次のように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc540-169">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a><span data-ttu-id="fc540-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc540-170">See also</span></span>

- [<span data-ttu-id="fc540-171">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="fc540-171">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="fc540-172">ObservableCollection を作成およびバインドする</span><span class="sxs-lookup"><span data-stu-id="fc540-172">Create and Bind to an ObservableCollection</span></span>](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [<span data-ttu-id="fc540-173">ビュー内のデータをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="fc540-173">Filter Data in a View</span></span>](../data/how-to-filter-data-in-a-view.md)
- [<span data-ttu-id="fc540-174">ビュー内のデータの並べ替え</span><span class="sxs-lookup"><span data-stu-id="fc540-174">Sort Data in a View</span></span>](../data/how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="fc540-175">XAML でビューを使用してデータの並べ替えおよびグループ化を行う</span><span class="sxs-lookup"><span data-stu-id="fc540-175">Sort and Group Data Using a View in XAML</span></span>](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
