---
title: C# での LINQ クエリの作成
description: C# で LINQ クエリを作成する方法について説明します。
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: ed32543b0422e0664a8577f2c27f7c7c00a719a1
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632873"
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="b8994-103">C\# での LINQ クエリの作成</span><span class="sxs-lookup"><span data-stu-id="b8994-103">Write LINQ queries in C\#</span></span>

<span data-ttu-id="b8994-104">この記事では、C# で LINQ クエリを作成できる 3 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8994-104">This article shows the three ways in which you can write a LINQ query in C#:</span></span>

1. <span data-ttu-id="b8994-105">クエリ構文を使用する。</span><span class="sxs-lookup"><span data-stu-id="b8994-105">Use query syntax.</span></span>

2. <span data-ttu-id="b8994-106">メソッド構文を使用する。</span><span class="sxs-lookup"><span data-stu-id="b8994-106">Use method syntax.</span></span>

3. <span data-ttu-id="b8994-107">クエリ構文とメソッド構文を組み合わせて使用する。</span><span class="sxs-lookup"><span data-stu-id="b8994-107">Use a combination of query syntax and method syntax.</span></span>

<span data-ttu-id="b8994-108">以下の例では、上記の各アプローチを使用したシンプルな LINQ クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="b8994-108">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="b8994-109">一般に、可能であれば常に (1) を使用し、(2) と (3) は必要に応じて使用するというのがルールになっています。</span><span class="sxs-lookup"><span data-stu-id="b8994-109">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="b8994-110">これらのクエリでは、シンプルなメモリ内コレクションに対して操作を実行します。ただし、基本的な構文は、LINQ to Entities および LINQ to XML で使用されるのと同じものです。</span><span class="sxs-lookup"><span data-stu-id="b8994-110">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>

## <a name="example---query-syntax"></a><span data-ttu-id="b8994-111">例 - クエリ構文</span><span class="sxs-lookup"><span data-stu-id="b8994-111">Example - Query syntax</span></span>

<span data-ttu-id="b8994-112">ほとんどのクエリ記述については、*クエリの構文*を使用して*クエリ式*を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b8994-112">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="b8994-113">次の例は、3 つのクエリ式を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8994-113">The following example shows three query expressions.</span></span> <span data-ttu-id="b8994-114">1 つ目のクエリ式は、`where` 句を使用した条件を適用することで、結果をフィルター処理または制限する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8994-114">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="b8994-115">このクエリは、値が 7 より大きいか、または 3 より小さいソース シーケンス内のすべての要素を返します。</span><span class="sxs-lookup"><span data-stu-id="b8994-115">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="b8994-116">2 つ目の式は、返された結果を並べ替える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8994-116">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="b8994-117">3 つ目の式は、キーに基づいて結果をグループ化する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b8994-117">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="b8994-118">このクエリは、単語の頭文字に基づいて 2 つのグループを返します。</span><span class="sxs-lookup"><span data-stu-id="b8994-118">This query returns two groups based on the first letter of the word.</span></span>

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

<span data-ttu-id="b8994-119">クエリの型が <xref:System.Collections.Generic.IEnumerable%601> であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b8994-119">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="b8994-120">これらのクエリはすべて、次の例で示すように、`var` を使用しても記述できます。</span><span class="sxs-lookup"><span data-stu-id="b8994-120">All of these queries could be written using `var` as shown in the following example:</span></span>

`var query = from num in numbers...`

