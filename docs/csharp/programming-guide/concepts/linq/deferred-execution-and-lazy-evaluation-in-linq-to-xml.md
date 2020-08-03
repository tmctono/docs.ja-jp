---
title: LINQ to XML における遅延実行とレイジー評価 (C#)
description: クエリと軸の操作では、C# で遅延実行が使用することができます。 遅延実行の要件と利点、および実装に関する注意点について説明します。
ms.date: 07/20/2015
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
ms.openlocfilehash: 8559505572404f895d75e0d9895f9ae2c07b795e
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105459"
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a><span data-ttu-id="ba209-104">LINQ to XML における遅延実行とレイジー評価 (C#)</span><span class="sxs-lookup"><span data-stu-id="ba209-104">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>
<span data-ttu-id="ba209-105">クエリと軸の操作は、多くの場合、遅延実行を使用するように実装されています。</span><span class="sxs-lookup"><span data-stu-id="ba209-105">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="ba209-106">このトピックでは、遅延実行の要件と利点、および実装に関する注意点について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba209-106">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="ba209-107">遅延実行</span><span class="sxs-lookup"><span data-stu-id="ba209-107">Deferred Execution</span></span>  
 <span data-ttu-id="ba209-108">遅延実行とは、"*具体*" 値が実際に必要となるまで、式の評価を遅らせることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ba209-108">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="ba209-109">大きなデータ コレクションの操作が必要な場合、特に連結されたクエリや操作が含まれているプログラムでは、遅延実行によってパフォーマンスが大幅に向上することがあります。</span><span class="sxs-lookup"><span data-stu-id="ba209-109">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="ba209-110">最も効果的なケースでは、遅延実行を使用することによって、ソース コレクションの繰り返し処理を 1 度行うだけで済むようになります。</span><span class="sxs-lookup"><span data-stu-id="ba209-110">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="ba209-111">LINQ テクノロジでは、コア <xref:System.Linq?displayProperty=nameWithType> クラスのメンバーにおいても、<xref:System.Xml.Linq.Extensions?displayProperty=nameWithType> などのさまざまな LINQ 名前空間の拡張メソッドにおいても、遅延実行が広く利用されています。</span><span class="sxs-lookup"><span data-stu-id="ba209-111">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=nameWithType> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="ba209-112">C# 言語では、反復子ブロック内で [yield](../../../language-reference/keywords/yield.md) キーワード (`yield-return` ステートメントの形式) を使用することにより、遅延実行が直接サポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba209-112">Deferred execution is supported directly in the C# language by the [yield](../../../language-reference/keywords/yield.md) keyword (in the form of the `yield-return` statement) when used within an iterator block.</span></span> <span data-ttu-id="ba209-113">このような反復子は <xref:System.Collections.IEnumerator> 型または <xref:System.Collections.Generic.IEnumerator%601> 型 (または派生型) のコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="ba209-113">Such an iterator must return a collection of type <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> (or a derived type).</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="ba209-114">集中評価とレイジー評価</span><span class="sxs-lookup"><span data-stu-id="ba209-114">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="ba209-115">遅延実行を実装するメソッドを記述するときは、レイジー評価と集中評価のどちらを使用してメソッドを実装するかについても決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba209-115">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
- <span data-ttu-id="ba209-116">"*レイジー評価*" では、反復子を呼び出すたびに、ソース コレクションの 1 つの要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="ba209-116">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="ba209-117">これが、一般的な反復子の実装方法です。</span><span class="sxs-lookup"><span data-stu-id="ba209-117">This is the typical way in which iterators are implemented.</span></span>  
  
- <span data-ttu-id="ba209-118">"*集中評価*" では、反復子への最初の呼び出しの結果として、コレクション全体が処理されます。</span><span class="sxs-lookup"><span data-stu-id="ba209-118">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="ba209-119">ソース コレクションの一時的なコピーが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ba209-119">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="ba209-120">たとえば <xref:System.Linq.Enumerable.OrderBy%2A> メソッドでは、最初の要素を返す前に、コレクション全体を並べ替える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba209-120">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="ba209-121">通常は、レイジー評価を使用するとパフォーマンスが向上します。コレクション評価時のオーバーヘッド処理が均等に分散され、一時データの使用が最小限に抑えられるためです。</span><span class="sxs-lookup"><span data-stu-id="ba209-121">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="ba209-122">もちろん、操作によっては、中間結果を具体化するより他に方法がない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ba209-122">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ba209-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="ba209-123">Next Steps</span></span>  
 <span data-ttu-id="ba209-124">このチュートリアルの次のトピックでは、遅延実行について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba209-124">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
- [<span data-ttu-id="ba209-125">遅延実行の例 (C#)</span><span class="sxs-lookup"><span data-stu-id="ba209-125">Deferred Execution Example (C#)</span></span>](./deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba209-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ba209-126">See also</span></span>

- [<span data-ttu-id="ba209-127">チュートリアル: クエリの連結 (C#)</span><span class="sxs-lookup"><span data-stu-id="ba209-127">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
- [<span data-ttu-id="ba209-128">概念と用語 (関数型変換) (C#)</span><span class="sxs-lookup"><span data-stu-id="ba209-128">Concepts and Terminology (Functional Transformation) (C#)</span></span>](./concepts-and-terminology-functional-transformation.md)
- [<span data-ttu-id="ba209-129">集計操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="ba209-129">Aggregation Operations (C#)</span></span>](./aggregation-operations.md)
- [<span data-ttu-id="ba209-130">yield</span><span class="sxs-lookup"><span data-stu-id="ba209-130">yield</span></span>](../../../language-reference/keywords/yield.md)
