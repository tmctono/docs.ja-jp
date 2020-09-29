---
title: クエリによる DataTable の作成 (LINQ to DataSet)
description: CopyToDataTable メソッドを使用してクエリの結果を取得し、そのデータを DataTable にコピーして、データ バインディングに使用する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b97afeb-03f8-41e2-8eb3-58aff65f7d18
ms.openlocfilehash: 064688f173e375481373e9a33d66c64666e1583f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148362"
---
# <a name="creating-a-datatable-from-a-query-linq-to-dataset"></a><span data-ttu-id="6ffb3-103">クエリによる DataTable の作成 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6ffb3-103">Creating a DataTable From a Query (LINQ to DataSet)</span></span>

<span data-ttu-id="6ffb3-104"><xref:System.Data.DataTable> オブジェクトの一般的な利用法の 1 つが、データ バインディングです。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-104">Data binding is a common use of <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="6ffb3-105"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドは、クエリの結果を受け取り、そのデータを <xref:System.Data.DataTable> にコピーします。これをデータ バインディングに利用できます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-105">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method takes the results of a query and copies the data into a <xref:System.Data.DataTable>, which can then be used for data binding.</span></span> <span data-ttu-id="6ffb3-106">このデータ操作が実行されると、新しい <xref:System.Data.DataTable> が、基となった <xref:System.Data.DataTable> にマージ バックされます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-106">When the data operations have been performed, the new <xref:System.Data.DataTable> is merged back into the source <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="6ffb3-107"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドでは、次の処理を実行することでクエリの結果から <xref:System.Data.DataTable> を作成します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-107">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method uses the following process to create a <xref:System.Data.DataTable> from a query:</span></span>  
  
1. <span data-ttu-id="6ffb3-108"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドにより、ソース テーブル (<xref:System.Data.DataTable> インターフェイスを実装する <xref:System.Data.DataTable> オブジェクト) から <xref:System.Linq.IQueryable%601> を複製します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-108">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method clones a <xref:System.Data.DataTable> from the source table (a <xref:System.Data.DataTable> object that implements the <xref:System.Linq.IQueryable%601> interface).</span></span> <span data-ttu-id="6ffb3-109">通常、<xref:System.Collections.IEnumerable> ソースは LINQ to DataSet 式またはメソッド クエリから生成されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-109">The <xref:System.Collections.IEnumerable> source has generally originated from a LINQ to DataSet expression or method query.</span></span>  
  
2. <span data-ttu-id="6ffb3-110">複製の <xref:System.Data.DataTable> のスキーマは、ソース テーブルで最初に列挙されている <xref:System.Data.DataRow> オブジェクトの列から作成されます。複製したテーブルの名前は、ソース テーブルの名前に "query" という単語を付加した名前になります。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-110">The schema of the cloned <xref:System.Data.DataTable> is built from the columns of the first enumerated <xref:System.Data.DataRow> object in the source table and the name of the cloned table is the name of the source table with the word "query" appended to it.</span></span>  
  
3. <span data-ttu-id="6ffb3-111">ソース テーブルの各行について、行の内容が新しい <xref:System.Data.DataRow> オブジェクトにコピーされた後、それが複製のテーブルに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-111">For each row in the source table, the content of the row is copied into a new <xref:System.Data.DataRow> object, which is then inserted into the cloned table.</span></span> <span data-ttu-id="6ffb3-112">このコピー操作の間、<xref:System.Data.DataRow.RowState%2A> プロパティと <xref:System.Data.DataRow.RowError%2A> プロパティは保持されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-112">The <xref:System.Data.DataRow.RowState%2A> and <xref:System.Data.DataRow.RowError%2A> properties are preserved across the copy operation.</span></span> <span data-ttu-id="6ffb3-113">基になる <xref:System.ArgumentException> オブジェクトが別々のテーブルに由来している場合、<xref:System.Data.DataRow> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-113">An <xref:System.ArgumentException> is thrown if the <xref:System.Data.DataRow> objects in the source are from different tables.</span></span>  
  
4. <span data-ttu-id="6ffb3-114">クエリ実行可能な入力テーブルの <xref:System.Data.DataTable> オブジェクトがすべてコピーされた後、複製の <xref:System.Data.DataRow> が返されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-114">The cloned <xref:System.Data.DataTable> is returned after all <xref:System.Data.DataRow> objects in the input queryable table have been copied.</span></span> <span data-ttu-id="6ffb3-115">基となるシーケンスに <xref:System.Data.DataRow> オブジェクトが含まれていない場合、このメソッドは空の <xref:System.Data.DataTable> を返します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-115">If the source sequence does not contain any <xref:System.Data.DataRow> objects, the method returns an empty <xref:System.Data.DataTable>.</span></span>  
  
