---
title: DataView オブジェクトの作成 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: afa760d890cf2857737372af5a9d3ba7c2749e6c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949419"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a><span data-ttu-id="6fdfe-102">DataView オブジェクトの作成 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6fdfe-102">Creating a DataView Object (LINQ to DataSet)</span></span>
<span data-ttu-id="6fdfe-103">LINQ to DataSet コンテキストでを作成するに<xref:System.Data.DataView>は、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-103">There are two ways to create a <xref:System.Data.DataView> in the LINQ to DataSet context.</span></span> <span data-ttu-id="6fdfe-104">を使用して<xref:System.Data.DataView> LINQ to DataSet クエリ<xref:System.Data.DataTable>からを作成することも、型指定されたまたは型指定<xref:System.Data.DataTable>されていないから作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-104">You can create a <xref:System.Data.DataView> from a LINQ to DataSet query over a <xref:System.Data.DataTable>, or you can create it from a typed or un-typed <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="6fdfe-105">どちらの場合も、 <xref:System.Data.DataView> <xref:System.Data.DataTableExtensions.AsDataView%2A>拡張メソッドのいずれかを使用してを作成します。<xref:System.Data.DataView>は、LINQ to DataSet コンテキストで直接構築することはできません。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-105">In both cases, you create the <xref:System.Data.DataView> by using one of the <xref:System.Data.DataTableExtensions.AsDataView%2A> extension methods; <xref:System.Data.DataView> is not directly constructible in the LINQ to DataSet context.</span></span>  
  
 <span data-ttu-id="6fdfe-106"><xref:System.Data.DataView> を作成した後に、Windows フォーム アプリケーションまたは ASP.NET アプリケーションの UI コントロールにバインドしたり、フィルターおよび並べ替えの設定を変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-106">After the <xref:System.Data.DataView> has been created, you can bind it to a UI control in a Windows forms application or an ASP.NET application, or change the filtering and sorting settings.</span></span>  
  
 <span data-ttu-id="6fdfe-107"><xref:System.Data.DataView> は、インデックスを構築します。これにより、フィルター処理や並べ替えなど、インデックスを使用できる操作のパフォーマンスが大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-107"><xref:System.Data.DataView> constructs an index, which significantly increases the performance of operations that can use the index, such as filtering and sorting.</span></span> <span data-ttu-id="6fdfe-108"><xref:System.Data.DataView> のインデックスは、<xref:System.Data.DataView> の作成時に構築されるほか、並べ替えまたはフィルター処理の情報が変更されたときにも構築されます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-108">The index for a <xref:System.Data.DataView> is built both when the <xref:System.Data.DataView> is created and when any of the sorting or filtering information is modified.</span></span> <span data-ttu-id="6fdfe-109"><xref:System.Data.DataView> を作成した後で、並べ替えまたはフィルター処理の情報を設定した場合、インデックスが最低でも 2 回 (<xref:System.Data.DataView> の作成時と、並べ替えまたはフィルターのプロパティの変更時) 構築されることになります。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-109">Creating a <xref:System.Data.DataView> and then setting the sorting or filtering information later causes the index to be built at least twice: once when the <xref:System.Data.DataView> is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="6fdfe-110">を使用した<xref:System.Data.DataView>フィルター処理と並べ替えの詳細については、「 [dataview によるフィルター処理](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)」と「 [dataview による並べ替え](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-110">For more information about filtering and sorting with <xref:System.Data.DataView>, see [Filtering with DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) and [Sorting with DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).</span></span>  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a><span data-ttu-id="6fdfe-111">LINQ to DataSet クエリの結果からの DataView の作成</span><span class="sxs-lookup"><span data-stu-id="6fdfe-111">Creating DataView from a LINQ to DataSet Query</span></span>  
 <span data-ttu-id="6fdfe-112">オブジェクトは、LINQ to DataSet クエリの結果から作成できます。この場合、結果はオブジェクトの<xref:System.Data.DataRow>射影になります。 <xref:System.Data.DataView></span><span class="sxs-lookup"><span data-stu-id="6fdfe-112">A <xref:System.Data.DataView> object can be created from the results of a LINQ to DataSet query, where the results are a projection of <xref:System.Data.DataRow> objects.</span></span> <span data-ttu-id="6fdfe-113">新しく作成される <xref:System.Data.DataView> は、その基となるクエリからのフィルター処理および並べ替え情報を継承します。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-113">The newly created <xref:System.Data.DataView> inherits the filtering and sorting information from the query it is created from.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fdfe-114">ほとんどの場合、フィルターに使用する式は、副作用のない確定的な式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-114">In most cases, the expressions used for filtering and sorting should not have side effects and must be deterministic.</span></span> <span data-ttu-id="6fdfe-115">また、並べ替えおよびフィルター処理は任意の回数実行されるため、特定の実行回数に依存するロジックが式に含まれないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-115">Also, the expressions should not contain any logic that depend on a set number of executions, as the sorting and filtering operations may be executed any number of times.</span></span>  
  
 <span data-ttu-id="6fdfe-116">匿名型を返すクエリまたは結合操作を実行するクエリからの <xref:System.Data.DataView> の作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-116">Creating a <xref:System.Data.DataView> from a query that returns anonymous types or queries that perform join operations is not supported.</span></span>  
  
 <span data-ttu-id="6fdfe-117"><xref:System.Data.DataView> の作成に使用されるクエリでは、次のクエリ演算子のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-117">Only the following query operators are supported in a query used to create <xref:System.Data.DataView>:</span></span>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
