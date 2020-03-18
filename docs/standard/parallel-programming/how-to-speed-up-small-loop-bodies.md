---
title: '方法: 小さいループ本体を高速化する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to speed up
ms.assetid: c7a66677-cb59-4cbf-969a-d2e8fc61a6ce
ms.openlocfilehash: 29d7fa8200ddd972c1a5c98ea6f30a7c8ff732e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139747"
---
# <a name="how-to-speed-up-small-loop-bodies"></a><span data-ttu-id="ac9c5-102">方法: 小さいループ本体を高速化する</span><span class="sxs-lookup"><span data-stu-id="ac9c5-102">How to: Speed Up Small Loop Bodies</span></span>
<span data-ttu-id="ac9c5-103"><xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> ループの本体が小さい場合、[for](../../csharp/language-reference/keywords/for.md) ループ (C#)、[For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) ループ (Visual Basic) など、同等の連続したループよりパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac9c5-103">When a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop has a small body, it might perform more slowly than the equivalent sequential loop, such as the [for](../../csharp/language-reference/keywords/for.md) loop in C# and the [For](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/44kykk21(v=vs.90)) loop in Visual Basic.</span></span> <span data-ttu-id="ac9c5-104">パフォーマンスの低下は、データのパーティション分割と、各ループのイテレーションでデリゲートを呼び出す負荷によって発生します。</span><span class="sxs-lookup"><span data-stu-id="ac9c5-104">Slower performance is caused by the overhead involved in partitioning the data and the cost of invoking a delegate on each loop iteration.</span></span> <span data-ttu-id="ac9c5-105">このようなシナリオに対処するため、<xref:System.Collections.Concurrent.Partitioner> クラスには <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> メソッドが用意されています。このメソッドにより、デリゲートがイテレーションごとに 1 回ではなく、パーティションごとに 1 回だけ呼び出されるように、デリゲートの本体に順次ループを提供できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac9c5-105">To address such scenarios, the <xref:System.Collections.Concurrent.Partitioner> class provides the <xref:System.Collections.Concurrent.Partitioner.Create%2A?displayProperty=nameWithType> method, which enables you to provide a sequential loop for the delegate body, so that the delegate is invoked only once per partition, instead of once per iteration.</span></span> <span data-ttu-id="ac9c5-106">詳細については、「[Custom Partitioners for PLINQ and TPL (PLINQ および TPL 用のカスタム パーティショナー)](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac9c5-106">For more information, see [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac9c5-107">例</span><span class="sxs-lookup"><span data-stu-id="ac9c5-107">Example</span></span>  
 [!code-csharp[TPL_Partitioners#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner01.cs#01)]
 [!code-vb[TPL_Partitioners#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/partitionercreate01.vb#01)]  
  
 <span data-ttu-id="ac9c5-108">この例で示す方法は、ループが最小限の作業を実行するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="ac9c5-108">The approach demonstrated in this example is useful when the loop performs a minimal amount of work.</span></span> <span data-ttu-id="ac9c5-109">作業がより負荷の大きい処理になるにつれ、既定のパーティショナーで <xref:System.Threading.Tasks.Parallel.For%2A> ループまたは <xref:System.Threading.Tasks.Parallel.ForEach%2A> ループを使用すると、同じまたはそれ以上のパフォーマンスが得られることがあります。</span><span class="sxs-lookup"><span data-stu-id="ac9c5-109">As the work becomes more computationally expensive, you will probably get the same or better performance by using a <xref:System.Threading.Tasks.Parallel.For%2A> or <xref:System.Threading.Tasks.Parallel.ForEach%2A> loop with the default partitioner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9c5-110">参照</span><span class="sxs-lookup"><span data-stu-id="ac9c5-110">See also</span></span>

- [<span data-ttu-id="ac9c5-111">データの並列化</span><span class="sxs-lookup"><span data-stu-id="ac9c5-111">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="ac9c5-112">PLINQ および TPL 用のカスタム パーティショナー</span><span class="sxs-lookup"><span data-stu-id="ac9c5-112">Custom Partitioners for PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
- [<span data-ttu-id="ac9c5-113">反復子 (C#)</span><span class="sxs-lookup"><span data-stu-id="ac9c5-113">Iterators (C#)</span></span>](../../csharp/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="ac9c5-114">反復子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac9c5-114">Iterators (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/iterators.md)
- [<span data-ttu-id="ac9c5-115">PLINQ および TPL のラムダ式</span><span class="sxs-lookup"><span data-stu-id="ac9c5-115">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
