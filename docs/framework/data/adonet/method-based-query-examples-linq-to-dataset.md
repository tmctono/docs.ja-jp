---
title: メソッド ベースのクエリ例 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
ms.openlocfilehash: 1c1ef8f1b6c05415ac6f5ee59d9a415bfab2c410
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175383"
---
# <a name="method-based-query-examples-linq-to-dataset"></a><span data-ttu-id="7e4c9-102">メソッド ベースのクエリ例 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="7e4c9-102">Method-Based Query Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="7e4c9-103">このセクションでは、メソッド ベースのクエリ構文で標準クエリ演算子を使用する LINQ to DataSet プログラミングの例を提供します。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-103">This section provides LINQ to DataSet programming examples in method-based query syntax that use the standard query operators.</span></span> <span data-ttu-id="7e4c9-104">これらの例で使用されている <xref:System.Data.DataSet> は、`FillDataSet` メソッド (「[DataSet へのデータの読み込み](loading-data-into-a-dataset.md)」を参照) を使用して設定します。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="7e4c9-105">詳しくは、「[標準クエリ演算子の概要 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)」または「[標準クエリ演算子の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7e4c9-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7e4c9-106">In This Section</span></span>  

 [<span data-ttu-id="7e4c9-107">射影</span><span class="sxs-lookup"><span data-stu-id="7e4c9-107">Projection</span></span>](method-based-query-syntax-examples-projection.md)  
 <span data-ttu-id="7e4c9-108">このトピックでは、<xref:System.Linq.Enumerable.Select%2A> メソッドおよび <xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使って <xref:System.Data.DataSet> を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-108">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="7e4c9-109">パーティション分割</span><span class="sxs-lookup"><span data-stu-id="7e4c9-109">Partitioning</span></span>](method-based-query-syntax-examples-partitioning-linq.md)  
 <span data-ttu-id="7e4c9-110">このトピックでは、<xref:System.Linq.Enumerable.Skip%2A> メソッドおよび <xref:System.Linq.Enumerable.Take%2A> メソッドを使って <xref:System.Data.DataSet> を照会し、結果をパーティション分割する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-110">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="7e4c9-111">順序付け</span><span class="sxs-lookup"><span data-stu-id="7e4c9-111">Ordering</span></span>](method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="7e4c9-112">このトピックでは、<xref:System.Linq.Enumerable.OrderBy%2A>、<xref:System.Linq.Enumerable.OrderByDescending%2A>、<xref:System.Linq.Enumerable.Reverse%2A>、<xref:System.Linq.Enumerable.ThenByDescending%2A> の各メソッドを使って <xref:System.Data.DataSet> を照会し、結果を並べ替える例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-112">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="7e4c9-113">集合演算子</span><span class="sxs-lookup"><span data-stu-id="7e4c9-113">Set Operators</span></span>](method-based-query-syntax-examples-set-operators.md)  
 <span data-ttu-id="7e4c9-114">このトピックでは、<xref:System.Linq.Enumerable.Distinct%2A>、<xref:System.Linq.Enumerable.Except%2A>、<xref:System.Linq.Enumerable.Intersect%2A>、<xref:System.Linq.Enumerable.Union%2A> の各演算子を使って、データ行の集合に対する値ベースの比較操作を実行する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-114">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.</span></span>  
  
 [<span data-ttu-id="7e4c9-115">変換演算子</span><span class="sxs-lookup"><span data-stu-id="7e4c9-115">Conversion Operators</span></span>](method-based-query-syntax-examples-conversion-operators.md)  
 <span data-ttu-id="7e4c9-116">このトピックでは、<xref:System.Linq.Enumerable.ToArray%2A>、<xref:System.Linq.Enumerable.ToDictionary%2A>、<xref:System.Linq.Enumerable.ToList%2A> の各メソッドを使ってクエリ式を即時実行する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-116">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 [<span data-ttu-id="7e4c9-117">要素演算子</span><span class="sxs-lookup"><span data-stu-id="7e4c9-117">Element Operators</span></span>](method-based-query-syntax-examples-element-operators.md)  
 <span data-ttu-id="7e4c9-118">このトピックでは、<xref:System.Linq.Enumerable.First%2A> メソッドおよび <xref:System.Linq.Enumerable.ElementAt%2A> メソッドを使用して <xref:System.Data.DataRow> から <xref:System.Data.DataSet> 要素を取得する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-118">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="7e4c9-119">集計演算子</span><span class="sxs-lookup"><span data-stu-id="7e4c9-119">Aggregate Operators</span></span>](method-based-query-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="7e4c9-120">このトピックでは、<xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A>、<xref:System.Linq.Enumerable.Max%2A>、<xref:System.Linq.Enumerable.Min%2A>、<xref:System.Linq.Enumerable.Sum%2A> の各メソッドを使って <xref:System.Data.DataSet> を照会し、データを集計する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-120">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="7e4c9-121">Join</span><span class="sxs-lookup"><span data-stu-id="7e4c9-121">Join</span></span>](method-based-query-syntax-examples-join-linq-to-dataset.md)  
 <span data-ttu-id="7e4c9-122">このトピックでは、<xref:System.Linq.Enumerable.GroupJoin%2A> メソッドおよび <xref:System.Linq.Enumerable.Join%2A> メソッドを使って <xref:System.Data.DataSet> を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="7e4c9-122">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4c9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e4c9-123">See also</span></span>

- [<span data-ttu-id="7e4c9-124">クエリ式の例</span><span class="sxs-lookup"><span data-stu-id="7e4c9-124">Query Expression Examples</span></span>](query-expression-examples-linq-to-dataset.md)
- [<span data-ttu-id="7e4c9-125">DataSet 固有の演算子の例</span><span class="sxs-lookup"><span data-stu-id="7e4c9-125">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)
- [<span data-ttu-id="7e4c9-126">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="7e4c9-126">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
