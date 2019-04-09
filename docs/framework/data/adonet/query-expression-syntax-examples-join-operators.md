---
title: クエリ式の構文例:結合演算子 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: c0bc66bfe78a52fe092890c070c339df1a89199d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088809"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a><span data-ttu-id="f84a5-102">クエリ式の構文例:結合演算子 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="f84a5-102">Query Expression Syntax Examples: Join Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="f84a5-103">結合は、リレーショナル データベース テーブルのように互いにナビゲート可能なリレーションシップを持たないデータ ソースをターゲットとするクエリにおいて重要な操作です。</span><span class="sxs-lookup"><span data-stu-id="f84a5-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="f84a5-104">2 つのデータ ソースを結合する操作とは、あるデータ ソース内のオブジェクトを、他方のデータ ソース内で共通の属性を持つオブジェクトと関連付けることです。</span><span class="sxs-lookup"><span data-stu-id="f84a5-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="f84a5-105">詳細については、次を参照してください。[標準クエリ演算子の概要 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)または[標準クエリ演算子の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="f84a5-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="f84a5-106">このトピックでは、<xref:System.Linq.Enumerable.GroupJoin%2A> メソッドおよび <xref:System.Linq.Enumerable.Join%2A> メソッドで、クエリ式の構文を使って <xref:System.Data.DataSet> に対するクエリを実行する例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="f84a5-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="f84a5-107">`FillDataSet`でこれらの例で使用されるメソッドが指定された[をデータセットにデータを読み込む](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)します。</span><span class="sxs-lookup"><span data-stu-id="f84a5-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="f84a5-108">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="f84a5-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f84a5-109">このトピックの例では、次を使用して`using` / `Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f84a5-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="f84a5-110">詳細については、「[方法 :Visual Studio での LINQ to DataSet プロジェクトの作成](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)です。</span><span class="sxs-lookup"><span data-stu-id="f84a5-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="groupjoin"></a><span data-ttu-id="f84a5-111">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="f84a5-111">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="f84a5-112">例</span><span class="sxs-lookup"><span data-stu-id="f84a5-112">Example</span></span>  
 <span data-ttu-id="f84a5-113">この例では、<xref:System.Linq.Enumerable.GroupJoin%2A> テーブルおよび `SalesOrderHeader` テーブルに対して `SalesOrderDetail` を実行することによって、顧客ごとの注文数を調べます。</span><span class="sxs-lookup"><span data-stu-id="f84a5-113">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `SalesOrderHeader` and `SalesOrderDetail` tables to find the number of orders per customer.</span></span> <span data-ttu-id="f84a5-114">GroupJoin は、左外部結合に相当します。つまり、1 つ目 (左側) のデータ ソースに存在するすべての要素は、関連する要素がもう一方のデータ ソースに存在するかどうかに関係なく返されます。</span><span class="sxs-lookup"><span data-stu-id="f84a5-114">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="f84a5-115">例</span><span class="sxs-lookup"><span data-stu-id="f84a5-115">Example</span></span>  
 <span data-ttu-id="f84a5-116">この例では、<xref:System.Linq.Enumerable.GroupJoin%2A> テーブルと `Contact` テーブルに対して `SalesOrderHeader` を実行します。</span><span class="sxs-lookup"><span data-stu-id="f84a5-116">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `Contact` and `SalesOrderHeader` tables.</span></span> <span data-ttu-id="f84a5-117">GroupJoin は、左外部結合に相当します。つまり、1 つ目 (左側) のデータ ソースに存在するすべての要素は、関連する要素がもう一方のデータ ソースに存在するかどうかに関係なく返されます。</span><span class="sxs-lookup"><span data-stu-id="f84a5-117">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="f84a5-118">Join</span><span class="sxs-lookup"><span data-stu-id="f84a5-118">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="f84a5-119">例</span><span class="sxs-lookup"><span data-stu-id="f84a5-119">Example</span></span>  
 <span data-ttu-id="f84a5-120">この例では、`SalesOrderHeader` テーブルと `SalesOrderDetail` テーブルを結合し、8 月以降のオンラインでの注文を取得します。</span><span class="sxs-lookup"><span data-stu-id="f84a5-120">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="f84a5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f84a5-121">See also</span></span>

- [<span data-ttu-id="f84a5-122">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="f84a5-122">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="f84a5-123">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="f84a5-123">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="f84a5-124">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="f84a5-124">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="f84a5-125">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f84a5-125">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
