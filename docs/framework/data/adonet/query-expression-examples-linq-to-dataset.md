---
title: クエリ式の例 (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: f743fbc7-faff-45e5-af1e-61577d87f0cc
ms.openlocfilehash: 4dd078c99d545397a032586d6814e0232a7641cc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783025"
---
# <a name="query-expression-examples-linq-to-dataset"></a><span data-ttu-id="80c83-102">クエリ式の例 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="80c83-102">Query Expression Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="80c83-103">このセクションでは、標準クエリ演算子を使用するクエリ式構文のプログラミング例に LINQ to DataSet を示します。</span><span class="sxs-lookup"><span data-stu-id="80c83-103">This section provides LINQ to DataSet programming examples in query expression syntax that use the standard query operators.</span></span> <span data-ttu-id="80c83-104">これら<xref:System.Data.DataSet>の例で使用されるは、「 `FillDataSet` [データセットへのデータの読み込み](loading-data-into-a-dataset.md)」で指定されているメソッドを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="80c83-104">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="80c83-105">詳細については、「[標準クエリ演算子C#の概要」 ()](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)または「[標準クエリ演算子の概要 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80c83-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80c83-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="80c83-106">In This Section</span></span>  
 [<span data-ttu-id="80c83-107">射影</span><span class="sxs-lookup"><span data-stu-id="80c83-107">Projection</span></span>](query-expression-syntax-examples-projection-linq-to-dataset.md)  
 <span data-ttu-id="80c83-108">このトピックでは、<xref:System.Linq.Enumerable.Select%2A> メソッドおよび <xref:System.Linq.Enumerable.SelectMany%2A> メソッドを使って <xref:System.Data.DataSet> を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-108">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="80c83-109">制限</span><span class="sxs-lookup"><span data-stu-id="80c83-109">Restriction</span></span>](query-expression-syntax-examples-restriction-linq-to-dataset.md)  
 <span data-ttu-id="80c83-110">このトピックでは、<xref:System.Linq.Enumerable.Where%2A> メソッドを使って <xref:System.Data.DataSet> を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-110">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="80c83-111">パーティション分割</span><span class="sxs-lookup"><span data-stu-id="80c83-111">Partitioning</span></span>](query-expression-syntax-examples-partitioning.md)  
 <span data-ttu-id="80c83-112">このトピックでは、<xref:System.Linq.Enumerable.Skip%2A> メソッドおよび <xref:System.Linq.Enumerable.Take%2A> メソッドを使って <xref:System.Data.DataSet> を照会し、結果をパーティション分割する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-112">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="80c83-113">順序付け</span><span class="sxs-lookup"><span data-stu-id="80c83-113">Ordering</span></span>](query-expression-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="80c83-114">このトピックでは、<xref:System.Linq.Enumerable.OrderBy%2A>、<xref:System.Linq.Enumerable.OrderByDescending%2A>、<xref:System.Linq.Enumerable.Reverse%2A>、<xref:System.Linq.Enumerable.ThenByDescending%2A> の各メソッドを使って <xref:System.Data.DataSet> を照会し、結果を並べ替える例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-114">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="80c83-115">要素演算子</span><span class="sxs-lookup"><span data-stu-id="80c83-115">Element Operators</span></span>](query-expression-syntax-examples-element-operators.md)  
 <span data-ttu-id="80c83-116">このトピックでは、<xref:System.Linq.Enumerable.First%2A> メソッドおよび <xref:System.Linq.Enumerable.ElementAt%2A> メソッドを使用して <xref:System.Data.DataRow> から <xref:System.Data.DataSet> 要素を取得する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-116">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="80c83-117">集計演算子</span><span class="sxs-lookup"><span data-stu-id="80c83-117">Aggregate Operators</span></span>](query-expression-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="80c83-118">このトピックでは、<xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A>、<xref:System.Linq.Enumerable.Max%2A>、<xref:System.Linq.Enumerable.Min%2A>、<xref:System.Linq.Enumerable.Sum%2A> の各メソッドを使って <xref:System.Data.DataSet> を照会し、データを集計する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-118">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="80c83-119">結合演算子</span><span class="sxs-lookup"><span data-stu-id="80c83-119">Join Operators</span></span>](query-expression-syntax-examples-join-operators.md)  
 <span data-ttu-id="80c83-120">このトピックでは、<xref:System.Linq.Enumerable.GroupJoin%2A> メソッドおよび <xref:System.Linq.Enumerable.Join%2A> メソッドを使って <xref:System.Data.DataSet> を照会する例を取り上げます。</span><span class="sxs-lookup"><span data-stu-id="80c83-120">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c83-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="80c83-121">See also</span></span>

- [<span data-ttu-id="80c83-122">メソッド ベースのクエリ例</span><span class="sxs-lookup"><span data-stu-id="80c83-122">Method-Based Query Examples</span></span>](method-based-query-examples-linq-to-dataset.md)
- [<span data-ttu-id="80c83-123">DataSet 固有の演算子の例</span><span class="sxs-lookup"><span data-stu-id="80c83-123">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)
- [<span data-ttu-id="80c83-124">LINQ to DataSet の例</span><span class="sxs-lookup"><span data-stu-id="80c83-124">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
