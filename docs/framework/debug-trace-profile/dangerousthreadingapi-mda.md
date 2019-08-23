---
title: dangerousThreadingAPI MDA
ms.date: 03/30/2017
helpviewer_keywords:
- suspending threads
- DangerousThreadingAPI MDA
- managed debugging assistants (MDAs), dangerous threading operations
- threading [.NET Framework], suspending
- MDAs (managed debugging assistants), dangerous threading operations
- Suspend method
- threading [.NET Framework], managed debugging assistants
ms.assetid: 3e5efbc5-92e4-4229-b31f-ce368a1adb96
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d635100c4e8214a7a8659c2d3e4da61825cf243
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966306"
---
# <a name="dangerousthreadingapi-mda"></a><span data-ttu-id="42653-102">dangerousThreadingAPI MDA</span><span class="sxs-lookup"><span data-stu-id="42653-102">dangerousThreadingAPI MDA</span></span>
<span data-ttu-id="42653-103">`dangerousThreadingAPI` マネージド デバッグ アシスタント (MDA) は、現在のスレッド以外のスレッドで <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> メソッドが呼び出されるとアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="42653-103">The `dangerousThreadingAPI` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> method is called on a thread other than the current thread.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="42653-104">症状</span><span class="sxs-lookup"><span data-stu-id="42653-104">Symptoms</span></span>  
 <span data-ttu-id="42653-105">アプリケーションがいつまでも応答しないかハングアップしています。</span><span class="sxs-lookup"><span data-stu-id="42653-105">An application is unresponsive or hangs indefinitely.</span></span> <span data-ttu-id="42653-106">システムまたはアプリケーションのデータが一時的に、またはアプリケーションのシャットダウン後も、予期しない状態のままになっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="42653-106">System or application data might be left in an unpredictable state temporarily or even after an application has been shut down.</span></span> <span data-ttu-id="42653-107">一部の操作が予期したとおりに完了していません。</span><span class="sxs-lookup"><span data-stu-id="42653-107">Some operations are not completing as expected.</span></span>  
  
 <span data-ttu-id="42653-108">問題に伴うランダム性により、症状は大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="42653-108">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="42653-109">原因</span><span class="sxs-lookup"><span data-stu-id="42653-109">Cause</span></span>  
 <span data-ttu-id="42653-110">スレッドは、<xref:System.Threading.Thread.Suspend%2A> メソッドを使用する別のスレッドによって非同期に中断されています。</span><span class="sxs-lookup"><span data-stu-id="42653-110">A thread is asynchronously suspended by another thread using the <xref:System.Threading.Thread.Suspend%2A> method.</span></span> <span data-ttu-id="42653-111">操作途中である可能性がある別のスレッドを安全に中断できるタイミングを判断する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="42653-111">There is no way to determine when it is safe to suspend another thread which might be in the middle of an operation.</span></span> <span data-ttu-id="42653-112">スレッドを中断すると、データの破損やインバリアントの中断が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="42653-112">Suspending the thread can result in the corruption of data or the breaking of invariants.</span></span> <span data-ttu-id="42653-113">スレッドが中断状態になっていて、<xref:System.Threading.Thread.Resume%2A> メソッドを使用して再開されないと、アプリケーションのハングアップ状態がいつまでも続き、アプリケーション データが損害を受けることがあります。</span><span class="sxs-lookup"><span data-stu-id="42653-113">Should a thread be placed into a suspended state and never resumed using the <xref:System.Threading.Thread.Resume%2A> method, the application can hang indefinitely and possibly damage application data.</span></span> <span data-ttu-id="42653-114">これらのメソッドは不使用とマークされています。</span><span class="sxs-lookup"><span data-stu-id="42653-114">These methods have been marked as obsolete.</span></span>  
  
 <span data-ttu-id="42653-115">同期プリミティブがターゲット スレッドによって保持されている場合は、中断の間も保持されたままになります。</span><span class="sxs-lookup"><span data-stu-id="42653-115">If synchronization primitives are held by the target thread, they remain held during suspension.</span></span> <span data-ttu-id="42653-116">これにより、<xref:System.Threading.Thread.Suspend%2A> を実行するスレッドなど、別のスレッドがプリミティブのロックを取得しようとすると、デッドロックが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="42653-116">This can lead to deadlocks should another thread, for example the thread performing the <xref:System.Threading.Thread.Suspend%2A>, attempt to acquire a lock on the primitive.</span></span> <span data-ttu-id="42653-117">この場合、問題自体がデッドロックとして現れます。</span><span class="sxs-lookup"><span data-stu-id="42653-117">In this situation, the problem manifests itself as a deadlock.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="42653-118">解決策</span><span class="sxs-lookup"><span data-stu-id="42653-118">Resolution</span></span>  
 <span data-ttu-id="42653-119"><xref:System.Threading.Thread.Suspend%2A> および <xref:System.Threading.Thread.Resume%2A> を使用する必要のある設計を避けます。</span><span class="sxs-lookup"><span data-stu-id="42653-119">Avoid designs that require the use of <xref:System.Threading.Thread.Suspend%2A> and <xref:System.Threading.Thread.Resume%2A>.</span></span> <span data-ttu-id="42653-120">スレッド間の協調では、<xref:System.Threading.Monitor>、<xref:System.Threading.ReaderWriterLock>、<xref:System.Threading.Mutex> などの同期プリミティブや、C# の `lock` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="42653-120">For cooperation between threads, use synchronization primitives such as <xref:System.Threading.Monitor>, <xref:System.Threading.ReaderWriterLock>, <xref:System.Threading.Mutex>, or the C# `lock` statement.</span></span> <span data-ttu-id="42653-121">これらのメソッドを使用する必要がある場合は、時間を短くし、スレッドが中断状態にある間に実行されるコードの量を最小限に留めます。</span><span class="sxs-lookup"><span data-stu-id="42653-121">If you must use these methods, reduce the window of time and minimize the amount of code that executes while the thread is in a suspended state.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="42653-122">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="42653-122">Effect on the Runtime</span></span>  
 <span data-ttu-id="42653-123">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="42653-123">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="42653-124">危険なスレッド処理操作に関するデータを報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="42653-124">It only reports data about dangerous threading operations.</span></span>  
  