- <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 <span data-ttu-id="6fdfe-118"><xref:System.Data.DataView> LINQtoDataSet<xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>クエリからを作成する場合、メソッドは、クエリで呼び出される最後のメソッドである必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-118">Note that when a <xref:System.Data.DataView> is created from a LINQ to DataSet query the <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> method must be the final method called in the query.</span></span> <span data-ttu-id="6fdfe-119">これを次の例に示します。この例<xref:System.Data.DataView>では、合計期限によって並べ替えられたオンライン注文のを作成しています。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-119">This is shown in the following example, which creates a <xref:System.Data.DataView> of online orders sorted by total due:</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 <span data-ttu-id="6fdfe-120">また、文字列ベース<xref:System.Data.DataView.RowFilter%2A>のプロパティと<xref:System.Data.DataView.Sort%2A>プロパティを使用して、クエリから<xref:System.Data.DataView>作成されたをフィルター処理したり並べ替えたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-120">You can also use the string-based <xref:System.Data.DataView.RowFilter%2A> and <xref:System.Data.DataView.Sort%2A> properties to filter and sort a <xref:System.Data.DataView> after it has been created from a query.</span></span> <span data-ttu-id="6fdfe-121">この操作を行うと、クエリから継承された並べ替えおよびフィルター情報がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-121">Note that this will clear the sorting and filtering information inherited from the query.</span></span> <span data-ttu-id="6fdfe-122">次の例では<xref:System.Data.DataView> 、' ' で始まる姓によってフィルター処理する LINQ to DataSet クエリからを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-122">The following example creates a <xref:System.Data.DataView> from a LINQ to DataSet query that filters by last names that start with 'S'.</span></span> <span data-ttu-id="6fdfe-123">文字列ベースの <xref:System.Data.DataView.Sort%2A> プロパティは、姓を昇順に並べ替え、名を降順に並べ替えるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-123">The string-based <xref:System.Data.DataView.Sort%2A> property is set to sort on last names in ascending order and then first names in descending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a><span data-ttu-id="6fdfe-124">DataTable からの DataView の作成</span><span class="sxs-lookup"><span data-stu-id="6fdfe-124">Creating a DataView from a DataTable</span></span>  
 <span data-ttu-id="6fdfe-125">LINQ to DataSet クエリから作成されるだけでなく、 <xref:System.Data.DataView> <xref:System.Data.DataTableExtensions.AsDataView%2A>メソッドを使用し<xref:System.Data.DataTable>てからオブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-125">In addition to being created from a LINQ to DataSet query, a <xref:System.Data.DataView> object can be created from a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTableExtensions.AsDataView%2A> method.</span></span>  
  
 <span data-ttu-id="6fdfe-126">次の例では、<xref:System.Data.DataView> を SalesOrderDetail テーブルから作成した後、<xref:System.Windows.Forms.BindingSource> オブジェクトのデータ ソースとして設定します。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-126">The following example creates a <xref:System.Data.DataView> from the SalesOrderDetail table and sets it as the data source of a <xref:System.Windows.Forms.BindingSource> object.</span></span> <span data-ttu-id="6fdfe-127">このオブジェクトは、<xref:System.Windows.Forms.DataGridView> コントロールのプロキシとして動作します。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-127">This object acts as a proxy for a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 <span data-ttu-id="6fdfe-128"><xref:System.Data.DataView> から <xref:System.Data.DataTable> を作成した後、フィルターおよび並べ替えを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-128">Filtering and sorting can be set on the <xref:System.Data.DataView> after it has been created from a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="6fdfe-129">次の例では、<xref:System.Data.DataView> を Contact テーブルから作成した後、姓を昇順に並べ替え、名を降順に並べ替えるための <xref:System.Data.DataView.Sort%2A> プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-129">The following example creates a <xref:System.Data.DataView> from the Contact table and sets the <xref:System.Data.DataView.Sort%2A> property to sort on last names in ascending order and then first names in descending order:</span></span>  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 <span data-ttu-id="6fdfe-130">ただし、<xref:System.Data.DataView.RowFilter%2A> をクエリから作成した後に <xref:System.Data.DataView.Sort%2A> プロパティまたは <xref:System.Data.DataView> プロパティを設定する操作を行うと、パフォーマンスが低下します。なぜなら、<xref:System.Data.DataView> により、フィルター処理および並べ替え処理をサポートするためのインデックスが構築されるからです。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-130">However, there is a performance loss that comes with setting the <xref:System.Data.DataView.RowFilter%2A> or <xref:System.Data.DataView.Sort%2A> property after the <xref:System.Data.DataView> has been created from a query, because <xref:System.Data.DataView> constructs an index to support filtering and sorting operations.</span></span> <span data-ttu-id="6fdfe-131"><xref:System.Data.DataView.RowFilter%2A> プロパティまたは <xref:System.Data.DataView.Sort%2A> プロパティを設定すると、データのインデックスが再構築され、アプリケーションのオーバーヘッドが増加してパフォーマンスの低下を招きます。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-131">Setting the <xref:System.Data.DataView.RowFilter%2A> or <xref:System.Data.DataView.Sort%2A> property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="6fdfe-132">可能な場合は、<xref:System.Data.DataView> を最初に作成するときにフィルター処理および並べ替え情報を指定して、後で情報を変更するのを避けてください。</span><span class="sxs-lookup"><span data-stu-id="6fdfe-132">When possible, it is better to specify the filtering and sorting information when you first create the <xref:System.Data.DataView> and avoid modifying it afterwards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fdfe-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fdfe-133">See also</span></span>

- [<span data-ttu-id="6fdfe-134">データ バインディングと LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="6fdfe-134">Data Binding and LINQ to DataSet</span></span>](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
- [<span data-ttu-id="6fdfe-135">DataView によるフィルター処理</span><span class="sxs-lookup"><span data-stu-id="6fdfe-135">Filtering with DataView</span></span>](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)
- [<span data-ttu-id="6fdfe-136">DataView による並べ替え</span><span class="sxs-lookup"><span data-stu-id="6fdfe-136">Sorting with DataView</span></span>](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)
