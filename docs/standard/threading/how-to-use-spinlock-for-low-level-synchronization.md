---
title: '方法: 下位レベルの同期に SpinLock を使用する'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
ms.openlocfilehash: ad254cb6208bff868e5fc689c502b7ddcc175ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137963"
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a><span data-ttu-id="b35a5-102">方法: 下位レベルの同期に SpinLock を使用する</span><span class="sxs-lookup"><span data-stu-id="b35a5-102">How to: use SpinLock for low-level synchronization</span></span>

<span data-ttu-id="b35a5-103"><xref:System.Threading.SpinLock> の使用例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b35a5-103">The following example demonstrates how to use a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="b35a5-104">この例では、クリティカル セクションが実行する作業量は最小限であるため、<xref:System.Threading.SpinLock> に適しています。</span><span class="sxs-lookup"><span data-stu-id="b35a5-104">In this example, the critical section performs a minimal amount of work, which makes it a good candidate for a <xref:System.Threading.SpinLock>.</span></span> <span data-ttu-id="b35a5-105">作業量を少し増やすと、標準ロックと比較して <xref:System.Threading.SpinLock> のパフォーマンスは高まります。</span><span class="sxs-lookup"><span data-stu-id="b35a5-105">Increasing the work a small amount increases the performance of the <xref:System.Threading.SpinLock> compared to a standard lock.</span></span> <span data-ttu-id="b35a5-106">ただし、SpinLock が標準ロックよりも高負荷になるポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="b35a5-106">However, there is a point at which a SpinLock becomes more expensive than a standard lock.</span></span> <span data-ttu-id="b35a5-107">プロファイリング ツールでコンカレンシープロファイリング機能を使用して、どのタイプのロックを使用すればプログラムのパフォーマンスが高まるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b35a5-107">You can use the concurrency profiling functionality in the profiling tools to see which type of lock provides better performance in your program.</span></span> <span data-ttu-id="b35a5-108">詳細については、「[コンカレンシー ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35a5-108">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <span data-ttu-id="b35a5-109"><xref:System.Threading.SpinLock> は、共有リソースのロックが非常に長い期間使用されない場合に有用なことがあります。</span><span class="sxs-lookup"><span data-stu-id="b35a5-109"><xref:System.Threading.SpinLock> might be useful when a lock on a shared resource is not going to be held for very long.</span></span> <span data-ttu-id="b35a5-110">そのような場合、マルチコア コンピューターでは、ロックが解除されるまで数回のサイクルの間、ブロックされたスレッドをスピンさせると効率が高まることがあります。</span><span class="sxs-lookup"><span data-stu-id="b35a5-110">In such cases, on multi-core computers it can be efficient for the blocked thread to spin for a few cycles until the lock is released.</span></span> <span data-ttu-id="b35a5-111">スピンするとスレッドはブロックされなくなりますが、これは CPU 負荷の高いプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b35a5-111">By spinning, the thread does not become blocked, which is a CPU-intensive process.</span></span> <span data-ttu-id="b35a5-112">ハイパースレッディングを使用するシステムでは、<xref:System.Threading.SpinLock> は特定の状況でスピンを停止して、論理プロセッサの不足や優先順位の逆転が発生するのを回避します。</span><span class="sxs-lookup"><span data-stu-id="b35a5-112"><xref:System.Threading.SpinLock> will stop spinning under certain conditions to prevent starvation of logical processors or priority inversion on systems with Hyper-Threading.</span></span>  
  
 <span data-ttu-id="b35a5-113">この例では、<xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> クラスを使用するため、マルチスレッド アクセスにはユーザーによる同期が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b35a5-113">This example uses the <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> class, which requires user synchronization for multi-threaded access.</span></span> <span data-ttu-id="b35a5-114">.NET Framework Version 4 をターゲットにしているアプリケーションでは、ユーザーのロックが不要な <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b35a5-114">In applications that target the .NET Framework version 4, another option is to use the <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, which does not require any user locks.</span></span>  
  
 <span data-ttu-id="b35a5-115">`false` の呼び出しに `False` (Visual Basic では <xref:System.Threading.SpinLock.Exit%2A?displayProperty=nameWithType>) が使用されていることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="b35a5-115">Note the use of `false` (`False` in Visual Basic) in the call to <xref:System.Threading.SpinLock.Exit%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b35a5-116">これにより、最適なパフォーマンスを得られます。</span><span class="sxs-lookup"><span data-stu-id="b35a5-116">This provides the best performance.</span></span> <span data-ttu-id="b35a5-117">メモリ フェンスを使用するには、IA64 アーキテクチャで `true` (Visual Basic では `True`) を指定します。これにより、書き込みバッファーがフラッシュされるので、ロックを使用して他のスレッドを終了できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b35a5-117">Specify `true` (`True` in Visual Basic) on IA64 architectures to use the memory fence, which flushes the write buffers to ensure that the lock is now available for other threads to exit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35a5-118">参照</span><span class="sxs-lookup"><span data-stu-id="b35a5-118">See also</span></span>

- [<span data-ttu-id="b35a5-119">スレッド処理オブジェクトと機能</span><span class="sxs-lookup"><span data-stu-id="b35a5-119">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="b35a5-120">lock ステートメント (C#)</span><span class="sxs-lookup"><span data-stu-id="b35a5-120">lock statement (C#)</span></span>](../../csharp/language-reference/keywords/lock-statement.md)
- [<span data-ttu-id="b35a5-121">SyncLock ステートメント (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b35a5-121">SyncLock statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/synclock-statement.md)
