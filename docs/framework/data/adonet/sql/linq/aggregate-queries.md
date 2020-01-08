---
title: 集計クエリ
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: 8defefb39974bea150fed84b0e7404b43882c41c
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634743"
---
# <a name="aggregate-queries"></a><span data-ttu-id="9f9a5-102">集計クエリ</span><span class="sxs-lookup"><span data-stu-id="9f9a5-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="9f9a5-103">は、`Average`、`Count`、`Max`、`Min`、および `Sum` の各集計演算子をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="9f9a5-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の集計演算子には、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="9f9a5-105">集計クエリは直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="9f9a5-106">詳細については、「[LINQ クエリの概要 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="9f9a5-107">通常、集計クエリはコレクションではなく 1 つの数値を返します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="9f9a5-108">詳細については、「[集計操作](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="9f9a5-109">匿名型に対して集計を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="9f9a5-110">以下のトピックの例は、Northwind サンプル データベースから派生しています。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="9f9a5-111">詳細については、「[サンプルデータベースのダウンロード](downloading-sample-databases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f9a5-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9f9a5-112">In This Section</span></span>  
 [<span data-ttu-id="9f9a5-113">一連の数値の平均値の取得</span><span class="sxs-lookup"><span data-stu-id="9f9a5-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="9f9a5-114"><xref:System.Linq.Enumerable.Average%2A> 演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="9f9a5-115">シーケンス内の要素数のカウント</span><span class="sxs-lookup"><span data-stu-id="9f9a5-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="9f9a5-116"><xref:System.Linq.Enumerable.Count%2A> 演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="9f9a5-117">一連の数値の中の最大値の検出</span><span class="sxs-lookup"><span data-stu-id="9f9a5-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="9f9a5-118"><xref:System.Linq.Enumerable.Max%2A> 演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="9f9a5-119">一連の数値の中の最小値の検出</span><span class="sxs-lookup"><span data-stu-id="9f9a5-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="9f9a5-120"><xref:System.Linq.Enumerable.Min%2A> 演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="9f9a5-121">数値のシーケンスの合計の計算</span><span class="sxs-lookup"><span data-stu-id="9f9a5-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="9f9a5-122"><xref:System.Linq.Enumerable.Sum%2A> 演算子を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9f9a5-123">関連セクション</span><span class="sxs-lookup"><span data-stu-id="9f9a5-123">Related Sections</span></span>  
 [<span data-ttu-id="9f9a5-124">クエリの例</span><span class="sxs-lookup"><span data-stu-id="9f9a5-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="9f9a5-125">Visual Basic および C# の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] クエリに関するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="9f9a5-126">クエリの概念</span><span class="sxs-lookup"><span data-stu-id="9f9a5-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="9f9a5-127">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]で LINQ クエリを設計するための概念について説明するトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-127">Provides links to topics that explain concepts for designing LINQ queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="9f9a5-128">LINQ クエリの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="9f9a5-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="9f9a5-129">LINQ でのクエリの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f9a5-129">Explains how queries work in LINQ.</span></span>
