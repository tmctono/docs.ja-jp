---
title: 標準クエリ演算子の概要 (C#)
description: LINQ 標準クエリ演算子には、フィルター処理、プロジェクション、集計、C# の並べ替えなどのクエリ機能が用意されています。
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 1ff98e47641dbe7a884b7d6c7758c1fe61b95091
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178776"
---
# <a name="standard-query-operators-overview-c"></a><span data-ttu-id="c945c-103">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-103">Standard Query Operators Overview (C#)</span></span>

<span data-ttu-id="c945c-104">"*標準クエリ演算子*" は、LINQ パターンを形成するメソッドです。</span><span class="sxs-lookup"><span data-stu-id="c945c-104">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="c945c-105">これらのメソッドの大部分はシーケンスに対して機能します。ここでシーケンスとは、<xref:System.Collections.Generic.IEnumerable%601> インターフェイスまたは <xref:System.Linq.IQueryable%601> インターフェイスを実装している型のオブジェクトのことです。</span><span class="sxs-lookup"><span data-stu-id="c945c-105">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="c945c-106">標準クエリ演算子には、フィルター処理、プロジェクション、集計、並べ替えなどのクエリ機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c945c-106">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="c945c-107">LINQ 標準クエリ演算子には 2 つのセットがあります。1 つは <xref:System.Collections.Generic.IEnumerable%601> 型のオブジェクトを操作する演算子、もう 1 つは <xref:System.Linq.IQueryable%601> 型のオブジェクトを操作する演算子です。</span><span class="sxs-lookup"><span data-stu-id="c945c-107">There are two sets of LINQ standard query operators: one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601>, another that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="c945c-108">各セットを構成するメソッドは、それぞれ、<xref:System.Linq.Enumerable> および <xref:System.Linq.Queryable> クラスの静的メンバーです。</span><span class="sxs-lookup"><span data-stu-id="c945c-108">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="c945c-109">そのメソッドの操作対象である型の "*拡張メソッド*" として定義されています。</span><span class="sxs-lookup"><span data-stu-id="c945c-109">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="c945c-110">拡張メソッドは、静的メソッド構文またはインスタンス メソッド構文のいずれかを使用して呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c945c-110">Extension methods can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="c945c-111">さらに、いくつかの標準クエリ演算子メソッドが、<xref:System.Collections.Generic.IEnumerable%601> または <xref:System.Linq.IQueryable%601> を基にする型以外の型を操作します。</span><span class="sxs-lookup"><span data-stu-id="c945c-111">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="c945c-112"><xref:System.Linq.Enumerable> 型は、このような 2 つのメソッドを定義し、その両方が <xref:System.Collections.IEnumerable> 型のオブジェクトを操作します。</span><span class="sxs-lookup"><span data-stu-id="c945c-112">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="c945c-113">これらのメソッド <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> と <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29> を使用して、LINQ パターンでクエリされるパラメーター化されていないまたは非ジェネリック型のコレクションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c945c-113">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="c945c-114">これを行うには、厳密に型指定されたオブジェクトのコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="c945c-114">They do this by creating a strongly typed collection of objects.</span></span> <span data-ttu-id="c945c-115"><xref:System.Linq.Queryable> クラスは、型 <xref:System.Linq.Queryable> のオブジェクトを操作する 2 つの類似したメソッド <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> と <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29> を定義します。</span><span class="sxs-lookup"><span data-stu-id="c945c-115">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="c945c-116">標準クエリ演算子の実行のタイミングは、シングルトン値を返すか、値のシーケンスを返すかで異なります。</span><span class="sxs-lookup"><span data-stu-id="c945c-116">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="c945c-117">これらのシングルトン値を返すメソッド (たとえば、<xref:System.Linq.Enumerable.Average%2A> と <xref:System.Linq.Enumerable.Sum%2A>) は、すぐに実行されます。</span><span class="sxs-lookup"><span data-stu-id="c945c-117">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="c945c-118">シーケンスを返すメソッドは、クエリの実行を遅延させ、列挙可能なオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c945c-118">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="c945c-119">メモリ内コレクションを操作するメソッド、つまり <xref:System.Collections.Generic.IEnumerable%601> を拡張するメソッドの場合、返される列挙可能なオブジェクトは、メソッドに渡された引数をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="c945c-119">For methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="c945c-120">オブジェクトが列挙されると、クエリ演算子のロジックが使用され、クエリ結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="c945c-120">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="c945c-121">対照的に、<xref:System.Linq.IQueryable%601> を拡張するメソッドではいかなるクエリ動作も実装されません。</span><span class="sxs-lookup"><span data-stu-id="c945c-121">In contrast, methods that extend <xref:System.Linq.IQueryable%601> don't implement any querying behavior.</span></span> <span data-ttu-id="c945c-122">実行するクエリを表す式ツリーがビルドされます。</span><span class="sxs-lookup"><span data-stu-id="c945c-122">They build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="c945c-123">クエリの処理は、ソース <xref:System.Linq.IQueryable%601> オブジェクトによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="c945c-123">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="c945c-124">クエリ メソッドの呼び出しは 1 回のクエリにまとめてチェーン化できるため、クエリが複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c945c-124">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="c945c-125">次のコード例は、標準クエリ演算子を使用してシーケンスに関する情報を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c945c-125">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="c945c-126">クエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="c945c-126">Query Expression Syntax</span></span>  

 <span data-ttu-id="c945c-127">頻繁に使用される標準クエリ演算子の中には、C# および Visual Basic 言語専用のキーワード構文が使用されているものがあります。こうした構文では、標準クエリ演算子を、"*クエリ* *式*" の一部として呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c945c-127">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="c945c-128">専用キーワードおよびそれに対応する構文が使用されている標準クエリ演算子の詳細については、「[標準クエリ演算子のクエリ式構文 (C#)](./query-expression-syntax-for-standard-query-operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c945c-128">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (C#)](./query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="c945c-129">標準クエリ演算子の拡張</span><span class="sxs-lookup"><span data-stu-id="c945c-129">Extending the Standard Query Operators</span></span>  

 <span data-ttu-id="c945c-130">標準クエリ演算子のセットを拡張するには、対象のドメインまたはテクノロジに適したドメイン固有のメソッドを作成します。</span><span class="sxs-lookup"><span data-stu-id="c945c-130">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="c945c-131">また、標準クエリ演算子を、リモート評価、クエリ変換、最適化などの追加サービスが用意されている独自の実装で置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="c945c-131">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="c945c-132">例については、「<xref:System.Linq.Enumerable.AsEnumerable%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c945c-132">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c945c-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="c945c-133">Related Sections</span></span>  

 <span data-ttu-id="c945c-134">次のリンクをクリックすると、さまざまな標準クエリ演算子に関する追加情報を機能別に提供する記事に移動します。</span><span class="sxs-lookup"><span data-stu-id="c945c-134">The following links take you to articles that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 [<span data-ttu-id="c945c-135">データの並べ替え (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-135">Sorting Data (C#)</span></span>](./sorting-data.md)  
  
 [<span data-ttu-id="c945c-136">セット操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-136">Set Operations (C#)</span></span>](./set-operations.md)  
  
 [<span data-ttu-id="c945c-137">データのフィルター処理 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-137">Filtering Data (C#)</span></span>](./filtering-data.md)  
  
 [<span data-ttu-id="c945c-138">量指定子操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-138">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)  
  
 [<span data-ttu-id="c945c-139">射影操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-139">Projection Operations (C#)</span></span>](./projection-operations.md)  
  
 [<span data-ttu-id="c945c-140">データのパーティション分割</span><span class="sxs-lookup"><span data-stu-id="c945c-140">Partitioning Data (C#)</span></span>](./partitioning-data.md)  
  
 [<span data-ttu-id="c945c-141">結合演算 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-141">Join Operations (C#)</span></span>](./join-operations.md)  
  
 [<span data-ttu-id="c945c-142">データのグループ化 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-142">Grouping Data (C#)</span></span>](./grouping-data.md)  
  
 [<span data-ttu-id="c945c-143">生成操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-143">Generation Operations (C#)</span></span>](./generation-operations.md)  
  
 [<span data-ttu-id="c945c-144">等価演算 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-144">Equality Operations (C#)</span></span>](./equality-operations.md)  
  
 [<span data-ttu-id="c945c-145">要素操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-145">Element Operations (C#)</span></span>](./element-operations.md)  
  
 [<span data-ttu-id="c945c-146">データ型の変換 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-146">Converting Data Types (C#)</span></span>](./converting-data-types.md)  
  
 [<span data-ttu-id="c945c-147">連結演算 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-147">Concatenation Operations (C#)</span></span>](./concatenation-operations.md)  
  
 [<span data-ttu-id="c945c-148">集計操作 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-148">Aggregation Operations (C#)</span></span>](./aggregation-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="c945c-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="c945c-149">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="c945c-150">LINQ クエリの概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-150">Introduction to LINQ Queries (C#)</span></span>](./introduction-to-linq-queries.md)
- [<span data-ttu-id="c945c-151">標準クエリ演算子のクエリ式構文 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-151">Query Expression Syntax for Standard Query Operators (C#)</span></span>](./query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="c945c-152">実行方法による標準クエリ演算子の分類 (C#)</span><span class="sxs-lookup"><span data-stu-id="c945c-152">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](./classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="c945c-153">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="c945c-153">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
