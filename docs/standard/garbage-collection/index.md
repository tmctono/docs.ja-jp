---
title: ガベージ コレクション
ms.date: 03/30/2017
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
ms.openlocfilehash: 846df5ecb1e681e8d0440e627586a681bf071efa
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160145"
---
# <a name="garbage-collection"></a><span data-ttu-id="9935e-102">ガベージ コレクション</span><span class="sxs-lookup"><span data-stu-id="9935e-102">Garbage Collection</span></span>
<span data-ttu-id="9935e-103">.NET のガベージ コレクターは、アプリケーションのメモリの割り当てと解放を管理します。</span><span class="sxs-lookup"><span data-stu-id="9935e-103">.NET's garbage collector manages the allocation and release of memory for your application.</span></span> <span data-ttu-id="9935e-104">新しいオブジェクトを生成するたびに、共通言語ランタイムは、マネージド ヒープからオブジェクトにメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9935e-104">Each time you create a new object, the common language runtime allocates memory for the object from the managed heap.</span></span> <span data-ttu-id="9935e-105">マネージド ヒープに使用可能なアドレス空間がある限り、ランタイムは新しいオブジェクト用に領域の割り当てを続けます。</span><span class="sxs-lookup"><span data-stu-id="9935e-105">As long as address space is available in the managed heap, the runtime continues to allocate space for new objects.</span></span> <span data-ttu-id="9935e-106">しかし、メモリの大きさは無限ではありません。</span><span class="sxs-lookup"><span data-stu-id="9935e-106">However, memory is not infinite.</span></span> <span data-ttu-id="9935e-107">最終的には、ガベージ コレクターが、一部のメモリを解放するためにガベージ コレクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9935e-107">Eventually the garbage collector must perform a collection in order to free some memory.</span></span> <span data-ttu-id="9935e-108">コレクションの実行に最適な時期は、ガベージ コレクターの最適化エンジンが、割り当てられるオブジェクトの状況に応じて決定します。</span><span class="sxs-lookup"><span data-stu-id="9935e-108">The garbage collector's optimizing engine determines the best time to perform a collection, based upon the allocations being made.</span></span> <span data-ttu-id="9935e-109">コレクションを実行する場合、ガベージ コレクターは、アプリケーションによって使用されなくなったオブジェクトがマネージド ヒープにあるかどうかをチェックし、使われていないオブジェクトのメモリを再利用するために必要な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9935e-109">When the garbage collector performs a collection, it checks for objects in the managed heap that are no longer being used by the application and performs the necessary operations to reclaim their memory.</span></span>  
  
<a name="related_topics"></a>
## <a name="related-topics"></a><span data-ttu-id="9935e-110">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9935e-110">Related Topics</span></span>  
  
|<span data-ttu-id="9935e-111">Title</span><span class="sxs-lookup"><span data-stu-id="9935e-111">Title</span></span>|<span data-ttu-id="9935e-112">説明</span><span class="sxs-lookup"><span data-stu-id="9935e-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9935e-113">ガベージ コレクションの基礎</span><span class="sxs-lookup"><span data-stu-id="9935e-113">Fundamentals of Garbage Collection</span></span>](../../../docs/standard/garbage-collection/fundamentals.md)|<span data-ttu-id="9935e-114">ガベージ コレクションの動作、マネージド ヒープに対するオブジェクトの割り当て方法、およびその他の主要な概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-114">Describes how garbage collection works, how objects are allocated on the managed heap, and other core concepts.</span></span>|  
|[<span data-ttu-id="9935e-115">ガベージ コレクションとパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="9935e-115">Garbage Collection and Performance</span></span>](../../../docs/standard/garbage-collection/performance.md)|<span data-ttu-id="9935e-116">ガベージ コレクションとパフォーマンスの問題を診断するために使用できるパフォーマンス チェックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-116">Describes the performance checks you can use to diagnose garbage collection and performance issues.</span></span>|  
|[<span data-ttu-id="9935e-117">発生したコレクション</span><span class="sxs-lookup"><span data-stu-id="9935e-117">Induced Collections</span></span>](../../../docs/standard/garbage-collection/induced.md)|<span data-ttu-id="9935e-118">ガベージ コレクションがどのように行われるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-118">Describes how to make a garbage collection occur.</span></span>|  
|[<span data-ttu-id="9935e-119">待機モード</span><span class="sxs-lookup"><span data-stu-id="9935e-119">Latency Modes</span></span>](../../../docs/standard/garbage-collection/latency.md)|<span data-ttu-id="9935e-120">ガベージ コレクションの割り込みの動作を決定するモードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-120">Describes the modes that determine the intrusiveness of garbage collection.</span></span>|  
|[<span data-ttu-id="9935e-121">共有 Web ホストの最適化</span><span class="sxs-lookup"><span data-stu-id="9935e-121">Optimization for Shared Web Hosting</span></span>](../../../docs/standard/garbage-collection/optimization-for-shared-web-hosting.md)|<span data-ttu-id="9935e-122">複数の小規模な Web サイトで共有されているサーバーで、ガベージ コレクションを最適化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-122">Describes how to optimize garbage collection on servers shared by several small Web sites.</span></span>|  
|[<span data-ttu-id="9935e-123">ガベージ コレクションの通知</span><span class="sxs-lookup"><span data-stu-id="9935e-123">Garbage Collection Notifications</span></span>](../../../docs/standard/garbage-collection/notifications.md)|<span data-ttu-id="9935e-124">フル ガベージ コレクションが近づいたときと完了したときを検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-124">Describes how to determine when a full garbage collection is approaching and when it has completed.</span></span>|  
|[<span data-ttu-id="9935e-125">アプリケーション ドメインのリソース監視</span><span class="sxs-lookup"><span data-stu-id="9935e-125">Application Domain Resource Monitoring</span></span>](../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)|<span data-ttu-id="9935e-126">アプリケーション ドメインによる CPU とメモリの使用状況を監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-126">Describes how to monitor CPU and memory usage by an application domain.</span></span>|  
|[<span data-ttu-id="9935e-127">弱い参照</span><span class="sxs-lookup"><span data-stu-id="9935e-127">Weak References</span></span>](../../../docs/standard/garbage-collection/weak-references.md)|<span data-ttu-id="9935e-128">アプリケーションからオブジェクトへのアクセスを許容したまま、そのオブジェクトをガベージ コレクターが収集できるようにする機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="9935e-128">Describes features that permit the garbage collector to collect an object while still allowing the application to access that object.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="9935e-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="9935e-129">Reference</span></span>  
 <xref:System.GC?displayProperty=nameWithType>  
  
 <xref:System.GCCollectionMode?displayProperty=nameWithType>  
  
 <xref:System.GCNotificationStatus?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCLatencyMode?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings?displayProperty=nameWithType>  
  
 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>  
  
 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
  
 <xref:System.IDisposable?displayProperty=nameWithType>  
  
## <a name="see-also"></a><span data-ttu-id="9935e-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="9935e-130">See also</span></span>

- [<span data-ttu-id="9935e-131">アンマネージ リソースのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="9935e-131">Cleaning Up Unmanaged Resources</span></span>](../../../docs/standard/garbage-collection/unmanaged.md)
