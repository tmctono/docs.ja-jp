---
title: スレッド処理オブジェクトと機能
ms.date: 10/01/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
ms.openlocfilehash: dd9b7b8cb194353d0a1c285af10d54dc7366896e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128968"
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="42fc8-102">スレッド処理オブジェクトと機能</span><span class="sxs-lookup"><span data-stu-id="42fc8-102">Threading objects and features</span></span>

<span data-ttu-id="42fc8-103">.NET では、<xref:System.Threading.Thread?displayProperty=nameWithType> クラスの他に、マルチ スレッド アプリケーションを開発するのに役立つ複数のクラスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="42fc8-103">Along with the <xref:System.Threading.Thread?displayProperty=nameWithType> class, .NET provides a number of classes that help you develop multithreaded applications.</span></span> <span data-ttu-id="42fc8-104">次の記事では、それらのクラスの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-104">The following articles provide overview of those classes:</span></span>

|<span data-ttu-id="42fc8-105">Title</span><span class="sxs-lookup"><span data-stu-id="42fc8-105">Title</span></span>|<span data-ttu-id="42fc8-106">説明</span><span class="sxs-lookup"><span data-stu-id="42fc8-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="42fc8-107">マネージド スレッド プール</span><span class="sxs-lookup"><span data-stu-id="42fc8-107">The managed thread pool</span></span>](the-managed-thread-pool.md)|<span data-ttu-id="42fc8-108">.NET によって管理されるワーカー スレッドのプールを提供する <xref:System.Threading.ThreadPool?displayProperty=nameWithType> について説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-108">Describes the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> class, which provides a pool of worker threads that are managed by .NET.</span></span>|  
|[<span data-ttu-id="42fc8-109">タイマー</span><span class="sxs-lookup"><span data-stu-id="42fc8-109">Timers</span></span>](timers.md)|<span data-ttu-id="42fc8-110">マルチスレッド環境で使用できる .NET タイマーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-110">Describes .NET timers that can be used in a multithreaded environment.</span></span>|
|[<span data-ttu-id="42fc8-111">同期プリミティブの概要</span><span class="sxs-lookup"><span data-stu-id="42fc8-111">Overview of synchronization primitives</span></span>](overview-of-synchronization-primitives.md)|<span data-ttu-id="42fc8-112">共有リソースへのアクセスを同期化する場合や、スレッドの相互作用を制御する場合に使用できる型について説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-112">Describes types that can be used to synchronize access to a shared resource or control thread interaction.</span></span>|
|[<span data-ttu-id="42fc8-113">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="42fc8-113">EventWaitHandle</span></span>](eventwaithandle.md)|<span data-ttu-id="42fc8-114">スレッドの同期イベントを表す <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-114">Describes the <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType> class, which represents a thread synchronization event.</span></span>|
|[<span data-ttu-id="42fc8-115">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="42fc8-115">CountdownEvent</span></span>](countdownevent.md)|<span data-ttu-id="42fc8-116">そのカウントがゼロのときに設定されるスレッド同期イベントを表す <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-116">Describes the <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> class, which represents a thread synchronization event that becomes set when its count is zero.</span></span>|
|[<span data-ttu-id="42fc8-117">ミューテックス</span><span class="sxs-lookup"><span data-stu-id="42fc8-117">Mutexes</span></span>](mutexes.md)|<span data-ttu-id="42fc8-118">共有リソースへの排他アクセスを付与する <xref:System.Threading.Mutex?displayProperty=nameWithType> クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-118">Describes the <xref:System.Threading.Mutex?displayProperty=nameWithType> class, which grants exclusive access to a shared resource.</span></span>|
|[<span data-ttu-id="42fc8-119">Semaphore と SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="42fc8-119">Semaphore and SemaphoreSlim</span></span>](semaphore-and-semaphoreslim.md)|<span data-ttu-id="42fc8-120">共有リソースまたはリソースのプールに同時にアクセスできるスレッドの数を制限する <xref:System.Threading.Semaphore?displayProperty=nameWithType> について説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-120">Describes the <xref:System.Threading.Semaphore?displayProperty=nameWithType> class, which limits number of threads that can access a shared resource or a pool of resources concurrently.</span></span>|
|[<span data-ttu-id="42fc8-121">バリア</span><span class="sxs-lookup"><span data-stu-id="42fc8-121">Barrier</span></span>](barrier.md)|<span data-ttu-id="42fc8-122">段階的な操作におけるスレッドの調整のためのバリア パターンを実装する <xref:System.Threading.Barrier?displayProperty=nameWithType> クラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-122">Describes the <xref:System.Threading.Barrier?displayProperty=nameWithType> class, which implements the barrier pattern for coordination of threads in phased operations.</span></span>|
|[<span data-ttu-id="42fc8-123">SpinLock</span><span class="sxs-lookup"><span data-stu-id="42fc8-123">SpinLock</span></span>](spinlock.md)|<span data-ttu-id="42fc8-124">特定の下位レベルのシナリオで <xref:System.Threading.Monitor?displayProperty=nameWithType> ロックの代わりに軽量クラスとして使用できる <xref:System.Threading.SpinLock?displayProperty=nameWithType> 構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-124">Describes the <xref:System.Threading.SpinLock?displayProperty=nameWithType> structure, which is a lightweight alternative to the <xref:System.Threading.Monitor?displayProperty=nameWithType> class for certain low-level locking scenarios.</span></span>|
|[<span data-ttu-id="42fc8-125">SpinWait</span><span class="sxs-lookup"><span data-stu-id="42fc8-125">SpinWait</span></span>](spinwait.md)|<span data-ttu-id="42fc8-126">スピンベースの待機のサポートを提供する <xref:System.Threading.SpinWait?displayProperty=nameWithType> 構造体について説明します。</span><span class="sxs-lookup"><span data-stu-id="42fc8-126">Describes the <xref:System.Threading.SpinWait?displayProperty=nameWithType> structure, which provides support for spin-based waiting.</span></span>|

## <a name="see-also"></a><span data-ttu-id="42fc8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="42fc8-127">See also</span></span>

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- <xref:System.ComponentModel.BackgroundWorker?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>
- [<span data-ttu-id="42fc8-128">スレッドの使用とスレッド処理</span><span class="sxs-lookup"><span data-stu-id="42fc8-128">Using threads and threading</span></span>](using-threads-and-threading.md)
- [<span data-ttu-id="42fc8-129">非同期ファイル I/O</span><span class="sxs-lookup"><span data-stu-id="42fc8-129">Asynchronous File I/O</span></span>](../io/asynchronous-file-i-o.md)
- [<span data-ttu-id="42fc8-130">並列プログラミング</span><span class="sxs-lookup"><span data-stu-id="42fc8-130">Parallel Programming</span></span>](../parallel-programming/index.md)
- [<span data-ttu-id="42fc8-131">タスク並列ライブラリ (TPL)</span><span class="sxs-lookup"><span data-stu-id="42fc8-131">Task Parallel Library (TPL)</span></span>](../parallel-programming/task-parallel-library-tpl.md)
