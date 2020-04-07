---
title: '方法: 単純な PLINQ クエリを作成して実行する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: c4cd75e55aabb551e5951a902ea6394a5659c9ee
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635854"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a><span data-ttu-id="29e8b-102">方法: 単純な PLINQ クエリを作成して実行する</span><span class="sxs-lookup"><span data-stu-id="29e8b-102">How to: Create and Execute a Simple PLINQ Query</span></span>

<span data-ttu-id="29e8b-103">この記事の例では、ソース シーケンスに対する <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> 拡張メソッドを使用して単純な並列統合言語クエリ (LINQ) クエリを作成し、<xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp> メソッドを使用して、そのクエリを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="29e8b-103">The example in this article shows how to create a simple Parallel Language Integrated Query (LINQ) query by using the <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=nameWithType> extension method on the source sequence and executing the query by using the <xref:System.Linq.ParallelEnumerable.ForAll%2A?displayProperty=nameWithTyp> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29e8b-104">ここでは、ラムダ式を使用して PLINQ でデリゲートを定義します。</span><span class="sxs-lookup"><span data-stu-id="29e8b-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="29e8b-105">C# または Visual Basic のラムダ式についての情報が必要な場合は、「[Lambda Expressions in PLINQ and TPL (PLINQ および TPL のラムダ式)](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e8b-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29e8b-106">例</span><span class="sxs-lookup"><span data-stu-id="29e8b-106">Example</span></span>  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 <span data-ttu-id="29e8b-107">この例では、結果シーケンスの順序付けが重要ではない場合に、並列 LINQ クエリを作成して実行する基本的なパターンを示しています。</span><span class="sxs-lookup"><span data-stu-id="29e8b-107">This example demonstrates the basic pattern for creating and executing any Parallel LINQ query when the ordering of the result sequence is not important.</span></span> <span data-ttu-id="29e8b-108">通常、順序なしのクエリは、順序ありのクエリより高速です。</span><span class="sxs-lookup"><span data-stu-id="29e8b-108">Unordered queries are generally faster than ordered queries.</span></span> <span data-ttu-id="29e8b-109">このクエリはソースを、複数のスレッドで非同期的に実行した複数のタスクにパーティション分割します。</span><span class="sxs-lookup"><span data-stu-id="29e8b-109">The query partitions the source into tasks that are executed asynchronously on multiple threads.</span></span> <span data-ttu-id="29e8b-110">各タスクが完了する順序は、その特定のパーティションに含まれる要素を処理するために必要な作業量だけでなく、オペレーティング システムが各スレッドをどのようにスケジュールするかといった外部要因にも依存します。</span><span class="sxs-lookup"><span data-stu-id="29e8b-110">The order in which each task completes depends not only on the amount of work involved to process the elements in the partition, but also on external factors such as how the operating system schedules each thread.</span></span> <span data-ttu-id="29e8b-111">この例は、使用方法を示すことを意図したものであるため、同等の順次的な LINQ to Objects クエリほど高速ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29e8b-111">This example is intended to demonstrate usage, and might not run faster than the equivalent sequential LINQ to Objects query.</span></span> <span data-ttu-id="29e8b-112">高速化の詳細については、「[PLINQ での高速化について](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e8b-112">For more information about speedup, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span> <span data-ttu-id="29e8b-113">クエリに含まれる要素の順序を保持する方法の詳細については、「[方法: PLINQ クエリの順序を制御する](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e8b-113">For more information about how to preserve the ordering of elements in a query, see [How to: Control Ordering in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e8b-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="29e8b-114">See also</span></span>

- [<span data-ttu-id="29e8b-115">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="29e8b-115">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)
