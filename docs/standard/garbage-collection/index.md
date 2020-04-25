---
title: .NET ガベージ コレクション
ms.date: 04/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- memory, garbage collection
- garbage collection, automatic memory management
- GC [.NET Framework]
- memory, allocating
- common language runtime, garbage collection
- garbage collector
- cleanup operations
- garbage collection
- memory, releasing
- common language runtime, automatic memory management
- automatic memory management
- runtime, automatic memory management
- runtime, garbage collection
- garbage collection, about
ms.assetid: 22b6cb97-0c80-4eeb-a2cf-5ed7655e37f9
ms.openlocfilehash: c087deb033a373dd8b3980feb7ec6901c7909569
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102243"
---
# <a name="garbage-collection"></a><span data-ttu-id="a3417-102">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="a3417-102">Garbage collection</span></span>

<span data-ttu-id="a3417-103">.NET のガベージ コレクターは、アプリケーションのメモリの割り当てと解放を管理します。</span><span class="sxs-lookup"><span data-stu-id="a3417-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="a3417-104">新しいオブジェクトを生成するたびに、共通言語ランタイムは、マネージド ヒープからオブジェクトにメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a3417-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="a3417-105">マネージド ヒープに使用可能なアドレス空間がある限り、ランタイムは新しいオブジェクト用に領域の割り当てを続けます。</span><span class="sxs-lookup"><span data-stu-id="a3417-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="a3417-106">しかし、メモリの大きさは無限ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3417-106">However, memory is not infinite.</span></span> <span data-ttu-id="a3417-107">最終的には、ガベージ コレクターが、一部のメモリを解放するためにガベージ コレクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3417-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="a3417-108">コレクションの実行に最適な時期は、ガベージ コレクターの最適化エンジンが、割り当てられるオブジェクトの状況に応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="a3417-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="a3417-109">コレクションを実行する場合、ガベージ コレクターは、アプリケーションによって使用されなくなったオブジェクトがマネージド ヒープにあるかどうかをチェックし、使われていないオブジェクトのメモリを再利用するために必要な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3417-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3417-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a3417-110">In this section</span></span>
  
|<span data-ttu-id="a3417-111">Title</span><span class="sxs-lookup"><span data-stu-id="a3417-111">Title</span></span>|<span data-ttu-id="a3417-112">説明</span><span class="sxs-lookup"><span data-stu-id="a3417-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a3417-113">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="a3417-113">Fundamentals of garbage collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="a3417-114">ガベージ コレクションの動作、マネージド ヒープに対するオブジェクトの割り当て方法、およびその他の主要な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="a3417-115">ワークステーションとサーバーのガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="a3417-115">Workstation and server garbage collection</span></span>](workstation-server-gc.md)|<span data-ttu-id="a3417-116">ワークステーションのクライアント アプリ用ガベージ コレクションと、サーバーのサーバー アプリ用ガベージ コレクションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-116">Describes the differences between workstation garbage collection for client apps and server garbage collection for server apps.</span></span>|
|[<span data-ttu-id="a3417-117">バックグラウンド ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="a3417-117">Background garbage collection</span></span>](background-gc.md)|<span data-ttu-id="a3417-118">バックグラウンド ガベージ コレクションについて説明します。これは、第 2 世代のコレクションを処理中の、第 0 世代と第 1 世代のオブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="a3417-118">Describes background garbage collection, which is the collection of generation 0 and 1 objects while generation 2 collection is in progress.</span></span>|
|[<span data-ttu-id="a3417-119">大きなオブジェクト ヒープ</span><span class="sxs-lookup"><span data-stu-id="a3417-119">The large object heap</span></span>](large-object-heap.md)|<span data-ttu-id="a3417-120">大きなオブジェクト ヒープ (LOH) について、および大きなオブジェクトをガベージ コレクションする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-120">Describes the large object heap (LOH) and how large objects are garbage-collected.</span></span>|
|[<span data-ttu-id="a3417-121">ガベージ コレクションとパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="a3417-121">Garbage collection and performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="a3417-122">ガベージ コレクションとパフォーマンスの問題を診断するために使用できるパフォーマンス チェックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-122">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="a3417-123">発生したコレクション</span><span class="sxs-lookup"><span data-stu-id="a3417-123">Induced collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="a3417-124">ガベージ コレクションがどのように行われるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-124">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="a3417-125">待機モード</span><span class="sxs-lookup"><span data-stu-id="a3417-125">Latency modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="a3417-126">ガベージ コレクションの割り込みの動作を決定するモードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-126">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="a3417-127">共有 Web ホストの最適化</span><span class="sxs-lookup"><span data-stu-id="a3417-127">Optimization for shared web hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="a3417-128">複数の小規模な Web サイトで共有されているサーバーで、ガベージ コレクションを最適化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-128">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="a3417-129">ガベージ コレクションの通知</span><span class="sxs-lookup"><span data-stu-id="a3417-129">Garbage collection notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="a3417-130">フル ガベージ コレクションが近づいたときと完了したときを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-130">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="a3417-131">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="a3417-131">Application domain resource monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="a3417-132">アプリケーション ドメインによる CPU とメモリの使用状況を監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-132">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="a3417-133">弱い参照</span><span class="sxs-lookup"><span data-stu-id="a3417-133">Weak references</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="a3417-134">アプリケーションからオブジェクトへのアクセスを許容したまま、そのオブジェクトをガベージ コレクターが収集できるようにする機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3417-134">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="a3417-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3417-135">Reference</span></span>

- <xref:System.GC?displayProperty=nameWithType>  
- <xref:System.GCCollectionMode?displayProperty=nameWithType>  
- <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
- <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
- <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="a3417-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a3417-136">See also</span></span>

- [<span data-ttu-id="a3417-137">アンマネージド リソースのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="a3417-137">Clean up unmanaged resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