## <a name="output"></a><span data-ttu-id="42653-125">Output</span><span class="sxs-lookup"><span data-stu-id="42653-125">Output</span></span>  
 <span data-ttu-id="42653-126">MDA は、アクティブになった原因である危険なスレッド処理メソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="42653-126">The MDA identifies the dangerous threading method that caused it to be activated.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="42653-127">構成</span><span class="sxs-lookup"><span data-stu-id="42653-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dangerousThreadingAPI />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="42653-128">例</span><span class="sxs-lookup"><span data-stu-id="42653-128">Example</span></span>  
 <span data-ttu-id="42653-129">`dangerousThreadingAPI` のアクティブ化の原因となる <xref:System.Threading.Thread.Suspend%2A> メソッド呼び出しのコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="42653-129">The following code example demonstrates a call to the <xref:System.Threading.Thread.Suspend%2A> method that causes the activation of the `dangerousThreadingAPI`.</span></span>  
  
```csharp
using System.Threading;  
void FireMda()  
{  
Thread t = new Thread(delegate() { Thread.Sleep(1000); });  
    t.Start();  
    // The following line activates the MDA.  
    t.Suspend();   
    t.Resume();  
    t.Join();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="42653-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="42653-130">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="42653-131">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="42653-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="42653-132">lock ステートメント</span><span class="sxs-lookup"><span data-stu-id="42653-132">lock Statement</span></span>](../../csharp/language-reference/keywords/lock-statement.md)
