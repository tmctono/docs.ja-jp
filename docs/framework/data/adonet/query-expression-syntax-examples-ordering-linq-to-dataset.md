---
title: クエリ式の構文例:順序付け (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 653a4a97-1e4a-4b2d-8d24-7dbe1f2a5c84
ms.openlocfilehash: 932f5e4f6073844a951d06dabec45e5ff3e743bf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782996"
---
# <a name="query-expression-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="54d8a-102">クエリ式の構文例:順序付け (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="54d8a-102">Query Expression Syntax Examples: Ordering (LINQ to DataSet)</span></span>
<span data-ttu-id="54d8a-103">このトピックでは、<xref:System.Linq.Enumerable.OrderBy%2A>、<xref:System.Linq.Enumerable.OrderByDescending%2A>、<xref:System.Linq.Enumerable.Reverse%2A>、および <xref:System.Linq.Enumerable.ThenByDescending%2A> の各メソッドで、クエリ構文を使って <xref:System.Data.DataSet> に対するクエリを実行し、その結果を並べ替える例を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="54d8a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results using the query expression syntax.</span></span>  
  
 <span data-ttu-id="54d8a-104">これら`FillDataSet`の例で使用されるメソッドは、「[データセットへのデータの読み込み](loading-data-into-a-dataset.md)」で指定されています。</span><span class="sxs-lookup"><span data-stu-id="54d8a-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="54d8a-105">このトピックの例には、AdventureWorks サンプル データベースの Contact、Address、Product、SalesOrderHeader、SalesOrderDetail の各テーブルが使用されています。</span><span class="sxs-lookup"><span data-stu-id="54d8a-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="54d8a-106">このトピックの例では、次`using` / `Imports`のステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="54d8a-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="54d8a-107">詳細については、「[方法 :Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)で LINQ to DataSet プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="54d8a-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="54d8a-108">OrderBy</span><span class="sxs-lookup"><span data-stu-id="54d8a-108">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="54d8a-109">例</span><span class="sxs-lookup"><span data-stu-id="54d8a-109">Example</span></span>  
 <span data-ttu-id="54d8a-110">この例では、<xref:System.Linq.Enumerable.OrderBy%2A> を使用して、姓の順に並べ替えられた連絡先の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="54d8a-110">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="54d8a-111">例</span><span class="sxs-lookup"><span data-stu-id="54d8a-111">Example</span></span>  
 <span data-ttu-id="54d8a-112">この例では、<xref:System.Linq.Enumerable.OrderBy%2A> を使用して、連絡先の一覧を名の長さの順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="54d8a-112">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP LINQ to DataSet Examples#OrderBySimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="54d8a-113">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="54d8a-113">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="54d8a-114">例</span><span class="sxs-lookup"><span data-stu-id="54d8a-114">Example</span></span>  
 <span data-ttu-id="54d8a-115">この例では、`orderby… descending` メソッドと同等の `Order By … Descending` (<xref:System.Linq.Enumerable.OrderByDescending%2A>) を使用して、価格の一覧を高いものから低い順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="54d8a-115">This example uses `orderby… descending` (`Order By … Descending`), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByDescendingSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="reverse"></a><span data-ttu-id="54d8a-116">Reverse</span><span class="sxs-lookup"><span data-stu-id="54d8a-116">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="54d8a-117">例</span><span class="sxs-lookup"><span data-stu-id="54d8a-117">Example</span></span>  
 <span data-ttu-id="54d8a-118">この例では、<xref:System.Linq.Enumerable.Reverse%2A> を使用して、`OrderDate` が 2002 年 2 月 20 日よりも前の日付である注文の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="54d8a-118">This example uses <xref:System.Linq.Enumerable.Reverse%2A> to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="54d8a-119">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="54d8a-119">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="54d8a-120">例</span><span class="sxs-lookup"><span data-stu-id="54d8a-120">Example</span></span>  
 <span data-ttu-id="54d8a-121">この例では、`OrderBy… Descending` メソッドと同等の <xref:System.Linq.Enumerable.ThenByDescending%2A> を使用して、製品の一覧を、名前順に、次に表示価格の高いものから低い順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="54d8a-121">This example uses `OrderBy… Descending` , which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price, from highest to lowest.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="54d8a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="54d8a-122">See also</span></span>

- [<span data-ttu-id="54d8a-123">DataSet へのデータの読み込み</span><span class="sxs-lookup"><span data-stu-id="54d8a-123">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="54d8a-124">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="54d8a-124">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="54d8a-125">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="54d8a-125">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="54d8a-126">標準クエリ演算子の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54d8a-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
