---
title: スレッドの一時中断および中断
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interrupting threads
- threading [.NET Framework], pausing
- pausing threads
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3dcee9c45cdbf029ccba90a963c9cea0a9c7ad4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963574"
---
# <a name="pausing-and-interrupting-threads"></a><span data-ttu-id="5ad69-102">スレッドの一時中断および中断</span><span class="sxs-lookup"><span data-stu-id="5ad69-102">Pausing and interrupting threads</span></span>

<span data-ttu-id="5ad69-103">スレッドの活動を同期する最も一般的な方法は、スレッドのブロックと解放を行うか、コード領域またはオブジェクトをロックすることです。</span><span class="sxs-lookup"><span data-stu-id="5ad69-103">The most common ways to synchronize the activities of threads are to block and release threads, or to lock objects or regions of code.</span></span> <span data-ttu-id="5ad69-104">ロックとブロックのしくみの詳細については、「[同期プリミティブの概要](../../../docs/standard/threading/overview-of-synchronization-primitives.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ad69-104">For more information on these locking and blocking mechanisms, see [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="5ad69-105">また、スレッドそのものをスリープ状態にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ad69-105">You can also have threads put themselves to sleep.</span></span> <span data-ttu-id="5ad69-106">スレッドがブロックされているかまたはスリープ状態の場合は、<xref:System.Threading.ThreadInterruptedException> を使用して待機状態を解除できます。</span><span class="sxs-lookup"><span data-stu-id="5ad69-106">When threads are blocked or sleeping, you can use a <xref:System.Threading.ThreadInterruptedException> to break them out of their wait states.</span></span>  
  
## <a name="the-threadsleep-method"></a><span data-ttu-id="5ad69-107">Thread.Sleep メソッド</span><span class="sxs-lookup"><span data-stu-id="5ad69-107">The Thread.Sleep method</span></span>

 <span data-ttu-id="5ad69-108"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> メソッドを呼び出すと、メソッドに渡した時間の間または数ミリ秒間、現在のスレッドがすぐにブロックされ、残りのタイム スライスは別のスレッドに生成されます。</span><span class="sxs-lookup"><span data-stu-id="5ad69-108">Calling the <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> method causes the current thread to immediately block for the number of milliseconds or the time interval you pass to the method, and yields the remainder of its time slice to another thread.</span></span> <span data-ttu-id="5ad69-109">時間が経過すると、スリープ状態のスレッドは実行を再開します。</span><span class="sxs-lookup"><span data-stu-id="5ad69-109">Once that interval elapses, the sleeping thread resumes execution.</span></span>  
  
 <span data-ttu-id="5ad69-110">もう一方のスレッドが他方のスレッドに対して <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5ad69-110">One thread cannot call <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> on another thread.</span></span>  <span data-ttu-id="5ad69-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> は静的メソッドであり、常に現在のスレッドがスリープ状態になります。</span><span class="sxs-lookup"><span data-stu-id="5ad69-111"><xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is a static method that always causes the current thread to sleep.</span></span>  
  
 <span data-ttu-id="5ad69-112"><xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> の値を指定して <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> を呼び出すと、スリープ状態のスレッドで <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> メソッドを呼び出す別のスレッドによって中断されるか、<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> メソッドの呼び出しによって中止されるまで、スリープ状態になります。</span><span class="sxs-lookup"><span data-stu-id="5ad69-112">Calling <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> with a value of <xref:System.Threading.Timeout.Infinite?displayProperty=nameWithType> causes a thread to sleep until it is interrupted by another thread that calls the  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the sleeping thread, or until it is terminated by a call to its <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method.</span></span>  <span data-ttu-id="5ad69-113">次の例は、スリープ状態のスレッドを中断する両方の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5ad69-113">The following example illustrates both methods of interrupting a sleeping thread.</span></span>  
  
 [!code-csharp[Conceptual.Threading.Resuming#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Threading.Resuming/cs/Sleep1.cs#1)]
 [!code-vb[Conceptual.Threading.Resuming#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Threading.Resuming/vb/Sleep1.vb#1)]  
  
## <a name="interrupting-threads"></a><span data-ttu-id="5ad69-114">スレッドの中断</span><span class="sxs-lookup"><span data-stu-id="5ad69-114">Interrupting threads</span></span>

 <span data-ttu-id="5ad69-115">待機中のスレッドを中断するには、ブロックされているスレッドに対して <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> メソッドを呼び出して <xref:System.Threading.ThreadInterruptedException> をスローさせます。これにより、スレッドは中断され、ブロックしている呼び出しから抜け出します。</span><span class="sxs-lookup"><span data-stu-id="5ad69-115">You can interrupt a waiting thread by calling the <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> method on the blocked thread to throw a <xref:System.Threading.ThreadInterruptedException>, which breaks the thread out of the blocking call.</span></span> <span data-ttu-id="5ad69-116">スレッドは、<xref:System.Threading.ThreadInterruptedException> をキャッチし、操作を継続するために適切な処理を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad69-116">The thread should catch the <xref:System.Threading.ThreadInterruptedException> and do whatever is appropriate to continue working.</span></span> <span data-ttu-id="5ad69-117">スレッドがこの例外を無視した場合は、ランタイムがこの例外をキャッチし、そのスレッドを停止します。</span><span class="sxs-lookup"><span data-stu-id="5ad69-117">If the thread ignores the exception, the runtime catches the exception and stops the thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5ad69-118"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> が呼び出されたときに対象となるスレッドがブロックされていない場合、スレッドはブロックされるまで中断されません。</span><span class="sxs-lookup"><span data-stu-id="5ad69-118">If the target thread is not blocked when <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> is called, the thread is not interrupted until it blocks.</span></span> <span data-ttu-id="5ad69-119">スレッドがまったくブロックされない場合は、中断されることなく完了することがあります。</span><span class="sxs-lookup"><span data-stu-id="5ad69-119">If the thread never blocks, it could complete without ever being interrupted.</span></span>  
  
 <span data-ttu-id="5ad69-120">待機がマネージド待機である場合、<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> と <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> はどちらもすぐにスレッドを起動します。</span><span class="sxs-lookup"><span data-stu-id="5ad69-120">If a wait is a managed wait, then <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> and <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> both wake the thread immediately.</span></span> <span data-ttu-id="5ad69-121">待機がアンマネージ待機の場合 (プラットフォームが Win32 [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) 関数を呼び出した場合など)、<xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> と <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> はどちらも、スレッドがマネージド コードに戻るか、またはマネージド コードを呼び出すまで、そのスレッドを制御できません。</span><span class="sxs-lookup"><span data-stu-id="5ad69-121">If a wait is an unmanaged wait (for example, a platform invoke call to the Win32 [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) function), neither <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> nor <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> can take control of the thread until it returns to or calls into managed code.</span></span> <span data-ttu-id="5ad69-122">マネージド コードの動作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5ad69-122">In managed code, the behavior is as follows:</span></span>  
  
- <span data-ttu-id="5ad69-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> はスレッドをどのような待機からも起動し、これによって起動先のスレッドで <xref:System.Threading.ThreadInterruptedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5ad69-123"><xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadInterruptedException> to be thrown in the destination thread.</span></span>  
  
- <span data-ttu-id="5ad69-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> はスレッドをどのような待機からも起動し、これによってスレッドで <xref:System.Threading.ThreadAbortException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5ad69-124"><xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> wakes a thread out of any wait it might be in and causes a <xref:System.Threading.ThreadAbortException> to be thrown on the thread.</span></span> <span data-ttu-id="5ad69-125">詳細については、「[スレッドの破棄](../../../docs/standard/threading/destroying-threads.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ad69-125">For details, see [Destroying Threads](../../../docs/standard/threading/destroying-threads.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ad69-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ad69-126">See also</span></span>

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadInterruptedException>
- <xref:System.Threading.ThreadAbortException>
- [<span data-ttu-id="5ad69-127">スレッド化</span><span class="sxs-lookup"><span data-stu-id="5ad69-127">Threading</span></span>](../../../docs/standard/threading/index.md)
- [<span data-ttu-id="5ad69-128">スレッドの使用とスレッド処理</span><span class="sxs-lookup"><span data-stu-id="5ad69-128">Using Threads and Threading</span></span>](../../../docs/standard/threading/using-threads-and-threading.md)
- [<span data-ttu-id="5ad69-129">同期プリミティブの概要</span><span class="sxs-lookup"><span data-stu-id="5ad69-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