<span data-ttu-id="b8994-121">上記の各例では、`foreach` ステートメントまたはその他のステートメントでクエリ変数を反復処理するまで、クエリは実際には実行されません。</span><span class="sxs-lookup"><span data-stu-id="b8994-121">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="b8994-122">詳しくは、「[LINQ クエリの概要](../programming-guide/concepts/linq/introduction-to-linq-queries.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b8994-122">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="example---method-syntax"></a><span data-ttu-id="b8994-123">例 - メソッド構文</span><span class="sxs-lookup"><span data-stu-id="b8994-123">Example - Method syntax</span></span>

<span data-ttu-id="b8994-124">一部のクエリ操作は、メソッド呼び出しとして表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8994-124">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="b8994-125">このようなメソッドで最も一般的なものは、<xref:System.Linq.Enumerable.Sum%2A>、<xref:System.Linq.Enumerable.Max%2A>、<xref:System.Linq.Enumerable.Min%2A>、<xref:System.Linq.Enumerable.Average%2A> のような単一の数値を返すメソッドです。</span><span class="sxs-lookup"><span data-stu-id="b8994-125">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="b8994-126">これらのメソッドは、単一の値のみを表し、追加のクエリ操作のソースとしては使用できないため、常に、どのクエリよりも後に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8994-126">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="b8994-127">次の例は、クエリ式でのメソッド呼び出しを示したものです。</span><span class="sxs-lookup"><span data-stu-id="b8994-127">The following example shows a method call in a query expression:</span></span>

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

<span data-ttu-id="b8994-128">メソッドに Action または Func パラメーターがある場合、それらは[ラムダ](../programming-guide/statements-expressions-operators/lambda-expressions.md)式の形式で提供されます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8994-128">If the method has Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

<span data-ttu-id="b8994-129">上記のクエリでは Query #4 だけが直ちに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b8994-129">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="b8994-130">これは、それがジェネリック <xref:System.Collections.Generic.IEnumerable%601> コレクションではなく、単一値を返すためです。</span><span class="sxs-lookup"><span data-stu-id="b8994-130">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="b8994-131">メソッド自体は、値を計算するために `foreach` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8994-131">The method itself has to use `foreach` in order to compute its value.</span></span>

<span data-ttu-id="b8994-132">上記の各クエリは、[var](../language-reference/keywords/var.md) による暗黙的型指定を使用しても記述できます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8994-132">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a><span data-ttu-id="b8994-133">例 - クエリとメソッド構文の併用</span><span class="sxs-lookup"><span data-stu-id="b8994-133">Example - Mixed query and method syntax</span></span>

<span data-ttu-id="b8994-134">この例では、クエリ句の結果に対してメソッド構文を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8994-134">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="b8994-135">方法は、クエリ式をかっこで囲み、ドット演算子を適用して、メソッドを呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="b8994-135">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="b8994-136">次の例では、Query #7 は、値が 3 ～ 7 である数値のカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="b8994-136">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="b8994-137">ただし一般的には、メソッド呼び出しの結果の格納には、2 番目の変数を使うほうが賢明です。</span><span class="sxs-lookup"><span data-stu-id="b8994-137">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="b8994-138">この方法のほうが、クエリをクエリ結果と混同する恐れがありません。</span><span class="sxs-lookup"><span data-stu-id="b8994-138">In this manner, the query is less likely to be confused with the results of the query.</span></span>

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

<span data-ttu-id="b8994-139">Query #7 はコレクションではなく単一の値を返すので、クエリはすぐに実行されます。</span><span class="sxs-lookup"><span data-stu-id="b8994-139">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>

<span data-ttu-id="b8994-140">上記のクエリは、`var` による暗黙的型指定を使用しても記述できます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8994-140">The previous query can be written by using implicit typing with `var`, as follows:</span></span>

```csharp
var numCount = (from num in numbers...
```

<span data-ttu-id="b8994-141">次のように、メソッド構文で記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8994-141">It can be written in method syntax as follows:</span></span>

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

<span data-ttu-id="b8994-142">次のように、明示的な型指定を使用して記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8994-142">It can be written by using explicit typing, as follows:</span></span>

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a><span data-ttu-id="b8994-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8994-143">See also</span></span>

- [<span data-ttu-id="b8994-144">チュートリアル: C# でのクエリの作成</span><span class="sxs-lookup"><span data-stu-id="b8994-144">Walkthrough: Writing Queries in C#</span></span>](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="b8994-145">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b8994-145">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="b8994-146">where 句</span><span class="sxs-lookup"><span data-stu-id="b8994-146">where clause</span></span>](../language-reference/keywords/where-clause.md)
