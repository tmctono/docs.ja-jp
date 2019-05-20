---
title: クエリ結果をメモリに格納する
description: 結果の格納方法。
ms.date: 11/30/2016
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.openlocfilehash: 66a7a95c74db4062e76c54d4339ccb7343f44067
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633563"
---
# <a name="store-the-results-of-a-query-in-memory"></a><span data-ttu-id="a3cb0-103">クエリ結果をメモリに格納する</span><span class="sxs-lookup"><span data-stu-id="a3cb0-103">Store the results of a query in memory</span></span>

<span data-ttu-id="a3cb0-104">クエリは、基本的に、データの取得方法と編成方法を指示するための一連の命令です。</span><span class="sxs-lookup"><span data-stu-id="a3cb0-104">A query is basically a set of instructions for how to retrieve and organize data.</span></span> <span data-ttu-id="a3cb0-105">結果の各項目は順次要求されるため、クエリは遅延実行されます。</span><span class="sxs-lookup"><span data-stu-id="a3cb0-105">Queries are executed lazily, as each subsequent item in the result is requested.</span></span> <span data-ttu-id="a3cb0-106">`foreach` を使用して結果を反復すると、項目はアクセスのたびに返されます。</span><span class="sxs-lookup"><span data-stu-id="a3cb0-106">When you use `foreach` to iterate the results, items are returned as accessed.</span></span> <span data-ttu-id="a3cb0-107">クエリを評価し、`foreach` のループを実行せずに結果を格納するには、クエリ変数で次のメソッドのいずれかを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a3cb0-107">To evaluate a query and store its results without executing a `foreach` loop, just call one of the following methods on the query variable:</span></span>

- <xref:System.Linq.Enumerable.ToList%2A>

- <xref:System.Linq.Enumerable.ToArray%2A>

- <xref:System.Linq.Enumerable.ToDictionary%2A>

- <xref:System.Linq.Enumerable.ToLookup%2A>

 <span data-ttu-id="a3cb0-108">クエリ結果を格納するときは、次の例に示すように、返されたコレクション オブジェクトを新しい変数に割り当てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3cb0-108">We recommend that when you store the query results, you assign the returned collection object to a new variable as shown in the following example:</span></span>

## <a name="example"></a><span data-ttu-id="a3cb0-109">例</span><span class="sxs-lookup"><span data-stu-id="a3cb0-109">Example</span></span>

[!code-csharp[csProgGuideLINQ#25](~/samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]

## <a name="see-also"></a><span data-ttu-id="a3cb0-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3cb0-110">See also</span></span>

- [<span data-ttu-id="a3cb0-111">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="a3cb0-111">Language Integrated Query (LINQ)</span></span>](index.md)
