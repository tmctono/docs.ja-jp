---
title: asynchronousThreadAbort MDA
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9bde6f6e625476712c5af516491ab9dd29b7dea3
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052959"
---
# <a name="asynchronousthreadabort-mda"></a><span data-ttu-id="37c8f-102">asynchronousThreadAbort MDA</span><span class="sxs-lookup"><span data-stu-id="37c8f-102">asynchronousThreadAbort MDA</span></span>
<span data-ttu-id="37c8f-103">`asynchronousThreadAbort` マネージド デバッグ アシスタント (MDA) は、スレッドが別のスレッドに非同期の中止処理を適用しようとするとアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-103">The `asynchronousThreadAbort` managed debugging assistant (MDA) is activated when a thread attempts to introduce an asynchronous abort into another thread.</span></span> <span data-ttu-id="37c8f-104">同期のスレッド中止では、`asynchronousThreadAbort` MDA はアクティブになりません。</span><span class="sxs-lookup"><span data-stu-id="37c8f-104">Synchronous thread aborts do not activate the `asynchronousThreadAbort` MDA.</span></span>

## <a name="symptoms"></a><span data-ttu-id="37c8f-105">症状</span><span class="sxs-lookup"><span data-stu-id="37c8f-105">Symptoms</span></span>
 <span data-ttu-id="37c8f-106">メインのアプリケーション スレッドが中止されると、アプリケーションは未処理の <xref:System.Threading.ThreadAbortException> でクラッシュします。</span><span class="sxs-lookup"><span data-stu-id="37c8f-106">An application crashes with an unhandled <xref:System.Threading.ThreadAbortException> when the main application thread is aborted.</span></span> <span data-ttu-id="37c8f-107">アプリケーションが実行を続けると、アプリケーションがクラッシュした場合よりも悪い結果が生じ、さらにデータが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-107">If the application were to continue to execute, the consequences might be worse than the application crashing, possibly resulting in further data corruption.</span></span>

 <span data-ttu-id="37c8f-108">不可分であるべき操作が部分的に完了した後で中断された可能性があり、アプリケーション データは予測不能な状態のままになっています。</span><span class="sxs-lookup"><span data-stu-id="37c8f-108">Operations meant to be atomic have likely been interrupted after partial completion, leaving application data in an unpredictable state.</span></span> <span data-ttu-id="37c8f-109"><xref:System.Threading.ThreadAbortException> は、コードの実行中に見かけ上はランダムなポイントから生成でき、例外の発生が予期されていない場所で生成されることもよくあります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-109">A <xref:System.Threading.ThreadAbortException> can be generated from seemingly random points in the execution of code, often in places from which an exception is not expected to arise.</span></span> <span data-ttu-id="37c8f-110">コードはこのような例外を処理できない場合があるため、破損した状態になります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-110">The code might not be capable of handling such an exception, resulting in a corrupt state.</span></span>

 <span data-ttu-id="37c8f-111">問題に伴うランダム性により、症状は大きく異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-111">Symptoms can vary widely due to the randomness inherent to the problem.</span></span>

## <a name="cause"></a><span data-ttu-id="37c8f-112">原因</span><span class="sxs-lookup"><span data-stu-id="37c8f-112">Cause</span></span>
 <span data-ttu-id="37c8f-113">あるスレッドのコードが、対象スレッドで <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> メソッドを呼び出したため、非同期のスレッド中止が発生しました。</span><span class="sxs-lookup"><span data-stu-id="37c8f-113">Code in one thread called the <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> method on a target thread to introduce an asynchronous thread abort.</span></span> <span data-ttu-id="37c8f-114"><xref:System.Threading.Thread.Abort%2A> への呼び出しを実行するコードは、中止操作の対象スレッドとは異なるため、スレッド中止は非同期になります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-114">The thread abort is asynchronous because the code that makes the call to <xref:System.Threading.Thread.Abort%2A> is running on a different thread than the target of the abort operation.</span></span> <span data-ttu-id="37c8f-115">同期のスレッド中止の場合、<xref:System.Threading.Thread.Abort%2A> を実行するスレッドがこの操作を実行するのは、アプリケーション状態に一貫性がある安全なチェックポイントのみであるため、問題になりません。</span><span class="sxs-lookup"><span data-stu-id="37c8f-115">Synchronous thread aborts should not cause a problem because the thread performing the <xref:System.Threading.Thread.Abort%2A> should have done so only at a safe checkpoint where application state is consistent.</span></span>

 <span data-ttu-id="37c8f-116">非同期のスレッド中止は、対象スレッドの実行中に予期しないポイントで処理されるため、問題になります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-116">Asynchronous thread aborts present a problem because they are processed at unpredictable points in the target thread's execution.</span></span> <span data-ttu-id="37c8f-117">これを回避するには、この方法で中止される可能性のあるスレッドで実行するように作成されたコードでは、ほとんどすべてのコード行で <xref:System.Threading.ThreadAbortException> を処理し、アプリケーション データを一貫性のある状態に戻せるように気を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-117">To avoid this, code written to run on a thread that might be aborted in this manner would need to handle a <xref:System.Threading.ThreadAbortException> at almost every line of code, taking care to put application data back into a consistent state.</span></span> <span data-ttu-id="37c8f-118">コードがこの問題を考慮して作成されることを想定したり、起こりうるすべての状況に対処するコードを作成したりすることは、現実的ではありません。</span><span class="sxs-lookup"><span data-stu-id="37c8f-118">It is not realistic to expect code to be written with this problem in mind or to write code that protects against all possible circumstances.</span></span>

 <span data-ttu-id="37c8f-119">アンマネージ コードの呼び出しと `finally` ブロックは非同期に中止されませんが、これらのカテゴリのいずれかから終了するとすぐに中止されます。</span><span class="sxs-lookup"><span data-stu-id="37c8f-119">Calls into unmanaged code and `finally` blocks will not be aborted asynchronously but immediately upon exit from one of these categories.</span></span>

 <span data-ttu-id="37c8f-120">問題に伴うランダム性により、原因を特定することが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-120">The cause might be difficult to determine due to the randomness inherent to the problem.</span></span>

