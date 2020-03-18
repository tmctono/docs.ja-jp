---
title: グループ化操作でのサブクエリの実行 (C# での LINQ)
description: C# で LINQ を使用して、グループ化操作でサブクエリを実行する方法について説明します。
ms.date: 12/01/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: fd26f87ad7d5b4892f086bf8c7a34cf19a7f9e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173368"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a><span data-ttu-id="1c8f8-103">グループ化操作でのサブクエリの実行</span><span class="sxs-lookup"><span data-stu-id="1c8f8-103">Perform a subquery on a grouping operation</span></span>

<span data-ttu-id="1c8f8-104">この記事では、ソース データを複数のグループに整理し、各グループに対して個別にサブクエリを実行するクエリを作成する方法を 2 つ紹介します。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-104">This article shows two different ways to create a query that orders the source data into groups, and then performs a subquery over each group individually.</span></span> <span data-ttu-id="1c8f8-105">各例の基本的な手法として、ソース要素のグループ化には、 *という名前の "* 継続`newGroup`" を使用し、`newGroup` に対する新しいサブクエリを生成します。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-105">The basic technique in each example is to group the source elements by using a *continuation* named `newGroup`, and then generating a new subquery against `newGroup`.</span></span> <span data-ttu-id="1c8f8-106">このサブクエリは、外部クエリによって作成された新しい各グループに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-106">This subquery is run against each new group that is created by the outer query.</span></span> <span data-ttu-id="1c8f8-107">この例では、最終出力がグループではなく、匿名型のフラットなシーケンスであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-107">Note that in this particular example the final output is not a group, but a flat sequence of anonymous types.</span></span>  
  
<span data-ttu-id="1c8f8-108">グループ化する方法の詳細については、「[group 句](../language-reference/keywords/group-clause.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-108">For more information about how to group, see [group clause](../language-reference/keywords/group-clause.md).</span></span>  
  
<span data-ttu-id="1c8f8-109">継続の詳細については、「[into](../language-reference/keywords/into.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-109">For more information about continuations, see [into](../language-reference/keywords/into.md).</span></span> <span data-ttu-id="1c8f8-110">次の例では、インメモリ データ構造をデータ ソースとして使用していますが、どの種類の LINQ データ ソースにも同じ原則が当てはまります。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-110">The following example uses an in-memory data structure as the data source, but the same principles apply for any kind of LINQ data source.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c8f8-111">例</span><span class="sxs-lookup"><span data-stu-id="1c8f8-111">Example</span></span>

> [!NOTE]
> <span data-ttu-id="1c8f8-112">この例には、「[オブジェクトのコレクションの照会](query-a-collection-of-objects.md)」のサンプル コードで定義されているオブジェクトへの参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-112">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]

<span data-ttu-id="1c8f8-113">上記のスニペットのクエリは、メソッド構文を使用して記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-113">The query in the snippet above can also be written using method syntax.</span></span> <span data-ttu-id="1c8f8-114">次のコード スニペットは、メソッド構文を使用して記述した意味的に同等のクエリです。</span><span class="sxs-lookup"><span data-stu-id="1c8f8-114">The following code snippet has a semantically equivalent query written using method syntax.</span></span>

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a><span data-ttu-id="1c8f8-115">参照</span><span class="sxs-lookup"><span data-stu-id="1c8f8-115">See also</span></span>

- [<span data-ttu-id="1c8f8-116">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="1c8f8-116">Language Integrated Query (LINQ)</span></span>](index.md)
