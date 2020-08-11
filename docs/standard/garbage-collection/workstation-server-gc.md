---
title: ワークステーションとサーバーのガベージ コレクション (GC)
description: .NET でのワークステーションとサーバーのガベージ コレクションについて説明します。
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, workstation
- garbage collection, server
- workstation garbage collection
- server garbage collection
ms.openlocfilehash: 640b5f42c1f841c2537284e4721e827248e3d300
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "87917010"
---
# <a name="workstation-and-server-garbage-collection"></a><span data-ttu-id="3958a-103">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="3958a-103">Workstation and server garbage collection</span></span>

<span data-ttu-id="3958a-104">ガベージ コレクターは、さまざまなシナリオに対応できるように自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="3958a-104">The garbage collector is self-tuning and can work in a wide variety of scenarios.</span></span> <span data-ttu-id="3958a-105">ただし、作業負荷の特性に基づいて[ガベージ コレクションの種類を設定](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection)できます。</span><span class="sxs-lookup"><span data-stu-id="3958a-105">However, you can [set the type of garbage collection](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) based on the characteristics of the workload.</span></span> <span data-ttu-id="3958a-106">CLR には、次の種類のガベージ コレクションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3958a-106">The CLR provides the following types of garbage collection:</span></span>

- <span data-ttu-id="3958a-107">ワークステーションのガベージ コレクション (GC)。これは、クライアント アプリ向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="3958a-107">Workstation garbage collection (GC), which is designed for client apps.</span></span> <span data-ttu-id="3958a-108">これはスタンドアロン アプリの既定の GC フレーバーです。</span><span class="sxs-lookup"><span data-stu-id="3958a-108">It's the default GC flavor for standalone apps.</span></span> <span data-ttu-id="3958a-109">ホストされているアプリ (ASP.NET によってホストされるアプリなど) の場合、ホストにより既定の GC フレーバーが決定されます。</span><span class="sxs-lookup"><span data-stu-id="3958a-109">For hosted apps, for example, those hosted by ASP.NET, the host determines the default GC flavor.</span></span>

  <span data-ttu-id="3958a-110">ワークステーションのガベージ コレクションは、同時実行または非同時実行のどちらかで実行できます。</span><span class="sxs-lookup"><span data-stu-id="3958a-110">Workstation garbage collection can be concurrent or non-concurrent.</span></span> <span data-ttu-id="3958a-111">同時実行 (または "*バックグラウンド*") ガベージ コレクションでは、ガベージ コレクションの実行中にマネージド スレッドの操作を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="3958a-111">Concurrent (or *background*) garbage collection enables managed threads to continue operations during a garbage collection.</span></span> <span data-ttu-id="3958a-112">.NET Framework 4 以降では、[同時実行ガベージ コレクション](background-gc.md#concurrent-garbage-collection)は、[バックグラウンド ガベージ コレクション](background-gc.md)に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="3958a-112">[Background garbage collection](background-gc.md) replaces [concurrent garbage collection](background-gc.md#concurrent-garbage-collection) in .NET Framework 4 and later versions.</span></span>

- <span data-ttu-id="3958a-113">サーバーのガベージ コレクション。高いスループットとスケーラビリティが必要なサーバー アプリケーションを対象としたオプションです。</span><span class="sxs-lookup"><span data-stu-id="3958a-113">Server garbage collection, which is intended for server applications that need high throughput and scalability.</span></span>

  - <span data-ttu-id="3958a-114">.NET Core では、サーバーのガベージ コレクションは、非同時実行ガベージ コレクションまたはバックグラウンド ガベージ コレクションである場合があります。</span><span class="sxs-lookup"><span data-stu-id="3958a-114">In .NET Core, server garbage collection can be non-concurrent or background.</span></span>

  - <span data-ttu-id="3958a-115">.NET Framework 4.5 以降のバージョンでは、サーバーのガベージ コレクションは、非同時実行またはバックグラウンドである場合があります。</span><span class="sxs-lookup"><span data-stu-id="3958a-115">In .NET Framework 4.5 and later versions, server garbage collection can be non-concurrent or background.</span></span> <span data-ttu-id="3958a-116">.NET Framework 4 以前のバージョンでは、サーバー ガベージ コレクションは非同時実行になります。</span><span class="sxs-lookup"><span data-stu-id="3958a-116">In .NET Framework 4 and previous versions, server garbage collection is non-concurrent.</span></span>

<span data-ttu-id="3958a-117">次の図は、サーバー上でガベージ コレクションを実行する専用のスレッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="3958a-117">The following illustration shows the dedicated threads that perform the garbage collection on a server:</span></span>

![サーバー ガベージ コレクションのスレッド](media/gc-server.png)

## <a name="performance-considerations"></a><span data-ttu-id="3958a-119">パフォーマンスに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3958a-119">Performance considerations</span></span>

### <a name="workstation-gc"></a><span data-ttu-id="3958a-120">ワークステーションの GC</span><span class="sxs-lookup"><span data-stu-id="3958a-120">Workstation GC</span></span>

<span data-ttu-id="3958a-121">ワークステーションのガベージ コレクションにおける、スレッド処理とパフォーマンスについての注意点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3958a-121">The following are threading and performance considerations for workstation garbage collection:</span></span>

- <span data-ttu-id="3958a-122">コレクションは、ガベージ コレクションをトリガーしたユーザー スレッドで、それと同じ優先順位で実行されます。</span><span class="sxs-lookup"><span data-stu-id="3958a-122">The collection occurs on the user thread that triggered the garbage collection and remains at the same priority.</span></span> <span data-ttu-id="3958a-123">ユーザー スレッドは一般に通常の優先順位で実行されるため、その場合 (通常の優先順位のスレッドで実行された場合)、ガベージ コレクターの CPU 時間が他のスレッドと競合します。</span><span class="sxs-lookup"><span data-stu-id="3958a-123">Because user threads typically run at normal priority, the garbage collector (which runs on a normal priority thread) must compete with other threads for CPU time.</span></span> <span data-ttu-id="3958a-124">(ネイティブ コードを実行するスレッドは、サーバーまたはワークステーションのガベージ コレクションでは中断されません)</span><span class="sxs-lookup"><span data-stu-id="3958a-124">(Threads that run native code are not suspended on either server or workstation garbage collection.)</span></span>

- <span data-ttu-id="3958a-125">プロセッサが 1 つしかないコンピューターでは、[構成設定](../../core/run-time-config/garbage-collector.md#workstation-vs-server)に関係なく、常にワークステーションのガベージ コレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3958a-125">Workstation garbage collection is always used on a computer that has only one processor, regardless of the [configuration setting](../../core/run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

### <a name="server-gc"></a><span data-ttu-id="3958a-126">サーバーの GC</span><span class="sxs-lookup"><span data-stu-id="3958a-126">Server GC</span></span>

<span data-ttu-id="3958a-127">サーバーのガベージ コレクションにおける、スレッド処理とパフォーマンスについての注意点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3958a-127">The following are threading and performance considerations for server garbage collection:</span></span>

- <span data-ttu-id="3958a-128">コレクションは、 `THREAD_PRIORITY_HIGHEST` の優先順位で実行される複数の専用スレッドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3958a-128">The collection occurs on multiple dedicated threads that are running at `THREAD_PRIORITY_HIGHEST` priority level.</span></span>

- <span data-ttu-id="3958a-129">ヒープおよびガベージ コレクションを実行するための専用スレッドは CPU ごとに 1 つずつ用意され、複数のヒープのコレクションが同時に行われます。</span><span class="sxs-lookup"><span data-stu-id="3958a-129">A heap and a dedicated thread to perform garbage collection are provided for each CPU, and the heaps are collected at the same time.</span></span> <span data-ttu-id="3958a-130">各ヒープには小さなオブジェクト ヒープと大きなオブジェクト ヒープがあり、どのヒープもユーザー コードからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3958a-130">Each heap contains a small object heap and a large object heap, and all heaps can be accessed by user code.</span></span> <span data-ttu-id="3958a-131">異なるヒープのオブジェクトを相互に参照できます。</span><span class="sxs-lookup"><span data-stu-id="3958a-131">Objects on different heaps can refer to each other.</span></span>

- <span data-ttu-id="3958a-132">複数のガベージ コレクション スレッドが連携して処理を行うため、同じサイズのヒープを処理した場合、サーバーのガベージ コレクションの方がワークステーションのガベージ コレクションよりも高速です。</span><span class="sxs-lookup"><span data-stu-id="3958a-132">Because multiple garbage collection threads work together, server garbage collection is faster than workstation garbage collection on the same size heap.</span></span>

- <span data-ttu-id="3958a-133">一般に、サーバーのガベージ コレクションの方が、格納されるセグメントのサイズは大きくなります。</span><span class="sxs-lookup"><span data-stu-id="3958a-133">Server garbage collection often has larger size segments.</span></span> <span data-ttu-id="3958a-134">ただし、これは一般論に過ぎません。セグメントのサイズは実装に固有であり、変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3958a-134">However, this is only a generalization: segment size is implementation-specific and is subject to change.</span></span> <span data-ttu-id="3958a-135">アプリをチューニングするときに、ガベージ コレクターによって割り当てられるセグメントのサイズに関して何らかの仮定をすることは避けてください。</span><span class="sxs-lookup"><span data-stu-id="3958a-135">Don't make assumptions about the size of segments allocated by the garbage collector when tuning your app.</span></span>

- <span data-ttu-id="3958a-136">サーバーのガベージ コレクションでは、リソースが大量に消費されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3958a-136">Server garbage collection can be resource-intensive.</span></span> <span data-ttu-id="3958a-137">たとえば、プロセッサが 4 つのコンピューターで実行されているサーバー GC が 12 個のプロセスで使用されているとします。</span><span class="sxs-lookup"><span data-stu-id="3958a-137">For example, imagine that there are 12 processes that use server GC running on a computer that has four processors.</span></span> <span data-ttu-id="3958a-138">すべてのプロセスで偶然、同時にガベージを回収すると、互いに干渉することになります。同じプロセッサで 12 のスレッドがスケジュールされるためです。</span><span class="sxs-lookup"><span data-stu-id="3958a-138">If all the processes happen to collect garbage at the same time, they would interfere with each other, as there would be 12 threads scheduled on the same processor.</span></span> <span data-ttu-id="3958a-139">プロセスがアクティブの場合、すべてのプロセスでサーバー GC を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="3958a-139">If the processes are active, it's not a good idea to have them all use server GC.</span></span>

<span data-ttu-id="3958a-140">実行するアプリケーションのインスタンスが数百に及ぶ場合は、同時実行ガベージ コレクションを無効にしてワークステーションのガベージ コレクションを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="3958a-140">If you're running hundreds of instances of an application, consider using workstation garbage collection with concurrent garbage collection disabled.</span></span> <span data-ttu-id="3958a-141">これによって、コンテキストの切り替えが少なくなり、パフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="3958a-141">This will result in less context switching, which can improve performance.</span></span>

## <a name="see-also"></a><span data-ttu-id="3958a-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="3958a-142">See also</span></span>

- [<span data-ttu-id="3958a-143">バックグラウンド ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="3958a-143">Background garbage collection</span></span>](background-gc.md)
- [<span data-ttu-id="3958a-144">ガベージ コレクションの実行時構成オプション</span><span class="sxs-lookup"><span data-stu-id="3958a-144">Run-time configuration options for garbage collection</span></span>](../../core/run-time-config/garbage-collector.md)
