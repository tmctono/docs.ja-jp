---
title: データの並べ替え (C#)
description: 並べ替え操作について、および C# の LINQ で並べ替え操作を実行する標準クエリ演算子メソッドについて説明します。
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 5feeb0e2229fc370fdcb9608817f41832bffd7cc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302335"
---
# <a name="sorting-data-c"></a><span data-ttu-id="d9417-103">データの並べ替え (C#)</span><span class="sxs-lookup"><span data-stu-id="d9417-103">Sorting Data (C#)</span></span>
<span data-ttu-id="d9417-104">並べ替え操作では、1 つ以上の属性に基づいてシーケンスの要素を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d9417-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="d9417-105">並べ替えの第 1 条件で、要素に対して一回目の並べ替えが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9417-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="d9417-106">第 2 条件を指定すると、第 1 条件で並べ替えられた各グループ内の要素を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="d9417-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="d9417-107">次の図は、文字のシーケンスに対してアルファベット順の並べ替え操作を実行した結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9417-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span>
  
 ![アルファベット順の並べ替え操作を示している図。](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="d9417-109">次のセクションでは、データの並べ替えを実行する標準クエリ演算子のメソッドの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d9417-109">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9417-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="d9417-110">Methods</span></span>  
  
|<span data-ttu-id="d9417-111">メソッド名</span><span class="sxs-lookup"><span data-stu-id="d9417-111">Method Name</span></span>|<span data-ttu-id="d9417-112">説明</span><span class="sxs-lookup"><span data-stu-id="d9417-112">Description</span></span>|<span data-ttu-id="d9417-113">C# のクエリ式の構文</span><span class="sxs-lookup"><span data-stu-id="d9417-113">C# Query Expression Syntax</span></span>|<span data-ttu-id="d9417-114">説明</span><span class="sxs-lookup"><span data-stu-id="d9417-114">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d9417-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="d9417-115">OrderBy</span></span>|<span data-ttu-id="d9417-116">値を昇順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d9417-116">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d9417-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="d9417-117">OrderByDescending</span></span>|<span data-ttu-id="d9417-118">値を降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="d9417-118">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d9417-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="d9417-119">ThenBy</span></span>|<span data-ttu-id="d9417-120">2 番目の並べ替えを昇順で実行します。</span><span class="sxs-lookup"><span data-stu-id="d9417-120">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d9417-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="d9417-121">ThenByDescending</span></span>|<span data-ttu-id="d9417-122">2 番目の並べ替えを降順で実行します。</span><span class="sxs-lookup"><span data-stu-id="d9417-122">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d9417-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="d9417-123">Reverse</span></span>|<span data-ttu-id="d9417-124">コレクションの要素の順序を反転させます。</span><span class="sxs-lookup"><span data-stu-id="d9417-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="d9417-125">該当なし。</span><span class="sxs-lookup"><span data-stu-id="d9417-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="d9417-126">クエリ式の構文例</span><span class="sxs-lookup"><span data-stu-id="d9417-126">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="d9417-127">1 番目の並べ替えの例</span><span class="sxs-lookup"><span data-stu-id="d9417-127">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="d9417-128">1 番目の並べ替え (昇順)</span><span class="sxs-lookup"><span data-stu-id="d9417-128">Primary Ascending Sort</span></span>  
 <span data-ttu-id="d9417-129">次の例は、LINQ クエリで `orderby` 句を使用して、配列内の文字列を文字列長に従って昇順に並べ替える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9417-129">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="d9417-130">1 番目の並べ替え (降順)</span><span class="sxs-lookup"><span data-stu-id="d9417-130">Primary Descending Sort</span></span>  
 <span data-ttu-id="d9417-131">次の例は、LINQ クエリで `orderby descending` 句を使用して、文字列を最初の文字に従って降順に並べ替える方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9417-131">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="d9417-132">2 番目の並べ替えの例</span><span class="sxs-lookup"><span data-stu-id="d9417-132">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="d9417-133">2 番目の並べ替え (昇順)</span><span class="sxs-lookup"><span data-stu-id="d9417-133">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="d9417-134">次の例は、LINQ クエリで `orderby` 句を使用して、配列内の文字列に対して 1 番目および 2 番目の並べ替えを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9417-134">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="d9417-135">文字列は、最初に文字列長を基準として、次に文字列の最初の文字を基準として、どちらも昇順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="d9417-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="d9417-136">2 番目の並べ替え (降順)</span><span class="sxs-lookup"><span data-stu-id="d9417-136">Secondary Descending Sort</span></span>  
 <span data-ttu-id="d9417-137">次の例は、LINQ クエリで `orderby descending` 句を使用して、1 番目の並べ替えを昇順で実行し、2 番目の並べ替えを降順で実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d9417-137">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="d9417-138">各文字列は、最初に文字列長を基準として、次に文字列の最初の文字を基準として並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="d9417-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9417-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9417-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="d9417-140">標準クエリ演算子の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="d9417-140">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="d9417-141">orderby 句</span><span class="sxs-lookup"><span data-stu-id="d9417-141">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="d9417-142">join 句の結果の順序指定</span><span class="sxs-lookup"><span data-stu-id="d9417-142">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="d9417-143">任意のワードまたはフィールドを基準にテキスト データの並べ替えまたはフィルター処理を実行する方法 (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d9417-143">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