<span data-ttu-id="6ffb3-116"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドを呼び出すと、ソース テーブルにバインドされているクエリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-116">Calling the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method causes the query bound to the source table to execute.</span></span>  
  
 <span data-ttu-id="6ffb3-117"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドにより、ソース テーブルの行に Null 参照または Null 許容の値型が検出された場合、その値は <xref:System.DBNull.Value> に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-117">When the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method encounters either a null reference or nullable value type in a row in the source table, it replaces the value with <xref:System.DBNull.Value>.</span></span> <span data-ttu-id="6ffb3-118">このようにして、返される <xref:System.Data.DataTable> の Null 値が適切に処理されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-118">This way, null values are handled correctly in the returned <xref:System.Data.DataTable>.</span></span>  
  
 <span data-ttu-id="6ffb3-119">メモ:<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドは、複数の <xref:System.Data.DataTable> オブジェクトまたは <xref:System.Data.DataSet> オブジェクトから行を返せるクエリを入力として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-119">Note: The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method accepts as input a query that can return rows from multiple <xref:System.Data.DataTable> or <xref:System.Data.DataSet> objects.</span></span> <span data-ttu-id="6ffb3-120"><xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドは、ソースの <xref:System.Data.DataTable> または <xref:System.Data.DataSet> オブジェクトから、返された <xref:System.Data.DataTable> にデータをコピーしますが、プロパティはコピーしません。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-120">The <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method will copy the data but not the properties from the source <xref:System.Data.DataTable> or <xref:System.Data.DataSet> objects to the returned <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="6ffb3-121"><xref:System.Data.DataTable> や <xref:System.Data.DataTable.Locale%2A> などの返された <xref:System.Data.DataTable.TableName%2A> に、明示的にプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-121">You will need to explicitly set the properties on the returned <xref:System.Data.DataTable>, such as <xref:System.Data.DataTable.Locale%2A> and <xref:System.Data.DataTable.TableName%2A>.</span></span>  
  
 <span data-ttu-id="6ffb3-122">次の例では、SalesOrderHeader テーブルに対して 2001 年 8 月 8 日以降の注文をクエリし、<xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドを使用して、このクエリから <xref:System.Data.DataTable> を作成します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-122">The following example queries the SalesOrderHeader table for orders after August 8, 2001 and uses the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method to create a <xref:System.Data.DataTable> from that query.</span></span> <span data-ttu-id="6ffb3-123">次に、<xref:System.Data.DataTable> が <xref:System.Windows.Forms.BindingSource> にバインドされます。これは <xref:System.Windows.Forms.DataGridView> のプロキシとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-123">The <xref:System.Data.DataTable> is then bound to a <xref:System.Windows.Forms.BindingSource>, which acts as proxy for a <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#copytodatatable1)]
 [!code-vb[DP LINQ to DataSet Examples#CopyToDataTable1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#copytodatatable1)]  
  
## <a name="creating-a-custom-copytodatatablet-method"></a><span data-ttu-id="6ffb3-124">カスタム CopyToDataTable\<T> メソッドの作成</span><span class="sxs-lookup"><span data-stu-id="6ffb3-124">Creating a Custom CopyToDataTable\<T> Method</span></span>  

 <span data-ttu-id="6ffb3-125">既存の <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> メソッドは、ジェネリック パラメーター <xref:System.Collections.Generic.IEnumerable%601> が `T` 型である <xref:System.Data.DataRow> ソースに対してのみ作用します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-125">The existing <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> methods only operate on an <xref:System.Collections.Generic.IEnumerable%601> source where the generic parameter `T` is of type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="6ffb3-126">有用ではありますが、一連のスカラー型、匿名型を返すクエリ、またはテーブルの結合を実行するクエリからは、テーブルを作成できません。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-126">Although this is useful, it does not allow tables to be created from a sequence of scalar types, from queries that return anonymous types, or from queries that perform table joins.</span></span> <span data-ttu-id="6ffb3-127">一連のスカラー型または匿名型からテーブルを読み込む 2 つのカスタム `CopyToDataTable` メソッドの実装例については、「[方法: ジェネリック型 T が DataRow](implement-copytodatatable-where-type-not-a-datarow.md) ではない CopyToDataTable\<T> を実装する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-127">For an example of how to implement two custom `CopyToDataTable` methods that load a table from a sequence of scalar or anonymous types, see [How to: Implement CopyToDataTable\<T> Where the Generic Type T Is Not a DataRow](implement-copytodatatable-where-type-not-a-datarow.md)s.</span></span>  
  
 <span data-ttu-id="6ffb3-128">このセクションの例には、次のカスタム型が使用されています。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-128">The examples in this section use the following custom types:</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#itemclass)]
 [!code-vb[DP Custom CopyToDataTable Examples#ItemClass](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#itemclass)]  
  
### <a name="example"></a><span data-ttu-id="6ffb3-129">例</span><span class="sxs-lookup"><span data-stu-id="6ffb3-129">Example</span></span>  

 <span data-ttu-id="6ffb3-130">この例では、`SalesOrderHeader` テーブルと `SalesOrderDetail` テーブルを結合し、8 月以降のオンラインでの注文を取得して、クエリからテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-130">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August and creates a table from the query.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#join)]
 [!code-vb[DP Custom CopyToDataTable Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#join)]  
  
### <a name="example"></a><span data-ttu-id="6ffb3-131">例</span><span class="sxs-lookup"><span data-stu-id="6ffb3-131">Example</span></span>  

 <span data-ttu-id="6ffb3-132">次の例では、価格が $9.99 を超える一連の商品を照会し、そのクエリの結果からテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-132">The following example queries a collection for items of price greater than $9.99 and creates a table from the query results.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintotable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintotable)]  
  
### <a name="example"></a><span data-ttu-id="6ffb3-133">例</span><span class="sxs-lookup"><span data-stu-id="6ffb3-133">Example</span></span>  

 <span data-ttu-id="6ffb3-134">次の例では、価格が $9.99 を超える一連の商品を照会し、その結果を射影します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-134">The following example queries a collection for items of price greater than 9.99 and projects the results.</span></span> <span data-ttu-id="6ffb3-135">返された一連の匿名型は、既存のテーブルに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-135">The returned sequence of anonymous types is loaded into an existing table.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsintoexistingtable)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsIntoExistingTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsintoexistingtable)]  
  
### <a name="example"></a><span data-ttu-id="6ffb3-136">例</span><span class="sxs-lookup"><span data-stu-id="6ffb3-136">Example</span></span>  

 <span data-ttu-id="6ffb3-137">次の例では、価格が $9.99 を超える一連の商品を照会し、その結果を射影します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-137">The following example queries a collection for items of price greater than $9.99 and projects the results.</span></span> <span data-ttu-id="6ffb3-138">返された一連の匿名型は、既存のテーブルに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-138">The returned sequence of anonymous types is loaded into an existing table.</span></span> <span data-ttu-id="6ffb3-139">`Book` 型と `Movies` 型は `Item` 型から派生するため、テーブル スキーマは自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-139">The table schema is automatically expanded because the `Book` and `Movies` types are derived from the `Item` type.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loaditemsexpandschema)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadItemsExpandSchema](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loaditemsexpandschema)]  
  
### <a name="example"></a><span data-ttu-id="6ffb3-140">例</span><span class="sxs-lookup"><span data-stu-id="6ffb3-140">Example</span></span>  

 <span data-ttu-id="6ffb3-141">次の例では、価格が $9.99 を超える一連の商品を照会し、新しいテーブルに読み込まれる一連の <xref:System.Double> を返します。</span><span class="sxs-lookup"><span data-stu-id="6ffb3-141">The following example queries a collection for items of price greater than $9.99 and returns a sequence of <xref:System.Double>, which is loaded into a new table.</span></span>  
  
 [!code-csharp[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/CS/Program.cs#loadscalarsequence)]
 [!code-vb[DP Custom CopyToDataTable Examples#LoadScalarSequence](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP Custom CopyToDataTable Examples/VB/Module1.vb#loadscalarsequence)]  
  
## <a name="see-also"></a><span data-ttu-id="6ffb3-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ffb3-142">See also</span></span>

- [<span data-ttu-id="6ffb3-143">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6ffb3-143">Programming Guide</span></span>](programming-guide-linq-to-dataset.md)
- [<span data-ttu-id="6ffb3-144">ジェネリック メソッド Field および SetField</span><span class="sxs-lookup"><span data-stu-id="6ffb3-144">Generic Field and SetField Methods</span></span>](generic-field-and-setfield-methods-linq-to-dataset.md)
- [<span data-ttu-id="6ffb3-145">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="6ffb3-145">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