## <a name="resolution"></a><span data-ttu-id="37c8f-121">解決策</span><span class="sxs-lookup"><span data-stu-id="37c8f-121">Resolution</span></span>
 <span data-ttu-id="37c8f-122">非同期のスレッド中止を使用する必要があるコード設計を避けます。</span><span class="sxs-lookup"><span data-stu-id="37c8f-122">Avoid code design that requires the use of asynchronous thread aborts.</span></span> <span data-ttu-id="37c8f-123"><xref:System.Threading.Thread.Abort%2A> の呼び出しを必要としない対象スレッドを中断するのにより適した方法はいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="37c8f-123">There are several approaches more appropriate for interruption of a target thread that do not require a call to <xref:System.Threading.Thread.Abort%2A>.</span></span> <span data-ttu-id="37c8f-124">最も安全な方法は、対象スレッドの中断要求をシグナル通知する、共通プロパティなどの機構を導入することです。</span><span class="sxs-lookup"><span data-stu-id="37c8f-124">The safest is to introduce a mechanism, such as a common property, that signals the target thread to request an interrupt.</span></span> <span data-ttu-id="37c8f-125">対象スレッドは、特定の安全なチェックポイントでシグナルをチェックします。</span><span class="sxs-lookup"><span data-stu-id="37c8f-125">The target thread checks the signal at certain safe checkpoints.</span></span> <span data-ttu-id="37c8f-126">中断が要求されたことが示されている場合は、適切にシャットダウンできます。</span><span class="sxs-lookup"><span data-stu-id="37c8f-126">If it notices that an interrupt has been requested, it can shut down gracefully.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="37c8f-127">ランタイムへの影響</span><span class="sxs-lookup"><span data-stu-id="37c8f-127">Effect on the Runtime</span></span>
 <span data-ttu-id="37c8f-128">この MDA は CLR に影響しません。</span><span class="sxs-lookup"><span data-stu-id="37c8f-128">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="37c8f-129">非同期のスレッド中止に関するデータを報告するだけです。</span><span class="sxs-lookup"><span data-stu-id="37c8f-129">It only reports data about asynchronous thread aborts.</span></span>

## <a name="output"></a><span data-ttu-id="37c8f-130">出力</span><span class="sxs-lookup"><span data-stu-id="37c8f-130">Output</span></span>
 <span data-ttu-id="37c8f-131">MDA は、中止を実行するスレッドの ID、および中止の対象となるスレッドの ID を報告します。</span><span class="sxs-lookup"><span data-stu-id="37c8f-131">The MDA reports the ID of the thread performing the abort and the ID of the thread that is the target of the abort.</span></span> <span data-ttu-id="37c8f-132">これは非同期の中止に限られるため、これらが同じになることはありません。</span><span class="sxs-lookup"><span data-stu-id="37c8f-132">These will never be the same because this is limited to asynchronous aborts.</span></span>

## <a name="configuration"></a><span data-ttu-id="37c8f-133">構成</span><span class="sxs-lookup"><span data-stu-id="37c8f-133">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a><span data-ttu-id="37c8f-134">例</span><span class="sxs-lookup"><span data-stu-id="37c8f-134">Example</span></span>
 <span data-ttu-id="37c8f-135">`asynchronousThreadAbort` MDA をアクティブにする場合、単独の実行スレッドで <xref:System.Threading.Thread.Abort%2A> を呼び出すだけです。</span><span class="sxs-lookup"><span data-stu-id="37c8f-135">Activating the `asynchronousThreadAbort` MDA requires only a call to <xref:System.Threading.Thread.Abort%2A> on a separate running thread.</span></span> <span data-ttu-id="37c8f-136">スレッドの開始関数の内容が、中止によって任意の時点に中断される可能性のある、より複雑な一連の操作である場合は、その結果を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="37c8f-136">Consider the consequences if the contents of the thread start function were a set of more complex operations which might be interrupted at any arbitrary point by the abort.</span></span>

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a><span data-ttu-id="37c8f-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="37c8f-137">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="37c8f-138">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="37c8f-138">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
